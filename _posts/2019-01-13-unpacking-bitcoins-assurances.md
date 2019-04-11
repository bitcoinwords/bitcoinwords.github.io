---
title: "Unpacking Bitcoin's Assurances"
permalink: "/unpacking-bitcoins-assurances" 

tags:
  - CY19 Q1
  - Nic Carter

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

# [Unpacking Bitcoin's Assurances](https://medium.com/@nic__carter/unpacking-bitcoins-assurances-a3c98824d3f0)
## Dis-aggregating the system's guarantees
### By [Nic Carter](https://medium.com/@nic__carter)
### Posted Jan 13, 2019

It has rightfully been pointed out that Bitcoin's decentralization is but a means to an end — censorship resistance. This is in response to the decentralization fetishism that has characterized Bitcoin competitors and the blockchain industry in general. This is an appropriate response: cosmetic network decentralization is probably not sufficient if you plan on breaking any serious rules, and irrelevant if the industry you are seeking to disrupt is dentistry.

Bitcoin's fault-tolerant architecture was designed to survive extreme duress, and its multi-variate decentralization was created (or more accurately: emerged) to promote this. However, censorship resistance — the ability to broadcast information without restriction — does not fully cover the guarantees that Bitcoin provides to users, although it is perhaps the most significant.

In this post I will try and define the various guarantees that Bitcoin users can expect by taking advantage of the system's features over the entire usage lifecycle — from acquisition to exit. Censorship resistance is central to these but not sufficiently comprehensive. I call these 'assurances,' although they aren't perfectly assured, since things go wrong in the real world. (I've been a fan of 'assurances' in this context since reading [this post.](https://blog.goodaudience.com/1-assurances-in-crypto-14c55a1fd616)) I also take a stab at assessing how well Bitcoin enshrines those assurances today. This framework can apply to other cryptocurrencies, but I've tailored the content to Bitcoin specifically as it is the best understood today.

![Bitcoin's assurances by usage phase](/assets/images/cy19q1/carter-assurances-by-usage.png){: .align-center}*Bitcoin's assurances by usage phase*


## Open access

This is the shorthand for "the right to freely acquire Bitcoin." No amount of decentralization in Bitcoin's architecture itself can guarantee this. As many Bitcoiners will point out, free access to the asset requires a vibrant and competitive industry of fiat onramps. The existence of quasi monopolists attempting to build regulatory moats in order to raise barriers to entry threatens this. If acquisition of the asset can only occur in a couple large venues, they are not only susceptible to state action, but also liable to collusively deplatform individuals at will. Imagine what happens to the Venezuelan equivalent of Coinbase during a currency crisis: the government trivially shuts it down to preserve its monetary monopoly.

Thus, while large, regulator-friendly, conventional exchanges are good onramps in the developed world, where cryptocurrencies are not (yet) a threat to local sovereign currencies, they aren't a good fit for states experiencing demonetization or high inflation, which is where access is most impactful. Centralized exchanges must be supplemented by peer to peer exchanges like [LocalBitcoins](https://localbitcoins.com/), [Hodl Hodl](https://hodlhodl.com/), [Paxful](https://paxful.com/) — and indeed, they are the venues where trading seems to occur (Venezuelan traders are doing $300m annualized on LocalBitcoins, Nigeria ~$170m, Russia close to a billion USD). Wallets which allow for trust-minimized trading like [Opendimes](https://opendime.com/) are vital here — receiving an Opendime where you can be sure your counterparty doesn't know the private key beats waiting an hour for six confirmations.

Lastly, paper voucher systems enabling users to acquire smaller quantities of Bitcoin at street kiosks or from corner shops are an important piece of the puzzle. Vouchers work by exchanging fiat for a receipt with a code on it; settlement can be done later. I have a vision of [sarafis](https://hackernoon.com/the-key-to-bitcoin-adoption-in-developing-countries-60edfbe60786) in the streets of Tehran and Kabul hawking Bitcoin vouchers — small-scale entrepreneurial activity is much more robust to government activity than larger exchanges in a demonetization event. [Fastbitcoins](https://fastbitcoins.com/) and [Azteco](https://azte.co/) are two startups advancing this use-case; I expect many others to join them.

Peer to peer exchanges like [Hodl Hodl](https://en.bitcoinwiki.org/wiki/Hodl_Hodl#How_does_Hodl_Hodl_work.3F) rely on a crucial and unheralded technology: Bitcoin's native multi-signature (multisig) capability. A simple, well-understood, trusted, and widely-used multisig implementation enables massive secondary benefits. In the case of Hodl Hodl, it allows buyers and sellers to transact with a high degree of confidence that they will not be cheated. In 2-of-3 multisig contract, the seller and buyer must both sign the release transaction; and if one disagrees, it is referred to the arbitrator for a decision. In practice, the vast majority of transactions settle without arbitration — the threat of mediation itself enforces good behavior.

Multisig is popular in Bitcoin today: about 1.65m BTC (about $6b) are held in known multisig wallets. This figure climbs to 3.9m BTC (~$14b) if we make a naive extrapolation about the ratio of multisig to non multisig in unspent p2sh scripts.
![P2SH Address by Type](/assets/images/cy19q1/carter-assurances-p2sh.png){: .align-center}*Source: [p2sh.info](https://p2sh.info/dashboard/db/p2sh-repartition-by-type?orgId=1)*


To sum up, open access to Bitcoin is a core component of the system — what use is the asset if you can't easily obtain it? — yet it is somewhat overlooked. It's important to be realistic about this. Bitcoin suffers from a paradox whereby individuals in countries with relatively less need for Bitcoin have frictionless access to it, while individuals dealing with hyperinflation have to reckon with a less developed onramp infrastructure. There is much work to be done here.

## Seizure resistance

One of the chief motivations for this article was to differentiate the unencumbered broadcast rights that Bitcoin grants users from the strong guarantees it grants to users when it is at rest. As mentioned above, censorship occurs at the time of broadcast, so 'censorship resistance' doesn't quite describe Bitcoin's unique properties when idle.

Thus the inclusion of **seizure resistance**(this is also sometimes referred to as 'tamper resistance' or 'judgment resistance'). By this I mean the ability of users to retain access to their Bitcoin under duress, during times of upheaval or displacement, all in a peaceful and covert way.

As Hasu and Su Zhu have [eloquently written](https://medium.com/@hasufly/bitcoin-and-the-promise-of-independent-property-rights-8f10e5c7efa8?sk=226124e0ff272801b8a9e49ce3403ac7), Bitcoin can be understood as an independent institution which provides users property rights which are untethered from the state or the legal system. As virtually all property rights trace back to the state, the legal system, or some local monopoly on violence, Bitcoin's cryptography-based property rights are a genuinely new paradigm.

This has been covered at length, but the fact that individuals can store their wealth in a 12 or 16-word passphrase held in their memory is quite astounding. While that's not the most failure-resistant way to operate, it makes one's wealth extremely portable and concealable.

Multisig also comes into play here. Innovative custody companies like [Casa](https://keys.casa/) (disclaimer: Castle Island is an investor) rely on a 3-of-5 multisignature setup whereby the user controls four keys physically dispersed, and Casa holds one for disaster recovery. This makes physical attacks on Bitcoin holders much more difficult and expensive, while preserving convenience and resilience to faults (seedless recovery is possible if a hardware wallet is lost). The secure key sharding that Bitcoin offers fundamentally reinvents what it means to be a custodian, and opens the door for all kinds of innovative hybrid models which offer various resilience/autonomy tradeoffs.

## Censorship resistance

This is the most celebrated assurance attributed to Bitcoin, so I'll be brief. At its core, Bitcoin allows permissionless broadcast through the p2p gossip protocol and the miner fee incentive. Anyone can make a transaction, although they have to sufficiently compensate a miner to include it in a block. If there is a lot of traffic, this could entail a delay or a higher fee. The other required component here is a well-connected network of nodes available to route transactions. If full nodes were to become very expensive and difficult to run, full node counts might decline, making broadcast more difficult. That said, node counts would have to drop precipitously to impair network performance, so this isn't an immediate concern.

One realistic impairment to censorship resistance is the simple approach of simply shutting off local access to the internet. While Bitcoin's global infrastructure cannot be realistically held back by even by the most motivated state actor, a state under severe monetary duress — experiencing a demonetization event, for instance — might take the extreme step of temporarily restricting access to Bitcoin by shutting off the internet. In recent memory, governments in [Iran](https://www.wired.com/story/iran-telegram-ban/), [Turkey](https://en.wikipedia.org/wiki/Block_of_Wikipedia_in_Turkey), and [Russia](https://www.theverge.com/2018/4/17/17246150/telegram-russia-ban) have shown themselves willing to exert massive collateral damage on local internet access to target services like Telegram and Wikipedia. Places like China where the internet and Bitcoin usage are already [tightly regulated](https://bitcoinist.com/bitcoin-node-illegal-china/) would be well-positioned to impose such restrictions. It's not inconceivable that a state could attempt to target Bitcoin in such a manner.

Touted mitigations to state censorship of Bitcoin's broadcast layer include Nick Szabo's [long-range radio proposal](https://scalingbitcoin.org/stanford2017/Day2/Weak-Signal-Radio-Communications-for-Bitcoin-Network-Resilience.pdf) as well as [Samourai](https://github.com/MuleTools/PonyDirect)/[Gotenna's](https://bitcoinmagazine.com/articles/samourai-and-gotenna-enable-bitcoin-transactions-without-internet-access/) SMS and short-range radio mesh proofs of concept. These initiatives, however, are still either in the R&D phase or the very earliest phases of deployment. At present, individuals in internet-restricted locations have little recourse when faced with such an attack, aside from physically getting their funds out of the country in a hardware or paper wallet. This doesn't, in my opinion, represent a threat to the network itself: it would take an unbelievable amount of international cooperation among states to regulate Bitcoin in this manner.

Network DOS attacks through fee spam are also an effective if costly way to make it more difficult for everyday users to broadcast transactions. There are few mitigations for this aside from waiting out the attacker or outbidding them.

## Counterfeit resistance

This is a crucial quality of the system, and yet it doesn't get quite the rhetorical exposure that censorship resistance does. **Counterfeit resistance** is simply the idea that individuals who use Bitcoin have very cheap access to the tools required to verify that payments they are receiving are legitimate, that their savings have not been debased through inflation, and that their counterparties aren't cheating them in some way.

Comparing Bitcoin to gold, the ability to run a full node is akin to owning a professional-grade XRF spectrometer to check the integrity of your bullion. Compared to the expensive and tricky tests to verify gold's authenticity, verifying the integrity of one's Bitcoin is a breeze. Running a node costs a few dollars a year and can be done on consumer hardware and bandwidth with little difficulty. This very accessible counterfeit resistance only persists as long as running a node is relatively cheap — a significant increase in the bandwidth, computation, or memory required to run a fully validating node would hinder it significantly. Right now, Bitcoin is growing at a stable rate, and physical plug-n-play node hardware has made full nodes more accessible than ever, so this assurance seems safe for now. For individuals and enterprises that don't want to run nodes directly, a good diversity of managed node software exists.

The other side of counterfeit resistance is the ability to determine that all units that exist were created according to a predefined, predictable schedule. The proof of work minting function, plus the difficulty adjustment, takes care of this. Well — close enough. Naively assuming that blocks were meant to arrive every 10 minutes on average, Bitcoin is actually slightly ahead of schedule by 30,000 blocks or so. This is because hash power has generally increased over time, and this caused block arrival to outpace the defined schedule due the coarse granularity in the difficulty adjustment. Aside from this interesting emergent property, Bitcoin's PoW has never been compromised, nor has the hash function been broken (and this doesn't seem eminently likely in the foreseeable future). Verifying that the correct number of units exist is as simple as running the _gettxoutsetinfo_ command in your Bitcoin Core node. The inherent auditability of Bitcoin and all of its derivatives is what makes deceptions like the [Bitcoin Private](https://coinmetrics.io/bitcoin-private/) covert inflation scandal easy to spot.

At present, Bitcoin's counterfeit resistance is made possible by a deliberate design philosophy from the core developers that prides accessibility and user self-sovereignty at all costs. It is augmented by a network of Bitcoin businesses that provide hardware nodes or managed access to node software. However, if the chain's growth were to radically accelerate, consumer-grade counterfeit resistance would be significantly impaired.

## Free exit

Free exit — the ability to sell Bitcoin unencumbered — is another aspect of the system that is sometimes overlooked. It's not strictly a Bitcoin guarantee, but Bitcoin's usefulness is significantly downgraded in its absence. The real world consequences of overzealous chain analysis companies (whose heuristics implicate innocent users through false positives) make themselves felt when those users attempt to sell their Bitcoin for fiat. Since fiat offramps are the most easily regulated and are run by risk-averse institutions, they are a natural target for entities that create blacklists and ascribe taint to individual UTXOs.

There are a few strategies to reckon with this. One is to obfuscate the origin of funds through collaborative tumblers like the [Wasabi wallet](https://www.wasabiwallet.io/) . Another approach is to reverse-engineer the heuristics that chain analysis firms use and develop mixing strategies that implicate everyone in taint (thus rendering those heuristics incoherent) or that avoid detection altogether through specialized transaction types. This is the general approach of the folks behind the [Samourai](https://samouraiwallet.com/features) wallet. Routing around the centralized, highly-regulated exchanges is another option, either on the p2p marketplaces or by exchanging BTC for goods and services, rather than fiat.

Ultimately, I expect that a tranche of grey or black-market Bitcoins will emerge, with coins available at a discount in exchange for their reduced access to capital markets. This will not be a death knell — there will likely be more than enough demand globally for slightly cheaper Bitcoins, even if they cannot be traded on Coinbase. The world is a big place, with a variety of regulatory regimes, and individuals fleeing hyperinflation may not be too bothered by the fact that the Bitcoins they acquired cannot be deposited on US-regulated exchanges.

The objective for this piece was to present a framework of the major assurances that Bitcoin provides to users, and make it clear that censorship resistance is only one of them. Additionally, I wanted to make the point that Bitcoin the software is only one part of a much vaster system — a collaborative social and industrial project aiming to provide unencumbered financial tools to individuals the world over. Entrepreneurs that have created hardware wallets, merchant services, novel exchanges, voucher systems, Bitcoin contract structuring, and hybrid custody models have all done their bit to advance user sovereignty and discretion when it comes to their personal wealth. They deserve to be recognized, as does the broader struggle to make these touted assurances a reality.
