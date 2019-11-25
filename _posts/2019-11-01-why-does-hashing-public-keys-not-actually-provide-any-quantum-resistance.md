---
title: "Why does hashing public keys not actually provide any quantum resistance?"
permalink: "/why-does-hashing-public-keys-not-actually-provide-any-quantum-resistance" 

author: andrewchow

tags:
  - Andrew Chow
  - CY19 Q4
  - Quantum Resistance
  - Technology

excerpt: Andrew Chow explains how and why public key quantum resistance is not something to worry about. Posted October 16, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Why does hashing public keys not actually provide any quantum resistance?](https://bitcoin.stackexchange.com/questions/91049/why-does-hashing-public-keys-not-actually-provide-any-quantum-resistance)
### By [Andrew Chow](https://bitcoin.stackexchange.com/users/48884/andrew-chow)
### Posted October 16, 2019

## In the discussions about taproot, it was mentioned that outputs will include the public key directly instead of hashing them. It is stated that, currently, hashing does not really provide quantum resistance. Why is that?

## Answer:
Although hashing a public key by itself does provide quantum resistance, this is really only when it is considered by itself in a vacuum. Unfortunately, public key hashes do not exist in a vacuum and there are many other things in Bitcoin that need to be considered.

Firstly, if public keys were hashed, the funds are only protected before they are spent. As soon as a P2PKH or P2WPKH output is spent, the public key is exposed. Whilst the transaction is unconfirmed, an attacker with a fast enough quantum computer could compute the private key and create a conflicting transaction which sends the funds to himself instead of the intended recipient.

Furthermore, if that attacker is a miner, they could do this with every single transaction and simply refuse to mine transactions that don't send the coins to himself.

While this is a problem, people often argue that it's better than someone just spending the Bitcoin outright because they have the public key from the blockchain. While that is true, there are an extremely large number of outputs with exposed public keys.

Over 5.5 Million Bitcoin are in outputs with exposed public keys, either because they are P2PK outputs, or because users are reusing addresses and thus public keys are exposed in other transactions. So if a quantum computer existed that could produce the private key for a public key in a reasonable amount of time, the attacker would be able to steal so much Bitcoin that they would decimate the Bitcoin economy and Bitcoin would become worthless.

So while your particular outputs may be protected by hashes, the value of those outputs would be 0 as millions of Bitcoin are stolen. All that the hashes really do is provide a false sense of security.

Then there are issues with tooling and wallet software the simply expose public keys in other ways than just in transactions and in the blockchain. No existing tools treat public keys as private information; there's no reason they should.

Many wallets send the parent extended public keys to a server so that the server can watch for transactions and send that data back to the client. Anyone who uses such a wallet, even temporarily, exposes their parent public key to a service provider. That provider could then compute the private keys to the public keys they have, derive all of the child keys, and steal all of the Bitcoin associated with anyone who has used their wallet.

Additional issues exist with complex scripts and contracts involving public keys. These scripts, such as multisigs, do not hash the public keys. Furthermore, these contracts typically exist because not all parties necessarily trust each other; one of them could be malicious. In such cases, a malicious participant in the contract would know the public keys involved (by virtue of knowing the script) and be able to steal the Bitcoin associated with those outputs. Existing public key hashes do not protect against this.

So overall, there are tons of ways that public keys are already exposed outside of transactions. These all would allow different kinds of attackers to steal millions of Bitcoin thereby causing the value of Bitcoin to go to 0, which renders any Bitcoin protected by public key hashes to be worthless anyways. Furthermore, users are probably exposing their public keys in unintended ways due to the software that they are using. So using public key hashes only serves to provide a false sense of security, while also increasing the size of transactions. In general, it is not worth the extra size.

Lastly, it is possible to do a transition to post quantum cryptography if it is found that a QC exists which can break ECDLP. If detected in time but still too late to do a proper upgrade, all use of signature algorithms relying on ECDLP (i.e. ECDSA and Schnorr) could be soft forked out thereby locking all coins. The coins could then be spent by providing a Zero Knowledge Proof of some non-exposed or quantum resistant information that indicates ownership of the private keys for the public key.

For example, users could provide a proof that they have the BIP 32 seed that was used to derive the private key for the given public key. Since it is a Zero-Knowledge Proof, the seed itself is not exposed (note that the seed is not part of a public-private keypair so there is no public component that is shared). Since most wallets use BIP 32, this should be sufficient. There may be other ways to prove ownership without risking coins that have not been thought of yet.

And of course, this all assumes that a quantum computer capable of computing the private key for a public key appears without the public being aware of the technology being close to existing. What is likely to happen is that the progression of quantum computers will be observed, and, at some point prior to them being powerful enough to break ECDLP, Bitcoin will soft fork in a Quantum resistant signature algorithm. Eventually, signatures relying on ECDLP will be removed. And all of that will occur before quantum computers truly becomes a thread. So in that scenario, hashing public keys provides no help anyways.

***

{% include signup.md %}