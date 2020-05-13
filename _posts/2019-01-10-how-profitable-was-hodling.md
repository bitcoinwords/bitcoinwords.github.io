---
title: "How profitable was HODLing?"
permalink: "/how-profitable-was-hodling"

author: tamasblummer

tags:
  - Tamas Blummer
  - 2019 Q1
  - Hodling
  - Finance
  - Charts
  - Metric
  - Liveliness

excerpt: Tamas Blummer explains the concept of LIveliness. Posted January 10, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***


# [How profitable was HODLing?](https://medium.com/@tamas.blummer/how-profitable-was-hodling-18e42400d7ad)
### By [Tamas Blummer](https://twitter.com/TamasBlummer)
### Posted January 10, 2019

Bitcoin’s blockchain reveals the length of holding every Bitcoin, which allows us to quantify its [Liveliness](https://medium.com/@tamas.blummer/liveliness-of-bitcoin-174001d016da) and estimate the number HODLed coins. Let’ use this information to discuss HODLer investment returns.

The [Liveliness](https://medium.com/@tamas.blummer/liveliness-of-bitcoin-174001d016da) measure splits the inventory of coins into frequently moving and HODLed units, by building a ratio of sum of used and sum of created stakes. Stake is a bitcoin amount multiplied with its holding period.

HODL is a measure of coins hold for long term, and can be derived with the help of Liveliness as (1 — Liveliness) multiplied with coins already mined.

HODL is well defined and mechanically derivable from the blockchain, yet it leads to estimates quite close those based on unique insight, published by [Chainalysis](https://blog.chainalysis.com/reports/money-supply).

HODL confirms the shape of HODL Waves as observed by [Unchained](https://blog.unchained-capital.com/bitcoin-data-science-pt-1-hodl-waves-7f3501d53f63) without much fuzz.

Here again for reference with data up to end of 2018:

![](/assets/images/cy19q1/cy19q1m1/tb1.png)

Since the HODL measure’s derivation is purely mechanic, it is not immune to one time effects of technical nature, such as the recent [Coinbase cold wallet reshuffle](https://blog.coinbase.com/a-behind-the-scenes-look-at-the-biggest-and-quietest-crypto-transfer-on-record-682ff4a6d9e4), that is mostly responsible for the latest temporary dip in HODL. But no worries, HODL will recover very soon, provided Coinbase customer will hold on to those coins.

![](/assets/images/cy19q1/cy19q1m1/tb2.png)

Since the group of HODLer is not constant, but new long term holders enter and some leave the market, this result has nothing to do with individual gains, but only with the changing success of then recent mix of long term holder. I visualized how this mix evolves and looks like [earlier](https://twitter.com/TamasBlummer/status/1032069042905997313).

![](/assets/images/cy19q1/cy19q1m1/tb4.png)

Market timing of HODLer was not that great, but also not too bad. Following the crypto winter, many sold as soon as they barely broke even, but some still had enough left to sell at the top of the craze:

![](/assets/images/cy19q1/cy19q1m1/tb5.png)

I will publish shortly how above gains are distributed by vintages of HODLer and what the split is between realized and unrealized gains.

Satoshi please…

![](/assets/images/cy19q1/cy19q1m1/tb6.png)

_I developed the concept of Liveliness during 2018 and wrote the software to calculate it from the Bitcoin blockchain. See related work at _[_https://github.com/rust-bitcoin_](https://github.com/rust-bitcoin)_. Plots were drawn with mathematica. The price data for illustration is from blockchain.info. Thanks to Michiel Lescrauwaet at Adamant Capital for the idea that Coinbase’s reshuffle might have caused the late dip of HODL._

This publication contained material errors at the date of its initial publication in some of its plots and commentary. I corrected them same day and apologize.



***

{% include signup.md %}