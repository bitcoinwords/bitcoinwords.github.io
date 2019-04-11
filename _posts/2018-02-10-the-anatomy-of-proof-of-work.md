---
title: "The Anatomy of Proof-of-Work"
permalink: "/the-anatomy-of-proof-of-work" 

tags:
  - CY18 Q1
  - Hugo Nguyen

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---

# [The Anatomy of Proof-of-Work](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667)
### By [Hugo Nguyen](https://medium.com/@hugonguyen)
### February 10, 2018

**This is Part 1 of a 5 part series**
* [Part 1 - The Anatomy of Proof-of-Work](https://cryptowords.github.io/the-anatomy-of-proof-of-work)
* [Part 2 - Bitcoin, Chance and Randomness](https://cryptowords.github.io/bitcoin-chance-and-randomness)
* [Part 3 - How Cryptography Redefines Private Property](https://cryptowords.github.io/how-cryptography-redefines-private-property)
* [Part 4 - Bitcoin's Incentive Scheme and the Rational Individual](https://cryptowords.github.io/bitcoins-incentive-scheme-and-the-rational-individual)
* [Part 5 - Bitcoin: Two Parts Math, One Part Biology](https://cryptowords.github.io/bitcoin-two-parts-math-one-part-biology)

<br>

***

Proof-of-Work (PoW) was originally invented as a [measure against email spams](https://en.m.wikipedia.org/wiki/Proof-of-work_system). Only later it was adapted to be used in digital cash [1].

What PoW mining actually does under the hood, is that it converts kinetic energy (electricity) into a ledger block. A mining machine repeatedly performs hash operations until it solves a cryptographic puzzle. All hash operations are thrown away except for the one hash that solves it.

This one tiny hash, which itself takes very little energy to compute, is a direct representation of the huge ball of energy that was required to produce it. The "proof" that the block was minted. In order to rewrite the block, an attacker later will have to spend a roughly equivalent number of hash operations that was originally required.

Let's say that again: reverting takes an equivalent number of hash operations, not an equivalent amount of energy. That is because the hash is only a representation of the energy used, not the energy itself.

Over time, this representation of energy becomes less & less accurate — as improved hardware becomes more efficient. Energy itself doesn't change, but its old representations "leak".

Another way to visualize this process, is to think of PoW mining as attaching physical weights to virtual blocks. Over time the older blocks get damaged and get lighter & lighter. This also reduces the total weight of the chain, all else being equal.

Bitcoin combats this attrition process by constantly creating new blocks with fresh weights. This ensures that the tip of the chain is always heavy in the present, protecting the integrity of the entire chain. Heavy chain == secure chain.

(Some have suggested that "heaviest chain" is a better terminology than Satoshi's "longest chain." Longest chain can be very misleading when we don't really mean length in the literal sense.)

SHA256 is the hash function that backs Bitcoin PoW mining. SHA256 protects the ledger from being rewritten. One hash in (to mine), one hash out (to revert). This is what gives Bitcoin its immutability property [2].

It's amazing when you think about it. Hash operations dedicate their entire existence to the purpose of securing the ledger! Rarely anything in the real world has 100% dedication & efficiency. (e.g.: contrast that with gasoline & the combustion engine).

In reality, it is probably not 100% but something close to it. Because irreversibility relies on the hashed results being uniformly random (just like when you roll a fair dice), and algorithms can't truly simulate real-world randomness.

Luckily for us, hash functions such as SHA256 have shown to be [sufficiently random](https://www.eecs.harvard.edu/~michaelm/postscripts/soda2008b.pdf), aka "pseudorandom". SHA256 has been reviewed & stress-tested for years, and has a rich research literature behind it. So it's not something we have to be too concerned about (yet).

Fundamentally, I believe the idea of "attaching energy" to blocks is the right one & probably the only way to simulate immutability virtually.

**Using energy burnt to back a block allows us to view immutability objectively. Whereas any non-energy-based method ultimately requires someone's** [**subjective interpretation of immutability**](https://twitter.com/hugohanoi/status/953346280134029312) **.** [3]

By attaching energy to a block, we give it "form", allowing it to have real weight & consequences in the physical world. We can also think of PoW as the magic that brings a bunch of 0s & 1s into life.

In other words, **PoW is the bridge between the digital & the physical**.

Compare that to some cryptokitties that someone creates, modifies & removes as they see fit. Their uniqueness & existence are neither guaranteed nor reliable.

Even if the current variant of PoW fails, I'm confident that there will be other ways of attaching energy to a block.

In conclusion, PoW's application in blockchains might prove to be far more significant & wide reaching than what it was originally invented for. PoW gives us immutability, which gives us uncensorable money, which could potentially change how society organizes itself. (Read Nick Szabo's wonderful essay on [**social scalability**](https://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html) for more on that.)

([Original tweetstorm](https://twitter.com/hugohanoi/status/957091071745433601).)

_*This is part 1 of the Bitcoin Fundamentals series. Check out the full series here:_ [_part 1_](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667) _,_ [_part 2_](https://medium.com/@hugonguyen/bitcoin-chance-and-randomness-ba49a6edf933) _,_ [_part 3_](https://medium.com/@hugonguyen/how-cryptography-redefines-private-property-34cd93d86036) _,_ [_part 4_](https://medium.com/@hugonguyen/bitcoins-incentive-scheme-and-the-rational-individual-dc20effa4715) _, and_ [_part 5_](https://medium.com/@hugonguyen/bitcoin-two-parts-math-one-part-biology-b45ef48a0422) _._

_[1]: The idea of using PoW in digital cash might have originated from Wei Dai's b-money & Nick Szabo's bitgold proposals in the late 90's. Hal Finney created the first implementation of PoW in digital cash (RPOW) in 2004._

_[2]: Immutability is a relative concept. When we say 'immutability' we usually mean it's practically immutable, not absolutely immutable. Even Gold can be synthesized given enough energy._

_[3]: One such method is Proof-of-Stake. Read_ [_my article on Proof-of-Stake_](https://medium.com/@hugonguyen/proof-of-stake-the-wrong-engineering-mindset-15e641ab65a2) _to understand its pitfalls & why it might be inferior to Proof-of-Work._
