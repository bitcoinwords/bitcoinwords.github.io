---
title: "There is only one blockchain and it's called Bitcoin"
permalink: "/there-is-only-one-blockchain-and-its-called-bitcoin"

author: olegandreev

tags:
  - Oleg Andreev
  - 2014 Q4
  - Criticism
  - Technology

excerpt: There is only one blockchain and it's called Bitcoin. Posted December 3, 2014.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [There is only one blockchain and it's called Bitcoin](https://blog.oleganza.com/post/104274846653/there-is-only-one-blockchain-and-its-called)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted December 3, 2014

The purpose of the blockchain is to help those who are interested to continuously establish global consensus on an ever-growing dataset without trusting any authority and assuming presence of active attackers that may gain measurable advantage by manipulating that consensus.

Consensus is securely established because every updated version of the dataset has a sufficiently large proof of work attached to it. Contrary to a popular belief, this proof of work should not simply be marginally larger than any alternative version. Active attacker may not advertise their version equally to all nodes so you could comfortably choose the most difficult one. What we need from the proof of work is to be *infeasible to redo*. There should not be even a possibility for someone to build a secret facility that can redo the same amount of proof of work that was produced by all “honest” (i.e. open) participants.

Lets imagine I receive $1M on a Bitcoin address and wait 1 week for it to be buried under a 1-week worth amount of work. What we need is to make redoing this work cost more than $1M. The amount of work done in one week should really cost more than $1M. **In other words, for a blockchain to be actually secure, there must be a huge gap in cost between that blockchain and the next best competitor.** In addition, number 2 blockchain cannot be considered secure or valuable because it has a dramatically lower cost of attack and the very existence of number 1 shows how feasible that attack is.

Note that choosing an incompatible PoW algorithm does not change that. In a well-developed Bitcoin world where mining is done with highly-specialized hardware, mining algorithms do not matter. Both Bitcoin and your scrypt altcoin are measured in amount of bucks to be invested to rewrite their histories.

This gap between number 1 and number 2 keeps growing because of opportunity cost. Those who invest in mining have to invest 100% into the most potentially profitable blockchain. Those who speculatively invest in coins themselves have to invest in the most promising and most secure storage (i.e. blockchain), inviting more miners to make it even more secure and more speculative investors to make it more valuable.

In the end there could only be one blockchain worth talking about and so far it seems like Bitcoin is winning that title.

***

{% include signup.md %}
