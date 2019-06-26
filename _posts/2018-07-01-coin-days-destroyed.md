---
title: "Coin Days Destroyed"
permalink: "/coin-days-destroyed" 

tags:
  - Jaoquin Roibal
  - CY18 Q3

excerpt: Jaoquin Roibal takes to stackexchange to answer. Posted June 20, 2019.

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

# [Coin Days Destroyed](https://bitcoin.stackexchange.com/questions/845/what-are-bitcoin-days-destroyed)
### [By Joaquin Roibal](https://twitter.com/BlockchainEng)
### Posted July 1, 2018

The idea of "bitcoin days destroyed" [came about](http://bitcointalk.org/index.php?topic=6172.msg90789#msg90789) because **it was realised that total transaction volume per day might be an inappropriate measure of the level of economic activity in Bitcoin**. After all, someone could be sending the same money back and forth between their own addresses repeatedly. If you sent the same 50 btc back and forth 20 times, it would look like 1000 btc worth of activity, while in fact it represents almost nothing in terms of real transaction volume.

With "bitcoin days destroyed", **the idea is instead to give more weight to coins which haven't been spent in a while**. To do this, you multiply the amount of each transaction by the number of days since those coins were last spent. So, 1 bitcoin that hasn't been spent in 100 days (1 bitcoin * 100 days) counts as much as 100 bitcoins that were just spent yesterday (100 bitcoins * 1 day). Because you can think of these "bitcoin days" as building up over time until a transaction actually occurs, the actual measure is called "bitcoin days destroyed". **This is believed to give a better indication of how much real economic activity is occurring on the bitcoin network**.

So how well does it work? Well, it's still not perfect, because the other day I moved some coins out of a wallet they've been in for several months without spending them or giving them away. And some genuine businesses have very rapid turnover in bitcoins, so they're not being measured well by this method. But it does do a good job of filtering out the "noise" of bitcoins that are just "bouncing around" without really going anywhere. **The graph of overall bitcoin days destroyed is believed to show that the genuine level of activity in the Bitcoin economy is continually increasing**--it's not just one person experimenting by rapidly sending the same coins back and forth, flooding the network with meaningless chatter. Looks pretty good, hey? 

![](/assets/images/cy18/cy18q3m7/coindays-1.png){: .align-center}

Image from the [Bitcoin wiki](https://en.bitcoin.it/wiki/File:June-17th-days-destroyed.png). The above graph is in percentage of bitcoin days destroyed and a little out of date--for a regularly updated version in bitcoin days destroyed check out [Bitcoin Days Destroyed - Active Chart](https://www.quandl.com/data/BCHAIN/BCDDE-Bitcoin-Days-Destroyed) instead!