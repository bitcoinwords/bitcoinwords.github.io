---
title: "Work is Timeless, Stake is Not"
permalink: "/work-is-timeless-stake-is-not" 

tags:
  - Hugo Nguyen
  - CY18 Q4

excerpt: This is a brief look at some of the arguments of Proof of Stake. By Hugo Nguyen, posted October 12, 2018

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

# [Work is Timeless, Stake is Not](https://medium.com/@hugonguyen/work-is-timeless-stake-is-not-554c4450ce18)
### [Hugo Nguyen](https://medium.com/@hugonguyen)
### Posted October 12, 2018

Much has been written about Proof-of-Stake (PoS).

There are many ways to slice and dice PoS and uncover its weaknesses. Mainly:

**Evolutionary Psychology/History**: "Collectibles" or "proto-money" in history all had one thing in common, [_unforgeable costliness_](https://nakamotoinstitute.org/shelling-out) [1] — or at least unforgeable costliness in the context of their times. From sea shells, furs, teeth, to precious metals to minted coins. As PoS merely involves the temporary lockup of existing capital and does not consume said capital, it does not satisfy the unforgeable costliness requirement that Nick Szabo identified as one of the 3 key properties of money.

**Economics**: If an object has value, people will spend effort to chase it, up to whatever the object is worth ([_MC=MR_](http://www.truthcoin.info/blog/pow-cheapest)). This effort is also "work". Paul Sztorc correctly concluded that PoS is an obfuscated form of PoW.

Work manifests in different ways in PoS, whether it is taking out a loan from the bank, running 24/7 staking servers, or attempting to steal online staking keys.

Not only PoS is obfuscated PoW, it is inferior PoW. Any potential cost saving PoS gives you, it pays back in _equal measure_ in the reduction in security.

As we shall see below, a dollar [2] fleetingly locked up in staking creates nowhere near the same level of security as a dollar spent in mining.

**Computer Science**: Andrew Poelstra wrote [one of the first formalized critiques of PoS](https://download.wpsoftware.net/bitcoin/pos.pdf), in which he coined the terms costless simulation (aka nothing-at-stake) and long-range attacks.

A [recent paper](https://arxiv.org/abs/1809.06528) by Jonah Brown-Cohen, Arvind Narayanan & co. also showed surprising barriers to having a good and reliable source of randomness in PoS protocols [3].

**Engineering**: I myself have written a 2-part series [[Part 1](https://medium.com/@hugonguyen/proof-of-stake-the-wrong-engineering-mindset-15e641ab65a2)] [[Part 2](https://medium.com/@hugonguyen/proof-of-stake-private-keys-attacks-and-unforgeable-costliness-the-unsung-hero-5caca70b01cb)] looking at PoS weaknesses from the practical engineering perspective, and listed specific worst-case scenarios where PoS is particularly vulnerable: network partition, private keys theft, or low rate of participation in staking.

But perhaps one of the simplest ways to look at PoS is through the lenses of Time, which I alluded to in my series, but want to expand on here.

## Proof of Stake is Proof of Temporary Stake

Proof-of-Stake is a misnomer. The correct, fully descriptive name for Proof-of-Stake should be Proof-of-Temporary-Stake (PoTS). This name is more accurate because it captures the time element, or lack thereof, of PoS.

To understand the effects of Time, let's first analyze how Time plays a role in PoW.

The ongoing energy expenditure in PoW contributes to network security in 2 ways:

* Energy expended per block not only secures the UTXOs belonging in that block but also [retroactively secures all global UTXOs that occurred in past blocks](https://medium.com/@laurentmt/gravity-10e1a25d2ab2). The reason for this is because it would be impossible to revert past UTXOs without reverting the current block first. Each new block effectively "buries" all existing UTXOs under its weight.
* Investment in specialized mining equipment, in essence, represents the [potential stream of rewards earned in the future](https://medium.com/@hugonguyen/bitcoin-stock-flow-c4d4db98b751), discounted back to the present. When a miner invests in a new piece of mining equipment, it is akin to buying a share of stock that pays regular dividends. What that means is that mining hardware in totality roughly represents potential energy expenditure of future blocks.

One way to visualize this is to imagine a timeline. Units of work expended in the past _accumulate_ in the ledger. Units of work expended in the future _accumulate_ in the current mining hardware.

![](/assets/images/cy18/cy18q4m10/hugo-1.png){: .align-center}*Ledger accumulates past work; Mining hardware accumulates future work.*

As time moves forward, units of work on the right side materialize and move to the left side. Mining hardware can also be seen as a "buffer", a place where units of work deposit before making their way to their final destination: the ledger [4].

The official term to describe this sort of time-based accumulation phenomenon is _stock & flow_, which occurs often in nature. Bitcoin is essentially protected by high stock-to-flow ratios in 2 areas: the ledger, and the mining hardware. ([Go here](https://medium.com/@hugonguyen/bitcoin-stock-flow-c4d4db98b751) for a detailed discussion of stock & flow.)

In contrast, PoS has no equivalent of this.

Past stakes (left side of the timeline) do not accumulate in the ledger, as stake is released after some arbitrary bonding period [5]. Long-range attack is the manifestation of this weakness: it works because of PoS's inability to secure the past. Long range attack is at the heart of the problems with PoS, because it shows that in the long run PoS fails to guarantee the integrity of the ledger — the most important asset of all this innovation.

Future stakes (right side of the timeline) also do not accumulate in the validators in the present time, as again the act of staking only has meaning within the short window that it occurs — what happens in the future does not count _today_. [Current-private-keys-theft](https://medium.com/@hugonguyen/proof-of-stake-private-keys-attacks-and-unforgeable-costliness-the-unsung-hero-5caca70b01cb) is the manifestation of this weakness: it works because of PoS's inability to secure the future. Keys theft sidesteps altogether the financial cost supposedly required to acquire controlling stake — whereas in PoW there's no sidestepping the fact that an attacker needs to overcome the mining hardware and ongoing energy costs to pull off _and_ sustain a majority attack [6].

(There is one form of accumulation in PoS. That is, the periodic staking rewards that accrue to the validators. However, unlike accumulation in PoW, rewards accumulation is only beneficial to the individual PoS validators, not to overall network security.)

In summary: the further one moves away from the present time in PoS, the faster stake loses its meaning, until stake becomes meaningless.

Work is robust against the ravages of time [7]. Stake is not.

The fact that the cost of PoW mining is irretrievably sunk and accumulates both in the ledger and the mining hardware, is an important feature, not a bug. PoS research is often based on the fundamental misconception that this is a bug and a source of inefficiency.

## Acknowledgments

Special thanks to [Vijay Boyapati](https://medium.com/@vijayboyapati), [Bob McElrath](https://medium.com/@BobMcElrath), [LaurentMT](https://medium.com/@laurentmt), [Nic Carter](https://medium.com/@nic__carter) and [Steve Lee](https://medium.com/@moneyball) for their valuable feedback.

_*Note: Another major criticism of PoS is that PoS pretty much guarantees a plutocracy system (rich getting richer). That is not discussed here as it is not related to security strength per se, and deserves its own separate discussion._

_[1] Some might confuse unforgeable costliness with the_ [_labor theory of value_](https://en.wikipedia.org/wiki/Labor_theory_of_value) _, but they are not the same thing. Energy cost alone is not enough, the asset must be unforgeable._

_[2] Dollar is only used as a unit here for convenience, it could be any other unit of account._

_[3] For a PoS currency, relying on an external source of randomness involves_ [_circular reasoning fallacy_](https://medium.com/@hugonguyen/feedback-loop-vs-circular-reasoning-1544ae7fd457) _. Therefore it is highly desirable that PoS generates randomness internally, using the content of its own ledger. However, this proves to be a difficult problem that has its own trade-offs._

_[4] Not all units of work make it all the way to the ledger. Some are thrown away, but even thrown-away work are necessary to keep the network decentralized._

_[5] The concept of "_ [_finality_](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQs#what-is-economic-finality-in-general) _" does not change the (lack of) accumulation aspect of PoS, as new/long-dormant/partitioned nodes can see different "finalities"._

_[6] Hardware seizure (e.g. by a state actor) is a risk in PoW, however this risk can be mitigated as long as mining is sufficiently decentralized. Disperse hardware, however, is not a defensive option for PoS, as PoS validators are just software nodes — which can be targeted from anywhere remotely. More importantly, even with seized hardware, an attacker still can't avoid ongoing energy costs._

_[7] Work is timeless / robust in terms of number of hashes, not energy required. New hardware technologies could improve mining efficiency — although at some point the efficiency gains will slow down as we run into hard physical limits. The robustness of Bitcoin's PoW also relies on SHA256 not being broken._
