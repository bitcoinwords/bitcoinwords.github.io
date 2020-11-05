---
title: "SNARKs and the future of blockchains"
permalink: "/snarks-and-the-future-of-blockchain"

author: rubensomsen

tags:
  - Ruben Somsen
  - 2020 Q4
  - Technology
  - SNARKs
  - Scaling

excerpt: Ruben Somsen explains what SNARKs can and can't do for blockchain. Posted October 3, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [SNARKs and the future of blockchains](https://medium.com/@RubenSomsen/snarks-and-the-future-of-blockchains-55b82012452b)
### By [Ruben Somsen](https://twitter.com/SomsenRuben)
### Posted October 3, 2020

SNARKs are often seen as a magical panacea to “solve” scaling. While SNARKs can provide incredible benefits, the limitations need to be acknowledged as well — SNARKs can’t solve the existing bandwidth constraints that blockchains are facing today.

This article is meant to demystify SNARKs by giving a (relatively) simple overview of what they can and can’t do for blockchains. We’ll look at how its functionality in relation to blockchains can be concisely summarized as Non-Interactive Witness Aggregation (NIWA). If you understand how Bitcoin works, you’ll be able to understand this article.

It should be noted that SNARKs are still very much an area of active research. Many SNARK variants either aren’t efficient enough to prove complex statements, have proof sizes that are impractically large, or require a trusted setup. That said, a lot of progress has been made over the years, and it’s expected that we’ll continue to see improvements in the coming decade. This article is written in anticipation of such improvements, even if it may not be practical today.

## What is a SNARK?

A SNARK is a construction that allows you to efficiently validate a result, given a rule set and a starting point. The inputs that led to the result are not revealed (“zero knowledge”). Confused already? This simple chess example will explain.

**Chess example**

\- Rules: The chess rule set  
\- Start: Starting position A of the board  
\- Result: New position B of the board

The regular way of proving that the game validly transitioned from position A to B is to simply reveal all the moves and checking whether they were valid. SNARKs can do the same thing, but better:

\- The set of moves does not have to be revealed (private, less data)  
\- Verification is more computationally efficient

There is one caveat — SNARKs tend to be computationally expensive to create. This can however still be worthwhile in systems where many people wish to validate the same result, such as blockchains. Only one person needs to put in the effort to create the SNARK, increasing verification efficiency for everyone.

**Blockchain example**

\- Rules: The full node software  
\- Start: The block header & UTXO set hash at time A  
\- Result: The block header & UTXO set at time B

Similar to our chess example, the regular way of validating the transition would be to start with the UTXO set (all unspent transactions) at time A, receive all the blocks, and update the UTXO set all the way until we reach time B. With a SNARK, none of this data would be needed to prove validity. In fact, if time A is set to the genesis block (empty UTXO set) and time B is set to now, then the entire chain can be validated without receiving any of the historic data.

It’s important to note that for time B the entire UTXO set is required, as opposed to just the UTXO set hash. While this data is not strictly required for proving validity, we also care about _availability_. If all you had was the UTXO set hash, then while you know a valid state exists, you wouldn’t actually know what that state is. This would mean you can’t spend any coins, because you don’t have the data that allows you to prove that a specific UTXO is part of the set. In the chess analogy, you would have a hash of the new board position, but don’t actually know what that position is, so you can’t continue to play the game.

Note that whoever made the SNARK (presumably miners) _would_ have this data (as it’s needed to create the SNARK in the first place), but they could potentially choose to withhold it from you.

## The SNARK blockchain

In order to guarantee that everyone can spend their coins, all the data that’s needed to update the UTXO set _must_ be communicated with each block. You’ll need to know which UTXOs were spent (inputs) and which were newly added (outputs). This is so-called non-witness data.

The validity of the transition can be verified by a single SNARK, replacing all witness data (scripts, signatures), and taking up almost no bandwidth. The relationship between inputs and outputs would not be apparent — a block would look like one big coinjoin transaction. The bulk of the data would be non-witness data.

Contrary to popular belief, SNARKs can’t solve the fundamental issues behind light clients or non-federated sidechains, because non-witness data must _always_ be downloaded. Full nodes have the crucial ability to reject a valid SNARK if non-witness data is missing, whereas if a light client neglected to download non-witness data, it could mistakenly consider a chain with missing data valid. If even a single piece of non-witness data is withheld by miners, nobody would be able to create new blocks with valid SNARKs, except for those specific miners, turning it into a permissioned system.

## SNARKs consume witnesses

SNARKs for blockchains can perhaps best be summarized as enabling the following function:

> Non-Interactive Witness Aggregation (NIWA)

I use the term “witness” here liberally. In Bitcoin, the witness is the data inside a transaction that proves whether a specific UTXO is allowed to be created. But over time, this UTXO (non-witness data) becomes a witness of its own when it gets spent. When 1 BTC gets sent from Alice to Bob to Carol, Bob’s transaction is a witness to the transfer from Alice to Carol. In the same vein, all spent transactions since genesis are witnesses to the current UTXO set.

Also note that a SNARK is in itself a witness. If each individual transaction is validated by a SNARK, we can also NIWA these SNARKs into a single SNARK per block. And because outputs become witnesses the moment they are spent, we can even take unconfirmed but already spent outputs in the mempool and aggregate them as well. Alice to Bob to Carol becomes Alice to Carol, achieving non-interactive [transaction cut-through](https://bitcointalk.org/index.php?topic=281848.0). This can be especially powerful when a single UTXO with many branching off-chain transactions is forced on-chain, such as may be the case for Lightning Channel factories.

## In short

We’ve summarized the core functionality of SNARKs for blockchains with NIWA. Any witness data can be non-interactively aggregated by a SNARK. The non-witness data that remains is a direct reflection of the state of the system — the UTXO set. While SNARKs can achieve amazing things such as allowing you to catch up from genesis by merely downloading the UTXO set and a single SNARK, or non-interactively aggregating sequences of unconfirmed transactions into a single transaction, there still remains a need to publish all non-witness data for each new block in order to allow all nodes to update their UTXO set. The fundamental bandwidth constraints of blockchains are therefore not solved by SNARKs.

— [Ruben Somsen](https://twitter.com/SomsenRuben)

_Thanks to_ [_Sanket Kanjalkar_](https://twitter.com/sanket1729) _for the helpful discussion and comments._

![](/assets/images/2020/m10/rs1.jpeg)
*NIWA in action. SNARKs consume witnesses and are also a witness of their own. SNARK eat SNARK.*

***

{% include signup.md %}