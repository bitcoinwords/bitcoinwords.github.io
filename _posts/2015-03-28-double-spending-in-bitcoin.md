---
title: "Double spending in Bitcoin"
permalink: "/double-spending-in-bitcoin"

author: mikehearn

tags:
  - Mike Hearn
  - 2015 Q1
  - Mining
  - Money
  - Security

excerpt: Double spending in Bitcoin. Posted March 28, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Double spending in Bitcoin](https://medium.com/@octskyward/double-spending-in-bitcoin-be0f1d1e8008)
### By Mike Hearn
### Posted March 28, 2015

### Double spending

### in Bitcoin

and how to make it harder

In this article I will discuss double spending against merchants in Bitcoin, analyse a couple of real cases and describe several proposed schemes to make it harder. I’ll also explain the plan we’re implementing in the bitcoinj project that I lead.

This article is intended for Bitcoin wallet developers and payment processors.

First off, how big of a problem is double spending?

#### Double spending in the real world

##### GHash.io

There are several ways to do double spending in Bitcoin. One is to get a miner to unwittingly help you commit fraud. Another is to actually be such a miner. In November 2013 it was discovered that the GHash.io mining pool [appeared to be engaging in repeated payment fraud against BetCoin Dice](https://bitcointalk.org/index.php?topic=327767.0), a gambling site. Dice sites use one transaction per bet and don’t wait for confirmations.

GHash.io claimed they had investigated and found a rogue employee who had been doing the double spending, who was fired. However no evidence supporting this was provided and the incident left a permanent cloud hanging over the pool. Regardless, it didn’t seem to hurt their market share much: most miners probably never heard about the incident at all.

##### Eligius

The Eligius pool implements a transaction check called “is notorious” on top of the normal “is standard”. A notorious transaction is one that sends money to addresses associated with things that the pool’s owner (Luke Dashjr) considers to be “non-transactional data spam”. The list of addresses that trigger this [can be found here](https://gitorious.org/bitcoin/luke-jr-bitcoin/commit/f4bb6e1501e6a624b751334ff20098c1dd2d509f). When it finds a notorious transaction the pool ignores it and acts like it was never broadcast: this means that by making a transaction that spends to both a merchant and a notorious address simultaneously, the mempool becomes inconsistent between Eligius and everyone else. A double spend can then be submitted directly to Eligius and if they find the block, the original transaction will be killed.

This exploit has been used to engage in double spending against a merchant that was performing a kind of quasi-exchange service. After the merchant implemented a recursive dependency check that detected the “notorious” transactions, the fraudster tried a couple more times, then gave up and went away.

The Eligius operators don’t actually want to help criminals commit payment fraud. The fact that they do is due to the way the transaction filtering patches were implemented. Luke Dashjr has told me he would accept code to fix this but isn’t going to fix it himself. Unlike most pools, Eligius and Luke are serious about decentralisation and are working on the *getblocktemplate* system, which lets miners pool without giving up control over transaction selection policies. So it’s possible that this policy will fade away over time, unless Eligius’ miners decide collectively to continue enforcing it as a group.

The above two cases are the ones I am most familiar with. The details of the second have been elided at the request of the parties involved. There’s probably more double spending going on that isn’t publicly discussed, but it seems rare enough to not be a major topic as of March 2015. I check in with payment processors and other merchants every so often to ask them about double spending: they tell me it’s not a problem for them right now.

There *are* plenty of double spend attempts happening on the Bitcoin network. But it seems like lots of them are tests, or people trying to bump the fees on their own transactions (the correct fix for this is [child-pays-for-parent](https://github.com/bitcoin/bitcoin/pull/1647)).

But let’s assume it gets worse and look at a series of proposed solutions for the double spending problem:

1. Risk analysis of transactions
2. Payment channels
3. Countersigning by a trusted third party
4. Remote attestation
5. ID verification
6. Waiting for confirmations
7. Punishment of double spending blocks

#### 1. Protocol risk analysis

It’s worth noting that the second case of double spending using Eligius is based on a protocol exploit: Eligius doesn’t use the same memory pool code as everyone else, but the rules it does use are public and quite easy to check for.

There were two giveaways that something was wrong:

1. A chain of transactions with a free transaction at the bottom. This ensures that there is as much time as possible for Eligius to find a block.
2. A transaction that pays to a “notorious” dice address.

Both of these things are easily checked for by quite simple code, which is why the merchant was able to kick the fraudster out so quickly.

This trick generalises: most memory pool differences between miners are due to version skew. Bitcoin Core releases a new version that changes the rules, and some miners upgrade quickly whilst others are slower. In the intervening time it becomes possible to exploit these differences. But the differences are often in quite obscure details that don’t crop up in regular usage. Wallets that are being kept up to date can detect transactions that are hitting the rule change and flag them as needing confirmations.

Given the types of double spending that seem to be reported today, I think it’s likely that protocol risk analysis could detect virtually all of them.

##### Double spend relaying

The best way to learn about a double spend is of course to see it for yourself. If you see it quickly enough, you can abort the trade before handing over anything of value.

That’s why Gavin Andresen and Tom Harding have implemented *double spend relaying*. This is a change to Bitcoin that makes nodes relay the first double spend of any given transaction that they see (but not others, in order to conserve bandwidth).

Both the Bitcoin Core wallet and the next release of the bitcoinj wallet know how to inform the user of conflicting unconfirmed transactions. BitcoinJ already tells you when an unconfirmed transaction is “killed” by a double spend getting confirmed, but informing the user as soon as the double spend is broadcast will go a lot further.

Double spend relaying didn’t get into Bitcoin Core because of endless arguments about whether attempting to fight double spending is pointless, but I integrated it into my [Bitcoin XT](https://github.com/bitcoinxt/bitcoinxt) patch set so anyone who wants to help relay double spends can help out by using XT instead of Core. Just make sure you stay up to date.

Bitcoin XT is still new and I haven’t done any promotion of it yet. There are [deterministic code signed builds for Windows, Mac and Linux](https://github.com/bitcoinxt/bitcoinxt/releases). They share data directories so if you can run Core you can easily switch back and forth: re-downloading the chain is not required.

The next major release of BitcoinJ has support in it for finding and connecting to Bitcoin XT nodes specifically, so people building on this library will be able to very quickly get access to an improved view of double spends on the network.

##### Risk analysis in bitcoinj

Most wallets don’t do protocol risk analysis today. BitcoinJ [has some code to do it](https://github.com/bitcoinj/bitcoinj/blob/master/core/src/main/java/org/bitcoinj/wallet/DefaultRiskAnalysis.java), but it’s not exhaustive. For instance it does not check for attempts to exploit Eligius.

It would make sense for someone to build a standalone server that uses this framework to risk analyse unconfirmed transactions and export the results over HTTP (using JSON-RPC, protobufs or both). If built on top of bitcoinj then we would have merchant-oriented hot wallets and client side SPV wallets using the same code to perform their risk analysis, and the pooled effort would be much more effective.

**Call to action:**If anyone is interested in this project, please join the bitcoinj mailing list and ask about it. I will be happy to point you in the right direction.

#### 2. Payment channels

A *payment channel* is a construct using [a contract protocol that I described in 2011](https://en.bitcoin.it/wiki/Contracts#Example_7:_Rapidly-adjusted_.28micro.29payments_to_a_pre-determined_party), with later tweaks from Jeremy Spilman. The original description doesn’t use the channel terminology: I think that is something I started using later when myself and Matt Corallo built an implementation of the scheme in bitcoinj.

Briefly, the idea behind a payment channel is that you lock up some value in a multi-sig contract with the seller, in such a way that all the value starts out by being sent back to yourself. This step involves broadcasting a transaction on the Bitcoin network. Then you begin a negotiation in which you send progressively better transactions (for the seller) privately without using the P2P network. The typical use case is micropayments: each time you buy a micro-service like a kilobyte of bandwidth or second of someone’s time you send them a new transaction that allocates slightly more money to them than before. Eventually the buyer signals to the seller that they’re done negotiating and the channel should be settled on the P2P network: the final state is broadcast and the channel is *closed*.

It was observed early on that this scheme allows for a kind of hub-and-spoke system in which networks of channels between payment processors route payments between entities without needing to touch the block chain. From there it’s easy to observe that if you have a payment channel pre-established some time ago you can’t double spend as the transaction which opened the channel is already confirmed.

I’m a big fan of payment channels for micropayments and in fact have implemented [a demo of using them to pay for file downloads](https://www.youtube.com/watch?v=r0BXnWlnIi4). I am less keen on the idea of using them to fight double spends for these reasons:

1. The payment channel protocol is complicated. Making a basic implementation is not too bad, but handling all the edge cases is a lot of work. The code in bitcoinj handles cases like one of the parties disappearing during the contract without formally closing the channel, serialising the state of the channel to disk so it can survive app restarts and so on. So far I believe that only bitcoinj has a production-ready implementation of payment channels. Asking *all* wallets to implement this protocol seems extreme: wallet authors are already maxed out just handling the complexities of the current Bitcoin protocol, let alone complex multi-step contract protocols on top.
2. Worse: even once all the protocol edge cases are handled, users don’t want to know about the details of how their payments are being handled. So build, usage and teardown of channels all has to be entirely transparent in the user interface. That adds even more complexity.
3. If only some wallets implement this scheme rather than all of them, the merchant still wants to accept plain old broadcast transactions. So payment fraudsters would just claim to be using a wallet that doesn’t support that feature, and it’d have little impact.
4. If you don’t have a payment channel with the merchant or payment processor, or a path through the hub-and-spoke network, then you would have to build such a channel first. This would require waiting for a confirmation (otherwise why bother) and so in practice, the user would sometimes still end up waiting. Avoiding waits is the goal of accepting unconfirmed transactions.
5. Payment channels tie up the users funds in ways that can be unintuitive. If you have money sitting in a channel and then want to use it to buy something from a non-channel-using merchant, you must close the channel, which requires going back to the first entity and asking them to close the channel for you. If they’re gone or unresponsive, now you have to wait for the channel to naturally expire. Explaining what’s happening to users in this case is …. difficult.

It’s also worth noting here that payment channels are subject to a malleability attack. However fixing transaction malleability is already being worked on: because payment channels are so complex, by the time any implementation of it had interesting levels of deployment I think the anti-malleability work would be done already.

#### 3. Countersigning by a trusted party

GreenAddress.it has proposed a scheme whereby multi-signature coins are owned by a combination of the user and a trusted wallet server. When a payment is made the wallet server signs a statement asserting that it won’t allow double spending of the used outputs.

In practice this means signing the BIP 70 Payment message with some key that is identifiable as coming from a particular trusted third party (TTP); the PKI is a good way to do this.

Whilst this technique is simple and would work, it effectively brings back elements of the old banking model with its known disadvantages:

1. Users who don’t have a relationship with a TTP would be out of luck.
2. The coins must be 2-of-2 because if the user could sign with a key they exclusively controlled, the extra protection wouldn’t work. GreenAddress tries to mitigate this by providing time locked transactions so if they go away or blacklist you, you will eventually get the coins back. This is a neat solution. But it’s something no other provider has adopted and I’m not sure how the tools situation looks.
3. Merchants have to learn about and evaluate TTPs. They must then configure their system to recognise those TTPs. Then Bitcoin users must also find a TTP, evaluate them, pick one and configure their coins. This is sticky and would give existing incumbents an inertial advantage.
4. Ideally there would be a way to automatically distribute a fraud proof and revoke the TTP if it misbehaved, but this isn’t specced.

This approach is in some ways like a network of non-anonymous miners that use regular signatures instead of PoW-style “signatures of effort” (Blockstream calls them “dynamic membership multi-party signatures”). But the current Bitcoin structure has quite a few advantages, namely that mining is a very liquid market. Ideally we’d do our best to keep that and fall back to the more traditional scheme only if we can’t make Satoshi’s more novel approach work reliably.

#### 4. Remote attestation

A variant of the GreenAddress scheme is to use trusted computing with remote attestation instead of a trusted wallet company.

Trusted computing is a feature of modern chipsets. The CPU or TPM chip signs a statement saying “I am a real piece of hardware manufactured by X and I am running software Y”. Remote attestation is a complex technology and I’m glossing over a lot of details, but to sum up — it would allow your computer to prove to another that it’s not double spending.

In effect, the manufacturer of your computer becomes the trusted third party, except one that doesn’t even know it’s doing so because the entire process is run entirely locally with no servers required.

The problem with TC is that the implementations shipped by AMD, Intel and ARM all suck, and actually building a computer capable of remote attestation is an exercise in frustration. The technology is currently targeted only at the server market and requires exceptionally good systems programming skills to utilise.

Intel are working on a new iteration of the idea called SGX. SGX is looking a lot more promising than the existing technologies based on the documentation they’ve published so far. Unfortunately, SGX is currently vapourware: beyond some technical docs, a scientific paper from Microsoft and a handful of blog posts nothing else about it is available. It seems likely to be several years before an SGX based solution becomes workable. And unfortunately whilst ARM TrustZone is widely deployed in mobile phones it apparently can’t do remote attestation. So it seems likely that only desktop wallets will be able to pull off this trick in the forseeable future.

Even if implemented this scheme has the same problem as all the others: if not all users can do it, then payment fraudsters will just pretend they don’t have the right setup and double spend with plain old transactions. Unless almost all transactions were being counter-signed in this way it wouldn’t be feasible to restrict regular old-style transactions and the benefits wouldn’t appear.

#### 5. ID verification

A very simple approach to fighting double spending is to just do what credit card accepting merchants already do: incrementally more aggressive ID verification of buyers depending on how much of a fraud problem there is. For example some payment processors in the credit card space use IP address profiling, billing/delivery address matching, Javascript, evercookies etc to try and catch repeat fraudsters. In extreme cases users can be blocked outright, or asked to submit documents.

This approach is simple and well tested, but of course, highly inconvenient for the buyer. Sufficiently advanced technology can make it much less inconvenient, but ideally this will never be needed because regular transactions will work well enough.

#### 6. Waiting for confirmations

This one might seem too obvious to mention. If you can wait for confirmations, ideally you would. Unfortunately often merchants don’t do so, even in cases you’d intuitively expect would be possible like shipping items from a warehouse.

I suspect the main reason is that existing business workflows are based on the assumption that payments take only a few seconds and double spending is revealed weeks or months later. This is the model used by credit cards. It’s not unheard of for chargebacks to roll in 4 or 5 months after the original payment, long after the goods have shipped. Delays of many weeks are more common as it takes time for people to get and check their statements. So outside of things like holidays or flight tickets, most merchants just have to accept credit card double spending as a business risk and price it in: they can’t usually undo a sale before the goods or services have been provided because credit cards are too slow.

So paradoxically even though Bitcoin can reveal that a double spend took place within minutes rather than months, these businesses cannot use the new information as they have no tools or procedures in place to do so. By the time the block chain makes a decision the merchant was already informed of the payment, databases have been updated, the orders dispatched to the warehouses, the email receipt has been sent etc. Being able to undo a purchase requires software and procedures they don’t have.

Businesses could fix that by making the user sit on the invoice screen for a couple of blocks, but that interrupts the users flow and would make Bitcoin feel much slower than credit cards, even though in a sense it’s actually much faster. So they just accept unconfirmed transactions via BitPay or Coinbase and enjoy the fact that double spending against them is still very rare anyway.

#### 7. Punishment of double spending blocks

The purpose of mining is to prevent double spending by recording the chronological order of transactions as accurately as possible. Miners that execute Finney attacks to defraud sellers are not doing that; they’re charging the collective Bitcoin community money via the inflation subsidy for a service they aren’t actually providing.

Normally when an entity charges you for something and then doesn’t provide it, there are consequences. The consequence for a miner trying to fork the chain and undo confirmed transactions is that they stand a good chance of losing the electricity (i.e. money) they used to mine: this is a good incentive to behave. For Finney attacks there are no consequences.

Tom Harding has been researching the possibility of identifying blocks that appear to be engaging in Finney attacks and making a slight alteration to the first seen rule for blocks. Of course, this rule is critical for Bitcoin’s operation so changes to it are not to be taken lightly at all. He has written [a paper on his proposed change to the rules](https://github.com/dgenr8/out-there/blob/master/ds-dep-win.md) which features a lot of analysis of the potential impacts. His goal is to give more certainty for transactions after about thirty seconds has passed.

I have not had time to thoroughly read or analyse this proposal and so have no strong opinion on it. That said, it’s unclear to me that 30 seconds is significantly better than ten minutes: I suspect the utility dropoff after about 5–10 seconds is dramatic given the desired “guy in queue paying for coffee” type user experience. 30 seconds is probably OK on the web but it would still make us far slower than EMV contactless credit cards for in person transactions.

#### Breaking 0-conf transactions

There’s a school of thought that says if something cannot be done perfectly, maybe it should not be done at all. If unconfirmed transactions are not bulletproof, these people reason, perhaps they should be entirely useless so nobody relies on them and then gets burned.

This line of thinking is one of the reasons that double spend relaying is not integrated into Bitcoin Core and has to be made available via Bitcoin XT instead.

The problem is that in the entire history of money there have been no fraudless payment systems, ever. Bank wires get reversed, credit cards are charged back, cheques bounce, bank notes are counterfeited and blocks are reorganised. If people were being routinely “protected” from imperfect payment systems they would be unable to trade at all. So in practice all trade involves double spending risk and businesses learn how to manage that risk with acceptable overheads.

Bitcoin is no different: it just involves a different sets of risks and management techniques. As of 2015, many merchants have decided that the risk:reward ratio of accepting unconfirmed transactions is worth it. So trying to break them in order to protect people makes about as much sense as forging $100 bills to educate merchants about the dangers of paper money. Not only is it logically nonsensical and harmful to innocent people, it’s also illegal.

But this idea fails for another reason. Although it’s always tempting to deal with potential problems by simply scrapping the feature that has them, this isn’t an option for Bitcoin:

1. Almost all online merchants today are accepting unconfirmed transactions, because that’s the default for BitPay, Coinbase, Coinify and other payment processors.
2. Physical shops need them.
3. Newer apps are often hiding or reducing the visibility of confirmations as a concept, because it’s hard to explain what this actually means to end users.

Based on my own experience of buying and selling things with Bitcoin the only sellers that make you wait for blocks are exchanges.

So whether we like it or not, the block chain algorithm as currently specified is not a solution for all payments and denying that won’t get us anything except market irrelevance. Finding ways to optimise the current system in backwards compatible ways is a reasonable and pragmatic path forward … and nobody will blame us for trying our best.

***

{% include signup.md %}
