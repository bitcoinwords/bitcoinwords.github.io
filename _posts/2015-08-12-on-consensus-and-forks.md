---
title: "On consensus and forks"
permalink: "/on-consensus-and-forks"

author: mikehearn

tags:
  - Mike Hearn
  - 2015 Q3
  - Mining
  - Technology
  - Governance

excerpt: On consensus and forks. Posted August 12, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [On consensus and forks](https://medium.com/@octskyward/on-consensus-and-forks-c6a050c792e7)
### By Mike Hearn
### Posted August 12, 2015

What is the difference between a hard and soft fork?

The long, hot summer of 2015 has revealed something surprising about the Bitcoin community: many people have strange and technically unsupportable ideas about how the block chain algorithm actually works.

This has culminated in Michael Marquardt, who admins bitcoin.org and various discussion forums, banning all discussion of Bitcoin XT and threatening to delete services that use it from the official Bitcoin website. His rationale is that Bitcoin XT is an alt coin because it is intended to trigger a hard fork. On the other hand, [“soft forks” are totally OK](https://bitcoin.org/en/posts/hard-fork-policy).

This position doesn’t make any technical sense, and in this article I will explain why not.

#### Soft and hard forks

You can’t be around Bitcoin forums for long without seeing these two terms. It’s become clear from my chats with random enthusiasts that an awful lot of Bitcoiners have been left behind with this terminology. Again and again I come across people who don’t understand what these words mean, but think they do.

That’s not surprising. The idea of a “soft fork” is relatively recent, and appears to have emerged out of IRC discussions rather than a BIP or other kind of precise standards document. It doesn’t help that even developers routinely define the term wrongly.

A hard fork is when the rules of the Bitcoin protocol change such that old nodes refuse to accept blocks created by newer nodes. As rule violating blocks are ignored, miners will produce blocks building on the last block they saw that followed their rule set.

A soft fork is when the rules of the Bitcoin protocol change such that old nodes don’t realise the rules are different, and continue to accept blocks created by newer nodes that follow the changed rule set. Miners may build on top of blocks that they didn’t fully understand or validate.

This is frequently described as “backwards compatibility” by various Bitcoin Core developers, but that’s not correct and probably contributes to the confusion. The definition of backwards compatibility is that new software accepts data/code produced by or for old software. When Windows 10 runs apps written for Windows XP, that’s backwards compatibility. Both fork types require backwards compatibility, because otherwise new nodes would be unable to verify the block chain from scratch.

The correct term is actually [*forwards compatibility*](https://www.google.com/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=define%3Aforwards%20compatibility): this is when old software continues to accept data/code produced by new software. When you save a document in Word 2013 and it can still be opened by Word 2011, that’s forwards compatibility.

It’s worth noting that Satoshi did not use the phrase “hard fork”; presumably the notion that any other kind of fork might exist didn’t occur to him. The idea of a soft fork wasn’t around back then, and rightly so, as the concept is itself deeply flawed: in a correctly functioning Bitcoin network no soft forks should ever happen.

That may seem like a bold claim, so let’s analyse it closer.

#### Why are soft forks bad?

It may appear that allowing old software to continue processing data without needing to be upgraded is a no-brainer: why would you *not* want this? And sure enough, software engineers like backwards and forwards compatibility a lot: if you can make a new version of your app that interoperates with old versions, that’s usually a win.

Forwards compatibility is rarer than backwards compatibility. The reason is that if you add some new feature to your file formats or protocols, then old software won’t be able to understand it. Sometimes you can make the new feature optional: it’s OK if old software ignores it. This is called *graceful degradation* and it’s a popular technique, especially on the web where people want to make web pages that work in old browsers whilst still using new features.

Given that backwards and forwards compatibility are normally desirable things in software engineering, why is Bitcoin different? The reason is simple:

**Forwards compatibility defeats the entire purpose of running a node.**

It’s easy to see why. XT/Core download and process every block from genesis day onwards because by doing this they are auditing the block chain. They add up every number, they check every signature. By the time the audit has finished, you can be sure that the ledger you’re using reflects application of the rules written into the software.

This is a key part of Bitcoin’s decentralisation: by using your own copy of the ledger that was calculated by your own computer, and then only accepting payments that are valid according to that ledger, you reinforce key economic policies like the inflation formula and the absence of double spending.

The idea is simple: nobody, not even a miner with majority hash power, can trick you into accepting money that violated these rules.

Or ……. can they?

And here’s the problem with soft forks.

In a soft fork, a protocol change is carefully constructed to essentially trick old nodes into believing that something is valid when it actually might not be.

Here’s an analogy. Imagine a big company with a team of auditors, and a team of traders. The traders want to make a new type of trade that the firm currently disallows: the auditors check what the traders are doing to enforce company policies. Changing the policies can be slow work. But one day, a trader has a brainwave. “*Hey guys*”, he says, “*I’ve had an idea. I’m going to submit some trades for derivatives, but I’m going to write it down on the paperwork as buying land. When you see that, just mentally replace land with derivatives, and carry on as normal. The auditors won’t find out!*”

The auditors are people and services that are running Bitcoin full nodes. The traders are people who want to change the rules. Whether their rule change is a good idea or not isn’t relevant here: what matters is how they’re doing it. The auditors are now cross checking every transaction, but their calculations can *arrive at the wrong answer,*because they don’t understand the true nature of the transactions they’re verifying.

How does this work technically? We can look at how a Bitcoin feature called P2SH was introduced to see. P2SH is a useful feature that makes multisig easier to use, but on the block chain it looks odd:

[https://blockchain.info/tx/f837ca5c1a15fa6c2e5c7380386bacba10e936fe8625e12d9fa6c177a8f605c1](https://blockchain.info/tx/f837ca5c1a15fa6c2e5c7380386bacba10e936fe8625e12d9fa6c177a8f605c1)

```
OP_HASH160 6af7caf9b09224af8a171318f69d254c1756e54e OP_EQUAL
```

This is a Bitcoin script, and in English it says “anyone who knows the password can spend this money”. The problem with making coins like this is it’s insecure: there’s no signature, so the moment you broadcast a transaction that provides the “password” anyone else in the Bitcoin network can make their own transaction that spends the output as well, because the password is now public. So it ends up being a pure race to see whose transaction propagates to miners first.

P2SH works because the Bitcoin protocol was changed to include a new rule: when you see an output script of the above form, don’t actually treat it as a script at all, instead apply special processing to it: the password is in fact the “real” script so run that. So P2SH is not insecure, don’t worry. But why use this roundabout and strange approach?

You guessed it — soft forking is to blame. This construct is designed to always be considered valid by old nodes that don’t understand the P2SH rule. If presented with a transaction that spends this coin under the classical Bitcoin rules but which doesn’t satisfy the new P2SH rule, *they will fail to audit it correctly and calculate an incorrect ledger.*

But preventing that from happening is the whole reason you’re running a full node in the first place! Oops!

#### What happens in a hard fork?

Let’s imagine P2SH was introduced in a different way: via a hard fork. The script would instead look something like this:

```
OP_HASH160 6af7caf9b09224af8a171318f69d2... OP_EQUAL OP_RUN
```

Note the final OP_RUN: this is an opcode that doesn’t exist in the current Bitcoin instruction set. Defined properly, the script would look to old nodes like this:

```
OP_HASH160 6af7caf9b09224af8a171318f69d2... OP_EQUAL OP_???
```

And when they reach the OP_??? bit, they’d stop and reject the transaction+block, because they’d realise they didn’t know what the transaction meant.

I should remark at this point that there actually was a counter-proposal to the current P2SH back then which was called OP_EVAL, and the discussions about which approach was better were quite dramatic. I don’t recall the details of that debate and don’t want to reopen it here: this is all just for illustration.

OK, so your node has rejected a block because it didn’t understand it. Now what? In our imaginary firm the auditors would call the CEO (you) and ask for a decision. You’re The Decider™. And so it is with Bitcoin: you will be alerted in some way, like via SMS or email if you configured that, and you get to decide what to do. You could …

1. Read about the rule change and decide that you’re OK with it. Upgrade and continue.
2. Read about the rule change and decide you’re **not** OK with it. More on this in a second.
3. Explicitly decide to trust any spend of the scripts you don’t understand. You might do this if uptime of your node is more important to you than correct audit results.

The last option is risky but hey, check it out — you just got the soft forking behaviour back! The difference is, you explicitly requested it and your choice doesn’t affect anyone else. Only you take the risk of calculating an incorrect ledger. Bitcoin Core & XT don’t support the third option today, but adding a switch to enable it would be easy if anyone wanted that.

My point? **Knowledge is power**. When you know the rules have changed, you can use that information to take better decisions. With a soft fork, you don’t know the rules have changed and are flying blind.

#### On optionality

Recently bitcoin.org [adopted a new policy](https://bitcoin.org/en/posts/hard-fork-policy). It says:

> Contentious hard forks are bad for Bitcoin. At the very best, a contentious hard fork will leave people who chose the losing side of the fork feeling disenfranchised. At the very worst, it will make bitcoins permanently lose their value.

This is a very curious statement because it implies that it’s possible to change Bitcoin without causing “disenfranchisment”.

But this isn’t how money works. Money is inherently a social tool and to use a currency is to accept its rules, even if you don’t like them. You can’t use the dollar whilst opting out of quantitiative easing. Even if this were technically possible (maybe you are a large bank), you’re going to start receiving “eased” dollars instead of “real” dollars in payment sooner or later and arguing with your customers about this is a quick route to commercial death.

*Any* change to Bitcoin that is accepted by the majority inherently “disenfranchises” the people who didn’t want that change. This has nothing to do with hard or soft forks: regardless of which technique is used, if transactions using the new rules start to enter widespread circulation then sooner or later you will receive coins in payment that trace back to a new-rule transaction. And then you have two choices. You can verify the new rule, or you can not verify it. But the only thing not verifying does is reduce your own security: it’s cutting off your nose to spite your face. So in practice everyone always upgrades. To disagree with a soft fork that is adopted by the majority is no different than disagreeing with a hard fork: if you don’t like the new rules ….. tough cookies. That’s trade.

We can see proof of this in P2SH itself. The competing proposal had some miner and developer support, but in the end everyone accepted the version we have today. They had no choice in the matter, or rather, they chose to accept the change and continue using Bitcoin. It being a soft fork made no difference.

So the idea that hard forks vs soft forks is some epic struggle for personal rights over oppression just doesn’t make any technical sense. The distinction is not just wrong: it’s completely irrelevant.

#### Forks for miners and merchants

This article is a bit long, so I’ll keep this section short. If you are a miner or a merchant, you should prefer changes to be made via hard forks. Here’s why.

**Merchants:** you really want to be sure that a transaction that’s paying you is valid according to the majority, and you want that as fast as possible. That means your node needs to be running the majority rule set. If you get left behind, you can be defrauded. This means you need to know ASAP if you’re no longer in the majority, and you want to ignore transactions that you couldn’t verify.

Ignoring is probably better than getting ripped off: if a user complains that their payment didn’t go through that’s a signal that you’re out of date, even if you forgot to configure your full node to email/SMS/phone you. But if you prefer to take the chance you can always configure your full node to act as if there was a soft fork whilst simultaneously trying to get your attention as best it can.

Note that after I raised some of these points with the Bitcoin Core developers, they tweaked the code so that some soft forks are actually more close to hard forks: Core will ignore transactions that seem to be using unknown opcodes (what we want!) … until they appear in a block (doh). So in practice whether this tweak helps you or not depends a lot on timing. Their reasoning for why this is OK: if you are waiting for “just” one block to accept a payment or — heaven forbid — not waiting for a block at all, then, you’re doing Bitcoin wrong and deserve to bleed.

**Miners:**if you are a miner and fall behind the majority rules, you *will* lose money regardless of which fork type is used. However, a hard fork is still better. Firstly, it’s detectable, so a properly configured node can email/SMS/phone you to let you know it’s out of date. It could also automatically shut down your mining operation so you don’t waste electricity mining doomed blocks. Secondly, if you think the other chain is wrong and you think others will come to agree with you, you can take a chance by continuing to mine a non-majority chain. If your bet pays off then at some point everyone will switch (back) to your chain, and you will get all the lovely coinbases that other miners didn’t get. This strategy is **extremely risky** and I do not recommend it at all. You can bleed vast sums very quickly this way and miners have never actually done this as a result. But it is a technical possibility.

With a soft fork you will mine blocks you think are valid, but are actually being ignored by other miners. Then when they orphan your block you will think it’s just ordinary bad luck and try to build another invalid block …. which will get orphaned again. If you are a small miner who doesn’t produce blocks very often it might be quite a long time until you figure out that this isn’t just a run of very bad luck but rather, a rule change you didn’t know about. Pocket, meet hole!

#### Can hard forks destroy Bitcoin?

No. If it were the case then literally anyone could kill Bitcoin by just mining a block or two with different rules. The entire purpose of the block chain algorithm is to ensure that this cannot do any damage!

The idea that “contentious” hard forks could cause bitcoins to “permanently lose their value” appears in the bitcoin.org policy, but it’s actually the other way around. To demand that any change must have 100% agreement (or 99%), as at least one Bitcoin Core developer wants, just means anyone can hold the entire community to ransom by refusing to agree unless they get what they want. No actual piece of infrastructure works this way. If Bitcoin did, it could never evolve and eventually would become worthless.

***

{% include signup.md %}
