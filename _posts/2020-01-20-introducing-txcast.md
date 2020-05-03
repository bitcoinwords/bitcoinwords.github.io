---
title: "Introducing txCast"
permalink: "/introducing-txcast" 

author: SixOneZeroTwo

tags:
  - SixOneZeroTwo
  - 2020 Q1
  - Technology
  - Privacy
  - Transmission
  - Transactions
  - txCast


excerpt: 6102 introduces a novel approach to broadcasting Bitcoin transactions in a private manner. Posted January 20, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Introducing txCast](https://medium.com/@6102bitcoin/introducing-txcast-2bf2d8033002)
### By [6102](https://twitter.com/6102bitcoin)
### Posted January 20, 2020

Randomised Bitcoin (testnet) transaction broadcasting to break timing analysis. Visit [txCast.org](https://txcast.org/) for more.

## Introduction

When attempting to use Bitcoin privately we often focus on the method of receiving relevant bitcoin blocks in a private way; Either by using a full node and downloading all blocks, or using bip158 block filters and downloading individual relevant blocks from random nodes over fresh tor circuits.

What is less often considered is the manner in which we **broadcast transactions**, and the privacy implications associated with each method.

Methods include;

*   Broadcasting from your own full node to your peers (clearnet / tor)
*   Broadcasting via a 3rd party node via a website / api (clearnet / tor)

We are concerned with the leakage of two pieces of data:

## Data Leak 1: Association of transactions & your IP

If you link your transaction(s) with your IP then you have undone, or at least undermined your previous work to improve your privacy using bitcoin.

### _Adversary 1: Malicious Node Peer_

In Bitcoin Core, random delays are added before forwarding transactions in order to obscure the transaction source. Specifically, all transactions are delayed until the next broadcast event, which occurs at Poisson-distributed times_ \[Pieter Wuille: _[_1_](https://bitcoin.stackexchange.com/a/76799)_, _[_2_](https://bitcoin.stackexchange.com/a/76799)_\]. _This makes it **difficult** for an individual malicious node peer to have any certainty regarding associating transactions & IP addresses.

### Adversary 2: Network Wide Sybil Attack

It is possible (and cheap) for an adversary to learn the structure of the Bitcoin network, and as a result, link transactions to IP addresses. [Dandelion](https://github.com/bitcoin/bips/blob/master/bip-0156.mediawiki) is a good potential solution to this problem, but it is not currently implemented.

If this attack is currently ongoing (we can’t know) we can mitigate by either broadcasting to new peers each time we send a transaction, or by broadcasting from the same 3rd party node which many other people use to broadcast. For the latter technique we must defend against the (above) malicious node peer scenario, and we can do this by connecting over a new tor circuit each time we broadcast.

## Data Leak 2: Association between transactions based on timing analysis

Separate to the details of how our transactions are broadcast is the issue of **when **they are broadcast / confirmed.

This is a particular issue for mixed coins in a hot wallet (used for mixing for example) which a user later decides to send to a hardware wallet for more secure storage. In this scenario it is likely that a user will want to deal with all their utxos in one session — which makes clustering easy to detect.

If a bunch of similar utxos (for example bech32 CoinJoin outputs) which have been dormant for a number of months are all spent in the same block it is possible that a blockchain analyst could cluster the utxos based on timing analysis.

_Note that this does not require there to be address reuse or coin merging._

## A prototype solution: [txCast](https://github.com/6102bitcoin/txCast)

For the purpose of getting the ball rolling I have developed a python script which uses blockstream’s API (accessed via tor) to broadcast transactions. The user inputs the signed transactions to broadcast & the maximum delay they can accommodate (minutes, hours, days) and the script does the rest.

It is not ready for mainnet use yet, I will make an announcement when it is. If you are interested in trying it out and improving it please visit the repository:

> [Try it on Testnet: https://github.com/6102bitcoin/txCast](https://github.com/6102bitcoin/txCast)

I have little coding experience so I would appreciate any feedback / suggestions that you can offer.

![](/assets/images/2020/m1/6102-1.png)

#### 23

*   [Bitcoin](https://medium.com/tag/bitcoin)
*   [Privacy](https://medium.com/tag/privacy)

***

{% include signup.md %}