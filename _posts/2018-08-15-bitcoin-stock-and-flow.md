---
title: "Bitcoin, Stock & Flow"
permalink: "/bitcoin-stock-and-flow" 

tags:
  - Hugo Nguyen
  - CY18 Q3

excerpt: Hugo Nguyen lays out one of the core fundamentals of Bitcoin's value proposition, stock to flow. Posted August 15, 2018. 

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

# [Bitcoin, Stock & Flow](https://medium.com/@hugonguyen/bitcoin-stock-flow-c4d4db98b751)
### By [Hugo Nguyen](https://medium.com/@hugonguyen)
### Posted August 15, 2018

Bitcoin is protected by a combination of [stock & flow](https://en.wikipedia.org/wiki/Stock_and_flow).

## What is stock? And what is flow?

In general terms, **flow** is defined as a quantity which is measured over a period of time. Flow is the rate of change. Examples include business earnings, cash flows, national GDP, rate of depreciation, mortgage payments, number of births/deaths per year, rate of carbon dioxide extraction by plants, etc.

**Stock**, on the other hand, is defined as an accumulation of flows over time, and is measured at one particular moment in time. Mathematically, stock is an integral function. Stock can also be depleted with outflows (negative flows). Examples include business capital, inventory, house equity, total oil reserve, total carbon dioxide concentration in the atmosphere, etc.

In accounting terms, stock is typically represented in the balance sheet, and flow is represented in the income statement.

## What does all this have to do with Bitcoin?

It turns out that Bitcoin economics is also governed by stock & flow variables.

![](/assets/images/cy18/cy18q3m8/hugo-5.png){: .align-center}
Bitcoin: stock vs. flow

Flow in Bitcoin is the total amount of reward per block — with a new block getting mined roughly every 10 minutes. During the bootstrapping phase of Bitcoin, flow consists of a nominal amount of transaction fees and a block subsidy.

When Bitcoin eventually takes off its "training wheels" (block subsidy goes away completely), flow will then consist purely of transaction fees.

Stock in Bitcoin is the specialized mining equipment, which has evolved into ASICs [1][2]. It is important to realize that mining equipment is also a manifestation of fees. They represent the potential stream of fees earned in the future, discounted back to the present. This is what we mean by "integration of flows".

Bitcoin, in essence, is protected by (i) the fees today and (ii) a stream of fees in the future (manifested in the mining equipment). A combination of stock & flow.

Understanding this basic fact helps us develop better models for understanding Bitcoin security. E.g., things such as the [true cost of a majority attack](https://medium.com/@hugonguyen/a-review-of-budishs-51-attack-theories-what-is-the-fair-price-of-an-old-asic-59a7dcf9ff94).

_[1]: Mining equipment is a stock as long as Proof-of-Work mining requires highly specialized & non-repurposable equipment. In some PoW cryptocurrencies, the equipment is repurposable, which makes the currencies vulnerable to rental attacks. Renting changes mining equipment from stock to flow, and potentially reduces the cost of attack for the attacker._

_[2]: Mining stock provides security to the extent that it is sufficiently decentralized. A high level of mining centralization exposes Bitcoin to threats such as government takeovers, and is a legitimate concern._
