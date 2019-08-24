---
title: "Proof-of-Stake & the Wrong Engineering Mindset"
permalink: "/proof-of-stake-and-the-wrong-engineering-mindset" 

author: hugonguyen

tags:
  - Hugo Nguyen
  - CY18 Q1
  - PoS
  - PoW
  - Technology

excerpt: Hugo Nguyen explains why PoS is flawed. Posted March 18,2018.

defaults:
  - scope:
      type: posts
---

# [Proof-of-Stake & the Wrong Engineering Mindset](https://medium.com/@hugonguyen/proof-of-stake-the-wrong-engineering-mindset-15e641ab65a2)
### By [Hugo Nguyen](https://medium.com/@hugonguyen)
### Posted March 18, 2018

Proof-of-Stake (PoS) is all the rage these days. Ethereum Casper, Cardano Ouroboros, etc. you name it. The rising interest in PoS protocols is probably due to the desire to scale blockchains indefinitely, combined with the mistaken notion that Proof-of-Work (PoW) is somehow "wasteful." (Go [here](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667) for a detailed discussion on PoW).

**A topic not emphasized enough with PoS protocols is their lack of resilience in dealing with worst-case scenarios [1].** For examples: extraordinary events that could knock offline or partition a significant portion of the network, or even the entire network. Or the risk of stolen/purchased private keys.

One might think that these kinds of scenarios are rare or unlikely, but a) they might not necessarily be as rare as you think and b) even something with a 0.1% chance of happening means that it _will_ happen in the long run — these are what Nassim Taleb termed [Black Swan events](https://en.wikipedia.org/wiki/Black_swan_theory).

Simply put, these events are highly unlikely to happen, but when they do happen, the results are often catastrophic. We humans regularly underestimate high-impact, long-tail events. E.g. the illusion that tomorrow is safe simply because it has been safe for the last 10 or 100 years.

Careful consideration of long tail events is especially important in the design of a protocol that has the potential to become the backbone of the global economy, that millions of people & businesses will rely on.

We must handle Bitcoin software with the same respect we handle nuclear reactor software. In engineering literature, this class of software is known as critical systems. There're three types of critical systems: _safety-critical_, _mission-critical_ and _business-critical_. Bitcoin fits the bill for all three (loss of money _can_ cause loss of life). There's absolutely no margin for error.

Experienced engineers wouldn't sleep well at night even with the current level of [Bitcoin security](https://www.coindesk.com/bitcoins-security-model-deep-dive), which is far from perfect. They know that we're always one step away from a disaster, no matter how sound things are on paper & how smoothly things seem to have gone so far.

There have been many high-profile engineering failures in the past that clearly demonstrate this type of hidden danger. Some examples:

**1) Concorde crash (2003)**

Concorde (1976–2003) was one of the only two supersonic passenger planes ever existed. The [Concorde crash](https://en.wikipedia.org/wiki/Air_France_Flight_4590) happened as a result of a blown tire hitting the fuel tank during takeoff, causing a chain reaction. Concorde was once considered one of "the safest planes in the world".

**2) Challenger disaster (1986)**

NASA initially estimated that the odds of failure was 1 in 100,000. Richard Feynman led the investigation which discovered the cause to be [the failure of the O-rings to expand in 32-degree weather](https://www.history.com/news/how-the-challenger-disaster-changed-nasa). The true odds was closer to 1 in 100. A thousand fold miscalculation!

**3) Fukushima meltdown (2011)**

Japan is one of the best countries in terms of earthquake technology & earthquake safety.

