---
title: "Crypto-incrementalism vs Crypto-anarchy"
permalink: "/crypto-incrementalism-vs-crypto-anarchy" 

tags:
  - Tony Sheng
  - CY18 Q3

excerpt: Tony Sheng believes all crypto projects fall into one of two camps, which he also believes can coexist. Posted July 2, 2018.

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      read_time: true
      comments: false
      share: true
      related: false
---

# [Crypto-incrementalism vs Crypto-anarchy](https://www.tonysheng.com/incremental-vs-anarchy)
### By [Tony Sheng](https://twitter.com/tonysheng)
### Posted July 2, 2018

A close friend of mine invests in crypto. He focuses on projects that either help with regulatory compliance or fiat inflows (e.g. institutional custody). He sees value in blockchain and the surrounding ecosystem not as an unstoppable force that tears down borders, undermines governments, and shepherds in an era of crypto-anarchy, but as nothing more than a new data structure with potentially disruptive use-cases.

Let's call this crypto-incrementalism.

My other friends want unstoppable, unseizable money that cripples legacy financial institutions; a transparent, uncensorable information infrastructure that precludes any abuses from states or corporations; true privacy and anonymity such that participants are completely unidentifiable by those that would seek to harm them; a society built on technologies unable to comply with authoritarian requests.

Let's call this the crypto-anarchy<sup>[1](https://www.tonysheng.com/incremental-vs-anarchy#fn:1)</sup> .

Crypto-incrementalists and the crypto-anarchists share strong convictions in the power of decentralization. Both can get excited about Satoshi's vision to improve on a financial system that relies "almost exclusively on financial institutions serving as trusted third parties to process electronic payments."<sup>[2](https://www.tonysheng.com/incremental-vs-anarchy#fn:2)</sup>

Nobody mourns the removal of the middle-man. It's a powerful starting point for crypto-incrementalists and crypto-anarchists alike.

However, these groups diverge quickly as we move from the abstract to the material. How should we handle a government's request to identify an individual using a cryptocurrency? How do we return assets stolen in a hack? How do we enforce legality for tokenized physical assets (e.g. real-estate)? Or tokenized securities?

## Crypto-incrementalism

Crypto-incrementalists think it's okay–even preferable–to design crypto systems able to comply with requests from governments and corporations. Assets stolen? Use a back-door to reverse the transactions. Need to enforce legality of tokenized securities? Design around the existing legal infrastructure so the legal system is the "source of truth." Here, the benefit of crypto is to reduce inefficiencies in existing systems by applying a new technology. Working with governments and corporations is the easiest way to drive that adoption.

Recent actions by the powers that govern EOS provide an instructive example. On June 22nd, the "EOS Core Arbitration Forum (ECAF)" asked the 21 EOS block producers (the 21 entities that decide what "truth" is on the chain) to freeze seven accounts, providing no explanation. The ECAF stated, "the logic and reasoning for this Order will be posted at a later date." Alarmingly, all 21 block producers complied.

![](/assets/images/cy18/cy18q3m7/ts-1.png){: .align-center}

Such a process gives EOS the flexibility to deal with malicious actors, but comes at the cost of potential abuses. It's not hard to imagine a scenario where hackers sent a similar decree to the block producers. Or for ECAF to ask the block producers to freeze accounts on behalf of a government.

This is a trade-off. Acceptance of these risks offers a way to incorporate blockchain into some very large industries such as enterprise blockchains, security tokens, tokenization of physical assets, and more. For these use cases, a centralized entity has authoritarian control of the protocol by design–it's the only way to comply with existing financial and legal systems. Debates around these use cases tend to reduce to this single design choice that is exciting to crypto-incrementalists and repulsive to crypto-anarchists.

## Crypto-anarchy


Crypto-anarchists want information infrastructures that are, by design, unable to comply with authoritarian requests. Assets stolen? Nobody has the power to reverse the transactions: best we can do is fork the protocol. Need to enforce legality of tokenized securities? Hard af and probably not worth working on. Want to identify an individual participant in the network? Sorry, that data does not exist. Any designs that make a protocol vulnerable to authoritarian control render said protocol useless. For crypto-anarchists, the success is binary: sufficient protections against centralized powers, or insufficient. Anything "in the middle" is insufficient.

Why require complete decentralization and privacy? The corner cases are unacceptable. Members of a persecuted minority could get their funds frozen, speech censored, identity deleted by an evil government. Even if the government couldn't directly freeze the funds (e.g. we're all using a Bitcoin), without sufficient privacy, they could identify the addresses belonging to members of the persecuted minority and take actions on them physically or through the ecosystem surrounding Bitcoin (e.g. retailers).

Use of popular decentralized networks are not yet sufficiently private. Torrent users will often receive cease-and-desists from their internet providers. Bitcoin users have been routinely identified for innocuous and criminal purposes. Users aren't sufficiently protected for two reasons: (1) privacy technology is not yet built into networks like Bitcoin, and (2) users are largely uneducated on privacy preservation, and unbeknowingly identify themselves with things like their IP address.

