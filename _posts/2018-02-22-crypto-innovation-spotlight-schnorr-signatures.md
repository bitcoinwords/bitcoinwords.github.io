---
title: "Crypto Innovation Spotlight: Schnorr Signatures"
permalink: "/crypto-innovation-spotlight-schnorr-signatures" 

author: spencerbogart

tags:
  - Spencer Bogart
  - CY18 Q1
  - Technology
  - Schnorr Signatures
  - Scaling

excerpt: Spencer Bogart highlights some key features in Schnorr Signatures. Posted February 22, 2018.

defaults:
  - scope:
      type: posts
---

# Crypto Innovation Spotlight: Schnorr Signatures
### By [Spencer Bogart](https://twitter.com/CremeDeLaCrypto)
### Posted February 22, 2018

![](/assets/images/cy18/cy18q1m2/sb-1.png){: .align-center}
_**Amid the commotion and flurry of excitement as crypto surged into mainstream, the significant implications of many real fundamental innovations being developed have been drowned out by the din of hand-wavy, hyperbolic claims. In this_ **_"Crypto Innovation Spotlight"_** _series, I hope to shine a light on fundamental innovations that are driving our industry forward.**_

### Schnorr — What is it?
Schnorr is a digital signature algorithm. A digital signature algorithm, among other things, determines the relationship between public keys and private keys ("address" and "password") — which means the choice has significant implications for security.

In addition, because digital signatures are a significant portion of all the data that comprises a transaction, the choice of digital signature algorithm has significant implications for privacy and efficiency.

If adopted, Schnorr would be an alternative to Bitcoin's current ECDSA (Elliptic Curve Digital Signature Algorithm).

### What does it do?
To start, Schnorr signatures are appealing because they're easy to compute and considered highly secure. However, the main benefits of Schnorr signatures actually derive from their aggregation capabilities.

### What does "aggregation capabilities" actually mean? What are we aggregating?
To put it simply, Schnorr signatures can aggregate multiple distinct signature into a single signature. This signature aggregation capability is particularly valuable in light of the amount of space that is consumed by signature data in a Bitcoin transaction — this is depicted visually in Figures 1 & 2, below:

![](/assets/images/cy18/cy18q1m2/sb-2.png){: .align-center}
**Figure 1:** A standard Bitcoin transaction. Note how much space is consumed by signature data (highlighted in yellow) **_Source:_** _Class materials from Jimmy Song's_ [_Programming Blockchain Seminar_](http://programmingblockchain.com/)

Even worse, this signature data grows in size linearly with the number of signers in a multi-signature transaction. For example, the yellow signature area in the figure above nearly doubles when we go from a standard transaction (1-of-1) to a 2-of-2 multi-signature transaction, as illustrated in Figure 2 below.

![](/assets/images/cy18/cy18q1m2/sb-3.png){: .align-center}
**Figure 2:** A multi-signature Bitcoin transaction — signature data highlighted in yellow. **_Source:_** _Class materials from Jimmy Song's_ [_Programming Blockchain Seminar_](http://programmingblockchain.com/)

Schnorr signature aggregation is potentially helpful in a few different ways that each has derivative benefits for the Bitcoin network and its users.

First, the ability to aggregate multiple signatures into a single signature is particularly valuable for "multi-signature transactions" — that is, Bitcoin transactions that require multiple signatures in order to be considered valid by the network. In Bitcoin's current structure, these "multi-signature" transactions are much larger than standard single-signature transactions — which has negative implications for efficiency and privacy (more on that later).

![](/assets/images/cy18/cy18q1m2/sb-4.png){: .align-center}

Second, it appears it's also possible to extend to concept of Schnorr signature aggregation — with a scheme known as MuSig — to aggregate the signatures pertaining to multiple UTXOs into a single signature. Conceptually, it's the same process as the example above but instead of just aggregating multiple-signatures that are required to spend a _single_ UTXO, we extend the concept to also consolidate signatures across _multiple_ UTXOs.

The end result is that while the former example enables us to achieve 1 signature _per UTXO_ (even if the UTXO is technically constrained by multiple signatures), the latter example helps us to achieve 1 signature _per transaction_ (which in itself could consume multiple UTXOs as inputs). This would mean a drastic reduction in the amount of data that needs to be processed and stored across the Bitcoin network (the benefits of which are discussed in more detail below).

### Why do we care? What are the advantages and economic implications?
In short, these aggregation capabilities improve Bitcoin's efficiency and privacy.

In terms of **_efficiency_**, the big benefit is smaller transactions — which means lower storage and computation costs. Indeed, Schnorr multi-signature transactions are even more compact and efficient than single-signature transactions in Bitcoin today. That's important because it lowers transaction fees for users and minimizes resource requirements for network participants (e.g. full nodes, mining).

Also, because Schnorr multi-signature transactions are the same size and cost as non-multi-signature transactions, the adoption of Schnorr signatures should encourage an increasing variety — and perhaps complexity — of multi-signature transactions on the network. It's a win-win: Users can create more complex transaction arrangements without burdening the network or incurring additional costs.

In terms of **_privacy_**, the advantages of a Schnorr signatures (or a Schnorr-based scheme like MuSig) are two-fold. The first is that multi-signature transactions are indistinguishable from single-signature transactions. Second, an aggregated Schnorr multi-sig does not reveal the individual public key inputs (participants of the multi-sig contract).

Said differently, Schnorr signatures help us avoid leaking info about the public-key identities that are party to a multi-sig contract and even help us avoid revealing whether or not a transaction is multi-sig or not.

Lastly, Schnorr-based MuSig could also offer an indirect privacy advantage by improving the economics of multi-sig contracts: if we can aggregate signatures across multiple UTXOs, MuSig could incentivize the usage of privacy-enhancing functions such as "coinjoin". That is, with MuSig, users could realize lower transaction costs by aggregating their transactions with others (effectively sharing the cost of your transactions space with others) — which would improve network privacy as a whole.

Ultimately, I'm excited about the potential for Schnorr signatures in Bitcoin because they reduce the size of transactions (lower cost, less network overhead), minimize network resource demands (easier for people to verify transactions), and improve privacy.

### Key People & Resources
· [**Research paper**](https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/) "Simple Schnorr Multi-Signatures with Applications to Bitcoin" authored by Gregory Maxwell, Andrew Poelstra, Yannick Seurin, Pieter Wuille, Jan 1018

· Bitcoin.org [**blog post**](https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/) summarizing the benefits of Schnorr signatures.

### Acknowledgements
Thank you to Andrew Poelstra and Jimmy Song for generously reviewing earlier drafts and offering corrections.
