---
title: "Introducing Realized Capital"
permalink: "/introducing-realized-capital" 

tags:
  - CY18 Q4
  - Coinmetrics Team

excerpt: A look at realized capital by the Coinmetrics Team, Posted December 14, 2018

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---

# [Introducing Realized Capitalization](https://coinmetrics.io/realized-capitalization/)
### By the Coinmetrics Team
### Posted December 14, 2018

The motivation for the creation of Realized Cap was the realization that "Market Capitalization" is often an empty metric when applied to cryptocurrencies. Market Capitalization, borrowed from the world of equities, is calculated for cryptocurrencies as

```
circulating supply * latest market price
```

However, unlike with equities, large fractions of cryptocurrencies tend to get lost, go unclaimed, or become otherwise inert through bugs.
By design, there is no Depository Trust and Clearing Corporation which keeps track of everyone's stock certificates. So when tokens or virtual coins get lost, they stay lost. In Bitcoin, this means that roughly 15% of supply is assumed to be permanently lost and out of circulation. Market Cap does not consider these nuances, instead aggregating the value of all coins ever mined and assessing them at the last market price.

We wanted to create a measure that reflected this, at least for UTXO chains. Our design goals were as follows:

* De-emphasize lost coins
* Where possible, maximize generalizability (so reduce reliance on idiosyncratic adjustments)

The eureka moment came when Pierre Rochard asked for data on a historically-weighted UTXO market cap for Bitcoin. This was mentioned to Coinmetrics engineer Antoine Le Calvez, who figured out an appropriate methodology and also dubbed it "Realized Capitalization." (It was previously called "Effective Cap".) Realized Cap seemed to fit the bill:

* It reduces the contemporary impact of long-lost coins
* It is trivially generalizable to UTXO chains, and, with some effort, generalizable to account chains
* It doesn't deviate from Market Cap by too much
* It is automated: it doesn't require (much) human oversight or intervention

When we first worked out the numbers in September, Bitcoin's Market Cap was $115 billion and its Realized Cap $88 billion. That seemed to make sense. Deriving new metrics from scratch is always tricky, so they need to pass the smell test too. Realized Cap seemed to do just what it said on the tin: weight coins according to their actual presence in the Bitcoin economy. It is one of a new generation of economic measures which hybridizes market and on-chain data.

Of course, exotic new measures are not without risks. There are a few challenges here: dealing with deep-cold-storage coins, interpreting Realized Cap for coins with little turnover, and generalizing it to account based coins.

First, imagine Satoshi's ~ 700k-1m coins really were just in deep storage, and our dear leader was planning on spending them all on Bitcoin's 10th birthday – Jan. 03 2019. In that case, Realized Cap would be seriously underweighting the economic weight of Bitcoins in circulation, since it prices those long-lost coins at 2009 values... of $0 per BTC. Realized Cap has a hard time differentiating between truly lost/abandoned coins and coins that are merely in yearslong deep cold storage. However, even the coldest of storage schemes do require periodic awakenings – to renew a multisig scheme, to take advantage of a fork, or to cash out a portion. So many of these accounts will have some amount of churn anyway.

Another issue is Realized Cap on smaller chains. Outside of the industry "blue chips," there are many chains with relatively little turnover. This poses a challenge for Realized Cap, as it is the sending of new coins that triggers the upwards (or downwards) revaluation at a new price. One common phenomenon we observed was price spikes, with many coins getting sent back and forth to exchanges, and an increase in Realized Cap, followed by a slow, low-velocity grind down where Realized Cap hardly moves. In this case the high Realized Cap was more of an artifact of the low turnover rather than a fair reflection of the network's pricing.

### So how is Realized Cap calculated?

The realized cap attempts to improve on the market cap by trying to discount coins that might be lost. Its crux is to value different part of the supplies at different prices, instead of using the daily close as market cap does.

For UXTO coins, this consists in valuing outputs at the price at the time of their creation. For example, for a UTXO currency of supply 10 and market price of $10, its market cap would be $100. But if the UTXO set is as follows:

| Value | Time of creation | Price at time of creation | USD Value at time of creation |
| --- | --- | --- | --- |
| 8.3 | 2009-02-01 | $0.00 | $0.00 |
| 1.2 | 2011-03-17 | $1.00 | $1.20 |
| 0.5 | 2018-11-15 | $10.00 | $5.00 |

Its realized cap would be $0.00 + $1.20 + $5.00 = $6.20 or 6.2% of its market cap as 83% of the supply hasn't moved for years.

### Extension to account based chains

