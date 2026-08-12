---
title: "Are bigger blocks better for bigger miners?"
permalink: "/are-bigger-blocks-better-for-bigger-miners"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2015 Q2
  - Mining
  - Economics
  - Money

excerpt: Are bigger blocks better for bigger miners?. Posted May 22, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Are bigger blocks better for bigger miners?](http://gavinandresen.ninja/are-bigger-blocks-better-for-bigger-miners)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted May 22, 2015

After taking a break to help review some pull requests and take a trip to New York, I’m ready to continue tackling objections to increasing the block size:

> Bigger blocks give bigger miners an economic advantage

This is a hard blog post to write; the arguments for **why** bigger blocks give bigger miners an economic advantage over smaller miners are highly technical (whenever I use the term “miner” in this post I really mean “solo miner or mining pool”).

To start: think about what happens when a miner gets lucky and finds a new block. They send it to their peers and immediately start working on finding another block on top of that new block.

Their peers will receive and validate the block, and, assuming validation passes, they then relay the block to *their* peers and start mining on top of the new block. The original miner is busy working during this whole validate-then-relay process; they have a head-start because they know about the new block before anybody else.

If all the miners have about the same hashing power, then the head-start doesn’t matter– they all benefit about the same amount.

If the miners don’t all have the same hashing power, then it gets complicated. Bigger miners have an advantage, but how much of an advantage?

I [ran some simulations](https://github.com/gavinandresen/bitcoin_miningsim), and if blocks take 20 seconds to propagate, a network with a miner that has 30% of the hashing power will get 30.3% of the blocks.

To put that extra 0.3% in perspective, here are a couple of recent profitability calculation froms the [Neighbourhood Pool Watch](http://organofcorti.blogspot.com/) blog: 

![](/assets/images/2015/m5/are-bigger-blocks-better-for-bigger-miners1.png)

 

![](/assets/images/2015/m5/are-bigger-blocks-better-for-bigger-miners2.png)

0.3% is in the noise, miner profitability varies much more than that from week to week.

We’ve just started to optimize block propagation for Bitcoin Core (see [pull request #6077](https://github.com/bitcoin/bitcoin/pull/6077) or [Matt Corallo’s high-speed relay network](http://sourceforge.net/p/bitcoin/mailman/message/31604935/) for example), and I’m confident that we will have 20MB blocks propagating across the network more quickly than 1MB blocks propagate today, eliminating even that small 0.3% advantage.

Longer term, I’m also confident smarter synchronization algorithms will get even much larger blocks propagating even more quickly.

***

All of the above assumes that miners are economically rational; that they’re not trying to mine blocks that destroy the network.

What if that is a bad assumption? Do 20MB blocks increase the risk that somebody with a lot of money to burn will try to use it to take down the Bitcoin network? Are there attacks possible with 20MB blocks that are *not* possible with 1MB blocks? Lets look at some possible attacks:

### Miner purposely creates a block that takes several minutes to validate

If a miner can create blocks that takes other miners a very long time to validate, and the miner is trying to attack the network and has a lot of hashing power, it becomes easier for that miner to dominate the network to censor or roll-back transactions.

I find it hard to worry much about this attack, because I find it difficult to believe that an economically irrational attacker would have the resources to successfully mount an attack with expensive-to-validate blocks, but would not have the resources to simply mount a brute-force 51% or selfish-mining attack. I find all of the “invest a lot of money or effort to subvert mining” attacks implausible; mounting a sustained DDOS attacks against the network would probably be much less expensive and more effective.

Nevertheless, I will propose that 20MB blocks limit transactions to 100kilobytes to mitigate this theoretical attack (which we’ve known about for over two years now; see [this discussion](https://bitcointalk.org/?topic=140078)).

### Miner is tricked into creating a block that takes a long time to propagate

Maybe you’re not worried about marginal, malicious miners, but you are worried that an honest miner might be tricked into creating a block that propagates slowly.

For example, an attacker might create 20 megabytes worth of double-spent transactions, and give the network one set of spends but feed a target miner the other set of spends. That will make the miner spend more time validating blocks that are found by the network, and will make the miner’s blocks propagate more slowly, because normally a block is full of transactions that the network has already seen and validated.

I’m not worried about this attack, because I’ve already benchmarked how long it takes to validate a 20MB block full of never-before-seen transactions– it takes about twenty seconds, which is simply not a big deal with a 600-second block time. And Bitcoin Core already has [rules in place](https://github.com/bitcoin/bitcoin/blob/master/src/main.h#L56) to prevent attackers from giving miners transactions that take a very long time to validate.

If the attacker’s goal is to put the honest miner out of business, this is a poor attack; it will decrease the number of blocks found by the honest miner by a tiny fraction of a percent.

If the attacker’s goal is to pull off a successful 0-confirmation double-spend, this is also a very poor attack. The transaction fees required to stuff a 20MB block full of the attacker’s transactions will easily overwhelm any marginal advantage they might gain from causing a slower-to-propagate-than-normal block.

### Marginal miners are left behind because they can’t afford…

I covered the cost of running a full node in a [previous post](http://gavinandresen.ninja/does-more-transactions-necessarily-mean-more-centralized). Even without any further optimizations (and we [are](https://github.com/bitcoin/bitcoin/pull/6064) [busy](https://github.com/bitcoin/bitcoin/pull/907) [optimizing](https://github.com/bitcoin/bitcoin/pull/3753)) it is not expensive to run a node capable of validating 20MB blocks.

## What am I missing?

I was worried that I would find out 20MB blocks would give big miners a significant advantage before I started working on this post a week ago. I’m not worried any more, but please send me email if there is something I’ve missed.

***

{% include signup.md %}
