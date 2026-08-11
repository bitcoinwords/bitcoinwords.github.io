---
title: "ELI5: Utreexo"
permalink: "/eli5-utreexo"

author: calvinkim

tags:
  - Calvin Kim
  - 2020 Q2
  - Politics
  - Technology
  - Security

excerpt: ELI5: Utreexo. Posted April 12, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [ELI5: Utreexo](https://medium.com/@kcalvinalvinn/eli5-utreexo-a-scaling-solution-9531aee3d7ba)
### By Calvin Kim
### Posted April 12, 2020

## ELI5: Utreexo — A scaling solution

About me: I’ve been actively contributing to the Utreexo implementation for the past 7 months and have been actively looking into Bitcoin and surrounding tech for the past 2 years as a co-organizer for the [Seoul Bitcoin Meetup](http://meetup.com/seoulbitcoin).

Utreexo is a [hash accumulator](https://en.wikipedia.org/wiki/Accumulator_(cryptography)) for Bitcoin, proposed by Tadge Dryja, the co-author of the [Lightning Network paper](https://lightning.network/lightning-network-paper.pdf). It introduces the following trade-offs.

## Pros & Cons

### 4 huge benefits to Bitcoin:

1. A new full node mode in a few kilobytes that syncs as fast as an ssd on an hdd.
2. Allows for parallelization of the initial block download.
3. Strengthens the security of Bitcoin by allowing consensus to be independent of the database implementation (the [current one](https://github.com/google/leveldb) in usage is made by Google).
4. No forks needed to bring Utreexo to Bitcoin.

### 2 main downsides:

1. Around 20% more bandwidth usage for the initial block download.
2. Additional storage requirements for Utreexo archival nodes.

## How it works

*Quick Overview: In Utreexo, a full node has the ability to keep only one hash per block, vs a traditional pruned full node where you have to keep all the UTXOs per block.*

To understand Utreexo, it is important that we take a look at how hash trees work. We’ll look at Merkle trees since it’s used in Bitcoin.

A Merkle tree with 8 leaves would look like this:

![](/assets/images/2020/m4/eli5-utreexo1.png)

*A typical Merkle tree*

Every number in this tree represents a [hash](https://en.bitcoin.it/wiki/Hash).

All the numbers in the bottom-most row, in Bitcoin, would be a [TXID](https://bitcoin.org/en/glossary/txid). 08 would be the result of concatenating and hashing of 00 and 01. 13 would be the result of concatenating and hashing of 10 and 11.

Currently in Bitcoin, the Merkle tree is used for generating the merkle root in the [block header](https://bitcoin.org/en/glossary/block-header). Utreexo takes this Merkle Tree concept and applies it to the UTXOs. It is important to note that Utreexo doesn’t replace the Merkle tree in the block header.

Currently, as a Bitcoin full node, you must store all the UTXOs that are existent. In Utreexo, you can be a full node and **only**store the root of the UTXOs. The tree would look like this:

![](/assets/images/2020/m4/eli5-utreexo2.png)

*Utreexo tree with just the root. Note that all the other hashes are deleted.*

All the other hashes from 00 to 13 are thrown away after validation and only 14, the root, is kept.

If a user wants to spend UTXO 07, they would have to prove to you that the transaction exists. This would be done by providing: 06, 07, 10, 12. Then the validating node would make a separate tree with the received hashes:

![](/assets/images/2020/m4/eli5-utreexo3.png)

*Tree for verifying. Note how the root can be calculated from this tree*

The empty spaces 11, 13, and 14 can be calculated by the verifying node. If this tree’s 14, the root, matches the one we stored, we can say that the transaction exists.

Utreexo is a bit more complicated and is different in how it works from this example, but this is a quick rundown of its concept and how you can only store one hash instead of all the hashes and still be a full node.

## The Good

### **1.** A full node in a few kilobytes that syncs as fast as an ssd on a hdd

### Full node in a few kilobytes

Currently, there are two full node types: Archival and pruned. In a pruned node, the user only keeps the unspent transaction outputs (aka UTXO). Utreexo allows for another full node mode called the **Compact State Node** (or CSN) in which we only store roots and wallet information. This enables a full node to be a less than a kilobyte in data vs the current state where the user has to store a couple of gigabytes of data.

This ability to **only** store UTXOs that belong to the user becomes more important as the adoption of Bitcoin increases. With one user needing at least one UTXO (and much more for privacy reasons), it will result in the **increase** of UTXOs. We can clearly see this growth of UTXOs from the below chart.

![](/assets/images/2020/m4/eli5-utreexo4.png)

*UTXO count. Excludes OP_RETURNs*

Because of this, the storage requirement for a pruned node **will** grow, increasing the minimum storage requirement for a Bitcoin full node. Utreexo thwarts this by allowing a user to prune the UTXOs that doesn’t belong to them.

### Initial block download as fast as an ssd on a hdd

Because a Compact State Nodes (CSN) can represent the entire Utreexo state in less than a kilobyte, there is no need to query the disk during the initial block download. This allows for the initial block download to happen **solely** **on RAM,**allowing for an hdd node to sync as fast as an ssd node.

### 2. Allows for the parallelization of the initial block download

UTXO snapshotting is saving the state of all the UTXOs at a particular block height. One potential use case for this is the [assumeUTXO](https://github.com/bitcoin/bitcoin/issues/15605) project, which allows blockchain syncing from the snapshotted height. The main hurdle for snapshotting is that the size of this snapshot is fairly big at it currently being around 5GB. The size of a snapshot will grow as the state above in Advantage 1. With Utreexo, this is possible with **less than a kilobyte** **in the worst case scenario**¹ (best case is around 100 bytes). UTXO snapshotting with Utreexo is so easy that the [ZKvM](https://medium.com/stellar-developers-blog/zkvm-a-new-design-for-fast-confidential-smart-contracts-d1122890d9ae) project has already [implemented](https://github.com/stellar/slingshot/blob/c0d0cdc927fa0f3a5a9b175a844a6f87bf3a1609/zkvm/docs/zkvm-blockchain.md) Utreexo and is using it for saving the blockchain state by including the Utreexo tree roots in the block header.

With snapshots being so cheap, it is feasible to have a snapshot at **every block height**. With this, future implementations of the blockchain sync can be done in parallel, meaning that one computer (or cpu core) can sync from block height 0 to 300,000 and another can sync from block height 300,001 to 600,000. With CPU optimizations now focused on [core count](https://www.tomshardware.com/news/amd-cto-mark-papermaster-more-cores-coming-in-the-era-of-a-slowed-moores-law) rather than [clock speed](https://software.intel.com/en-us/blogs/2014/02/19/why-has-cpu-frequency-ceased-to-grow) and the emergence of [GPGPU](https://en.wikipedia.org/wiki/General-purpose_computing_on_graphics_processing_units), this asynchronous block sync will help in further reducing the time needed to start up a Bitcoin Full node.

### 3. Utreexo strengthens the security of Bitcoin

### Allows consensus code to be separated from the database

The [libconsensus](https://bitcoincore.org/en/meetings/2016/10/20/) project was aimed at separating the consensus code from Bitcoin Core so that:

1. Non-consensus code can be changed without fear of breaking consensus.
2. Allow for one consensus API across different Bitcoin implementations.

It was ultimately abandoned since it was very difficult for the database (leveldb) to be separated from the consensus code. This is a hugely important problem to solve, [as in 2013](https://blog.bitmex.com/bitcoins-consensus-forks/), Bitcoin Core moved away from Berkeley DB to levelDB and suffered an unintended temporary hardfork, an unintended temporary softfork, and a hardfork (BIP50).

Currently, consensus is dependent on levelDB functioning correctly as you need to fetch the stored transaction. This means if levelDB is not functioning correctly, there can be a fork vs another client that is using a different database.

With Utreexo, you can validate an incoming transaction or block against the Utreexo tree without needing the database. The existence of a UTXO that the incoming transaction is spending would be checked upon with the included proofs.

### 4. No forks needed

The [RSA accumulator](https://eprint.iacr.org/2018/1188.pdf), proposed by Boneh et al. is more efficient in size vs Utreexo. However, the implementation of this would have to be done with a soft fork. With a conservative system like Bitcoin where even soft forks are done with extreme caution, these types of accumulators are very hard to implement into Bitcoin. **Utreexo doesn’t require any forks**. Users just have to opt into using Utreexo by running Utreexo nodes.

## The Bad

### 1. Needs Around 20% more bandwidth

In a hypothetical situation in which one is syncing a bitcoin node with a really beefy computer, but lives in the middle of nowhere with very small bandwidth, Utreexo is gonna hurt, not help. The aforementioned proofs would have to be sent over along with the TXO, leading to around 20% more data to download from a peer.

Utreexo can be seen as a trade-off between bandwidth and storage requirements in this sense. If you think the price for storage (hdd, ssd) is a bigger hurdle compared to internet speed (and cost), Utreexo helps with decentralization efforts. If you think internet speed is a bigger hurdle, Utreexo hurts decentralization efforts.

### **2.** Additional storage requirement for an Utreexo archival node

Utreexo archival nodes are the current Bitcoin archival nodes that store the aforementioned proofs that Utreexo nodes require.

Utreexo archival nodes store:

1. All blocks starting from genesis
2. All proofs starting from genesis

Because of #2, this will put additional storage burden on archival nodes. If an Utreexo archival node stores all proofs for every block, this will be around 100% extra data to store.

However, this can be improved upon by not storing proofs for every block. One can store proofs for every odd block and “resync” if a node requests for proofs from an even block. For example, if proofs for block 566 is requested, the Utreexo archival node would:

1. Retrieve block 566.
2. Retrieve Utreexo tree that was formed at block 565.
3. Apply the transactions from block 566 to the Utreexo tree, re-generating the proofs.
4. Send out generated proofs to the node that requested it.

This could be taken even further and one can store proofs for every 10 blocks and so on, further lessening the storage burden.

Ultimately, a user can choose their own trade-off between cpu usage and storage. If a user has access to cheap data storage, they can choose to store all the proofs for all blocks. If a user has limited storage but has cpu time to spare, they can choose to store less and compute more.

## Conclusion

Overall, Utreexo represents some trade-offs like any other system. I believe that Utreexo will aid in decentralization of Bitcoin by giving users the option to pick what trade-offs fit best for themselves.

An implementation is in active development at github.com/mit-dci/utreexo. Any contribution is greatly appreciated :)

Many thanks to [Tadge Dryja](http://twitter.com/tdryja), [Ruben Somsen](http://twitter.com/SomsenRuben), [Paul Grau](http://twitter.com/graycoding), and [Janus Troelsen](http://twitter.com/ysangkok) for reviewing this article.

### Additional Resources

*In order of least technical to most technical*

[What Bitcoin Did podcast interview with Tadge Dryja](https://www.whatbitcoindid.com/podcast/tadge-dryja-on-scaling-bitcoin-with-utreexo)

[MIT DCI grey mirror podcast with Tadge Dryja](https://medium.com/mit-media-lab-digital-currency-initiative/grey-mirror-1-tadge-dryja-digital-currency-initiative-utreexo-and-bootstrapping-bitcoin-upgrades-51975411002)

[Bitcoin Magazine article by Ellie Frost and Aaron van Wirdum](https://bitcoinmagazine.com/articles/bitcoins-growing-utxo-problem-and-how-utreexo-can-help-solve-it)

[Bitcoin Edge talk by Tadge Dryja](https://www.youtube.com/watch?v=xlKQP9J88uA)

[Core Dev meeting transcript](https://diyhpl.us/wiki/transcripts/bitcoin-core-dev-tech/2019-06-06-utreexo/)

[MIT Bitcoin Expo Utreexo introduction by Tadge Dryja](https://www.youtube.com/watch?v=edRun-6ubCc)

[Original Utreexo paper by Tadge Dryja](https://eprint.iacr.org/2019/611.pdf)

[Reference Implementation (Golang)](http://github.com/mit-dci/utreexo)

### Footnote

¹ In Utreexo, you have to keep multiple roots at times. Some block heights have less roots to keep vs others. This is explained in more detail in the [Utreexo paper](https://eprint.iacr.org/2019/611.pdf) as well as the [MIT Bitcoin Expo Utreexo introduction video](https://www.youtube.com/watch?v=edRun-6ubCc).

***

{% include signup.md %}
