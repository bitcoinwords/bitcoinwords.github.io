---
title: "Excited for Schnorr signatures"
permalink: "/excited-for-schnorr-signatures" 

author: murch

tags:
  - Murch
  - CY18 Q1
  - Schnorr Signatures
  - Technology

excerpt: Murch recaps the pending BIP technology, Schnorr Signatures. Posted February 3, 2018. 

defaults:
  - scope:
      type: posts
---

# [Excited for Schnorr signatures](https://hackernoon.com/excited-for-schnorr-signatures-a00ee467fc5f)
### By [Murch](https://twitter.com/murchandamus)
### Posted February 3, 2018

If you're keeping a finger on the pulse of [Bitcoin](https://hackernoon.com/tagged/bitcoin) development, you've probably already heard about Schnorr signatures and you probably won't find much new here. You might rather want to check out Pieter Wuille's recent [talk at BPASE18](https://www.youtube.com/watch?v=oTsjMz3DaLs), or Bryan Bishop's [compilation of transcripts of Schnorr signature talks](http://diyhpl.us/~bryan/papers2/bitcoin/bitcoin-tech-dev-talks-schnorr-signatures.2018-02-01.pdf) whom this article heavily leans on.

Bitcoin signatures are created using the Elliptic Curve Digital Signing Algorithm (ECDSA). Schnorr signatures are another form of digital signatures. The signatures are based on the same [security](https://hackernoon.com/tagged/security) assumptions as ECDSA and are compatible with the elliptic curve Bitcoin already uses (secp256k1). This means that Schnorr signatures can be created with the same private keys and are compatible with currently used key derivation schemes.

### **Schnorr signatures are smaller**
ECDSA signatures vary in size, but almost all come in at a length of 72 or 71 bytes. A small portion will turn out smaller with a theoretical minimum of 8 bytes. [h/t Greg Maxwell]

Schnorr signatures are more efficient and compact than ECDSA signatures. The maximum length of each signature is 64 bytes. [[via Harding]](https://bitcoin.stackexchange.com/q/34288/5406) Bitcoin blocks include thousands of signatures, and I estimate from the top of my head that signatures make up more than a third of the blockchain data. Simply by being more compact, Schnorr signatures would reduce the blockchain data footprint by a few percent.

### **Schnorr signatures allow for compact multi-signature...**
The multi-signature scheme in Bitcoin is straightforward but naïve. You first list the set of public keys of the authorized signers, and then provide a sufficient count of signatures by the former. E.g., in a 2-of-3 multi-signature transaction input, three public keys and two signatures are provided.

Schnorr signatures have a neat mathematical property that allows multiple signatures to be combined into a single signature. The combined signature has the size of a single signature, but provides the authorization of the original separate signatures.

This allows for a more compact multi-signature scheme, where you only list the authorized public keys and provide a single signature. This is even more efficient for bigger multi-signature transactions. For example, a 3-of-15 and a 10-of-15 transaction input could now have the same weight (if you don't care who signed).

### **...and aggregated signatures across a whole transaction!**
While multi-signature transactions make up a solid portion of the blockspace, the real breakthrough is that signatures can be aggregated across multiple inputs of a transaction. Instead of providing one (or multiple signatures) for each input, a transaction with Schnorr signatures can have **a single signature for all inputs**.

For example at BitGo, we use 2-of-3 multi-signature transactions. Every transaction input therefore has two signatures. As we're seeing low fee rates on the network, some of our customers have started consolidating funds from low-value UTXO. With the current signature scheme, a 2-of-3 multi-sig transaction with 200 inputs would need 400 signatures or about 28.5 kB of signature data. With Schnorr signatures the same transaction could be signed with a single 64-byte Schnorr signature.

In his [talk at BPASE18](https://www.youtube.com/watch?v=oTsjMz3DaLs), Pieter Wuille estimated that purely from aggregating signatures for each transaction and leaving everything else the same, the Bitcoin blockchain would be between 25% and 30% smaller.

### Scriptless Scripts, and... various black crypto magic
There is some interesting work by Andrew Poelstra lately which he calls "Scriptless Scripts" (see e.g. his talk at [Real World Crypto 2018](https://www.youtube.com/watch?v=ovCBT1gyk9c)). The idea is that you can express conditions in a smart contract by requiring certain signatures to be provided for the payout. By means of the above mentioned signature aggregation, this could be used to compactly encode smart contracts. The terms of the contract would be hidden from other users and only transparent to its participants, yet enforced by the whole Bitcoin network.

You may have heard about the recent cross-chain atomic swaps. The basic idea is that two payments on two different blockchains are linked in a way that they either both go through or neither. This can be used to decentrally trade cryptocurrencies.
Hereby, the traders first lock up funds in shared addresses on both chains, and then create two interdependent transactions. The second transaction depends on a hash preimage that is revealed by the first transaction. Either party can back out and wait for the lock to expire to reclaim their funds, but when the first transaction is executed, the other transaction becomes immediately valid.

By means of the same property that allows for the signature aggregation, all of the above cross-chain atomic swap can be expressed in a single Schnorr signature indistinguishable from a regular spending transaction.

### A BIP for Schnorr signatures is in the works
The introduction of Schnorr signatures into Bitcoin requires a new OP_CODE for signature verification. Luckily, Segwit gave us versioning for Bitcoin script, so support for Schnorr signatures can be activated with a soft fork. I hear that multiple Bitcoin Improvement Proposals are in the works and forthcoming shortly.
_Thanks to Pieter Wuille for review.
Edit: Corrected the length of ECDSA DER-encoded signatures._
