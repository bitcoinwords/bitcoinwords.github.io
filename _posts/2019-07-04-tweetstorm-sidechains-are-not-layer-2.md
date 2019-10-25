---
title: "Tweetsorm: SIDECHAINS ARE NOT LAYER 2"
permalink: "/tweetstorm-sidechains-are-not-layer-2" 

author: georgioskonstantopoulos

tags:
  - Georgios Konstantopoulos
  - CY19 Q3

excerpt: Georgios Konstantopoulos shares a much needed tweetstorm where he describes the difference between sidechains and L2. Posted July 4, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

# [Tweetstorm:SIDECHAINS ARE NOT LAYER 2](https://twitter.com/gakonst/status/1146793685545304064)
### By [Georgios Konstantopoulos](https://mobile.twitter.com/gakonst)
### Posted July 4, 2019

Let's put a myth to bed.

Thread on the history of sidechains, their security properites, concluded by their differences to Layer 2 solutions.

(there's a lot of resources, feel free to skip/bookmark for later!)

👇
## -- History of Sidechains --
"Sidechains" is a term coined in [1] by [@Blockstream](https://twitter.com/Blockstream), as a way to access innovative blockchain features which are too risky to try on Bitcoin.

This is done by enabling the transfer of BTC between chains w/ varying feature sets

[1] [blockstream.com/sidechains.pdf](https://blockstream.com/sidechains.pdf)
They introduced the "two-way-peg" (2WP) for PoW blockchains.

To transfer assets from the "sending chain" (SC) to the "receiving chain" (RC), you lock them on the SC, and mint an equivalent amount on RC by providing a proof of ownership on SC along with a DMMS* with enough work.

![](/assets/images/cy19/cy19q3m7/gk-1.png){: .align-center}

* DMMS: Dynamic Membership Multi-party Signature. In the PoW case, that's an SPV proof. Screenshots from [1].

![](/assets/images/cy19/cy19q3m7/gk-2.png){: .align-center}
![](/assets/images/cy19/cy19q3m7/gk-3.png){: .align-center}

Note that the 2WP between PoW chains requires each chain be able to verify the other chain's Proof of Work algo.

Blockstream's Liquid uses a multisig federation and doesn't need SPV proofs for peg-in/out (more on that later on PoS sidechains).

## -- PoW Sidechains --

A few years later [@sol3gga](https://twitter.com/sol3gga), [@socrates1024](https://twitter.com/socrates1024) and [@dionyziz](https://twitter.com/dionyziz) came up with NiPoPoWs [2], a succinct SPV proof technique where the main insight is that some blocks have a better mining target than others.

[2] [nipopows.com](https://nipopows.com/)

![](/assets/images/cy19/cy19q3m7/gk-4.png){: .align-center}

(obviously, [@socrates1024](https://twitter.com/socrates1024) talked about this in bitcoin talk in 2012 [bitcointalk.org/index.php?topi...](https://bitcointalk.org/index.php?topic=98986.0))

![](/assets/images/cy19/cy19q3m7/gk-5.png){: .align-center}

This works only for constant difficulty PoW, so is still not practical, and is vulnerable to block withholding/bribing! [@gtklocker](https://twitter.com/gtklocker) implemented a NiPoPoWs velvet fork and interlinker for Bitcoin Cash which he writes about in his thesis [3].

[3] [arctan.gtklocker.com/thesis.pdf](https://arctan.gtklocker.com/thesis.pdf)
FlyClient [4] by [@benediktbuenz](https://twitter.com/benediktbuenz) utilizes [@peterktodd](https://twitter.com/peterktodd) 's MMRs* [5] to succinctly commit to the chain history. Combined with probabilistic sampling** has better performance than NiPoPoWs and works for varying PoW difficulty.

[4] [eprint.iacr.org/2019/226](https://eprint.iacr.org/2019/226)
[5][**proofchains/python-proofmarshal** Contribute to proofchains/python-proofmarshal development by creating an account on GitHub. <small>https://github.com/proofchains/python-proofmarshal/blob/master/proofmarshal/mmr.py</small>](https://github.com/proofchains/python-proofmarshal/blob/master/proofmarshal/mmr.py)
 
We recently wrote a ZIP with [@_prestwich_](https://twitter.com/_prestwich) and [@therealyingtong](https://twitter.com/therealyingtong) to add MMRs in ZCash's blockheaders. Full FlyClient ZIP soon?

![](/assets/images/cy19/cy19q3m7/gk-1.png){: .align-center}

[_Link to tweet_](https://twitter.com/zooko/status/1146456571322482689)

 **the light client repeatedly asks a full node about random parts of the chain history until they're convinced that the chain being shown to them is correct. This is made non interactive via the Fiat Shamir Heuristic

Short discussion on FlyClient vs NiPoPoWs:

![](/assets/images/cy19/cy19q3m7/gk-7.png){: .align-center}

[@summa_one's](https://twitter.com/summa_one) stateless SPV proofs [6] can also be used for pegs, but are 'cryptoeconomic': the more work inside the provided headers the more confident you can be about the transaction being part of the heaviest chain

[6]
![](/assets/images/cy19/cy19q3m7/gk-8.png){: .align-center}
[_link_](https://www.youtube.com/watch?v=njGSFAOz7F8&feature=youtu.be&t=560)

All PoW sidechain schemes assume that each chain is independently secure. That is a BIG assumption, as argued by Peter against Dionysis: .

Constructing PoW sidechains is also described in [7].

[7] [eprint.iacr.org/2018/1048.pdf](https://eprint.iacr.org/2018/1048.pdf)

![](/assets/images/cy19/cy19q3m7/gk-8.png){: .align-center}
[_link_](https://twitter.com/peterktodd/status/953619414523375616)

TAKEAWAY:

The moment your bitcoins move to an output that is spendable based on an event that happens on a chain with less hashrate than the bitcoin chain, you're exposing yourself to counterparty risk (the miners of the other chain, or the validators if PoS)
I like to think of crosschain assets as alloys.

BTC on the bitcoin chain is BTC-100. It is pure, inefficient, boring; but it is the most sovereign asset that has ever existed.

BTC-X would explore a different tradeoff space, as envisioned by the original [@blockstream](https://twitter.com/Blockstream) paper

![](/assets/images/cy19/cy19q3m7/gk-10.png){: .align-center}

Based on that thought, [@ethereum](https://twitter.com/ethereum) 's or [@binance](https://twitter.com/binance) 's WBTC would be BTC-X, where X is (cost of corrupting the federation) / (cost of attacking bitcoin). It's easy to see how the fraction's value could become 0 on regulatory pressure.

![](/assets/images/cy19/cy19q3m7/gk-11.png){: .align-center}
![](/assets/images/cy19/cy19q3m7/gk-12.png){: .align-center}

What if the receiving chain's consensus halts (i.e., no blocks are produced)? What if the miners refuse to include your locking transaction?

WORST CASE SCENARIO: YOU LOSE ALL YOUR MONEY

![](/assets/images/cy19/cy19q3m7/gk-13.png){: .align-center}

What is the point of gambling your BTC with WBTC in the [#DeFi](https://threadreaderapp.com/hashtag/DeFi) casino if you cannot cash out? It's as if as the casino shut down with all your money inside. Remember Mt. Gox?

## -- PoS sidechains --
In [8], Andrew Poelstra formalizes DMMS security, and argues that a properly implemented PoS with long/short-range attacks protection can be DMMS-like, but has different security from Bitcoin's DMMS.

Maybe that's BTC-99.99?

[8] [download.wpsoftware.net/bitcoin/pos.pdf](https://download.wpsoftware.net/bitcoin/pos.pdf) (my favorite PoS paper)
Since there's no notion of "work", can we construct a secure DMMS that can convince us that an asset was locked on another chain?

Dionysis' work [9], [10] covers this area extensively

[9] [eprint.iacr.org/2018/1239.pdf](https://eprint.iacr.org/2018/1239.pdf) 
[10]
[**Proof-of-Stake Sidechains for Cardano** <small>https://docs.google.com/presentation/d/17x25AfvnMOpmXFO7wqs5q0AtW4yrYJeVPS2Lb22thyo/edit?usp=sharing</small>](https://docs.google.com/presentation/d/17x25AfvnMOpmXFO7wqs5q0AtW4yrYJeVPS2Lb22thyo/edit?usp=sharing)
![](/assets/images/cy19/cy19q3m7/gk-14.png){: .align-center}
[_link_](https://twitter.com/peterktodd/status/953619414523375616)


## -- Crosschain communication in practice (follow IBC for standardization) --
Deposit from sending PoW chain to receiving PoS chain:
1. Send asset to special output on sending chain
2. Validator listens for deposit *with a light client* and signs it
3. If 2/3rds of validators weighted by stake signed, the asset gets minted on the receiving chain

Withdraw from sending PoS chain to receiving PoW chain:
1. Burn on sending chain
2. Make withdrawal request to validators with proof of burn
3. Validators signs on the withdrawal request
4. Output on receiving chain gets unlocked if signatures with 2/3rds of stake are shown

I hope that I have convinced you that there is counterparty risk in moving assets from a PoW chain to a sidechain with less hashrate, or a PoS chain.

There may be feature tradeoffs which justify that move, but the extra risk must be part of your security model.

![](/assets/images/cy19/cy19q3m7/gk-15.png){: .align-center}

What makes Layer 2 special?

L2 security == L1 security

A L1 smart contract acts as an escrow.
Unlocking the assets relies on:
1. Playing a fixed duration game where honest players are guaranteed to win, OR
2. Cryptographically proving ownership with a ZKP.

In detail:
Fraud proofs:

Client side validation with an L1 smart contract as adjudicator. Withdrawal requests take time T, after which you can unlock the claimed asset. If another user comes online and submits a fraud proof, the request is cancelled. (add slashing for incentives).
Assumptions: user comes online, L1 is not congested

Example: Lightning Network, Plasma, State Channels

![](/assets/images/cy19/cy19q3m7/gk-16.png){: .align-center}
![](/assets/images/cy19/cy19q3m7/gk-17.png){: .align-center}


Validity Proofs:

- L1 smart contract stores hash of state.
- Aggregator gathers state updates, generates & submits ZKP.
- Update contract hash If proof is valid.
- Supports instant withdrawals
- Has no liveness assumption
Assumptions: fancy crypto doesn't break, data availability (sort of)

Examples: ZkRollup, StarkDEX, Loopring

![](/assets/images/cy19/cy19q3m7/gk-18.png){: .align-center}

The above was a quick summary of L2 techniques. The biggest issue with L2 that's not state channels is the data availability problem, but that's a separate discussion.

More about Fraud vs Validity Proofs in [@StarkWareLtd](https://twitter.com/StarkWareLtd) 's blog post:
![](/assets/images/cy19/cy19q3m7/gk-19.png){: .align-center}
[**Validity Proofs vs. Fraud Proofs - StarkWare - Medium** Validity Proofs and Fraud proofs are both used in different L2 scalability solutions. In this post we analyze and compare them. <small>https://medium.com/starkware/validity-proofs-vs-fraud-proofs-4ef8b4d3d87a</small>](https://medium.com/starkware/validity-proofs-vs-fraud-proofs-4ef8b4d3d87a)

This was my longest thread! I hope I got my point across, and maybe you, dear reader, are now less confused.

I am considering doing "Drivechains & Statechains are not Layer 2" & "Plasma & Rollup is Layer 2" threads, let me know on your thoughts.

{fin}
