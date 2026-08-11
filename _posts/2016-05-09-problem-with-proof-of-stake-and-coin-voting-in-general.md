---
title: "Problem with Proof of Stake and “coin voting” in general"
permalink: "/problem-with-proof-of-stake-and-coin-voting-in-general"

author: olegandreev

tags:
  - Oleg Andreev
  - 2016 Q2
  - Proof of Stake
  - Governance
  - Criticism

excerpt: Problem with Proof of Stake and “coin voting” in general. Posted May 9, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Problem with Proof of Stake and “coin voting” in general](https://blog.oleganza.com/post/144087873288/problem-with-proof-of-stake-and-coin-voting-in)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted May 9, 2016

The problem with “voting by coins” is that most coins do not vote. This leaves a small fraction of UTXO to actually vote which is not representative and highly volatile since anyone risking to use idle keys to a large stash of coins can dramatically affect the voting outcome.

Most coins are locked up well “under matress” with multisig, time locks and possibly even with HSM-controlled keys. Also, pubkeys to long-term stashes do not want to be exposed from under their hashes in order to be better protected against a QC development in the long term.

In other words, most coins that matter, cannot and will not vote.

This leaves only the least important coins to perform voting. Obviously, the result of such voting will be worthless.

UPDATE: it is possible that people annotate output scripts with a dummy “voting hash” that commits to a separate pubkey, intended only for voting and stored elsewhere. But then security of the voting keys is not equivalent to the security of bitcoin keys which is what we want to begin with: that voters perfectly map to actual bitcoin holders.

***

{% include signup.md %}
