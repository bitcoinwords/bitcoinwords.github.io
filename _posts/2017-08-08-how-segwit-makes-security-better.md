---
title: "How SegWit makes security better"
permalink: "/how-segwit-makes-security-better"

author: olegandreev

tags:
  - Oleg Andreev
  - 2017 Q3
  - SegWit
  - Security
  - Technology

excerpt: How SegWit makes security better. Posted August 8, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [How SegWit makes security better](https://blog.oleganza.com/post/163955782228/how-segwit-makes-security-better)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted August 8, 2017

**UPDATE (Aug 9, 2019):** the described proposal has some significant flaws. A more secure proposal is discussed here:

* [https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-August/017229.html](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-August/017229.html)
* [https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-August/017231.html](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-August/017231.html)

Some people on the internet underappreciate how important a “malleability” aspect of Bitcoin is which is one of the things that [Segregated Witness](https://segwit.org) upgrade is going to fix.

Let’s take a look at [Bitcoin Covenants](http://fc16.ifca.ai/bitcoin/papers/MES16.pdf) paper from 2016 that introduces a “Vault” feature. I will briefly explain how Vaults work and how would you implement them in today’s Bitcoin without SegWit (today) and with SegWit (in two weeks).

First of all, **what is a Vault?** A slightly simplified version looks like this: you move funds to a special address **V** (“Vault”) from which you can only move them into address **W** (“initiate a withdrawal process”) and no other addresses. There are two paths from **W**. Path 1 allows moving funds from **W** anywhere after a 24 hour delay since the initiation of a withdrawal (that is, since the transaction **V->W** was published) using only an active key **A**. Path 2 allows moving funds anywhere without a delay, but requires both the active key **A** and a recovery key **R** (or multiple recovery keys).

Here’s a diagram:

`initial deposit:     $ -------> V`

`initiate withdrawal: V -------> W, using key A`

`unlock after delay:  W --(a)--> *, using key A & 24h delay`

`recover funds:       W --(b)--> *, using keys A & R, no delay`

**The theory behind Vault** is that regular keys are convenient to use (they are always ready), but since they are more vulnerable, we require a publication of a “withdrawal attempt” with a grace period. If the withdrawal was legitimate, user would simply have to wait for the payment to go through. If it was not, the user has time to notice the attempt and will have to dig up the recovery keys: maybe ask friends to co-sign a transaction, or get a printed copy from a deep hole in their backyard. The time delay could be proportional to the amount of funds in question. Small amounts won’t use any vault, medium amounts would use 24 hour delay, long-term savings would use 72-hour delay and a multisig recovery setup with trusted friends/family.

Today Bitcoin does not have a `CheckOutputVerify` function suggested in the Covenants paper. To simulate it for the Vault case we can use a temporary key **V** for the Vault address and a pre-signed transaction **V->W**. Key **V** is destroyed after the address **V** is funded. Then, withdrawal can only be initiated by publishing the transaction **V->W**. Address **W** can use an already existing feature `CheckSequenceVerify` that enforces relative timelock (e.g. “24 hours since publication”), plus If/Else branches to allow a recovery path without a delay.

If we did not have transaction malleability, we would simply do the following:

1. Create a temporary key **V**.
2. Create and pre-sign transaction T1 that pays to **V**.
3. Create and pre-sign transaction T2 that pays from **V** to **W**.
4. Delete key **V**.
5. Publish transaction T1.
6. Store transaction T2 encrypted with an active key **A**.
7. To make a withdrawal: publish transaction T2, pre-sign a delayed spending from transaction T2 into a given address, publish later when timelock is over.

If we do have to deal with transaction malleability, we cannot do steps 1-6 at once. We would have to store the temporary key **V** for a much longer time, persisted on disk (instead of in RAM for a millisecond), until transaction T1 is well-confirmed and the risk of chain reorganization that has a mutated version of it is very low.

What’s worse: we would introduce a new vulnerability. For regular payments, reorgs may cancel the payment, which can be retried by the sender. If you send to yourself, this is not a problem. But if you erase a temporary key and the pre-signed transaction (T2) is the only way to recover your funds, a reorg can lock you out forever. So you have to wait a significantly long time for your non-trivial amount of bitcoins to be securely locked by transaction T1.

While you wait, your key **V** has to be stored and backed up. If it is backed up, you need to protect it with a very strong password, but the whole premise of the scheme is to allow storing active key **A** with a mediocre password because strong passwords do not really exist. So if your key **V** is leaked while you wait, you lose all protections: attacker will not have to use your specially-crafted transaction T2, but would simply sign anything with key **V** directly.

So you need to store **V** stronger than you’d store **A**. You can achieve it with the same multisig setup you’d use for the recovery key(s) **R**: ask your friends to act as a collective additional key to your temporary **V** to pre-sign transaction T2 (using my [blind signature scheme](https://github.com/oleganza/bitcoin-papers/blob/master/BitcoinBlindSignatures.md) to maintain privacy). But now you no longer ask your friends to be only your recovery mechanism (which you **may never have to use**), but you have to ask them **every time** you move money into a vault.

As a result, your wallet has to be much more complicated, with a lot of moving parts, more user interactivity, and additional security assumptions instead of doing one obvious thing with one push of a button.

Segregated witness fixes transaction malleability and makes highly desireable security schemes possible. This is much more important than a minor increase in transaction throughput, because Bitcoin is **stored most of the time** and only **occasionally changes hands**.

***

{% include signup.md %}
