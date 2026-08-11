---
title: "The capacity cliff"
permalink: "/the-capacity-cliff"

author: mikehearn

tags:
  - Mike Hearn
  - 2015 Q2
  - Mining
  - Technology
  - Scaling

excerpt: The capacity cliff. Posted May 5, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The capacity cliff](https://medium.com/@octskyward/the-capacity-cliff-586d1bf7715e)
### By Mike Hearn
### Posted May 5, 2015

And why we can’t use fancy tricks to avoid it

Meep meep!

This article analyses some proposed alternatives to raising Bitcoin’s network capacity, specifically, the [**Lightning network**](http://lightning.network/lightning-network.pdf). But the arguments made are general and could apply to other proposed alternatives too.

Firstly, a bit of background.

Many years ago Satoshi Nakamoto added a quick hack to the Bitcoin source code. He artificially limited its capacity to avoid a rogue miner causing problems for people in an era when using Bitcoin meant downloading the entire chain, with a slow and unoptimised client.

The limit was intended to be removed. In fact, Satoshi intended it to be removed as soon as SPV wallets were developed.

I know this because at the end of 2010 I emailed him to ask about it. He responded,

> A higher limit can be phased in once we have actual use closer to the limit and make sure it’s working OK.

> Eventually when we have client-only implementations, the block chain size won’t matter much. Until then, while all users still have to download the entire block chain to start, it’s nice if we can keep it down to a reasonable size.

By client-only he was talking about wallets like Bitcoin Wallet for Android, MultiBit, BreadWallet etc. The term *SPV wallet* wasn’t in use back then — it’s [a phrase I coined when I wrote the first implementation](https://bitcointalk.org/index.php?topic=7972.msg116285#msg116285).

According to Satoshi’s original thinking the limit could have been increased years ago. But we’ve left it to the last minute instead. According to [my rough calculations](https://medium.com/@octskyward/bitcoin-s-seasonal-affective-disorder-35733bab760d), Bitcoin grows in the winter and stagnates in the summer. If current trends continue Bitcoin should run out of capacity by the start of winter 2015, and quite possibly months before. Because upgrades take time, we need to prepare for this now. Hence [Gavin proposing a patch and starting the discussion](http://gavinandresen.ninja/time-to-roll-out-bigger-blocks).

[Some people](https://www.reddit.com/r/Bitcoin/comments/34riua/hard_fork_allow_20mb_blocks_after_1_march_2016/cqxfr43) would like to believe that we can avoid changing this limit, by relying on another way to scale Bitcoin up. These people are typically not implementors. I think it won’t work, and in this article I will explain why not.

Finally, a brief word about my own background for those who don’t know me. I have spent the last five years implementing Bitcoin wallets, and before that I spent nearly 8 years at Google. Three of those years were spent on the Geo Team (Maps/Earth), where I was a professional capacity planner for one of the world’s busiest websites. Just like now, capacity planning had to be done with long lead times. In the Google world it was because we had to physically manufacture the machines and physically build the data centers. In the Bitcoin world it’s because it takes time for people to upgrade. So I am not inexperienced with our current dilemma.

#### The Lightning Network

What is the [Lightning Network](http://lightning.network/lightning-network.pdf)? It is the latest name for [an old idea](https://bitcointalk.org/index.php?topic=25786.msg480826#msg480826): to use *payment channels* between various low-trust intermediaries in order to transmit payments. A payment channel is essentially a pot of bitcoins, established on the block chain, the split of which can be negotiated by passing messages around outside the Bitcoin network. Eventually the final split of the pot settles on the chain. Various Bitcoin protocol features are used to make this work in a low trust manner.

The first and primary usage of this technique is for micropayments: the messages that re-split the pot can be passed around much faster and cheaper than a Bitcoin payment can be, because it’s only between two parties. But it was observed early on that a network of channels could be established between clients/servers and servers/servers that would allow for fast, low trust payments between the parties. Effectively, a clearing network that runs on top of the block chain and occasionally settles up on it.

Such a clearing network should be better than most are because the requirement to settle on the block chain would keep the intermediaries honest. And in theory it could process more transactions than Bitcoin itself could because the block chain only sees aggregated payments.

![](/assets/images/2015/m5/the-capacity-cliff1.png)

It’s a neat and attractive idea. So attractive that although the Lightning guys are currently getting all the attention, their idea has already been implemented by a Swedish startup called [**StrawPay**](https://www.reddit.com/r/Bitcoin/comments/2r3ri7/strawpay_cheap_and_secure_micropayments/).

StrawPay has designed a protocol called *Stroem* (actually *Ström* but lots of people don’t know how to type/pronounce that). It defines how wallets, hubs and merchants interact and set up payment channels between them. They have also implemented a cross platform GUI wallet that can actually do it all.

The Stroem protocol isn’t identical to Lightning — they vary in some technical details, notably, Stroem works with the Bitcoin protocol of today and accepts the caveats whereas Lightning doesn’t. Also, Stroem specifies all the other details the Lightning paper ignores, like how to actually start such a payment in a backwards compatible way (Bitcoin addresses cannot be used in these schemes).

I like the StrawPay guys and I wish them well. I think Stroem has a lot of potential for making micropayment routing faster and easier. It’s quite possible it will find a place in the Bitcoin ecosystem. But using it should not be mandatory.

There are several reasons why *requiring* this approach to scale up is not good.

The first is that the implementation complexity will hurt decentralisation.

![](/assets/images/2015/m5/the-capacity-cliff2.jpg)

#### Complexity kills kittens

It’s natural for people to focus on problems and ignore things that are going well — there’s only so much patting a back can take, after all. So Bitcoiners tend to stress out about the centralisation of mining, of exchanges, of payment processing etc. We spend much less time reflecting on our successes, and the wallet market is a big decentralisation success.

By now there are probably hundreds of different wallets out there, with dozens of different implementations of the underlying algorithms. No single wallet is obviously dominant. They compete for users in a vibrant market. This is important: if there were only one or two wallets with all the users then those wallets would essentially be gatekeepers to the system, and worse, able to change the rules of Bitcoin at a whim. The block chain wouldn’t matter because people experience the block chain almost exclusively through their wallets.

Building a wallet is no walk in the park. I should know — I’ve spent the last five years writing [bitcoinj](https://bitcoinj.github.io/), a reusable “wallet engine” that sits at the core of quite a few Bitcoin apps and services. But still, it’s possible for someone to do it in their spare time and without a large team of people. Contrast this to HTML5 which is only implementable by large corporations. The Bitcoin protocol isn’t as simple as it looks, but it’s not overwhelming either. That simplicity is key to the diversity of wallets in present use.

Unfortunately, payment channels are not simple. Especially once you introduce more advanced features like what Lightning proposes, you end up with a much larger, more complex piece of code. A few people have made toy implementations of payment channels, but *only* bitcoinj has a real, production-quality implementation. Toys don’t have to think about things like documentation, serialization of state to disk, unit tests, documentation, user interface integration, error management and so on. The difference between a toy and something real is whether it’s been used to make apps that you could actually give to a non-nerd.

Payment channels in bitcoinj have been used to make [PayFile](https://www.youtube.com/watch?v=r0BXnWlnIi4), which lets you pay per kilobyte to download files, multiple Android prototypes of wifi micropayment billing …. and StrawPay itself. The entire StrawPay implementation is built on bitcoinj from the ground up, and their GUI wallet is a fork of MultiBit HD. So we know that the code works. That means we also know how much effort it took. Luckily, most of the work had corporate funding.

You might imagine I’d be happy at the idea of everyone being forced to implement payment channels by the start of next summer. Inevitably many developers would conclude it’d be faster to just replace their own code with bitcoinj/StrawPay, and I’d get a lot more users. But I don’t want people to be forced to use my code in a hurry. That’d create a giant dev support headache for me, and I don’t want to see the hit to decentralisation, even though forking bitcoinj is very easy. Plus developers would resent being “required” to use my software and I don’t want that either.

So if we make it harder to build wallets, it stands to reason that there will be fewer of them. [The StrawPay developers say](https://www.reddit.com/r/Bitcoin/comments/2r3ri7/strawpay_cheap_and_secure_micropayments/cnc7n5u):

> We have a lib written in Java that wallets should use, but it’s under development. There is no support for iOS wallets yet (they don’t even have a payment channel impl AFAIK).

> Even with the lib at hand there is a lot of GUI work and general plumbing for a wallet developer before the wallet is Stroem enabled.

Eventually the wallet market may consolidate around a handful of engines anyway, just as the game industry has done. But there’s no need for us to accelerate that trend unnecessarily. And it *would* be unnecessary, because all of this is solving a non-existent problem: Bitcoin’s core technology can scale up without any external assistance.

#### Examples of dead kittens

From [the Lightning white paper](http://lightning.network/lightning-network-paper-DRAFT-0.5.pdf):

> If one does not broadcast a transaction at the correct time, the counterparty may steal funds. This can be mitigated by having a designated 3rd party to send funds. An output fee can be added to create an incentive for this 3rd party to watch the network.

This sort of problem may seem academic, but “not broadcasting at the correct time” can be caused by issues as mundane as your phone running out of batteries or roaming into an area with weak signal. It can be solved by adding yet more semi-trusted third parties …. but up goes the complexity yet again!

For special cases like extremely rapid micro-billing, where there’s no other way to do it, we just have to swallow such things. For situations where we can avoid it, we should.

Another case:

> When one party loses data, it is possible for the counterparty to steal funds.

And another ….

> While there may be methods to mitigate the [hacking] threat for the sender and the receiver, the intermediary nodes must be online and will likely be processing the transaction automatically. For this reason,
>
> the intermediary nodes will be at risk and should not be holding a substantial amount of money
>
> in this “hot wallet.”

> Intermediary nodes which have better security will likely be able to outcompete others in the long run and be able to conduct greater transaction volume due to lower fees. Historically, one of the largest component of fees/interest is from various forms of counterparty risk —
>
> in Bitcoin it is possible that the largest component in fees will be derived from security risk premiums
>
> .

Hub and spoke payment channel networks require always-on servers that have sensitive signing keys. This is quite different to ordinary Bitcoin usage, where only the sender needs to sign, and doing all signing offline is both possible and commonplace. That raises complexity and thus costs.

#### Bitcoin nodes are easier than hubs

One common complaint about scaling Bitcoin up is that it will become harder to run a full node. Some people who make this complaint then point to payment channels as a solution, ignoring that it makes it easier to run a full node by simply shifting the work onto different kinds of nodes …. nodes that are much harder to set up and run.

The main reason is that hubs in payment channel networks are stateful, so you have to make sure they have good uptime, reliability and working backups. In contrast Bitcoin nodes are almost entirely stateless, and all software that accesses the P2P network knows how to recover from a node suddenly vanishing. It happens all the time and is transparent to the user.

That makes running a full node very easy and safe: if your cheap $10 VPS goes down for a reboot, nobody will notice or complain. If it suffers from massive data loss, you can just re-install the node and it will recalculate all the data it needs from scratch. If it gets hacked, there’s nothing there to steal. None of these things are true of payment channel hubs.

#### Performance risks are high

StrawPay doesn’t use the design you would intuitively imagine, in which channels link sender to hub, hub to hub, and hub to receiver. Instead hubs issue receivers with promissary notes. [The designers say](https://www.reddit.com/r/Bitcoin/comments/2r3ri7/strawpay_cheap_and_secure_micropayments/cncxxim):

> I was waiting for this question. This was probably the longest discussion we had. The reasons:

> 1) Security: it is a complex thing to keep a payment channel server running. It has to be secure. Most merchants do not have the knowledge, and could get their wallet hacked. The Promissory Note, the way we designed it, cannot be used by anyone else than the merchant, so it is pointless to steal it.

> 2) Performance: we worry that in a network of hubs the progression of micropayments from hub to hub would not be fast enough. Better to tell the merchant that the consumer has paid ASAP, and let the merchant hold the Promissory Note instead.

> Very hard choice.

We have already covered the security issues so that’s no surprise. But you may raise eyebrows at the mention of performance. Don’t — the payment channel protocols involve a lot of message round trips and signature creation/verification. These steps are not individually slow: they’re measured in milliseconds. But if each step takes 200 milliseconds and you have ten of them, suddenly payments are getting a little pokey.

Broadcasting a Bitcoin transaction across the network is hardly a fast thing either, but it’s at least a flood fill with plenty of room for optimisation. And a transaction can be verified locally extremely fast: it’s only the propagation delays that matter. Payments across a hub/spoke network are a graph traversal: rather different.

To put this in perspective, the EMV Contactless specifications require that a payment takes less than 500 milliseconds. That includes the time needed for the smart card to boot up, establish the radio link, perform ECDSA signatures and authorise the payment, and for the terminal to verify. Online authorizations have latency timeouts of only 200 msec on each server request. The London Underground network has [stations that require people to get through the gate in only three seconds](http://www.bcs.org/upload/pdf/tfl-sep09.pdf). So performance matters.

It might be that the StrawPay guys are overly conservative — the point is, nobody knows yet, because nobody has tried to build and deploy such a network. Thus, many important questions remain unanswered.

#### There is no time

Let’s ignore all of the above and assume payment channel networks are the best thing ever. It doesn’t matter, because we need a solution by the middle of next year at the latest, and none of the proposed networks even exist yet.

Quite simply, we are out of time. There are no credible technical proposals that could gain widespread adoption within the next twelve months, beyond simply raising the capacity on the existing system, which is well understood and implemented by everyone already.

I like the idea of Stroem/Lightning for fast routing of micropayments. I like the idea of payment channels for direct sender/receiver micro-billing. We may well one day all be using wallets that support these systems. But it’s engineering nonsense to talk about these things as solutions to our current problems.

Some people seem to think that if we hit Bitcoin’s capacity limits, there will be a smooth rise in fees and the free market will sort everything out. This is incorrect. In my next article, I’ll write about what will *actually* happen if we don’t fix this problem in time.

##### To be continued …

***

{% include signup.md %}
