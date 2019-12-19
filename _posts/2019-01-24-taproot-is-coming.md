---
title: "Taproot Is Coming: What It Is, and How It Will Benefit Bitcoin"
permalink: "/taproot-is-coming" 

author: aaronvanwirdum

tags:
  - Aaron van Wirdum
  - CY19 Q1
  - Taproot
  - Schnorr
  - MAST
  - Technology
  - Smart Contracts
  - Privacy

excerpt: Aaron van Wirdum covers scmart contract and privacy benefits of Taproot. posted January 24, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Taproot Is Coming: What It Is, and How It Will Benefit Bitcoin](https://bitcoinmagazine.com/articles/taproot-coming-what-it-and-how-it-will-benefit-bitcoin)
### By [Aaron van Wirdum](https://twitter.com/AaronvanW)
### Posted January 24, 2019

Bitcoin users may, before long, be able to benefit from a trick called “Taproot.” First [proposed](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-January/015614.html) by Bitcoin Core contributor and former Blockstream CTO Gregory Maxwell, Taproot would expand on Bitcoin’s smart contract flexibility, while offering more privacy in doing so. Even the most complex smart contracts would, on the blockchain, typically be indistinguishable from regular transactions.

While a big undertaking, this is not just theory. Several of the most prolific Bitcoin Core contributors — including Pieter Wuille, Anthony Towns, Johnson Lau, Jonas Nick, Andrew Poelstra, Tim Ruffing, Rusty Russell and, indeed, Gregory Maxwell — are working on a [Schnorr signature](https://bitcoinmagazine.com/articles/the-power-of-schnorr-the-signature-algorithm-to-increase-bitcoin-s-scale-and-privacy-1460642496/) proposal that would include Taproot, all in one protocol upgrade.

Here’s what Taproot is and how it works.

## P2SH
All bitcoins are essentially “locked up” in scripts: a couple lines of code embedded in a transaction included in the blockchain, that define how the coins can be spent in the next transaction. Spending conditions usually involve providing a signature to prove ownership of the coins. But other, well-known conditions for example include timelocks (coins can only be spent after a specific block height or date) or multisig (coins can only be spent if some number of private keys out of a set of private keys provide signatures).

Different conditions can be mixed and matched, to create complex types of smart contracts. An example of such a contract could be that coins can be spent if both Alice and Bob sign, or if Alice alone signs after a week has passed, or if Bob alone signs while also providing a secret number. Whichever of these three conditions is met first, is how the coins are spent.

Since 2012, scripts (the conditions) are often not publicly visible at first; only the new owner of the coins knows how they can be spent. This is done with a trick called P2SH (pay to script hash), where initially only a hash of the script is included in the blockchain. This seemingly randomly scrambled number holds the coins. When the owner spends the coins, he reveals the whole script as well as the “solution” to the script at the same time. Anyone can then use the initial hash to check that the supplied script was indeed the original script locking up the coins and can immediately conclude that the requirements of the script were met.

Still, when the coins are spent, it’s currently necessary to reveal all the possible conditions that could have been met — including the conditions that weren’t met. This has two main downsides. One, it’s data heavy, especially if there are many conditions. And two, it’s bad for privacy. Everyone learns all the different ways in which funds could have been spent, which can, for example, reveal what kind of wallet was used and perhaps even more.

## MAST
[MAST](https://bitcoinmagazine.com/articles/the-next-step-to-improve-bitcoin-s-flexibility-scalability-and-privacy-is-called-mast-1476388597/) (Merkelized Abstract Syntax Tree) is a proposed solution that uses Merkle trees (a decades-old, compact data structure invented by cryptographer Ralph Merkle) to work around these two downsides. In short, all the different conditions under which the funds can be spent are individually hashed (as opposed to combined into a single hash) and included in a Merkle tree, which ultimately produces a single hash: the Merkle root. This Merkle root “locks up” the coins.

The unique benefit is that if any of the data in the Merkle tree is revealed, the Merkle root and some additional data (called the Merkle path) can be used to verify that that specific data was included in the Merkle tree. The rest of the Merkle tree remains hashed and hidden.

With MAST, this means that only the condition that is met needs to be revealed. If, in the initial example above, Alice alone spends the funds after a week, she just reveals that condition (and the Merkle path). No one learns that the money could have also been spent by Alice and Bob together, or by Bob alone if he’d added a secret number. This makes MAST more data efficient than complex P2SH smart contracts and adds privacy to boot.

Yet with Schnorr, Taproot can do even better: a transaction can hide that a MAST-structure existed at all.

## Schnorr
The Schnorr signature scheme has long been on the wishlist of many Bitcoin developers and is currently in development to be deployed as a soft fork protocol upgrade. Many cryptographers consider the Schnorr signature scheme to be the best in the field, as its mathematical properties offer a strong level of correctness, it doesn’t suffer from malleability and is relatively fast to verify.

As its best-known benefit in the context of Bitcoin, Schnorr’s “linear math” allows for signature aggregation: several signatures in the same transaction can be combined into one. A similar trick could be applied to multisig transactions. Combining both public keys and signatures into “threshold public keys” and “threshold signatures,” a multisig transaction can be made indistinguishable from any regular transaction.

And the signature scheme can be used in even more interesting ways. For example, it’s possible to use data to “tweak” both a private key and a public key. As a simplified example, a private key and its corresponding public key could be tweaked by multiplying both by two. The “private key x 2” and the “public key x 2” would still correspond, and the “private key x 2” could still sign messages that could be verified with the “public key x 2.” Anyone unaware that the original key pair was tweaked wouldn’t even see any difference; the tweaked keys look like any other key pair.

This is what enables Taproot.

## Taproot
Taproot is based on an interesting realization: no matter how complex, almost any MAST-construction could (or should) include a condition that allows all participants to agree on the outcome and simply sign off on a settlement transaction together. In the earlier example, if Bob knows Alice can, by herself, claim all the funds next week, he might as well cooperate with her now to sign off together. (In many typical smart contract setups he would even be penalized if he doesn’t. The complexity really just serves to keep everyone honest.)

Taproot resembles MAST and always includes a condition where all participants can cooperate to spend the funds: the “cooperative close.”

By utilizing Schnorr signatures, this is where it gets interesting.

First off, the cooperative close would utilize Schnorr’s threshold trick to make it look like a regular transaction, from one person to another. So, the public keys of all participants are added together, resulting in the “threshold public key.” Corresponding with this threshold public key, the combination of all participants’ signatures — their “threshold signature” — allows them to spend the funds.

So far so good, but spending the funds as if it were a normal transaction is the only thing they can do — no MAST-like structures yet. That’s where the other Schnorr trick comes in.

All the alternative ways in which the funds can be spent — the non-cooperative outcomes — are this time combined into a different script. This script, then, is hashed and used to tweak the threshold public key. Rather than “public key x 2,” as used in the example earlier, this results in a “threshold public key x script.” (We’re still simplifying.) This “threshold public key x script” corresponds, of course, to a “threshold signature x script.”

Now, if the money is spent cooperatively, all participants combine their signatures into the “threshold signature” and tweak it with the script. The resulting “threshold signature x script” allows them to spend the funds. Yet, and importantly, to the outside world, all this would still just look like a regular public key and a regular signature — a regular transaction.

Only if a cooperative close proves impossible, the threshold public key can be shown for what it really is: tweaked.

In this case, both the original threshold public key and the script are revealed. This proves that the “threshold public key x script” was tweaked with this specific script. So, like the hash in P2SH, the tweak proves to the world that the funds should be spendable if the alternative conditions, as specified in this script, are met. (And, like with P2SH, these conditions are of course immediately met to spend the funds.)

Alternatively, instead of tweaking the threshold public key with script, the threshold public key can be tweaked with a Merkle root of a Merkle tree that includes all the different conditions under which the funds can be spent: a MAST structure. To spend the funds, then, only the spending condition that’s been met needs to be revealed.

As such, Taproot offers all the benefits of MAST, while under normal circumstances no one will ever know that a regular transaction was hiding such a complex smart contract as a fallback.

This is a general outline of the Taproot concept; implementation specifics may vary. For more details, read the [original Taproot proposal](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-January/015614.html) by Gregory Maxwell or watch [this presentation](https://youtu.be/YSUVRj8iznU) by Pieter Wuille.

***

{% include signup.md %}
