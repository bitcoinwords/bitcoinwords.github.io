---
title: "The Lightning Paradox"
permalink: "/the-lightning-paradox"

author: alexberge

tags:
  - Alex Berge
  - CY17 Q1
  - Lightning
  - Mining
  - Fees
  - Jevons Paradox
  - Economics

excerpt: Alex Berge makes the case that Lightning Network will eventually lead to MORE mining revenue. Posted March 21, 2017.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Lightning Paradox](https://medium.com/@bergealex4/the-lightning-paradox-f15ce0e8e374)
### By [Alex Berge](https://twitter.com/bergealex4)
### Posted March 21, 2017

![](/assets/images/cy17/m3/ab-1.png)
*Historical demand for light over centuries of technological innovation*

_The goal of this post is to argue that second-layer technologies will ultimately translate to a growth in revenue for miners who will increasingly be relied upon to secure settlements of contracts across the various use cases enabled by technologies such as the Lightning Network._

The introduction of the Lightning Network was a paradigm shift in terms of how we all imagined the Bitcoin Network could scale to accommodate a global demand for transactional capacity. Inspired by the ideas put forth by the system’s creator, the protocol leads us to reconsider our assumptions about the nature of Bitcoin transactions and how users should leverage the unique properties of the blockchain and the resources allocated to it by its peers.

> Intermediate transactions do not need to be broadcast. Only the final outcome gets recorded by the network — [Satoshi Nakamoto](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2013-April/002417.html)

In the original implementation of the system, every transaction was to be recorded on-chain and appended to the blockchain. Early contributors to the project quickly [realized](https://bitcointalk.org/index.php?topic=2500.msg34211#msg34211) that such a decentralized global broadcast system involved very poor scalability properties.

Enter [payment channels](https://bitcointalk.org/index.php?topic=244656.0): an implementation of a [smart-contract](https://medium.com/@bergealex4/why-2017-may-be-the-year-the-industry-figures-out-smart-contracts-via-bitcoin-cd72e25bacdc) allowing users to enter into relationships wherein consensus around the history of transactions they are involved depends only on the participants of the contract. In case of a dispute, the Bitcoin blockchain is used as a trustless adjudicator which ensures accountability and prevents uncooperative parties from cheating their respective counterparties. The Lightning Network, first proposed in [a paper](https://lightning.network/lightning-network-paper.pdf) by Joseph Poon and Tadge Dryja, extends this construction to allow contracts to be interconnected, creating a multi-lateral network of counterparties & [channels](https://en.bitcoin.it/wiki/Payment_channels) that is used to to move obligations among peers in the network and leverage the liquidity they provide. For a high-level description of how this is achieved, I recommend Lightning Labs’ Elizabeth Stark’s excellent [primer](https://coincenter.org/entry/what-is-the-lightning-network) available on the CoinCenter website.

The emergence of such a system begs us to re-examine the role of miners as the main processors of Bitcoin transactions. Considering that the long-term security of the network is expected to be financed by transaction fees, many flags have been raised questioning the decision to move the bulk of these revenue-generating transactions to a layer which miners cannot monetize directly. Fortunately, history is ripe with examples of how the introduction of more efficient technologies affected the demand for an underlying resource. More importantly, these economic dynamics are well-studied and provide us with a valuable point of reference as to how the market for Bitcoin transactions may unfold post-Lightning.

## The price elasticity of demand

Little in-depth analysis has been made of Bitcoin’s demand curve and a great deal less of the elasticity of said demand under increasing transaction fees. On the other hand, one does not have to look too hard to detect many instances of use cases that, along the way, were priced out of the market only to be replaced by a persistent influx of higher fee paying transactions. Early adopters will remember the bulk of transactions originating from services such a SatoshiDice or other micro-payment services such a faucets & tipping bots. It is worth mentioning that at its peak the former was responsible for anywhere from 80 to 90% of Bitcoin’s transaction volume.

Today, most of these applications have been moved to off-chain services. Their inefficient usage of the space available in blocks made them unable to compete with organic growth of transactions coming from users who possess little to no alternative available which could provide the same unique features that Bitcoin does. Of course, history indicates that demand for Bitcoin transactions has persisted and pushed through continuous all-time highs, even with the recent materialization of a more competitive fee market.

While these are only anecdotal evidence, they offer strong indications that the demand for Bitcoin transactions is considerably inelastic. What this suggests is that the supply of space in blocks will find demand even as transaction fees increase. The reasons for this are subjective and hard to accurately assay as they are simply the result of decisions made by independent market actors. Nevertheless, this observation has strong implications for anyone interested in figuring out Bitcoin’s value proposition.

When gauging the price elasticity of demand, perhaps the main determinant is the availability of[ substitute goods](https://en.wikipedia.org/wiki/Substitute_good). As it turns out, it may be that the opportunity cost of opting for current alternatives which are more centralized and less liquid or secure is much higher than the price of having one’s transaction included into the Bitcoin blockchain.

## The Lightning engine

> It is wholly a confusion of ideas to suppose that the economical use of fuel is equivalent to a diminished consumption. The very contrary is the truth. — [William Stanley Jevons](https://en.wikipedia.org/wiki/The_Coal_Question)

The Jevons paradox is a staple of environmental economics used to describe how the introduction of more efficient technologies tends to increase the consumption of resources rather than decrease it. In his thesis “_The Coal Question_**_”, _**Jevons challenges conventional wisdom by pointing out the resounding impact that James Watts’ steam engines had on the consumption of coal during England’s industrial revolution.

With Bitcoin ushering in a new revolution of its own, it’s interesting to draw parallels between Jevons’ analysis and the current issue that concerns us. Provided we can agree that the space in blocks is a scarce economic resource and considering solutions such as the Lightning Network are a clear innovation in terms of how efficiently we use this resource, can we arrive at the same conclusion that Jevons did?

> _…new applications of coal are of an unlimited character. In the command of force, molecular and mechanical, we have the key to all the infinite varieties of change in place or kind of which nature is capable. No chemical or mechanical operation, perhaps, is quite impossible to us, and invention consists in discovering those which are useful and commercially practicable…. — _[William Stanley Jevons](https://en.wikipedia.org/wiki/The_Coal_Question)

I highlighted above various examples of use cases which have been priced-out of the on-chain transaction market over the years. The fact is that a plethora of other use cases involving transfers of bitcoins between individuals have never made in on-chain. Consider, for example, intra-platform transfers between users of Bitcoin exchanges and other services. In a recent [conference call](https://www.docdroid.net/2qjyYlp/transcript-bitcoin-quarterly-update-call-needham-co-november-2016.pdf.html#page=2) held by Needham & Company, Wences Casares, CEO of Bitcoin company Xapo, revealed that his company were doing upwards of **500,000** transactions per day off-chain. These transactions are potential revenues which the miners are never going to be able to tap into under the current technological context.

More importantly, there is an entire class of potential use-cases relying on high-frequency micro-transactions that would never make it onto a blockchain either because of fees, delays or throughput. By using Lightning as an aggregation layer, we optimize the utilization of block space and allow users to process these transactions between themselves and ultimately incur fees of which a fraction is released to miners any time a channel is opened or closed. Considering the potential rate of return bestowed to users who allocate their assets to Lightning channels, it is more likely than not that they will, in turn, be willing to pay higher fees for those on-chain transactions.

Economists have long observed that the induced demand from technological improvements generally drives along with it further economic growth. This idea is more popularly known as the [Khazzoom-Brookes postulate](https://en.wikipedia.org/wiki/Khazzoom-Brookes_postulate) and derives its insights from Jevons’ argument that improving energy efficiency makes the use of resources more economically viable for a larger share of market participants and use cases.

In this regard, the Lightning Network may turn out to be the steam engine of the Bitcoin economy. By introducing a cache layer which users can leverage for low-cost access to blockchain storage, Lightning provides a more efficient way for us to make use of the raw and scarce block space resource. Such a development creates endless opportunities for entrepreneurs, inventors & market forces to come up with new products and services that directly contribute to the economic growth of our ecosystem. Consequently, miners will not only benefit from an increased demand for on-chain transactions but will also profit from potentially dramatic appreciation of the underlying asset.

## Conclusion

> We are in the age of digital gold. We are replaying the history of money right now and I think today we are smack dab in the 1700s and for the past 5–6 years I think we have been 2000 BC. We have been talking about pure value but this value is a foundation for everything else we build on top of it. First you need money, after that you need payment systems, after that contracts, institutions, etc. — [Joseph Poon](http://www.coindesk.com/events/construct-2017/videos/)

At this most important juncture of our journey, it is important to take a step back and acknowledge how far we still have to go until we can fully realize the promises brought about by the invention of Bitcoin. While Bitcoin users tend to scoff at traditional financial systems and their failure of upholding the trust lent to them by market participants, it would be unwise for us to dismiss the innovations they fostered over centuries of evolution. We have an opportunity to learn from this history but also to use the technology available to us today to build superior systems. This transformation will not happen without leveraging the layered infrastructure that enabled the economic growth that we have enjoyed under the old paradigm.

Lightning is the first large scale implementation of a contract system on top of Bitcoin. While it challenges early expectations about the economic relationships between protocol participants, market dynamics suggest that the outcome of this incoming **r**evolution presents little to no drawbacks for everyone involved. New markets will be opened to the benefits of all users and the value extracted from those will necessarily trickle down to miners securing the chain backing all of these applications.

For that reason, I believe the apprehension we are experiencing should leave place to enthusiasm and lead everyone to embrace the potential of these breakthroughs. We are working at the frontier of technology and while the path ahead is unarguably challenging, we cannot allow uncertainty to prevent us from moving forward.

> Nothing in life is to be feared, it is only to be understood. Now is the time to understand more, so that we may fear less. — Marie Curie

* * *

_Thanks to the various people who reviewed and provided inputs for this post, especially to Chris Belcher for introducing me to Jevons’ work._

***

{% include signup.md %}
