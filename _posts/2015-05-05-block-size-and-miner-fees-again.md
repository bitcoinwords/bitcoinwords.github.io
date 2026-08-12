---
title: "Block size and miner fees… again"
permalink: "/block-size-and-miner-fees-again"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2015 Q2
  - Mining
  - Economics
  - Security

excerpt: Block size and miner fees… again. Posted May 5, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Block size and miner fees… again](http://gavinandresen.ninja/block-size-and-miner-fees-again)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted May 5, 2015

I’m still seeing variations on this argument for keeping the one-megabyte block limit:

> The network will be more secure with one megabyte blocks, because there will be more competition among transactions, and, therefore, higher transaction fees for miners.

I’ve written before about the [economics of the block size](https://blog.bitcoinfoundation.org/blocksize-economics/) (and even went to the trouble of having Real™ Economists review it), but I’ll come at that argument from a different angle.

Miner rewards expressed in BTC are:

`block reward + ( number of transactions x average fee )`

In the currencies that most miners care about right now (dollars or euros or yuan) rewards are:

`(reward + number transactions x average_fee) x exchange rate`

The fear is that as the block reward diminishes, either the number of transactions or the average transaction fee will not rise enough to replace the block reward. So miners will drop out, and the network will be less secure against an attacker with a lot of mining power (or, equivalently, it would cost an attacker less to amass enough mining power to successfully attack the network).

Focusing on just the average_fee term in that equation is a mistake; the number of transactions is just as important. If the goal is to maximize the #transaction x average_fee part of the equation, we would need to know the [“price elasticity of demand”](http://en.wikipedia.org/wiki/Price_elasticity_of_demand) for bitcoin transactions to calculate the most-profitable-to-miners maximum block size.

But the exchange rate is even more important, at least until the reward drops to zero. So if the goal is to keep the network as secure as possible over the next ten or fifteen years, we should be focusing on doing things that are likely to increase the exchange rate. All of the things that come to my mind that make Bitcoin more valuable (like increasing the number of people using Bitcoin, increasing security using multisig wallets, allowing people to innovate and leverage the security of the blockchain for things other than payments) will benefit from a larger maximum block size.

***

{% include signup.md %}
