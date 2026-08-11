---
title: "Miners should be hubs on Lightning Network"
permalink: "/miners-should-be-hubs-on-lightning-network"

author: olegandreev

tags:
  - Oleg Andreev
  - 2017 Q2
  - Lightning
  - Mining
  - Technology

excerpt: Miners should be hubs on Lightning Network. Posted April 1, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Miners should be hubs on Lightning Network](https://blog.oleganza.com/post/159059675953/miners-should-be-hubs-on-lightning-network)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted April 1, 2017

Some miners are worried about the fees. What if blocks remain small and most transactions are cleared on the Lightning Network — miners will earn very little while the block reward is quickly coming to an end. An ignorant answer is “lets just raise the block size indefinitely”. Slightly less ignorant answer “fees will be higher, and BTC will be worth more, so don’t you worry”. What if the actual answer is: miners could be the best Lightning Network hubs?

Here’s how it could work. Lightning Network scales Bitcoin payments by compressing chains of transactions into a single transaction, protected by mutual security deposits from both sides of each node and some clever smart contract conditions that make cheating more expensive than playing by the rules. Security deposit lock up money and put a natural limit on how much value and through how little hops can be transferred in the network. **The more fees a node wants to earn, the more money they have to lock up in order to service more peers.**

How miners are in privileged position to profit from Lightning Network? **They are recipients of the large amount of coins (reward + fees) that are also unspendable for 100 blocks** (≈16 hours, so called “coin maturity”). That means, that unlike any other bitcoin holder that can put bitcoins to a better use any time they want, miners cannot use coins for over 100 blocks. Miner could use these coins to open many payment channels with interested users (they will pay their deposit using a separate transaction, for free).

Miners, by virtue of having access to large amounts of funds, could open between each other fat payment channels to connect each other’s users in much shorter number of hops, making it cheaper and faster for users, but having a larger chunk of off-chain transaction fees.

Per-block reward and on-chain fees would end up locked up for longer than 100-block intervals, which is even healthier for the network: all the miners become motivated to extend a single chain not for a few days, but for months!

Therefore, problem solved and everyone’s happy.

1. No hard forks are necessary.
2. Large per-block rewards put to good use.
3. Coin maturity increased by 10-100x significantly reducing risk of blockchain fork.
4. Users get channel opening for free.
5. Users get faster and cheaper LN payments by having lower number of hops.
6. Power-hungry miners remain in minority and stop pushing stupid consensus changes.
7. /r/btc goes apeshit.

***

{% include signup.md %}
