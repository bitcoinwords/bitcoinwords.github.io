---
title: "Bitcoin Average Dormancy"
permalink: "/bitcoin-average-dormancy" 

tags:
  - Reginald Smith
  - CY18 Q4

excerpt: Reginald Smith proposes Bitcoin Average Dormancy as a measure of turnover and trading activity. Posted December 2018.

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

# [Bitcoin Average Dormancy](https://ledgerjournal.org/ojs/index.php/ledger/article/download/99/112)
## A Measure of Turnover and Trading Activity
### By [Reginald Smith](https://twitter.com/SupremeVinegar)
### Posted December 2018

Abstract. Attempts to accurately measure the monetary velocity or related properties of Bitcoin have often attempted to either directly apply definitions from traditional macroeconomic theory or to use specialized metrics relative to the properties of the Blockchain such as bitcoin-days destroyed. In this paper, it is demonstrated that beyond being a useful metric, bitcoin-days destroyed has mathematical properties that allow one to calculate the average dormancy (time since last use in a transaction) of the bitcoins used in transactions over a given time period. In addition, transaction volume and average dormancy are shown to have unexpected significance in helping estimate the average size of the pool of traded bitcoins by virtue of the expression Little's Law, though only under limited conditions.

## Introduction
Since the white paper by Satoshi Nakamoto in 2008 proposing the concept of Bitcoin and its later launch in January 2009,[^1] Bitcoin has rapidly emerged to become one of the most unique financial innovations in recent times.[^2, 3, 4, 5, 6] As Bitcoin grew and evolved, it became increasingly important to have metrics to characterize the growth and behavior of Bitcoin. This was enabled by the Blockchain whose public and decentralized nature made measurements relatively easy. The first metric was the measurement of total transaction volume in bitcoin (BTC) on chain (transactions recorded in the Blockchain). While clear and easily calculated, this metric had drawbacks since not all transactions represent the same type of spending activity. For example, users moving bitcoin between several addresses they own versus market transactions reflecting the acceptance of bitcoin and usage in the wider economy.[^5], [^6]

In order to deal with this issue, the idea of bitcoin-days destroyed was first proposed on the forum Bitcointalk.org on April 20, 2011 by the user ByteCoin.7 Bitcoin-days destroyed would be a weighted measure of transaction volume where transactions in BTC would be multiplied by the number of days since those bitcoin were last spent. The intention was for Bitcoin-days destroyed to give a more nuanced measure of the economic activity in Bitcoin by discounting higher frequency transactions. In days-destroyed, 1 BTC created 100 days prior produces an equivalent days-destroyed to 100 BTC spent one day after their creation. The heavier weighting for less frequently circulating coins helps remove some “noise” that is due to rapid, repeating short term transactions that may not be indicative of the true demand for Bitcoin usage. It has been viewed by some as both a better indicator of relative economic activity than raw transaction volume and also a proxy for monetary velocity.8, 9, 10 While