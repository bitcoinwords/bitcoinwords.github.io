---
title: "Segwit2x: What you need to know about the 2x Hard Fork (aka 2MB non-Segwit Transaction Capacity per block/8MB Total Block Size HardFork)"
permalink: "/segwit2x-what-you-need-to-know-about-the-2x-hard-fork-aka-2mb-non-segwit"

author: jimmysong

tags:
  - Jimmy Song
  - 2017 Q2
  - Mining
  - Economics
  - Technology

excerpt: "Segwit2x: What you need to know about the 2x Hard Fork (aka 2MB non-Segwit Transaction Capacity per block/8MB Total Block Size HardFork). Posted June 26, 2017."

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Segwit2x: What you need to know about the 2x Hard Fork (aka 2MB non-Segwit Transaction Capacity per block/8MB Total Block Size HardFork)](https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-about-the-2mb-hard-fork-27749e1544ce)
### By Jimmy Song
### Posted June 26, 2017

## Segwit2x: What you need to know about the 2x Hard Fork (aka 2MB non-Segwit Transaction Capacity per block/8MB Total Block Size Hard Fork)

When I wrote [my last article on Segwit2x](https://medium.com/p/segwit2x-what-you-need-to-know-b747e6326266), I concluded with questions about the lack of clarity around the 2x part of Segwit2x. Since then, there’s been more clarification, especially in the [btc1/bitcoin](https://github.com/btc1/bitcoin) (aka Segwit2x) repository. In this article, I’m going to describe what is likely to happen for those running Segwit2x and how that will affect you.

![](/assets/images/2017/m6/segwit2x-what-you-need-to-know-about-the-2x-hard-fork-aka-2mb-non-segwit-transac1.jpg)

#### Yet another BIP — BIP102

[BIP102](https://github.com/bitcoin/bips/blob/master/bip-0102.mediawiki) is a flag-day hard fork to 2MB, written in 2015 by Jeff Garzik. Jeff Garzik created a [pull request](https://github.com/bitcoin/bitcoin/pull/6451) to the Bitcoin Core repository on July 16, 2015 and after 8 months of discussion, it was never merged. Jeff Garzik closed this pull request in September of 2016 as it seemed pretty clear that BIP102 was not getting merged into Core.

BIP102 has surfaced again recently as part of Segwit2x in modified form, which is unsurprising since the lead developer of Segwit2x is none other than Jeff Garzik. The essence of this BIP (Bitcoin Improvement Proposal) is that there’s a hard fork to 2MB on a “flag day”. This is a coordinated date where all network participants start accepting 2MB blocks. If this sounds familiar, it should. This “flag day” activation was the proposed mechanism for the [original User-Activated Soft Fork](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-February/013643.html) (UASF) to Segwit by shaolinfry.

In any case, the original BIP102 had a hard flag date (literally a unix timestamp). The modified BIP102 proposal in Segwit2x activates exactly 144*90 blocks after Segwit activation. 144 blocks takes about 1 day (10 minutes * 144 = 1 day) so this is meant to activate a hard fork roughly 3 months after Segwit activates.

#### Segwit2x Contents

It may be useful at this point to look at what Segwit2x actually is.

Segwit2x branched off the Bitcoin Core 0.14 release and has a diff of less than 500 lines as of this writing from Bitcoin Core 0.14. About half are related to BIP91 (orphan blocks that don’t signal Segwit) and the rest is split between testnet5 (new testnet), change of name (Bitcoin Core => Segwit2x) and BIP102 (2MB Blocks). It’s within the realm of possibility that this code can get merged into Core, for example.

![](/assets/images/2017/m6/segwit2x-what-you-need-to-know-about-the-2x-hard-fork-aka-2mb-non-segwit-transac2.png)

In fact, according to Charlie Shrem’s tweet above, the hope of Segwit2x is that the hard fork changes would simply be accepted into Bitcoin Core. Of course, some signers of the New York Agreement have [explicitly stated](https://twitter.com/ViaBTC/status/876047086533214208) they don’t want Core to control the reference client, so this is an open question.

#### Who’s going to run this software?

The big question, then, is who’s going to be running Segwit2x? Who is willing to run a Bitcoin client that’s not Bitcoin Core? Well, according to the [New York Agreement](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77), everyone who’s signed the agreement has essentially agreed to run this software. Based on the latest statistics from coin.dance, that’s roughly 87% of mining hash power, a lot of exchanges, a lot of merchants and a lot of wallets. If these companies do what they said they’d do in the agreement, that would represent a significant portion of the economic nodes in Bitcoin.

The notable companies that aren’t obligated to run Segwit2x are BlockStream, Chaincode Labs, BitGo, Poloniex, BitStamp, Bithumb, BitFinex, Kraken and Gemini. As they have not signed the agreement, they are not obligated to follow it.

#### What can we expect?

The easiest way to think about what will happen is with some rough dates:

* July 21 — Segwit2x is due to be released and presumably all participants to the New York Agreement will run it. The miners currently signaling “NYA” in their coinbase transactions, or [about 87% of the last 24 hours’ worth of blocks](https://coin.dance/blocks), are a good estimate of blocks that will mine using Segwit2x.
* July 23 — BIP91 should lock in (requires 80% of 336 blocks to signal)
* July 26 — BIP91 should activate. At this point, all blocks are required to signal for Segwit (BIP141) or they will be orphaned off the network.
* Around July 26–27 — This is also around when we can expect a new difficulty adjustment period to begin. The last one as of this writing was June 17 and they typically take 12–14 days (closer to 13 since new hardware comes online constantly). So June 30 (block 473760), July 13 (block 475776) and July 26 (block 477792) seem to be the next 3 difficulty adjustment period starts.
* August 10 — This is around when we can expect block 479808, which is the end of the difficulty adjustment period. Very close to 100% of blocks in this difficulty adjustment period should be signaling for BIP141 (Segwit). As this is above 95%, Segwit should be locked in.
* August 23 — This is around when we can expect block 481824, which is when Segwit should activate. From this block on, Segwit transactions will be legal on the network. This also sets the activation date for BIP102 on Segwit2x to block 494784 (exactly 144*90 blocks later).
* November 18 — This is around when we can expect block 494784, which is when Segwit2x should hard fork to 2MB blocks.

#### What this means for you

Practically speaking, as long as Segwit2x releases something that works for mining by July 21, we should get Segwit on the network around August 23. That means that Lightning Network transactions should be available soon after and everyone will be watching to see if block congestion and transaction fees reduce.

Assuming Segwit2x release goes without a hitch, it should be safe to transact until block 494784, which will be when the 2MB hard fork for Segwit2x is expected to occur. This is expected to happen around November 18 and depending on how much of the network (miners, merchants, economic nodes) hard forks and what response Bitcoin Core and some objecting companies may have, this may mean 2 Bitcoins at that point.

My recommendation previously was to be very careful transacting after August 1. That still may be the case if Segwit2x is not released on time. If Segwit2x is released on time, then the new date becomes November 18 (or thereabouts) and I would recommend being very careful about transacting after the hard fork as many of the problems I’ve written about before, such as [replay and wipeout attacks](https://medium.com/p/uasf-bip148-scenarios-and-game-theory-9530336d953e) become serious problems.

#### Conclusion

Segwit looks like a reality on the network, but with it comes a 2MB hard fork. Whether the 2MB hard fork will have teeth is an open question, but the fact that a significant percentage of the economic nodes have signed an agreement to hard fork means, well, that there will probably be a hard fork. If there is even a little resistance to a hard fork, we can expect two Bitcoins around November 18.

That said, it’s important to note that there are a lot of moves from here until November 18. Bitcoin Core, Blockstream, Chaincode Labs, BitGo and other non-signers of the New York Agreement will all have something to say about this turn of events and it would be very surprising if they don’t. It would then be up to the New York Agreement signers to respond and so on.

In other words, the Bitcoin scaling drama isn’t over. This is may be the 2nd inning. In the meantime, enjoy the relative peace of the ceasefire.

*Edit: Updated the list of non-signers of NYA per*[*Alex B.*](https://medium.com/@bergealex4)

*Want to get curated Technical Bitcoin News?*[*Sign up*](http://eepurl.com/cZr_Aj)*for the Bitcoin Tech Talk newsletter!*

***

{% include signup.md %}
