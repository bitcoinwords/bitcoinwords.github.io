---
title: "Bitcoin, UASF and Skin in the Game"
permalink: "/bitcoin-uasf-and-skin-in-the-game"

author: jimmysong

tags:
  - Jimmy Song
  - 2017 Q2
  - Mining
  - Politics
  - Technology

excerpt: Bitcoin, UASF and Skin in the Game. Posted May 29, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin, UASF and Skin in the Game](https://medium.com/@jimmysong/bitcoin-uasf-and-skin-in-the-game-7695031c5689)
### By Jimmy Song
### Posted May 29, 2017

If you’ve been following various Bitcoin personalities on Twitter, you’ll notice that a lot of people have UASF in their Twitter name. If you don’t know what it is, the supporters of a User-Activated Soft Fork (UASF) have an [informative website](http://www.uasf.co/) and if you’re technical, you can read the [Bitcoin Improvement Proposal](https://github.com/bitcoin/bips/blob/master/bip-0148.mediawiki) (BIP-148). I will note here that BIP-149 is another UASF proposal, but BIP-148 is a bit more urgent as there’s an important date set by that proposal on August 1, 2017.

In this article, I seek to show what the UASF actually does and what each actor in this unfolding drama has to weigh going forward. In particular, I will attempt to make clear what support or opposition to BIP-148 looks like and what it would mean to each constituency in the Bitcoin network. I have [written about this before](https://medium.com/p/why-the-uasf-segwit-scenario-is-hopelessly-naive-70338711bc3c), but this article will spell out what will be required for the UASF to work.

#### What Does BIP-148 Actually Do?

BIP-148 has [reference implementation code](https://github.com/bitcoin/bips/blob/master/bip-0148.mediawiki#reference-implementation) for exactly what it does:

```
// BIP148 mandatory segwit signalling.int64_t nMedianTimePast = pindex->GetMedianTimePast();if ( (nMedianTimePast >= 1501545600) &&  // Tue 01 Aug 2017 00:00:00 UTC     (nMedianTimePast <= 1510704000) &&  // Wed 15 Nov 2017 00:00:00 UTC     (!IsWitnessLockedIn(pindex->pprev, chainparams.GetConsensus()) &&  // Segwit is not locked in      !IsWitnessEnabled(pindex->pprev, chainparams.GetConsensus())) )   // and is not active.{    bool fVersionBits = (pindex->nVersion & VERSIONBITS_TOP_MASK) == VERSIONBITS_TOP_BITS;    bool fSegbit = (pindex->nVersion & VersionBitsMask(chainparams.GetConsensus(), Consensus::DEPLOYMENT_SEGWIT)) != 0;    if (!(fVersionBits && fSegbit)) {        return state.DoS(0, error("ConnectBlock(): relayed block must signal for segwit, please upgrade"), REJECT_INVALID, "bad-no-segwit");    }}
```

If you don’t read C++, the comments themselves are pretty instructive. All these conditions have to be met for BIP-148 software to reject a block that’s otherwise valid:

1. The block has to be found between the dates August 1, 2017 and November 15, 2017. August 1, 2017 is the date chosen by BIP-148 for block rejection. November 15, 2017 is when the current Segwit proposal expires.
2. Segwit is not already on the network
3. Block is not signaling Segwit.

#### How will this affect the network?

Practically speaking there will come a block X, the first block after August 1, 2017 not signaling Segwit, that will be rejected by the BIP-148 nodes, but accepted by the non-BIP-148 nodes. For the sake of clarity, we’ll call the block before X, C. BIP-148 nodes will be on C, other nodes on X.

At some point, miners running BIP-148 will produce block Y, building on block C.

![](/assets/images/2017/m5/bitcoin-uasf-and-skin-in-the-game1.png)

We have what’s called a fork, though for the time being, this will be what’s called a “soft fork”. Now should there be no miners running BIP-148, the scenario would look like this:

![](/assets/images/2017/m5/bitcoin-uasf-and-skin-in-the-game2.png)

In this case, BIP-148 nodes will simply stop at C and will be stuck with no transactions possible until the software is changed.

#### Who can make this happen?

As shown above, despite having “user-activated” in the name, the actual fork still is triggered by a miner. At least one miner needs to be running BIP-148 software to fork. In fact, short of a switch to proof-of-stake or something similar, there really isn’t a way for any sort of fork to be triggered by anyone but a miner.

This is an important point, because despite all the rhetoric, BIP-148 still needs miners to have any chance of success. Essentially, BIP-148 is creating a new consensus rule for its chain, namely, signaling for Segwit.

This means that for the BIP-148 fork, provided there is enough hashing power, Segwit will activate as 100% of their blocks will be signaling Segwit, which is above the 95% needed.

#### What does this mean for me?

If you’re a user on the network, that means that transactions will be slower for two weeks at a minimum (longer if the hashing power is lower) and more likely, there will be some [serious disruption](https://medium.com/p/100-blocks-of-terror-or-why-a-51-miner-split-wont-work-c6fce4adef89) as merchants and exchanges will likely suspend any Bitcoin transactions until there’s some clarity on the forking situation.

Further, even after the forking situation is resolved, there’s a high likelihood of there being two Bitcoins and a [very messy divorce](https://medium.com/p/why-a-bitcoin-divorce-will-be-really-painful-65fc54dec61d).

#### So why is it called “user-activated”?

There are two ways in which BIP-148 is “user-activated”.

The first is that if enough users buy coins on the UASF chain, they can make even a minority fork succeed by giving it more economic value than the other chain. Indeed, [that is the power users have](https://medium.com/@jimmysong/bitcoin-realism-or-how-i-learned-to-stop-worrying-and-love-1mb-blocks-c191c35e74cb), to buy and sell the currency. The hope is that by giving the UASF chain more value, they can create incentives for miners to mine more on their chain and eventually overtake the other chain in length. At this point, without [a permanent fork](https://medium.com/p/why-any-contentious-change-will-become-a-permanent-fork-a1c6ed3faa06), the other chain would disappear in a really large reorg. In this way, the proponents of BIP-148 believe the users would show everyone who’s boss and bring the miners to heel.

The other argument is that it’s actually not user-activated as much as “economic node” activated. Economic nodes are the nodes that matter, like the nodes at various exchanges, wallets, miners, etc. The hope is that if enough economic nodes can be convinced to run BIP-148 software, that more users would then utilize the chain, giving it more value and creating better monetary incentives for miners eventually overtaking the other chain in length. Once again, the end game here would be making the other chain disappear.

#### What does supporting BIP-148 mean, anyway?

Many users on reddit seem to think that if enough users ran BIP-148 software, that it would make BIP-148 more likely. Perhaps, but there’s a lot of evidence to the contrary. First, running node software is very easy and cheap. In fact, it’s so easy that you really [shouldn’t be trusting the node statistics](https://medium.com/p/why-bitcoin-node-statistics-arent-trustworthy-5882d9a9d2bf) as it’s very easy to fake. Node software is useful because the node owners can validate the transactions and blocks for themselves. Essentially, node software is useful because you don’t have to trust others, but doesn’t do much for the actual blockchain state unless you mine.

As a node, you have the right to reject blocks or transactions for any reason, but that, too, is not useful unless others agree with you. This is why BIP-148 proponents desire support from “economic nodes” such as miners, exchanges, wallets and merchants. Let’s take a look at each and see what their incentives might be.

#### Users and BIP-148

From the perspective of a user, owning and transacting the coin is the main concern. Supporting BIP-148 means being able to own and transact the coin that results from the fork. That doesn’t preclude owning or transacting the other fork. In fact, most supporters of BIP-148 will *want* to have a non-BIP-148 node running so they can sell it!

#### Exchanges and BIP-148

From the perspective of an exchange, the main thing they’ll need to do is to allow deposits and withdraws for people using their service. Supporting BIP-148, then means that their users can buy and sell the BIP-148 coin should it happen. Note this does not preclude supporting the other chain! In fact, it’s very much in the interest of the exchanges and even UASF advocates for the exchange to support the other chain as many will want to trade one chain’s coin for the other.

This unfortunately, has a lot of consequences. Exchanges likely will not support a coin without some sort of replay-protection. That is, transactions on one chain should not be valid on the other. This cannot happen as Bitcoin currently stands [without a permanent fork](https://medium.com/p/why-any-contentious-change-will-become-a-permanent-fork-a1c6ed3faa06). Thus, getting an exchange’s support likely means there is no chance of Bitcoin merging back to one chain.

That said, there may be a way around this by using futures. That is, not actually trade the coins themselves, but the potential split in the future. Bitfinex already does this with the Bitcoin Unlimited fork. This has its own perils, however, as there may not be enough liquidity and bitcoins will have to be locked up with the exchange for the duration of the whole drama (much like Bitcoin Unlimited coins on Bitfinex today).

Because of this lockup custodial risk, futures are not something we can expect the vast majority of bitcoin holders to utilize. As a result, we can expect much less liquidity in a futures market than in a normal market. Low liquidity means that the futures are very easily manipulated, which likely means futures won’t be a reliable indicator until the event happens (for those that doubt this, ask betting markets what happened with Brexit or Trump).

#### Wallets and BIP-148

Wallets in the Bitcoin space are almost entirely open-source. Support for BIP-148 simply means that the wallet is compatible with the software. Should the wallet developers oppose BIP-148, a fork will likely be made supporting BIP-148 and vice-versa. In fact, a wallet that supports both forks is desirable since everyone will want to know the balance of their coins on both chains. Even if the values of the coins on the forks are $10000 and $100, you’ll still want to transact on the chain with $100 so you can do something with it (like trade for coins on the higher-value fork).

#### Merchants and BIP-148

Merchants and payment processors mainly want to get paid for their goods or services. Supporting BIP-148 simply means allowing people to pay for goods on that chain. This is not an unreasonable expectation and once again, does not preclude utilizing the other chain. Again, this may be desirable even from UASF advocates since being able to spend coins from the other chain gives it liquidity.

Of course, merchants will have the same expectations as exchanges in that the coins they receive won’t simply disappear. Hence, they’ll want some [chain reorg protection and replay protection](https://medium.com/p/why-any-contentious-change-will-become-a-permanent-fork-a1c6ed3faa06) before supporting both chains.

#### Miners and BIP-148

For all constituents that we’ve examined thus far, supporting BIP-148 means they can support both forks when the UASF happens. There are really only economic benefits, not really economic penalties for supporting a BIP-148 fork other than some fixed costs (running a node, changing some software, etc). These actors in the Bitcoin Ecosystem do not *have to choose* which software they run, they can run both and really, they should if they want to maximize their value.

Miners are the exception. When mining a block, they *have to choose* which fork to build on. In fact, they are the only ones in the entire ecosystem that are forced to choose. Everyone else can and probably will run both forks should a UASF happen. Miners have to choose one or the other fork when they mine a block.

#### Skin in the game

Skin in the game means that there’s cost to supporting something. Everybody else, as seen above, essentially has only fixed costs (often fairly small) to support BIP-148. Miners have a significant continuing cost to support BIP-148. Miners, because of the forced choice of having to signal one way or the other in blocks that they mine, have significant skin in the game.

This has some significant consequences.

You would expect that miners will be the last ones to show support for BIP-148 since they take the most risk. This seems to be the case as only 1 [miner](http://www.uasf.co/) out of [the top 17](https://coin.dance/blocks/today) seem to be supporting BIP-148. And that one, Bitfury, seems to now be backing [the agreement from Consensus 2017](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77). In other words, more than 94% of the mining hash power (probably a lot more) are not supporting BIP-148.

You would expect that miners on the side of the fork that has chain reorganization risk to protect the skin they’ve put in by forcing a hard fork should a UASF happen. Indeed, that seems to be the plan:

![](/assets/images/2017/m5/bitcoin-uasf-and-skin-in-the-game3.png)

#### Conclusion

Really the only way, then, to have skin in the game and support BIP-148 is to mine BIP-148 blocks. Everyone else will simply be running both chains as it’s to their advantage. Mining equipment has [dropped in price](https://canaan.io/product/avalonminer-741/) recently and mining yourself is really the only way to really contribute to a UASF via BIP-148. All other attempts are really attempts to solve the [Byzantine General’s Problem](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance#Byzantine_Generals.27_Problem) without Proof-of-Work.

This should make intuitive sense. Bitcoin is a decentralized system where if a big change were achievable with little in the way of money, resources, or time, it would get exploited very quickly. There’s a real cost to change things and that very well may mean lots of money ($700+) spent by lots of people (1000+). In other words, Bitcoin is [really hard to change](https://medium.com/p/why-bitcoin-transaction-capacity-doesnt-really-matter-fddcc0c9f021), and that’s [a wonderful feature](https://medium.com/p/why-bitcoin-will-get-scaling-without-segwit-or-large-blocks-772799fab021).

Our culture is used to being able to sign some meaningless change.org petition and feel like we’ve done something to actually change things. Advertisers tell you all the time that if you only buy their product, your problems would be solved. Our society that wants to believe there are easy answers to everything. We’re used to wishful thinking, minimal effort and rejecting responsibility.

Bitcoin. Doesn’t. Care.

Bitcoin doesn’t care if you post arguments on Reddit. Bitcoin doesn’t care if you put something clever in your Twitter name. Bitcoin doesn’t care if you educate people, write articles, or make clever Twitter insults. Bitcoin doesn’t care about your wishes, your feelings or your arguments.

With Bitcoin, you have to put real skin in the game. Real time, like [years spent refining software to remove vulnerabilities](https://github.com/bitcoin/bitcoin). Real money like millions of dollars to [design, test and manufacture ASICs](https://medium.com/p/mining-profitability-and-asicboost-ffdb779ef6dd). Real resources like [developers, marketers, project managers and venture capital](https://medium.com/p/why-bitcoin-is-different-than-other-cryptocurrencies-e16b17d48b94) making real things like node software, wallets, mining equipment, payment processors and exchanges.

Whatever side you’re on in this debate, this is a certainty: If you want to change Bitcoin, you have to pay the price.

***

{% include signup.md %}