Extending this metric to account based coins is a bit more complex. Instead of a list of unspent coins, the state in this case is represented as a list of accounts:

| Account | Balance |
| --- | --- |
| 0xabc | 8.3 |
| 0xdef | 1.2 |
| 0xfad | 0.5 |

Compared to the UTXO model, it is not possible to always assign a time of creation to a balance which makes assigning it a price, and thereby a value, hard.

Let's take an example transaction history for an account and see what methods can be used to accurately value its balance. We'll assume the current time is 2018-11-01 and the market price is $150.00

| Time | Change in balance | Price at time | Balance |
| --- | --- | --- | --- |
| 2015-08-01 |  +1,000.00 | $0.01 | 1000.00 |
| 2016-02-01 |  +100.00 | $10.00 | 1100.00 |
| 2017-05-01 | -50.00 | $50.00 | 1050.00 |
| 2017-12-17 | -100.00 | $1200.00 | 950.00 |
| 2018-04-01 |  +20.00 | $200.00 | 970.00 |

From this data, several approaches can be used to value the balance:

### Last movement price

We use the price at the last movement on the account: here $200.00, this gives a realized balance of **$194,000.**

This values accounts when they are active at all on the network. However, if someone sends dust to a lost account, its whole balance is re-valued at the current market price.

### Last outgoing movement price

To avoid lost accounts being re-valued when someone sends money to them, we can use the price of the last time it had an outgoing movement (defaulting to the creation of the account if no outgoing payment).

In our case, this price is $1200.00, the realized balance would be **$1,164,000.**

### Virtual UTXO

One downside of using the last movement price is that an account which has a very high balance and sends a tiny amount out would trigger a re-valuation of the whole balance at market price.

While it's the desired effect (after all, we just want to discount lost coins), it is unfair to UTXO based chains where the whole balance of an address is not taken into account for the realized cap, but just the coins used.

To reduce this undesirable effect, we can simulate a UTXO set for account based systems:

* each incoming payment creates a new coin attached to the account, the coin is valued at the price of the movement
* each outgoing payment triggers a coin selection on the coins attached to the account, the change is valued at the current market price

Let's replay the example account's history while maintaining this virtual UTXO, the coin selection we'll use is largest coins first:

| Time | Change in balance | Price at time | Balance | Virtual coins | Realized balance |
| --- | --- | --- | --- | --- | --- |
| 2015-08-01 |  +1,000.00 | $0.01 | 1000.00 | (1000.0 at $0.01) | $10.00 |
| 2016-02-01 |  +100.00 | $10.00 | 1100.00 | (1000.0 at $0.01), (100.00 at $10.00) | $1,010.00 |
| 2017-05-01 | -50.00 | $50.00 | 1050.00 | (100.00 at $10.00), (950.00 at $50.00) | $48,500.00 |
| 2017-12-17 | -100.00 | $1200.00 | 950.00 | (100.00 at $10.00), (850.00 at $1200.00) | $1,021,000.00 |
| 2018-04-01 |  +20.00 | $200.00 | 970.00 | (100.00 at $10.00), (850.00 at $1200.00), (20.00 at $200.00) | $1,025,000.00 |

This gives this account a realized balance of **$1,025,000.**

### Using Realized Cap on Coinmetrics

Right now, Realized Cap is only available for UTXO chains – we are still refining it for account-based chains.

For charting, you can find it on the chart as **Realized Network Value** (in keeping with our naming convention of using "Network Value" rather than Market Cap). If comparing Realized Cap to Market cap, we recommend hitting **settings** and selecting **no** on **Compare on different axes**.

![using unrealized capital image](/assets/images/cy18/cy18q4m12/coin-1.png){: .align-center}

This lets you create nice comparisons like this:

![realized network value](/assets/images/cy18/cy18q4m12/coin-2.png){: .align-center}

Bitcoin realized network value (solid red line) and network value (shaded area). [Link here](https://coinmetrics.io/charts/#assets=btc_log=false_left=realizedCap_right=marketcap_zoom=1367107200000,1544400000000_sameAxisComparison=true) Keep in mind that on our charts builder page, the command for realized cap is

```
Ticker.realizedCapUsd
```

You can also create a ratio of the two.

![Market cap to realized cap ratio](/assets/images/cy18/cy18q4m12/coin-3.png){: .align-center}
Market cap to realized cap ratio The reasoning behind the ratio has been explored by Murad Mahmudov and David Puell [here](https://blog.goodaudience.com/bitcoin-market-value-to-realized-value-mvrv-ratio-3ebc914dbaee).
