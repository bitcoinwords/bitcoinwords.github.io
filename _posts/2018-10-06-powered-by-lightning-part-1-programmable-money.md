---
title: "Powered by Lightning - Part 1, Programmable Money"
permalink: "/powered-by-lightning-part-1-programmable-money" 

tags:
  - JP Thor
  - CY18 Q4

excerpt: This is part 1 of a 5 part series. By JP Thor, posted October 13, 2018. A quick primer on the Lightning Network and how it is making money programmable.

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

# [Powered by Lightning; Programmable Money — Part 1](https://medium.com/coinmonks/powered-by-lightning-part-1-3b6a514a0670)
## A quick primer on the Lightning Network and how it is making money programmable.
### [JP Thor [ ₿ ⚡️]](https://twitter.com/jpthor__)
### Oct 6, 2018

* **[Part 1 — Programmable Money](https://cryptowords.github.io/powered-by-lightning-part-1-programmable-money)**
* [Part 2— Using the LN as an individual](https://cryptowords.github.io/powered-by-lightning-part-2-using-lightning-network-as-a-user)
* Part 3— Using the LN as a business
* Part 4— Using the LN as a country
* Part 5— When the world is powered by LN

## The Layers of the Internet
Bitcoin is emerging as a multi-layer value-transfer protocol, with different layers serving different needs and being used for different things. To understand this, we need to look at the Internet Model, which is a conceptual model around the four layers of the internet; Application, Transport, Internet and Network.

![](/assets/images/cy18/cy18q4m10/jp-1.png){: .align-center}*The Internet Model. Source: Stemjar*

### The Four Layers in Use
When users of the internet send data between each other (you and a website's server), the data transfer takes place across the four layers. Firstly the data is collected from the sending user at the application layer (the website's interface), which uses the underlying APIs to transport encrypted data packets via https (hopefully) to the server. These data packets are routed via the internet's infrastructure, which are essentially bits of information streamed across a high-speed link between servers. The data is acted upon (updating or changing state on the server), and the reverse in the download of updated information back to you.

Most likely the server's database is backed up on a schedule (such as iCloud or any of Google's services), and the changed state is replicated across other servers.

The end result is that you transferred data to and from another internet user (the server) directly, which was done in less than a few seconds and only you and the server knew about it. At some point later the changed data was backed-up across other servers. Overall, the user experience would have met our expectations, and the final data was safely backed up.

Before the internet as we know it, users would connect directly with each other at the networking layer. It was not possible to simply "go to a website". Indeed the internet that we know of today is mostly thanks to the Application Layer and its micro-services, APIs and browser-side processing.

## The Layers of Bitcoin
A multi-layered Bitcoin is no different from a conceptual point of view. The base layer is the chain of blocks containing the immutable transaction graph, the "Layer 1". This layer is completely public and everyone can view and validate the entire history of the database. This layer defines and secures what Bitcoin is.

Bitcoin Core is part of the network layer, allowing nodes to gossip, propagate blocks and connect with each other. The information in this layer is always only partial, each node may store a different view of the network, the "mempool". This layer also contains the Lightning Network, a network of nodes that facilitate unicast transactions of value between nodes. This is the "Layer 2".

The third layer will be the application layer, where APIs are built to interact with Layer 2 and allow highly performant user interactions with the network. This was first observed with satoshis.place where less than a week after it was launched, enterprising users were utilizing APIs to paint complex pictures, such as photos and a copy of the Bitcoin white paper, and even performing state-reversions of the entire billboard.

![](/assets/images/cy18/cy18q4m10/jp-2.png){: .align-center}*MULTI-LAYERED BITCOIN*

With this in mind, we can see that an on-chain transaction at the base layer is one of the most cumbersome things to do with Bitcoin, and is akin to sending data packets at the networking layer of the Internet. We simply don't do it unless we need to rig to servers together to transfer data at high speed; such as in data-centres, trading desks or agency/enterprise-level infrastructure.

Even sending a lightning transaction itself is one-level too deep for the desired experience. It is substantially more scalable and useable than transacting at the base layer, but for mainstream adoption it is not desirable.

We need to keep building to get ourselves to the Application Layer. We're quite a long way off that (3–5 years), but the good thing is we don't need to rush there. It's actually only necessary to allow 8 billion people to onboard, with performance, scalability and an excellent user experience. In the meantime, base layer and network layer transactions are perfectly fine for early adopters.

## The Networking Layer

Lightning Network is a relatively new layer of Bitcoin, but it makes more sense to see that it is the unicast networking layer that sits above the base layer, and below an application layer. However the application layer is absolutely dependent on a robust networking layer. Indeed it is only being realised now that for the LN to work as best as it should, it needs to bring in other aspects of technology never before thought related to Bitcoin, such as machine learning and artificial intelligence.

### Autopilot

![](/assets/images/cy18/cy18q4m10/jp-3.png){: .align-center}*Lightning Network*

In the LN, users choose their route to their destination address. However there can be thousands of different choices of route, and the user may have different preferences between liquidity, fees, reliability and privacy. Each route has different characteristics that are non-deterministic as they are set by nodes that can connect and leave at any time. Additionally, with [Atomic Multi-path Payments (AMP)](https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-February/000993.html) the number of routes actually transacted across for a single payment may number in hundreds or thousands.

This is currently far too much for client-side processing, and indeed there is no algorithm that can easily solve for this. Instead, advanced ML algorithms will do far better in choosing routes between peers, and will allow the user to make payments with close to optimal speed, reliability, liquidity and privacy; all across a permissionless and decentralised network.

Indeed, an advanced AI-powered Autopilot will ensure that the connections made between nodes and users, as well as the parameters chosen for each route, counters most forms of attack on the network. Some of these attacks (such as parasitic, oppressive or censoring nodes) are not yet clearly defined or understood. For LN to ever function securely, it requires building first on a robust, resilient and secure Base Layer. Then once the Networking Layer is mature, then we can build the Application Layer.

![](/assets/images/cy18/cy18q4m10/jp-4.png){: .align-center}

### Programmable Money
We've actually never truly seen programmable money before. Before Paypal and other payment services, sending money online was extremely difficult. Paypal's innovation wasn't making a better money, it simply created a network effect and consolidated a lot of ecommerce users in one place, so it could transfer money faster. Stripe and Square also didn't create a better programmable money, they just simplified the on-boarding process for users and merchants.

The digital money we have been using the entire time never improved. Even in 2018, the minimum credit card fees have never been lower than around $1 and processing time never less than a few seconds. Beating these limits could only be possible by giving another entity access to your money, and this will never be feasible at scale.

With multi-layered Bitcoin, transactions to the 100th of a cent can be processed close to the absolute maximum limit of performance of the underlying internet infrastructure — and this can all be done completely trustlessly and never giving over control of money. Early tests show a single payment channel of LN processing payments at over [1m transactions per second](https://www.youtube.com/watch?v=txcjxSRDvqQ).

These capabilities are about to usher in a new generation of marketplaces, experiences and economies. It is feasible that in future payments could be paid at the per-byte, per-millisecond, per-millimetre, per-millilitre or per-gram level; and these payments are entirely streamed between machines.

Some examples could be:
1. Your fridge detects emptiness and orders your next meal for you.
2. Your phone pays at the per-byte level for a faster internet connection, spending up to a cap you set.
3. Your self-driving car drives faster than other traffic, paying to over-take.
4. Your browser pays for the per-second view of online content.

## Machines understanding value
Once our machines start interacting across the multi-layered value-transport protocol that is Bitcoin, it is conceivable that they will be taught to become aware of value. This will give rise to an entirely new generation of efficiency and effectiveness, as well as intelligence.

With more machines performing redundant tasks, humanity will gravitate more and more to what can keep us occupied, stimulated and happy. This will likely be around entertainment and consumption of content, especially in virtual and augmented reality.

At the same time, creation of content will be increasingly be served by artificial intelligence, reducing the feedback loop between creation of content, and assignment of value to that content by humanity. If an AI is producing video, music, art, virtual sports or games to an audience of humans, and it is being paid at the per-second or per-byte level; then the feedback between creation and consumption will rapidly reduce, and there is no more concise or clearer feedback than being paid for something.

Whether or not this accelerates us to singularity, is up for debate. However, the assuring thing about this reality is that the future with a multi-layered programmable money is that it is owned by all, and controlled by no one. This is far better scenario than a state-sponsored singularity.

![](/assets/images/cy18/cy18q4m10/jp-5.png){: .align-center}

## Lightning for you, now
A multi-layered Bitcoin sounds exciting, but what can be used now? In truth the network is extremely young and under constant development. There is still a strong sense of naivety in what it really all is, and there is a large camp of users who don't yet subscribe to or understand the multi-layer properties of the Bitcoin protocol yet.

The take-away is that Bitcoin is a multi-layered value-transport protocol, just how the internet is a multi-layered information-transport protocol. And the two will converge in a perfect storm.

\#getoffzero \#buybitcoin

In the next blog we'll discuss how individuals can use the LN. Before then, you should download a lightning wallet: [https://play.google.com/store/apps/details?id=fr.acinq.eclair.wallet.mainnet2&hl=en](https://play.google.com/store/apps/details?id=fr.acinq.eclair.wallet.mainnet2&hl=en)

You should also buy a lightning node to host at home: [https://store.casa/lightning-node/](https://store.casa/lightning-node/)

More resources: [https://lnroute.com/](https://lnroute.com/)

Follow me on twitter: [twitter.com/jpthor_](twitter.com/jpthor_)

I share, write and talk about the decentralised future.
