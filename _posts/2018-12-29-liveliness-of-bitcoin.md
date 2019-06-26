---
title: "Liveliness of Bitcoin"
permalink: "/liveliness-of-bitcoin" 

tags:
  - Tamas Blummer 
  - CY18 Q4

excerpt: Tamas Blummer explains Bitcoin Liveliness and what it means as an indicator. Posted December 29, 2018.

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      read_time: true
      comments: false
      share: true
      related: false
---

# [Liveliness of Bitcoin](https://medium.com/@tamas.blummer/liveliness-of-bitcoin-174001d016da)
### By [Tamas Blummer](https://medium.com/@tamas.blummer)
### Posted December 29, 2018

_29. December 2018 by_ [_Tamas Blummer_](https://twitter.com/TamasBlummer)

**Liveliness** is new quantitative measure that gives insight to shifts in **HODL**ing behavior.

Whenever someone moves Bitcoins there is a record of that on the blockchain. The blockchain records the move's time point, the amount and the source of every Bitcoin involved, which again discloses the length of the recent holding period. Such an insight is unique to an asset tracked on a blockchain, and is not attainable in traditional financial markets. Let's use this information to derive a quantitative measure that gives more insight to investor's behavior than those available in traditional markets.

### Liveliness

A holding period multiplied with the amount is often called stake. We define Liveliness as the ratio of sum of stakes used and sum of all stakes existed.

![](/assets/images/cy18/cy18q4m12/tb-1.png){: .align-center}
[ti, to] is the recent holding period, c(t) is coin issued at t. Time is measured as difference of block numbers.

Liveliness would temporarily reach 1 if all coins would move within a single block and remain at 0 for a blockchain that have not yet had a transaction other than issuance. Liveliness will trend down for a blockchain with dormant units and up for a vivid ecosystem. A reading between 0 and 1 hence may be understood as a measure of Liveliness.

**Liveliness** gives us insight to behavior of investors. It **increases as long term holder liquidate positions and decreases while they accumulate** to HODL.

Liveliness **could be used to weight market cap if comparing crypto currencies**, as it will be close to zero for currencies that have inflated market cap through pre-mined coins or wash trading of the same few units.

![](/assets/images/cy18/cy18q4m12/tb-2.png){: .align-center}
Liveliness of Bitcoin in percentage

Liveliness is the **inverse** **measure of lost or HODLed Bitcoins** and alerts us of moves of large or old stashes. For this purpose subtract Liveliness from one and multiply with coins issued.

![](/assets/images/cy18/cy18q4m12/tb-3.png){: .align-center}
Approximate number of lost or HODLed coins in millions (red) price on log scale (gray)

It is apparent that Liveliness increases (and HODL decreases) during time periods of Bitcoin price increases and investors accumulate to HODL during periods of range bound prices.

_I developed the concept of Liveliness during 2018 and wrote the software to calculate it from the Bitcoin blockchain. See related work at_ [_https://github.com/rust-bitcoin_](https://github.com/rust-bitcoin) _. Plots were drawn with mathematica. The price data for illustration is from blockchain.info._
