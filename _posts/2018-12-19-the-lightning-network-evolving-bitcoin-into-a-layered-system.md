---
title: "The Lightning Network - Evolving Bitcoin into a layered system"
permalink: "/the-lightning-network-evolving-bitcoin-into-a-layered-system" 

tags:
  - CY18 Q4
  - Jordan Clifford

excerpt: By Jordan Clifford, Posted December 19, 2018 

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

# The Lightning Network
## Evolving Bitcoin into a layered system
### By [Jordan Clifford](https://medium.com/@jcliff)
### Posted December 19, 2018

![lightning](/assets/images/cy18/cy18q4m12/clifford-1.png){: .align-center}*photo credit: [John Fowler](https://www.flickr.com/photos/snowpeak/43257678172/)*

In this post, we'll explore the Lightning Network (LN): what it is, how it works, what makes it special, what tradeoffs it makes and some of the weaknesses it has. At a high level, the Lightning Network utilizes smart contract functionality within Bitcoin allowing users to temporarily keep the state of the books locally, rather than having each update happen on the global blockchain.

The ideas within the Lightning Network are not new. Satoshi himself envisioned using [payment channels](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2013-April/002417.html) to batch transactions off chain before writing a final settlement transaction to the chain. In 2014, Peter Todd, a famous Bitcoin developer and blockchain consultant, [discussed](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2014-December/006988.html) how payment channels could be tied together in a hub-and-spoke model.

The Lightning Network builds on this prior art, and was formally introduced in a February 2015 [white paper](https://lightning.network/lightning-network-paper.pdf) — a collaboration of blockchain researchers [Joseph Poon](https://twitter.com/jcp) and [Tadge Dryja](https://twitter.com/tdryja). The vision of the Lightning Network is a mighty one. The goal is to create an overlay network on the Bitcoin protocol allowing arbitrary parties to route payments to each other without writing to the blockchain.

### Background

Bitcoin was created to be a peer-to-peer cash system. One tenet dear to the Bitcoin community is the ideal that anyone on the planet is able to validate the state of the chain. Many within Bitcoin feel that to fulfill its promise of no trusted third parties, verifying the current state of the ledger must be achievable with modest bandwidth and typical consumer grade hardware. These beliefs have halted momentum towards increasing the block size, leaving developers to pursue alternative strategies for scaling the system.

The Lightning Network was pitched as a viable alternative to increasing the block size via a hard fork increase of the block size, which Bitcoin's developers felt too controversial and difficult to coordinate. However, in order to have a fully functional Lightning Network, a malleability fix was a necessary prerequisite. Transaction malleability means that transactions can be altered before they are included in a block, creating a near-identical transaction, but with a different transaction id. A malleability fix prevents transactions from being altered.

A change called Segregated Witness was [introduced](https://github.com/bitcoin/bips/blob/master/bip-0141.mediawiki) in late 2015 that served as a malleability fix and included [other benefits](https://bitcoincore.org/en/2016/01/26/segwit-benefits/). The developer community liked that it was a soft fork rather than a hard fork, since soft forks are easier to coordinates as clients can update at their own leisure. The promise of the Lightning Network is undoubtedly one of the deciding factors in this change getting adopted in August of 2017.

### **Building Blocks**

One of the best aspects of the Lightning Network is that it works using only existing functionality of Bitcoin. In fact, from the perspective of the Bitcoin network, LN transactions appear as ordinary transactions. Bitcoin doesn't need to know which transactions are part of the Lightning Network.

#### Transactions

Bitcoin operates on a model called the unspent transaction output (UTXO) model. A UTXO belongs to anyone who can meet the criteria assigned to that UTXO. The typical criteria is codified as an address, and is satisfied by creating a signature with a specific private key that created the address.

A transaction in Bitcoin results in the movement of bitcoin from one or more UTXO inputs into newly created UTXO outputs.

Possession of a private key is the most common spending criteria for a UTXO, but many other criteria are available as well such as the following:

#### MultiSig

A multisig UTXO requires signatures from multiple keys, ensuring that multiple parties agree to the transaction. The Lightning Network makes heavy use of multisig addresses. Parties choosing to connect to each other do by depositing into a multisig address that holds funds that are spendable only upon consent of both parties.

#### Hash Lock

It is possible to add rather interesting spending criteria to a UTXO. One such criteria built into Bitcoin is the ability to require a solution to a cryptographic puzzle be submitted when spending. The bitcoin is locked until the puzzle is solved. A hash lock is exactly such a lock. Hash locked bitcoin require the recipient to publish data that results in a specific hash.

A hash function takes an arbitrary amount of data and condenses it down into a fixed length string. A tiny change in the original data makes the hash unrecognizably different. The fact that a hash function is incredibly difficult to reverse is what makes Bitcoin secure.

The data that results in a specified hash is called a pre-image. The pre-image is chosen by the intended recipient, and they provide the hash to the sender. We'll see later that it's exactly this hash lock that guarantees funds are not intercepted when being sent over the Lightning Network.

#### Time Lock

A time lock is a useful building block for smart contracts. As it sounds, a time lock prevents bitcoin from being spent before a certain time. The time can be absolute (specified as a block height), or relative to the publishing of the transaction.

As we'll see these delays are very important for allowing parties the needed time to keep each other honest. Without time locks, it would be possible for a party to publish an out of date closing transaction and instantly cash out more than they are entitled to.

#### Payment Channels

Payment channels were conceived by Satoshi Nakamoto. They are a clever way of allowing users to keep a running tally between themselves, without broadcasting each update to the world. Fundamentally, a payment channel requires two transactions, a funding transaction and a closing transaction.

A funding transaction sets up the channel by depositing bitcoin into a multisig address. From there, the parties can update the balance as often as they wish. They exchange enough information when transacting so that each has a copy of the closing transaction. They won't typically publish the closing transaction. Only once they are done transacting with each other, will they feel compelled to close the channel with a closing transaction.

Note that payment channels only really make sense if you expect to make multiple transactions in the interim.

#### One way Payment Channels

The simple case for a payment channel is when all payments happen in one direction. If Alice expects to be doing a lot of business with Bob, then it can make sense for Alice to open a one-way payment channel to Bob. Alice funds the channel herself. The money goes into a multisig address requiring both Alice and Bob's consent to spend it. As she wants to spend money with Bob, she signs a closing transaction updating the balance. When Bob is ready to close the channel, he signs his half of the closing transaction and broadcasts it.

What makes this efficient is that Bob typically does not close the channel until he doesn't expect any more business coming from Alice. Alice can make many payments for the price of two transactions being written to the chain.

In this simplified model, Alice cannot close the channel at all. In practice, there is a timeout for the channel, allowing Alice to claim her money back if Bob hasn't closed the channel within the specified window of time.

#### Bidirectional Payment Channels

One way payment channels can only get us so far if we want to make a massively interconnected web allowing payments between arbitrary parties. The one-way payment channels worked because the recipient can be relied on to only close the channel with the closing transaction that pays him the most. Bidirectional payment channels are quite a bit more complicated to get right.

With bidirectional channels, when the channel is funded, both parties get a copy of a commitment transaction which can close the channel. The commitment transaction has special properties which makes the setup work. For one, the commitment transactions are not the same. Alice's commitment transaction has Alice's bitcoin locked up for 1000 blocks, but Bob's bitcoin are immediately spendable. Meanwhile in Bob's commitment transaction, he has his bitcoin locked up for 1000 blocks, while Alice's can be spent immediately.

The reason for the asymmetry is to allow room for disputes. When Alice and Bob update the state of the channel with a payment in either direction, they are making an agreement to revoke old commitment transactions. In order to do so, they reveal to each other enough information to allow each to steal the counterparty's bitcoin if the counterparty were to publish an old commitment transaction.

So, the party publishing the commitment transaction has to wait 1000 blocks to spend their bitcoin. However, if the commitment transaction is stale, the other party can take all of the bitcoin. This backdoor is installed via a key that changes with each transaction called the revocation key. When a commitment transaction is revoked, the revocation key becomes known to the other party. If a stale transaction is published, the counterparty can withdraw the entire contents of the channel, via a penalty transaction. The possibility of a penalty transaction is key to keeping Lightning Network trustless.

#### Linking Payment Channels

Payment channels are only so useful if you have to open up a payment channel with every counterparty you ever plan to transact with. The Lightning Network really shines when opening channels with just a few counterparts allows you to make payments to nearly everyone on the Lightning Network.

Imagine that Alice has a payment channel to Bob, but she wants to pay Charlie. If Bob has a payment channel with Charlie, the Lightning Network gives us the tools for Alice to pay Charlie without any on-chain transactions.

The key to allowing payments that run through multiple hops is the hash lock. The ultimate recipient of a payment generates some private data, which becomes the pre-image. They hash that data and give it to the original sender. Each party in the chain of payment creates a new commitment transaction that is hash locked with the same hash. The updated closing transaction is conditional on the pre-image being revealed.

The pre-image will only be revealed by the recipient once they have received the requisite funds. Once it is revealed, all of the intermediary payments become unlocked as well since the data is now public. It is through this series of hash locks that payments can be sent trustlessly across multiple hops without fear of interception. Bob can only collect his payment from Alice if he also pays Charlie, otherwise Charlie will not reveal the pre-image.

### Tradeoffs and Open Problems

The Lightning Network is very anticipated, but not without some drawbacks and open problems.

#### Scales transactions not users

The Lightning Network undeniably allows more transactions per second for people within the Lightning Network. Transactions can happen at blazing speed and because the intermediate state is held locally, not globally, it scales very well.

However, it should be noted that for each user entering the Lightning Network, it requires at least one transaction up front, and another down the line. More likely it will require multiple transactions since it's recommended that users open multiple channels. Therefore the Lightning Network scales up the number of transactions a particular group can do very well, but enlarging the group is going to require more space for on-chain transactions.

#### Not great for some use cases

The Lightning network requires extra overhead that a normal transaction does not. If someone wants to receive a portion of their paycheck in Bitcoin and hold for an extended period of time, they may not benefit from the Lightning Network, and would be better off just receiving a standard bitcoin transaction.

The Lighting Network requires monitoring the blockchain to rebut any transactions to ensure that an old one is not used. This can be outsourced, but is still adds a bit of complexity.

#### Routing

In order for a payment to work over the Lightning Network, a route between the payor and payee must be found. This is really a two stage problem. First the network topology (an outline of the connections each user has) should be such that it's likely a route exists. Second, when it comes time to send a payment, the route must be identified.

One way we know that we can solve the routing problem is with a hub-and-spoke model, but this has been heavily criticized within the crypto community. The hub-and-spoke model has a small number of power users, typically companies that everyone connects to. Routes are easy to find since the hubs are very well connected, but it creates powerful intermediaries — something crypto was designed to avoid. Such a design would potentially compromise privacy and engender possible censorship.

The ideal Lightning Network is a peer-to-peer mesh network. Each user would be connected to a handful of other users, and through the "[Six Degrees of Kevin Bacon](https://en.wikipedia.org/wiki/Six_Degrees_of_Kevin_Bacon)" theory, it's postulated that a route can be found between arbitrary parties.

The truth is that this is still very much an active area of research. Leading the charge, BitFury, a mining hardware manufacturer, has put forth a [paper](about:invalid#zSoyz) outlining an algorithm called Flare.

#### Balancing the channels

Once a route is found between two parties, if most transactions are happening in one direction, that route may not be good for very long. The sender will deplete their balance on the outgoing channel, so it's important to keep balance in the channels by finding different routes or finding a way to push money back to the outbound channel via another route. This remains an area of open research.

### Where are we?

Currently, the Lightning Network is live in beta mode, meaning it's not mature software and bugs are expected. Reflective of its still experimental nature, the Lightning Network as of 12/18/2018 has ~2000 active nodes each with an average of 14 channels open. The average channel capacity is approximately $120.

Adoption so far has been minimal, given the early stages of the network. Only a few test cases have emerged so far such as [Bitrefill](http://@justincamarena) which allows you to buy gift cards and pay bills, Blockstream's Lightning [store](https://store.blockstream.com/) and the now infamous graffiti wall, [Satoshi's Place](https://satoshis.place/).

#### Who's behind this?

The Lightning Network is built on a series of interoperability standards called the [Basis of Lightning Technology](https://github.com/lightningnetwork/lightning-rfc/blob/master/00-introduction.md) (BOLTs). Three teams are building clients that all are capable of working together: [Lightning Labs](https://lightning.engineering/), [Blockstream](https://blockstream.com/lightning/), and [ACINQ](https://acinq.co/).

Lightning Labs is the de facto leader of the Lightning Network. The company was co-founded by [Elizabeth Stark](https://twitter.com/starkness) and [Olaoluwa Osuntokun](https://twitter.com/roasbeef) to bring this concept to a reality. Lightning Labs has built the reference client for the Lightning Network called Lightning Network Daemon (lnd) and they also maintain the network standards documents (BOLTs) repository. The lnd is written in the Go programming language.

Blockstream is involved in much of the cutting edge Bitcoin development and the Lightning Network is no exception. Blockstream's Rusty Russell has contributed heavily to the Lightning specification documents and also leads Blockstream's cLightning client development. Blockstream has positioned cLightning as the go-to client for enterprise deployments. The client is written in C and is very performant.

ACINQ is a startup based in Paris, France that is carving out its own niche within the Lightning ecosystem. Their client, [eclair](https://github.com/ACINQ/eclair) (French for Lightning), is written in Scala so it can run on nearly any platform. They want to build user friendly interfaces and have released an Android Lightning Network client for mobile use.

Two other clients previously under development, [Blockchain](https://www.blockchain.com/)'s [Thunder](https://github.com/blockchain/thunder) and [MIT-DCI](https://dci.mit.edu/)'s [lit](https://github.com/mit-dci/lit) are now inactive. They are not currently being updated to the latest network standards.

### What's next?

The Lightning Network is promising technology, yet still in its infancy. Whether it is able to fulfill on the hype will depend on how successful bitcoin is at continuing to grab the lionshare of the demand for crypto and how well the competition is able to scale. It will also depend on how quickly the user experience can be polished. This is a story that will unfold over the coming years, and will certainly teach us plenty of lessons in how to scale up payments.

Thank you to [caleb tebbe](https://medium.com/@caleb_7708), [Justin Camarena](https://medium.com/@justincamarena), [Linda Xie](https://medium.com/@linda.xie), [Cyrus Younessi](https://medium.com/@cyrus.younessi), and [Jordan Palmer](https://medium.com/@jordanpalmer_26003) for reviewing this post.

_Disclaimer: Jordan Clifford is a Managing Director of Scalar Capital Management, LLC, an investment manager focused on cryptographic and blockchain related assets. Scalar Capital holds a position in Bitcoin._


Thanks to [Linda Xie](https://medium.com/@linda.xie?source=post_page), [Cyrus Younessi](https://medium.com/@cyrus.younessi?source=post_page), [Jordan Palmer](https://medium.com/@jordanpalmer_26003?source=post_page), and [caleb tebbe](https://medium.com/@caleb_7708?source=post_page).