Is decentralization good enough? If Bitcoin cannot comply with an authoritarian request to seize funds (which it cannot), doesn't that satisfy the needs of crypto-anarchists? It's certainly good, and covers the majority of authoritarian requests, but does not protect users from e.g. physical violence. While a user can't have their funds seized at the protocol level, if their identity is exposed, a powerful entity could find them physically and coerce them.

Luckily, lots of exciting work is happening around privacy. There are privacy-forward cryptocurrencies like Zcash and Monero, projects like Enigma and Keep, and the big protocols like Bitcoin and Ethereum have plans to improve their privacy technology.

## Use cases


Here are some example implementations of the most commonly discussed use cases for crypto.

**Money**

* Incremental: a cryptocurrency that can, without the consent of the majority of the network, report the identities and behaviors of participants in the network to governments, freeze or seize balances, or change the "rules" (e.g. monetary policy)
* Anarchic: a cryptocurrency that is unable to comply with authoritarian requests (e.g. Bitcoin) and offers strong privacy guarantees (e.g. Zcash)


**Computing platform**

* Incremental: a smart contract protocol that can, without the consent of the majority of the network, blacklist accounts (e.g. EOS) or prevent access to certain groups (e.g. private blockchains).
* Anarchic: a smart contract protocol that is unable to comply with authoritarian requests (e.g. Ethereum) and offers strong privacy guarantees (none yet exist of material scale)


**Tokenized securities**

* Incremental: a protocol or set of smart contracts designed to comply with existing financial and legal systems, necessarily enabling those in power to control access and modify data of the protocol
* Anarchic: a completely new system for securities where the source of truth is not existing systems, but what is on the chain. This new system is unable to comply with authoritarian requests and sufficiently protects user privacy


**Non-fungible tokens**

* Incremental: just like tokenized securities where the token is only a pointer to the provenance ("true" version) of the asset. When the token and the asset are out of sync, a centralized entity is able to modify the ledger to match the token with the asset.
* Anarchic: the provenance of the asset is the token. The ledger is unable to comply with authoritarian requests and the privacy of users is preserved.


In each of these cases, there are possible benefits in adopting the incremental approach compared with current technologies. For example, an incremental approach to tokenized securities scales the technology behind securities while maintaining compatability with today's systems. However, the incremental approach will never satisfy the requirements of crypto-anarchists because the incremental approach can always comply with authoritarian requests and does not necessarily (but could) offer privacy.

## Conclusion

![](/assets/images/cy18/cy18q3m7/ts-2.png){: .align-center}

In sum, one can think of crypto projects as either crypto-incremental or crypto-anarchic. Both remove the middle-man omnipresent in today's web2 systems, but differ in their abilities to comply with authoritarian requests and preserve privacy.

Crypto-incrementalists envision numerous applications of blockchain that improve efficiencies in existing systems, designing around current legal and financial systems. The protocols of crypto-incrementalists remove the middle-man but are not resistant to censorship. While their protocols may behave like decentralized networks, they are still able to comply with authoritarian requests. The crypto-incremental future does not look _that_ different from today. Users may enjoy incrementally reduced fees, but no new freedoms.

The protocols of crypto-anarchists cannot comply with authoritarian requests. And they preserve the privacy and anonymity of its users. These requirements are hard to satisfy (as evidenced by Bitcoin's poor privacy guarantees), and make certain use cases all but impossible (e.g. enterprise blockchains, tokenized securities) with legacy financial and legal systems.

Many of the most common debates in crypto reach an impasse because one party is a crypto-incrementalist and the other is a crypto-anarchist. Critics of EOS/IOTA/(anything that's not Bitcoin) complain that it's too centralized. If you are a crypto-anarchist, EOS would never satisfy your requirements. But if you're a crypto-incrementalist, you may happily accept centralization for the faster transactions.

I believe crypto-incremental and crypto-anarchic projects can coexist. Where we see problems is in the widespread conflation of crypto-anarchic properties with crypto-incremental projects. Early crypto evangelists have been so successful in promoting censorship resistance and privacy that many assume that all crypto projects have or will have these properties. This is a dangerous misconception, as it's highly unlikely (mostly impossible) that a project can go from crypto-incremental to crypto-anarchic. Crypto-incremental projects are simply not contenders for use cases that require crypto-anarchy, but many market themselves as contenders because the "value" of those use cases (e.g. unseizable money, permissionless platforms) is much higher than an incremental improvement to an existing system. We would do well as an industry to clarify.

1. https://nakamotoinstitute.org/crypto-anarchist-manifesto/#selection-71.665-71.898 [↩](https://www.tonysheng.com/incremental-vs-anarchy#fnref:1)
2. https://bitcoin.org/bitcoin.pdf [↩](https://www.tonysheng.com/incremental-vs-anarchy#fnref:2)
