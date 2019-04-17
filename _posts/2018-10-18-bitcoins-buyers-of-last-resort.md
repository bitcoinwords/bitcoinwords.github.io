---
title: "Bitcoin's Buyers of Last Resort"
permalink: "/bitcoins-buyers-of-last-resort" 

tags:
  - Pierre Rochard
  - CY18 Q4

excerpt: By Pierre Rochard, posted October 18, 2018

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

# [Bitcoin's Buyers of Last Resort](https://medium.com/@pierre_rochard/bitcoins-buyers-of-last-resort-920d0470a994)
### By [Pierre Rochard](https://medium.com/@pierre_rochard)
### Posted October 18, 2018

What stops the price of bitcoins from crashing to zero in a bear market? Let's start with what a lender of last resort is.

## Lenders of Last Resort

_Trigger warning: if you are very familiar with interbank lending, fed funds rate, open market operations, etcetera, you may be frustrated and/or annoyed by this simplified explanation. It's safe to skip since you already know what a lender of last resort is._

Today's existing fractional-reserve banking system creates new currency when it lends to you. The bank's accounting, in simplified form, is to debit the bank's Loans asset account and credit a Deposits liability account. Your accounting is to debit your Deposits asset account and credit your Loans liability account. This process of money creation is limited on the supply side both by banks' self-discipline as well as central banks setting reserve requirements. On the demand side it is limited by the quality of borrowers and their financing needs. These factors create a ceiling for how much new money gets created when the system is growing.

When the system is contracting you have the reverse process and money is "destroyed". This gets into a negative feedback loop as money destruction causes deflation, making existing loans harder to pay back and new loans harder to make. One by one, the system's banks become insolvent and collapse from a bank run. To "break" the negative feedback loop of a contracting fractional-reserve banking system, the central bank steps in as the **lender of last resort**. Here is a [good paraphrasing](https://www.bis.org/publ/bppdf/bispap79.pdf) of Walter Bagehot on the role of a lender of last resort:

> Central banks should make clear that they stand ready to lend early and freely (ie without limit), to sound firms, against good collateral, and at rates higher than those prevailing in normal market conditions. This is an integral part of a monetary economy with fractional-reserve banking.

Central banks, as lenders of last resort, create a floor for how much money gets destroyed when the system is contracting.

The Bitcoin system itself does not create new currency through lending. New bitcoins are created as a subsidy to the proof of publication function of the system, which provides a decentralized transaction ordering service. A difficulty adjustment mechanism creates a ceiling for how many new bitcoins are issued, this mechanism is enforced by block validation rules. Read more about Bitcoin's governance [here](https://medium.com/@pierre_rochard/bitcoin-governance-37e86299470f).

The Bitcoin system does not have a mechanism for destroying bitcoins, though individual users can choose to do so. Thus there is no deflationary negative feedback loop that plagues today's fractional-reserve banking systems.

