---
title: "Introducing: Fee Ratio Multiple (FRM)"
permalink: "/introducing-fee-ratio-multiple-frm"

author: matteoleibowitz

tags:
  - Matteo Leibowitz
  - 2018 Q4
  - Mining
  - Economics
  - Money

excerpt: "Introducing: Fee Ratio Multiple (FRM). Posted October 1, 2018."

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Introducing: Fee Ratio Multiple (FRM)](https://medium.com/coinmonks/introducing-fee-ratio-multiple-frm-1eada9ac9bec)
### By Matteo Leibowitz
### Posted October 1, 2018

### *A novel metric for measuring the distance PoW chains have to cover in order to sustain current security levels solely through transaction fee revenue*

*As always, the following is for educational purposes only. This is not investment advice.*

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm1.jpg)

#### **Fee Ratio**

Nic Carter recently [advocated](https://www.youtube.com/watch?v=D2WXxgZ8h-0&feature=youtu.be&t=1h18m27s) for a new metric to replace the ever-misleading ‘market capitalization’, the latter currently occupying a hegemonic position as the lead reference when framing the state of the crypto asset market.

**The Fee Ratio** is the answer to the following question [posed](https://www.docdroid.net/FbgH1WS/bitcoin-institution-riga.pdf) by Nic:

> “If block rewards disappeared tomorrow what percentage of
>
> [BTC’s]
>
> economic volume would we have to pay in fees to replace them”

> “about 0.6% of economic volume would have to be paid in fees to support an equivalent level of network security.”

For the mathematically inclined, the Fee Ratio can be expressed as follows:

**FR (%) = Miner Revenue ($) / Transaction Volume ($)**

or in BTC’s case:

**0.41% = $6.11bn / $1.49tn**

For the FR thought experiment, transaction fee revenue is substituted in for total miner revenue post hoc.

*(Data provided by*[*CoinMetrics.io*](http://coinmetrics.io)*, FR calculated using 1 year worth of Miner Revenue and Adjusted Transaction Volume data)*

#### **Why is FR important?**

The vast majority of crypto assets employ disinflationary monetary policies, whereby the rate of issuance declines geometrically.

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm2.png)

BTC Inflation Schedule (Kiran Vaidya)

Miners, who secure Proof of Work (PoW) chains by expending energy, thereby building an economic obstacle to monopoly power, rely on a combination of block rewards and transaction fees to cover their costs — this may be referred to as the **Security Budget (SB)**(H/T [Jordan McKinney](https://twitter.com/jordanmmck)).

With block rewards set to halve every four years, PoW chains will be increasingly at the mercy of transaction fee revenue as the dominant source of funds for the SB.

Meanwhile, as the ratio between SB and Network Value decreases, the risk:reward for attackers increases. This ratio may be referred to as the Security Factor (H/T again to [Jordan McKinney](https://twitter.com/jordanmmck)).

FR ostensibly assumes that the SB for existing chains has always been at an equilibrium state — any lower and the chain would be insecure: any higher and users would be overpaying. If SB has not been at an equilibrium state then FR provides no insight as we don’t have a benchmark for what minimum percentage of economic volume and/or network value would be sufficient to secure the chain.

Under these assumptions, one may deduce that a low FR is a desired metric.

A low FR means that users can transact **securely** while simultaneously paying a **minimal % of each transaction as a fee**. Conversely, a high FR means that users have to **pay a high % of each transaction as a fee in order to transact securely.**

#### **Back to Bitcoin**

With a FR of 0.41%, BTC seems to be in good shape. BTC’s FR is far lower than that of Zcash(6.70%), Decred (9.54%), and even Ether (1.16%).

One might be forgiven for presuming that users will be more than willing to pay this percentage to BTC miners for their services.

But to truly understand the implications of FR it is necessary to understand ***what multiple of existing transaction fee revenue would be required to reach the FR.***

#### **Fee Ratio Multiple (FRM)**

And so I present the **Fee Ratio Multiple (FRM)**, which, as it turns out, is equal to:

**Miner Revenue [Block Reward + Transaction Fees] / Transaction Fees**

FRM is **explicitly about security,**which should be considered the foundational layer of the chain stack. By looking at FRM we can deduce how secure chains will be once block rewards disappear.

> Further,
>
> FRM implicitly measures the strength of an assets properties as a Store of Value.

> A low FRM suggests that an asset can maintain its current security budget (miner revenue) without having to rely on an inflationary subsidy.

> Conversely, a high FRM suggests that an asset will require heavy inflation via block reward subsidies in order to maintain its existing security budget.

FRM can only be applied on a block reward halving cycle basis — i.e. for BTC, looking at FRM in the period between 2012–2016 and then 2016–2020.

This is because FRM *has* to trend towards 1 as block rewards become negligible. By measuring over 4 year periods you keep block reward as a constant and measure its changing relationship with transaction fees.

As with FR, FRM only works under the assumption that SB has been sufficient up until now.

#### **A Few Words on NVT:**

FRM is not the same as Network Value to Transaction (NVT), which is calculated as **Price * Supply / Transaction Count**.

NVT is used to **measure a chain’s strength as a payment network compared to its market value**— a low NVT may suggest that a network is undervalued compared to the service it is providing as a settlement layer.

NVT and FRM will not always be correlated. A chain could feasibly have a high number of transactions and a low network value, and therefore a low NVT, while simultaneously having a high FRM depending on the current size of block rewards and average transaction fee.

Moreover, NVT is far easier to spoof than FRM: one merely need spam the network with low fee transactions. By contrast, significant manipulation of FRM would by definition require significant cost as FRM measures the aggregate value of transaction fees rather than count.

#### **Methodology**

FRM can be calculated on various time frames.

Perhaps the most obvious path would be to take miner revenue (transaction fees + block rewards) from a single day and then divide that number by transaction fee revenue from that same day.

Below is an illustration of FRM calculated on a ‘daily basis’ for Bitcoin over a 1 year period.

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm3.png)

While this methodology does provide some sense of BTC’s FRM trend over time, the volatile nature of daily transaction fee revenue makes for a ‘noisy’ chart.

Calculating FRM using this ‘daily’ methodology yields similarly ‘noisy’ results for ETH:

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm4.png)

One could take an average for transaction fee revenue across a 2 day timeframe, a 4 year timeframe, and anywhere in between.

For this exercise I have decided to take a 30 day EMA for transaction fee revenue.

As for daily generated coins (i.e. block reward), it’s not necessary to calculate based on EMA as issuance rate is close to constant over each 4 year period.

For this exercise I used [CoinMetrics.io](http://coinmetrics.io) data via [CryptoSheets](https://cryptosheets.com/vacm).

**Please note: my intention is not to necessarily present this methodology as gospel but to provide a foundation for others to then build on and improve.**

**I am aware that the data for ZEC does not include Shielded Transactions. At the same time it seems to be well accepted that Transparent Transactions make up the dominant majority of ZEC transaction volume.**

#### **Historical FRMs:**

Here’s Bitcoin’s (BTC) FRM over the last 2 years.

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm5.png)

*BTC FRM (linear)*

And here’s Ether’s (ETH) FRM over the same period:

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm6.png)

Here are the FRMs for BTC, ETH, Litecoin (LTC), Zcash (ZEC), Decred (DCR), and Bitcoin Cash (BCH).

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm7.png)

FRM (log)

What information can be drawn from the chart above?

1. **ZEC, DCR, and BCH all have FRMs above 1000x:**

Remember: this means that in order to reach current security budget levels without block reward subsidies, transaction fee revenue for each chain has to 1000x+.

**2. BTC FRM is on the rise:**

Just two years ago BTC FRM was 26. By November 2017 it was as low as 2. Since then, FRM has risen 40-fold to the 80–90 range.

**3. ETH FRM is declining:**

ETH FRM in September 2016 was 891x. Today it has the lowest FRM among the assets measured at 43x. ETH’s FRM is also the only FRM to be lower today than it was in July 2017.

#### **FRM Correlations:**

What do correlations between FRM and Price look like? And what would we expect correlations to look like?

For this exercise I will use BTC price as a proxy for market price.

![](/assets/images/2018/m10/introducing-fee-ratio-multiple-frm8.png)

FRM vs. Price (log)

**Expected Correlations:**

We would naturally *expect* a strong inverse correlation between large price movements and FRM:

Strong price action in either direction is usually accompanied by a surge in volume →

More volume suggests more people are moving assets to exchanges →

More people transacting with crypto asset means higher transaction fee revenue →

Higher transaction fee revenue means lower FRM

**Desired Correlations:**

We would naturally *desire* 0 correlation between P and FRM.

In a perfect world, FRM for capped supply assets would continue to decline over time, eventually reaching something close to 1, the point at which transaction fee revenue makes up 100% of total miner revenue.

**Actual correlations:**

Actual correlations are closer to expected correlations than desired correlations.

Every asset’s FRM bottomed out during their ATH period between November ’17 — January ’18.

**ETH is the only asset to have a lower FRM today compared to this time last year.** This is in spite of the fact that **ETH price is actually *down $*50, or 18%**, YTD.

Meanwhile, **BTC FRM is up by a factor of 7x YTD, despite price being *up*47%.**

What might this suggest?

1. **The market is not currently placing enough emphasis on FRM as a metric.**BTC is priced at 5x of ETH, yet [does not have a particularly . convincing path](https://medium.com/@matteoleibowitz/bitcoin-disinflating-to-death-b4ba7b691969) to multiply transaction fee revenue by **87x**, which would be required to sustain security at current levels.
2. **Price appreciation for BTC is not catalyzing usage.**Perhaps instead it is encouraging hoarding: that is, after all, the Austrian way. But this might well be to the ultimate detriment of BTC as miner revenue, the Security Budget, continues to deplete.
3. **Conversely, price depreciation for ETH is not acting as an obstacle for usage.**Despite the heavy decline in price, ETH transaction fee revenue continues to trend upwards, indicating a growing trend in usage outside of speculation.

#### Moving forward:

When assessing the long term value proposition of a blockchain and its native digital asset one must first consider how resilient it will be to attacks. If securing 51% of hash power — or for Proof of Stake chains, stake — is not prohibitively expensive then the blockchain’s digital asset is worthless.

If blockchains with disinflationary monetary policies do not drastically increase transaction fee revenue over the next several years then they are destined to disappear into obscurity. In the long term the fee market is the only market that matters.

The alternative is to alter monetary policy to retain some degree of block rewards, although this inflationary subsidy will limit the asset’s attractiveness as a long term store of value.

I hope that this article will encourage further exploration of chain security and look forward to readers improving upon the methodology for calculating FRM.

*Subscribe to CryptoChat*[*here*](http://cryptochat.us)*.*

Many thanks to [Jordan McKinney](https://twitter.com/jordanmmck) and Chris Ware for their feedback.

***

{% include signup.md %}
