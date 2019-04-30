---
title: "How soft forks might work or fail"
permalink: "/how-soft-forks-might-work-or-fail" 

tags:
  - Tahas Blummer
  - CY19 Q2

excerpt: Tamas Blummer discusses soft fork mechanics. Posted April 17, 2019.

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

# How soft forks might work or fail
### By [Tamas Blummer](https://medium.com/@tamas.blummer)
### Posted April 17, 2019

Attempts to deploy a soft fork on the Bitcoin network might fail, and some will have to before Bitcoin ossifies.

I recently twitted about my anticipation of events as:

![](/assets/images/cy19/cy19q2m4/tamas-1.png){: .align-center}

This sparked some curiosity how I meant competition and rejection, so I wrote this longer explanation.

## What is a soft fork?

A soft fork is a change to network nodes such that they apply stricter rules to blocks that those that are already in effect on the network.

Nodes that do not apply the change will not technically recognize that a soft fork was deployed as blocks continue to obey all rules they know of.

## Can a soft fork split the chain?

As soon as a miner produces a block that violates the stricter rules, other miners are presented with a choice, they could either:

* ignore (orphan) the offending block, means supporting the soft fork
* build on top of the offending block, means rejecting the soft fork

The chain forks once a miner choses to ignore the offending block. There is no technical difference between a fork and a split, the later merely refers to a situation where miner work on both sides of the fork for a longer period.

Such a split would be technically a really messy one, since both sides would share coins in existence before the split and use the same communication network. There would be no guarantee that a pre-fork coin would be spent only on one side (no replay protection). An increasing and not obvious set of coins would become only valid on one side.

## How splits compete and eventually resolve

Forks that are rooted in a block that is not acceptable by the soft fork will not be automatically resolved by the most total work rule. The reason is that validating nodes that support the soft fork will not even see blocks that are successors of the offending block.

The split chain can proceed on both sides until some miner work on both. The proportion of mining power is technically irrelevant to their existence. Miners will however constantly re-evaluate the situation and may with time settle on only one side, which would resolve the split.

We have not yet seen a soft fork split as recent soft fork activation via UASF successfully moved miners in sync.

## A miner activated soft fork is unlikely

There are powerful arguments against supporting a soft fork by a miner

1. Avoid operational risk: A miner that does not know or care about the soft fork does not have to upgrade its systems and will reject the soft fork by just doing what it used to do.
2. Avoid financial risk: Supporting the soft fork means ignoring offending blocks, which comes with the risk that others that did not care to upgrade will build on the ignored block and thereby more likely win the race for most total work in the next round. A miner will therefore support the soft fork only if there are good reasons to assume that most other miner will also do so.
3. Avoid network disruption: An split is potentially disastrous to the value of the asset produced by the miner.

Above explains why the latest 'segwit' soft fork activation did not happen until miner were forced by UASF.

## How a user activated soft fork (UASF) works or fails.

A credible threat such as the one imposed by the famous UASF (BIP148) can push miner instantly to one side and thereby avoid a chaotic resolution of a temporary split. The threat of the first UASF was that validating nodes would stick to the side of the soft fork even if majority of miner would not apply BIP141 (segwit). Miner's new coins would not had been accepted by UASF nodes if they were mined on the other side of the fork. The first UASF threat worked so well that no miner created a block offending segwit rules, the upgrade was so seamless that some think it was not soft fork (event) at all.

Orchestrating such a credible threat will get harder as the network grows. The case supporting a soft work will be less convincing for a miner and at some point they will stop considering one, at latest after one that creates a split.

And then the soft fork window will close for ever, just like that of the hard forks is closing now with the demise of the Bitcoin XXX fork coins.
