---
title: "Segwit2x: What you need to know"
permalink: "/segwit2x-what-you-need-to-know"

author: jimmysong

tags:
  - Jimmy Song
  - 2017 Q2
  - Mining
  - Politics
  - Technology

excerpt: Segwit2x: What you need to know. Posted June 19, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Segwit2x: What you need to know](https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-b747e6326266)
### By Jimmy Song
### Posted June 19, 2017

Bitmain rocked the Bitcoin world last week when they [published a press release](https://blog.bitmain.com/en/uahf-contingency-plan-uasf-bip148/) detailing their plans for a hard fork should BIP148 gain traction. The very next day, Segwit2x [merged a pull request to make their client software compatible with BIP91](https://github.com/btc1/bitcoin/pull/21). The day after, a group of miners [published their own press release](https://medium.com/@Litecoinchina/china-bitcoin-rountable-resolution-on-the-implementation-of-the-new-york-agreement-8834869e6c0d) proclaiming that they’d start signaling for Segwit2x starting on June 19.

![](/assets/images/2017/m6/segwit2x-what-you-need-to-know1.jpg)

*Current state of Bitcoin*

In this article, I’m going to describe the events of the last 5 days or so and explain how things will play out. In the process, I hope to enlighten you on how BIP91 works and how Segwit will get activated on the network and what needs to happen when in order to avoid a soft fork on August 1.

#### Bitmain’s Press Release

![](/assets/images/2017/m6/segwit2x-what-you-need-to-know2.png)

I’ve already [examined the press release](https://medium.com/p/examining-bitmains-press-release-6b47b0646f15), but as Charlie Shrem points out in the above tweet, I forgot to include one point about Segwit2x. To wit:

![](/assets/images/2017/m6/segwit2x-what-you-need-to-know3.png)

Bitmain is saying that they would prefer the [New York Agreement](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77) to any hard fork. Bitmain would like Segwit2x (aka New York Agreement) to activate before BIP148. One big reason this may be the case is that Segwit2x requires Segwit and thus, if Segwit is locked in on the network, [BIP148 won’t do anything](https://medium.com/p/uasf-bip148-scenarios-and-game-theory-9530336d953e).

So naturally, you may be wondering how does Segwit2x activate? This is actually a trickier question than it may seem.

#### Segwit2x Activation Mechanism

The original New York Agreement stated this:

![](/assets/images/2017/m6/segwit2x-what-you-need-to-know4.png)

The press release actually doesn’t get into technical detail about Segwit activation other than the one bullet point circled in red above. Note that the original Segwit proposal, BIP141, requires 95% threshold and is signaled at bit 1. Those are obviously different, so the community was left wondering, would the two signals be compatible at all? Is it possible to signal for Segwit2x and *not* BIP141 or vice versa?

What would happen, for example, if Segwit2x managed to activate Segwit, but nodes running BIP141 thought it wasn’t active or vice versa?

To solve these problems, a clever mechanism was proposed (interestingly on May 22, a day *before* the New York Agreement publication) by James Hilliard on the [Bitcoin Devs mailing list](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-May/014380.html). It is this clever mechanism (now called BIP91) that leads us to the next part of the story.

#### Merging the two Segwit activation mechanisms

[BIP91](https://github.com/bitcoin/bips/blob/master/bip-0091.mediawiki) is a clever way to translate 80% signaling to 95% signaling. The way it does so is like this:

* Signaling at bit 4 is accepted.
* If 269 of 336 blocks signal either bit, BIP91 is locked in.
* After another 336 blocks, BIP91 is activated.
* When BIP91 is active, blocks not signaling bit 1 (that is, signaling for Segwit BIP141) are rejected from the network.

If this last point sounds familiar, it should. It’s exactly what [BIP148 does](https://github.com/bitcoin/bips/blob/master/bip-0148.mediawiki). As a result of “forced signaling”, the chain will have 100% signaling for BIP141 (Segwit) and will lock in and activate. The difference between BIP91 and BIP148 is that BIP91 waits for 80% of the miners to agree first.

What happened last Thursday is that [BIP91 was merged](https://github.com/btc1/bitcoin/pull/21) into the Segwit2x repository, ensuring that Segwit would activate with 80% mining support.

#### The Miner Roundtable Resolution

The next day, the Chinese miners published [a press release](https://medium.com/@Litecoinchina/china-bitcoin-rountable-resolution-on-the-implementation-of-the-new-york-agreement-8834869e6c0d) proclaiming that they would run the Segwit2x software. As the software is not ready, they are not going to signal either bit 1 or bit 4 but actually add the string “NYA” into the Coinbase string. These miners represent about 80% of all hashing power and will presumably signal bit 4 as soon as the Segwit2x software is ready.

#### What this means for you

Here’s what needs to happen in order to avoid a soft fork on August 1:

1. Segwit2x software has to be released and in the hands of miners
2. At least 269 of 336 blocks must signal bit 4 (about 80%). This would achieve BIP91 lock-in.
3. Another 336 blocks must pass. This achieves BIP91 activation. After this point, every block must signal bit 1 (Segwit/BIP141).

If all of the above happen before August 1, BIP148 will not do anything and no soft-fork will result. What’s still unclear is if we’re at step 2 on August 1. Would the BIP148 supporters take that as “good enough” and not soft fork? Probably, but thus far, BIP148 supporters haven’t clarified that with a statement. It would probably be in the interests of everyone that BIP148 supporters clarify this as soon as possible.

#### But Wait, There’s More

This is a positive development if you’re hoping to avoid a permanent split as it looks like Bitcoin will stay on one chain. But the battle is not over. The bigger and more contentious issue of a 2MB hard fork is the one that still needs to be settled.

Per the [New York Agreement](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77), a 2MB Hard Fork must be activated within 6 months. What software will activate the 2MB Hard Fork? Will that be Bitcoin Core? Unlikely since they didn’t sign the agreement. Segwit2x? Possible, but how is that going to get rolled out? Bitcoin Unlimited? BUIP0055 already has a target date of October 18, but it allows blocks larger than 2MB.

Furthermore, if a client other than Bitcoin Core is what the New York Agreement signers will run, how is that repository going to get managed? Will Bitcoin Core developers be involved or not? If Segwit2x is proposed as a merge to Core, what if Core rejects it?

None of these questions have been answered. We are by no means out of the woods yet.

#### Conclusion

The steps taken in the past week look like Segwit will be activated and avoid a network fork on August 1. This is good news in the short term, but the long term question of whether there will be a hard fork to larger blocks or not is still unanswered. There is room for optimism, but there are still more battles to be fought.

**Edit: Thanks to Aaron van Wirdum for pointing out a flaw in my article. I’ve corrected it.*

***

{% include signup.md %}