Bitcoin's monetary crises occur due to a "hangover" from adoption waves. If humans were asocial animals without any [herd mentality](https://en.wikipedia.org/wiki/Bandwagon_effect), we could imagine a world where Bitcoin's system accumulates users at a steady rate. The price of bitcoins would slowly appreciate over time. However, humans are very social animals and highly susceptible to herd mentality. Adoption happens in [waves](https://blog.unchained-capital.com/bitcoin-data-science-pt-1-hodl-waves-7f3501d53f63), causing the price to go parabolic as new adopters compete for space on the UTXO set at the same time. On top of organic new adoption, there are highly speculative momentum traders who are just trying to profit off the adoption wave by buying high and selling higher. When adoption and momentum peak, there is a massive unwinding. Leveraged long positions are liquidated, marginal adopters panic sell, momentum traders reverse into shorting. With everyone expecting the price to go lower, buyers disappear and bitcoins become a high-velocity hot potato. The lower the price goes, the more panic and selling there is.

The negative feedback loop of a crisis of confidence is broken by two groups (which have plenty of overlap): **holders of last resort** and **buyers of last resort**.

I first heard the phrase "holders of last resort" [when Trace Mayer came on the Noded Bitcoin Podcast to talk with Bitstein and me](https://noded.org/podcast/noded-0110-with-trace-mayer/). The phrase amusingly repurposed the fiat system's "lender of last resort" phrase and captured the imagery of unwavering conviction and calm stubbornness in an environment of anti-"HODL" gloating, panic selling, and pervasive FUD. Holders of last resort break the negative feedback loop by **not** panic selling.

Before I continue, I'd like to illustrate how a generic order book works. Let's say the previous price at which BTC was traded was $10,000. A _bid limit order_ says "I am willing to buy 0.2 BTC at $9,999". An _ask limit order_ says "I am willing to sell 0.2 BTC at $10,001". A _market sell order_ says "hello bid limit order, you said you're willing to buy 0.2 BTC at $9,999 and I'm taking you up on your offer", a _market buy order_ says the same with the ask limit order. The limit orders create liquidity, the market orders consume liquidity. The larger the total quantity of USD in the bid limit order book, the less the price moves when large quantities of BTC are market sold. There are numerous BTC / fiat order books, at different exchanges and with different fiat currencies. In an abstract sense, these can all be rolled up into a hypothetical "global order book". This global order book includes not only visible limit orders, but also hidden limit orders which can be as casual as someone thinking "if the price goes to X, then I'll buy or sell Y bitcoins". We each have our own internal personal order book!

Buyers of last resort break the negative feedback loop in two ways. **Bidders of last resort**put in limit orders — buy bids. This provides liquidity that is consumed by panic sellers putting in market orders. They are a damper on slippage in a disorderly and volatile market. Absent these liquidity providers, the massive "gapping" on downticks increases the price impact of panicked selling. **Buyers of last resort** put in market buy orders. This consumes seller liquidity. As market orders set the marginal price, they are the upticks that eventually turn the panic around and reestablish confidence in BTC's price.

In either case of a limit or market order, the buyers of last resort fall into one of the following categories (shout at me on Twitter if I'm missing one):

1. People paid in bitcoins. Their employers or clients may already own bitcoins or have to go buy them, in either case people receiving bitcoins as income are the economic equivalent of buyers. The value of the transfer is likely denominated in USD, so the demand pressure is constant.
2. Recurring buyers. For example, someone who set up an auto-buy on Coinbase, every two weeks they market buy BTC regardless of what is happening with the price. Some have even forgotten they have it on, like a monthly charge for a gym they don't go to anymore. Individually it may be a small $50 buy, but in aggregate these accumulators could be a large pool of buyers of last resort.
3. Windfall buyers. They've been wanting to buy more BTC for a while now, and their employer just had a successful IPO or they landed a big new client. They take the cash from the windfall and go buy a nice spot on the UTXO set. The timing is unrelated to the BTC price.
4. Opportunistic buyers, market timers. They sold the BTC top or knew the market was overheated. They're back to buy the bottom.
5. Relative value and flight to safety traders. This can range from someone selling their altcoin mining rig for bitcoins, to someone dumping their portfolio of distressed illiquid ICO tokens for bitcoins. They were trying to make more bitcoins during "alt-season" and now they are guiding their ship of bags into port during the storm.
6. Transactional buyers. They're not actually speculating on the price of BTC, they're buying to use the underlying payment rails. The person they're sending value to may be quick to sell, so transactional buyers only affect the market with the residual amount and time held. Individually this is small but it can add up, especially as the "Bitcoin economy" scales up and closes the loop between buyers and sellers. We'll also end up seeing transactional users who are buying BTC to fund Lightning Network channels. There are also lower-velocity transactional users, for example corporate multisig contracts, using properties unique to Bitcoin's programmable money.

Together, Bitcoin's buyers and holders of last resort help break the negative feedback loop in a bitcoin exchange rate crisis, setting up the base for the next bull market. Is being a buyer of last resort a sensible approach to speculating on the value of BTC? If you think that Bitcoin is going to continue to attract adopters due to BTC's monetary properties and the network's payment processing capabilities, buying into a volatile bear market is indeed sensible and here's why from [Wealthfront](https://blog.wealthfront.com/invest-despite-volatility-2/) (they're applying it to equities but this particular point about the price path is relevant to BTC)...

> Many facets of investing are counterintuitive. Investment strategies that feel right seldom are. A classic example of this is how to deal with market volatility. During a [recent investment seminar](http://www.slideshare.net/wealthfront/dropbox-investment-seminar)I gave to Dropbox employees, I asked the audience which type of market they would prefer to invest in periodically each year if they didn't intend to withdraw their money until 10 years from now. I showed them the three charts below and asked them to vote.

![](/assets/images/cy18/cy18q4m10/pierre-1.png){: .align-center}

> You probably won't be surprised to learn that Behavior Chart A was the vote's biggest winner while Behavior Chart C garnered the fewest votes. However, you may be surprised to discover that **Behavior Chart C actually displays the best market to invest in**and Behavior Chart A is the worst.

Read the full piece [here](https://blog.wealthfront.com/invest-despite-volatility-2/). Granted, these charts are assuming a positive outcome. Could BTC continue to drift downwards and never see another parabolic bull market? To make that case you would have to point to a fundamental break with the past: a material, negative change to Bitcoin's ability to attract new adopters. We've seen positive changes over the past few years like SegWit and an order of magnitude increase in liquidity. There are more positive changes on the horizon from the Lightning Network to financial infrastructure.

Whether you are a buyer of last resort buying $20 or $2 billion worth of BTC, please work with a financial planner to see how Bitcoin fits with your financial objectives and experience, time horizon, risk tolerance, and financial situation. Don't over-extend yourself and become a panic seller of first resort!
