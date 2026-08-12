---
title: "Merge avoidance"
permalink: "/merge-avoidance"

author: mikehearn

tags:
  - Mike Hearn
  - 2013 Q4
  - Privacy
  - Technology

excerpt: Merge avoidance. Posted December 11, 2013.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Merge avoidance](https://medium.com/@octskyward/merge-avoidance-7f95a386692f)
### By Mike Hearn
### Posted December 11, 2013

##### A note on privacy-enhancing techniques in the Bitcoin protocol

In this article I am going to briefly discuss some Bitcoin privacy leaks, and a new technique that does not currently have a name but in this article I will call *merge avoidance.* I will compare and contrast it to CoinJoin.

#### Introduction

It is an unfortunate fact that despite Bitcoin’s reputation in the press, its users currently leak large amounts of personal information. It is distressingly easy for someone to learn about your balance, trading history and more. Protecting this information is a basic function of any useful financial system.

Here are a handful of leaks that crop up in daily usage.

#### Address reuse

Many privacy problems in Bitcoin are caused by an adversary learning which outputs are owned by the same wallet. If you can calculate this, you can discover the wallets balance and possibly who it traded with. The most common way this happens is when addresses are reused. This is easily understood because popular sites like blockchain.info index outputs and transactions by address, allowing you to quickly look up all the transactions that reference any given address.

Address reuse has many different root causes. Here are a sampling:

1. **End-user wallet problems.** The bitcoinj library always reuses addresses by policy, thus leaking a lot of private information. There are two reasons for this. One is that prior to the development of HD wallets, constantly using up keys would result in invalidation of old wallet backups. Bitcoin-Qt has a “key pool” to try and address this, but it only puts the problem off: the key pool can be silently exhausted giving the same problem. Invalidating backups can cause people to lose money.
Once HD wallets are implemented (which is in progress) this problem will go away, leaving only the second problem of memory pressure on low end phones. Address re-use may still be required on such devices, but higher end phones and desktops/laptops shouldn’t encounter any issues.
2. **Server wallet problems.** There are no public, open source wallet implementations that scale to wallets with very large numbers of keys. As far as I know exchanges and major payment processors have all had to implement lots of custom code to work around the lack of scalability of Bitcoin-Qt (and bitcoinj). This puts pressure on receivers to reuse addresses.
3. **Social conventions.**Putting static addresses into forum signatures, qrcodes, etc.

Over time, we will need to make progress with all these issues to reduce address reuse. HD wallets and the payment protocol are important tools to help us achieve this.

#### Change outputs

One of the most irritating privacy leaks in Bitcoin is people learning lower bounds on your balance. How this works is intuitively understandable via the analogy to cash. With paper money, if you hand over a 500 CHF note to pay for a drink costing only 5 CHF the bar tender learns that your balance is at least 495 CHF. It may well be higher of course, but it’s at least not lower. Bitcoin has the same issue.

The root cause of this problem is a mismatch between the size of a payment you wish to make and the coins (outputs) available to you. If the mismatch is in one direction, you have a lot of tiny outputs and making payments for any non-tiny amounts starts to cost a lot in fees, because the transactions you generate are huge. If the mismatch is in the other direction then to pay for a small thing requires the usage of a big coin, and the change output leaks valuable data about how rich you are.

#### Network traffic

Bitcoin P2P connections are unencrypted. One reason is that most of the data flowing across the P2P network is public, thus encrypting it seems pointless. Another reason is that by its very nature, when you connect to a P2P network your peers could be absolutely anyone and do absolutely anything — for instance they could be nodes run by the NSA. And that’s not even a bad thing! Why should the NSA not run nodes? If someone were to tell them not to, that would imply some kind of central authority who was dictating who gets to run Bitcoin and who doesn’t. We don’t want that.

![](/assets/images/2013/m12/merge-avoidance1.jpg)

So encrypting data is useful when you have a clear idea of who should see it and who shouldn’t. Encrypting public data to random people whom you know nothing about — not quite so useful.

Despite all that, there are still four reasons why it would help to encrypt connections.

The **first reason** is for *Bloom filters*. These are compact representations of what’s relevant to your wallet: typically, what addresses/keys are in it. A filter is one way and can be noisy, that is, you can’t read out addresses directly from a filter, you can only apply it to the block chain and see what it matches. And filters can have false positives, so a node can never be sure if an address is really yours or not. That’s pretty good, but even with a high false positive rate it still narrows down what coins you might own pretty massively. Bloom filters are not public information, they’re just shared between a client and the node it connects to. So it would be good to hide those against passive eavesdroppers, like people sharing your wifi hotspot.

The **second reason** is that even though transactions are public, their origin IP address is not (or it’s not supposed to be). But an adversary who can observe lots of internet links could fairly reliably decide where a transaction started by precisely recording the times when a transaction was first seen and examining the first moment it transited a fibre link. It seems like some intelligence agencies could do this kind of analysis. Encrypting links doesn’t guarantee a fix for this because timing analysis may still be possible, but it certainly makes it harder.

The **third reason** is that if encryption was combined with “trust on first use” (TOFU) authentication, it would make it harder even for active MITMs to perform sybil attacks on wallets and feed them bad data. This is more important for SPV clients than full nodes, but both could benefit.

The **final reason** is that properly implemented, using SSL for P2P connections would make them harder to identify and block using deep packet inspection devices.

#### CoinJoin

Of the above problems, the solution to leaking data via change outputs is one of the most hotly debated (although a lot of people don’t realise they’re debating it). The CoinJoin proposal has received a lot of attention and some initial implementations. Some people see this primarily as a privacy tool, and others as a way to try and break coin tracing. When used for privacy, it can best be described as a way to try and delete information that has already been leaked.

![](/assets/images/2013/m12/merge-avoidance2.png)

*The Sheep Marketplace reddit seems to show some of the limits of coin mixing*

However, CoinJoin has a number of serious problems that make an alternative desirable. It is deeply complex to implement well, vulnerable to sybil/DoS attacks (they’re often the same thing in this context), legally questionable and it’s not clear that the obfuscation even works. The Sheep Marketplace theft has seen someone claim to trace coins through tumblers and mixers, and apparently with a modicum of success. One of the tracer’s tools was sybil/DoS attacks on mixing services so those are not a theoretical concern. Whilst toy implementations are not too hard to put together, robust real-world implementations with proper timeout handling, security checks, good wallet UI integration etc are a lot more effort. So far only blockchain.info has managed to create one (at sharedcoin.com), and you just have to trust that it doesn’t keep logs. Otherwise anyone with the logs could unmix.

Perhaps the least discussed issue is user experience. A CoinJoin transaction requires other people to take part. The more people who take part, the better. But Bitcoin only peaks at about one transaction per second currently. Even if all transactions were CoinJoined, and all rendezvoused at a single point (ack, centralisation!), you would still have to wait 10-15 seconds to get a good set of participants to mix with. That’s just to start the protocol. Then those participants would all have to retrieve the candidate transaction and sign. If any time out, the whole thing has to start again. In poor conditions it could easily take a minute or more to complete this process, especially if some participants have flaky networks (i.e. phones) and are using Tor. Given that we’re trying to improve performance rather than reduce it, that seems like a big problem all by itself.

Whilst increasing traffic and usage would help reduce this issue, even if traffic doubled, splitting the single central rendezvous point would immediately put waiting times back to square one.

One might solve this problem by doing CoinJoins in the background, unrelated to an actual spend that’s taking place. That solves the problem of waiting in line at the coffee shop, but then fees must be paid on those transactions, and it may be difficult to explain to people why their balance suddenly dropped overnight due to an unexpected privacy tax. That sort of nasty surprise would make Bitcoin rather unappealing to ordinary users. It also raises the question of when and how often it is done.

#### Merge avoidance

As a common root cause of privacy leaks is a mismatch in the sizes of available coins vs what is required, it seems we could approach the problem from another angle: by avoiding creating any information leaks that need to be erased in the first place.

Consider the case of Alice, a coffee shop worker who gets paid a salary. Alice does a great job and her boss recognises that with a higher than normal pay packet. Her coworker Bob suspects he doesn’t get paid as much as Alice and wants to know, so convinces Alice to make a small payment to him just after pay day (perhaps they make a bet and Bob wins).

With regular Bitcoin, Alice’s wallet will probably use her salary output and the change will reveal what she gets paid. Even if she made several payments already, Bob can follow the chain of transactions backwards until he finds a reasonably round looking number on the right date and conclude that’s most likely her salary payment.

Plain CoinJoin also doesn’t help her. She would put in one large input to the mix, and get back one large output. She could request lots of smaller outputs, but the input will still be salary-sized and on the right date. Unless lots of people who earn coffee-shop-sized salaries all happen to share the same CoinJoin transaction, the leak hasn’t been fixed.

What she really needs is to avoid ever having such a large single output in the first place. Let’s call this *merge avoidance*. When she submits her [BIP 70 payment request](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki) to her employer, she requests a nice mix of denominations, just like as if she was buying cash at a foreign exchange desk. The request also specifies a unique address for each output. The payment protocol does not specify how a wallet should satisfy this request, but it does allow the possibility that the senders wallet submits multiple independent transactions in order to satisfy the desired outputs.

If her employer uses an old wallet that doesn’t understand merge avoidance, it will generate and submit to her a single giant transaction that has many inputs (from all the coffees) and all her requested outputs. It will look much like a CoinJoin transaction would, but it only has a single participant. However there is no way to know this from looking at the block chain.

If her employer uses a newer wallet that does understand merge avoidance, then something better happens — she will receive a number of different, smaller transactions, each one of which creates one or two of the outputs she requested. There is nothing to link any of them together. Because she trusts her employer not to double spend, she can spread out the broadcast so not even timing gives them away.

If the selection of outputs is chosen smartly, she will never be in a situation whereby she has outputs awkwardly large or small for a particular payment. Bob will simply see a small transaction that yields a small change output, and no matter how far he traces back he will never find any salary-sized output. Alice wins!

Change outputs can leak data in another way. Bob failed in his attempt to learn Alice’s salary by tracing backwards through the block chain, but he can still watch the change output of the payment he received to see what happens to it. If the change is later combined with many others to create a huge payment, suddenly he knows that Alice must have owned at least that much money. Here CoinJoin seems like it should work — if the change goes into a mix, who can say who owns the outputs? But it’s fragile. Even if the outputs are randomly sized, in the absence of merge avoidance they will be recombined again to make a large payment. If Alice happens to mention in passing that she’s going on holiday with her boyfriend, Bob can look at the outputs of the mix her change went into and wait for some of the outputs to be recombined. If a third of the outputs sit there unspent, a third are spent without being combined in any significant way and a third get combined into a $5000 payment the evening before Alice mentions her holiday, it’s a pretty good bet that the trip is costing her $5k.

#### Implementation properties

This scheme has several things that make it nice to implement:

* It can be written incrementally — a simple and not very smart algorithm can nevertheless still improve someone’s privacy. Later, a better algorithm can be developed and deployed, but it doesn’t require any complicated global upgrades. This is a good fit for the volunteer driven fits-and-spurts, competing-wallets development model that Bitcoin has.
* It is very simple and has no moving parts or big state machines. You don’t have to worry about a random mobile phone the other side of the world driving into a tunnel at the wrong moment, or running a buggy reimplementation of the software.
* There is no centralisation, not even any transient rendezvous servers.
* There are no legal risks, because you’re not relying on any services that could be considered money laundering tools.
* It is robust. Above, I gave examples of how CoinJoin can appear to work but still leak in the presence of very little additional information. Merge avoidance doesn’t have that problem.

There are also some downsides:

* How good your privacy is depends heavily on how smartly the people sending you money craft transactions. Thus your privacy relies on people who may not have much incentive to do anything about it. Hopefully common wallet software would do the right thing by default.
* It increases the number of transactions, although the overhead is not as high as you might think — a transaction is merely a list of inputs, outputs and a two-field header (version and lock time). Inputs and outputs are not really changed over a good CoinJoin implementation, and version/locktime could easily be compressed/varint encoded to save space. The difference would be on the order of bytes rather than kilobytes.
* It relies on the payment protocol. But many things rely on that, and the payment protocol is critical to cracking down on address reuse, which is needed for all proposed privacy schemes to work anyway. It’s important that we make BIP70 as easy and widespread as possible.

Merge avoidance doesn’t interfere with coin tracing. Some people may wish to implement CoinJoin systems for that reason alone. However, I can’t imagine that becoming widespread. If people’s privacy is being protected via other means, then CoinJoin becomes a “help thieves hide their stolen money” system which reduces incentive to take part, increases legal risk even further and would make people wonder why their wallet apps were asking them to pay fees simply in order to shield people whom they most likely think are bad. Besides, the Sheep Marketplace incident shows that decentralised crime fighting as a technique is sometimes the only option: nobody is going to ask the police to help recover their stolen drug money, and no government would bother helping if they did.

***

{% include signup.md %}
