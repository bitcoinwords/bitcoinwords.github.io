---
title: "Bitcoin “mining” is a misnomer"
permalink: "/bitcoin-mining-is-a-misnomer"

author: olegandreev

tags:
  - Oleg Andreev
  - 2013 Q1
  - Mining
  - Technology

excerpt: Bitcoin “mining” is a misnomer. Posted January 8, 2013.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin “mining” is a misnomer](https://blog.oleganza.com/post/39962302913/bitcoin-mining-is-a-misnomer)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted January 8, 2013

Bitcoin “mining” is a process of creating hard-to-compute chain of transactions to make sure nobody tries to spend money twice. It is important because the chain is not stored on a trusted server, but rather copied thousands of times among all the computers in the network. The resulting structure is called a “blockchain”, that is a chain of blocks of transactions. As it is nearly impossible to change the history of payments (and therefore cancel transactions or double-spend bitcoins), users stay confident that the history of transactions looks the same to everyone. This is the central part of the Bitcoin protocol: a solid and distributed mechanism to verify validity of payments.

People who spend electricity to create blocks are called “miners”. They are paid for their trouble by transaction fees (offered voluntarily by others) and block rewards that are source of the new bitcoins. There is a limited number of bitcoins and all of them are distributed among the first several million blocks available to everybody to “mine”. That’s why the process of building the blockchain is called “mining”.

However, the term makes sense only within the earliest history of Bitcoin when there were almost no economy and no transactions, but only a bunch of geeks computing almost empty blocks for reward that they were trading for fun and a couple of cents. If you tried to find any info on Bitcoin in 2010, you would find mostly the info about mining. Back then a pizza was sold for 10000 BTC ([https://en.bitcoin.it/wiki/History](https://en.bitcoin.it/wiki/History)) and the whole project looked like a game.

Today there is a much more interesting economy, daily transaction volume is almost $3 million and rapidly growing, more than 50% of all bitcoins are mined already and the per-block reward has already been halved in December 2012 (as defined by the protocol). Blockchain is used for real transactions — purchases, currency transfers, investment, bets and all other things we use money for. Miners are making very real money which is a strong incentive to carefully include and validate all transactions to keep the value of the system growing.

So today it is a good time to remind ourselves and everyone that the Bitcoin is not about “mining” money. It is about verifying payments in a very secure manner, without trust in any authority, very quickly and efficiently. Mining is just a temporary effect of bootstrapping the next era in human kind.

***

{% include signup.md %}