The [Fukushima meltdown](https://en.wikipedia.org/wiki/Fukushima_Daiichi_nuclear_disaster) happened as a result of what you can call the perfect storm of disasters: a magnitude-9 earthquake, the most powerful ever recorded in Japan, followed by a 15-meter (~50 feet), once-in-a-thousand-year tsunami.

**Thinking about worst case scenarios is an absolute must when dealing with critical systems, and even more important when these systems are on the global scale.**

***

Let's examine how PoW & PoS deal with network partition & unexpected outage [2].

Just to drive home the point that this type of scenario is not as far-fetched as one might think: during the Arab Spring movement, the Turkish government successfully performed [BGP hijacking](https://bgpmon.net/turkey-hijacking-ip-addresses-for-popular-global-dns-providers/) to block Twitter traffic from Turkish citizens. China has even more sophisticated tools to block Internet traffic, as part of their Great Firewall.

You can also imagine situations like wars — where countries might try to take out the enemy's communication infrastructure, which would be typically the first target since whoever has better communication gains the upper hand.

So how resilient is a PoW or PoS system under these scenarios? Let's go through some examples.

**Scenario 1: The entire network is forced offline for some period. Then reboot.**

Since all regions might not reboot and regain contact with each other simultaneously, what you'll likely end up with is several regions starting their own independent chain, from the last common block just before the network went dark, in effect creating multiple chain splits.

When cross-region communication gets re-established, nodes on these independent chains will come into contact with one another.

In PoW, the nodes will automatically self-organize & eventually gravitate towards one single chain: the chain with the most accumulated PoW (and the most secure _)_. It will be painful, since some chains will get wiped out in the process. But it will work, and the behavior is deterministic.

In PoS, the nodes would have no idea which chain is the more "correct" chain. Unlike PoW, PoS has no objective yardstick to compare the "realness" between 2 chains. Behavior is indeterministic & impossible to automate away without introducing some arbitrary rules that increase the attack surface. The split might become permanent, as some PoS protocols [make it impossible to go back too far into the past](https://github.com/ethereum/research/wiki/Casper-Version-1-Implementation-Guide).

PoS protocol designers often go to great lengths to "punish" misbehaving actors. What they don't consider is the possibility that all nodes act honestly, but there's a chain split nonetheless!

**Scenario 2: Some portions of the network get partitioned from the main network.**

It turns out that this scenario results in a similar outcome to what we saw in scenario 1. Partitions will continue to run as if everything is operational- except that the number of "active" staking nodes in each isolated partition is smaller. When the partitions regain contact with the main network, confusion will ensue. Nodes have no idea which chain is the canonical chain.

One crucial difference between scenario 1 and scenario 2 is that the likelihood of scenario 2 happening is even higher. Redirecting traffic is easier than shutting down traffic wholesale- we already saw it being done. Partitions can be as small as a small town's network. We can imagine something like that happening once every few years or even more frequently.

***

**Scenario 3: PoS also fares worse in other worst case scenarios such as stolen private keys.**

Wealth distributions often follow power laws, and there's no reason to think cryptocurrencies are any exception. The "1% of crypto", which could be just a handful of people, might very well control a significant portion or the majority of the total coin supply.

These richest PoS stake holders' private keys might get stolen as a result of sophisticated social engineering attacks (kidnapping, torture, extortion, etc.). By stealing keys instead of renting or buying coins on the open market, the attacker avoids raising the currency value during the attack. Strangely, when considering this attack vector, PoS protocol designers often assume that buying coins on the open market is the only way to get majority control, and thereby incorrectly conclude that the cost of attacking a PoS currency is merely determined by its market value. Stealing private keys sidesteps that "defense" altogether & significantly reduce the cost of attack.

(A variant of this attack is to purchase old keys from past large stake holders who no longer have an interest in the currency).

In PoW, this is equivalent to gaining control over the majority hash rate.

What can someone with majority hash rate do in PoW? He can try to double-spend or rewrite history. But to double-spend, he has to spend a lot of money. Gaining majority control is only the first step. As bad as it sounds, even under this scenario, the protocol still functions as expected & only one chain can be considered valid (although SPV nodes might get confused- hence the reason running full nodes is often encouraged). To rewrite history costs an even more insane amount of money, so the risk of losing user balance is low. Users could choose to wait out the storm or take action to change the PoW algorithm.

All in all, it's a pretty ugly situation. But we can see that gaining majority hash rate in PoW doesn't grant the attacker unlimited power. You have to gain majority control AND spend money to carry out an attack. We can think of this as a _two-layer defense_. When there's an attack, the behavior is deterministic & there's no confusion about which chain is valid. This resilience in hostile situations is under-appreciated.

In contrast, gaining majority stake in PoS grants you unlimited power. You can double-spend without spending any extra money unlike in PoW. You can also either a) rewrite history, if the protocol doesn't have checkpoints or b) cause irreconcilable chain splits, if the protocol has checkpoints (e.g. [Casper](https://arxiv.org/abs/1710.09437v2)). Changing PoS algorithm doesn't help as there's virtually no switching cost, unlike investment in hardware.

To sum it up, what PoW gives you are two benefits, when it comes to security guarantees:

1. _PoW protects the future_: When there's a chain split, it gives us an objective mechanism, automatable way of resolving conflicts, without requiring manual human intervention or trusted third parties.
2. _PoW protects the past_: Getting control of majority hash rate still costs an attacker an enormous amount of time & money to rewrite history, so the balances are somewhat safe.

PoS offers neither of these things. PoS proponents might claim that checkpoints alleviate problem #2, but in reality checkpoints just shift the problem from one area to another. Checkpoints is a [centralized solution](https://www.coindesk.com/bitcoins-security-model-deep-dive/) that opens up another can of worms [3].

_(*For a more in-depth discussion of "private keys attacks", check out_ [_Part 2_](https://medium.com/@hugonguyen/proof-of-stake-private-keys-attacks-and-unforgeable-costliness-the-unsung-hero-5caca70b01cb) _.)_

***

In conclusion, it's very important to have the right mindset when it comes to Bitcoin & blockchain protocol development. They are critical systems that deserve the highest level of engineering.

**PoS protocols are built on faulty & naive assumptions that rapidly break down under worst-case scenarios.** PoS is a step in the wrong direction: lowering the bar of quality, instead of raising it.

***

Part 2 _:_ [Proof-of-Stake, Private Keys Attacks and Unforgeable Costliness the Unsung Hero](https://medium.com/@hugonguyen/proof-of-stake-private-keys-attacks-and-unforgeable-costliness-the-unsung-hero-5caca70b01cb) _._

_[1]: Some prior analysis of PoS: Andrew Poelstra, 'On Stake & Consensus'_ [_https://download.wpsoftware.net/bitcoin/pos.pdf_](https://download.wpsoftware.net/bitcoin/pos.pdf)

_[2]: Network partition is an important area of research. Check out Ethan Heilman's work in this area:_ [_https://eprint.iacr.org/2015/263.pdf_](https://eprint.iacr.org/2015/263.pdf)

_[3]: Checkpoints could be implemented in a decentralized manner, but they will cause problems that will require centralized solutions down the line. So in effect, checkpointing is centralizing._
