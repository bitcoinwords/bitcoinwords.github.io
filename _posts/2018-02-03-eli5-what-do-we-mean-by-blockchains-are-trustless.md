---
title: "ELI5: What do we mean by “blockchains are trustless”?"
permalink: "/eli5-what-do-we-mean-by-blockchains-are-trustless"

author: preethikasireddy

tags:
  - Preethi Kasireddy
  - 2018 Q1
  - Economics
  - Money
  - Technology

excerpt: "ELI5: What do we mean by “blockchains are trustless”?. Posted February 3, 2018."

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [ELI5: What do we mean by “blockchains are trustless”?](https://medium.com/@preethikasireddy/eli5-what-do-we-mean-by-blockchains-are-trustless-aa420635d5f6)
### By Preethi Kasireddy
### Posted February 3, 2018

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless1.jpg)

Source: [https://libcom.org/library/consensus-its-discontents](https://libcom.org/library/consensus-its-discontents)

#### Intro

Many of us are guilty of describing blockchains as “trustless” systems. However, I’ve come to realize that the term “trustless” is ambiguous, confusing, and most importantly, inaccurate.

Blockchains don’t actually ***eliminate*** trust. What they do is ***minimize*** the amount of trust required from any single actor in the system. They do this by ***distributing*** ***trust*** among different actors in the system via an economic game that incentivizes actors to cooperate with the rules defined by the protocol.

Let me explain in more detail.

A truly trustless transactional system would look something like this:

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless2.png)

Two people who are interested in transacting with one another change hands directly. They are physically present, and therefore can easily verify

1. **Authenticity**: the actual sender is handing over the money, and
2. **No double spending:**the money is not fake, it’s a real $10 bill

While theoretically flawless, this transactional system is limited. Consider: two individuals may trade with one another only when they are in close physical proximity. For economies to function at scale, a transactional system should enable transfers with anyone in the world, regardless of distance.

So, what we really want is this:

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless3.png)

As you can see from the diagram above, the way we achieve this aim is by having an intermediary who can facilitate the transfer of value to make sure that the actual sender is sending the money and the money is real.

This begs the question: who serves as the wholly trustworthy intermediary?

In modern day transactional systems, the intermediary can be a bank (e.g. Chase Bank); a payment provider (e.g. Paypal); a remittance company (e.g. Western Union); a credit card (e.g. Visa), and so on.

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless4.png)

In this centralized model, the bank authenticates you, and guarantees the recipient that they are getting real money.

In other words, unless there is a direct physical transfer of value from one individual to the other, there must be some intermediary that exists that we *“trust”.*

Blockchains are no different.

Blockchains define a protocol that allows two individuals to transact with one another in a “peer-to-peer” manner over the Internet. When you digitally transfer value from one account to another on the blockchain, you’re trusting the underlying blockchain system to both enable that transfer and ensure **sender authenticity** and **currency validity**.

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless5.png)

In a “centralized” system, we trust a single third party (e.g. Chase Bank) to act as the intermediary who guarantees those two properties; in a “decentralized” system, our trust is placed elsewhere, namely in **public-key cryptography** and a **“consensus mechanism”**that allows us to determine the truth.

#### Public-Key Cryptography

Public key cryptography (or asymmetrical cryptography) uses:

1. a set of public keys visible to anyone, and
2. a set of private keys visible only to the owner

The private key generates a “digital signature” for each blockchain transaction that a user sends out. The signature ensures **authenticity** by:

1. confirming that the transaction is coming from the user, and
2. preventing the transaction from being altered by anyone once it has been issued

Changing the transaction message in any way will cause verification to fail.

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless6.png)

Okay, so we’ve figured out that public-key cryptography helps us authenticate users in a peer-to-peer system. But to ensure **no double spending**, we need to keep track of who has what so that we can know whether someone is sending real digital money or fake digital money.

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless7.png)

This is where the “**consensus system”** — which allows us to preserve a digitally shared truth — must come into play.

#### Machine Consensus (The Cryptoeconomic Protocol)

Blockchains have a shared ledger that gives us the absolute truth of the state of the system. It use mathematics, economics, and game theory to incentivize all parties in the system to reach a “consensus”, or coming to an agreement on a single state of this ledger.

Let’s take Bitcoin, for example. The Bitcoin protocol has a consensus algorithm called “Proof of Work” that holds the system together. For a transaction to be settled between two consumers, the algorithm requires that a set of nodes (called “miners”) compete to validate transactions by solving a complex algorithmic problem. In other words, Bitcoin “economically incentivizes” miners to purchase and use compute power to solve complex problems. These economic incentives include:

1. miners earning a transaction fee that users pay for carrying out a transaction, and
2. miners earning new Bitcoins for successfully solving the puzzle

Because of these economic incentives, miners are constantly watching the network so that they can gather a new set of transactions to fit into a new “block.” Then they use their computing resources to solve the complex algorithm in order to “prove” that they did some work.

The first miner to solve the algorithm adds the proof and the new block (and all the transactions in it) to the blockchain and broadcasts it to the network. At that point, everyone else in the network syncs the latest blockchain because it’s a “truth” everyone believes in.

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless8.png)

Since miners are competing to run computations, there are times when multiple blocks get solved at the same time. This then creates a “fork” of multiple chains:

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless9.png)

When there are forks like this, the network’s “canonical” chain is the one which is the “longest” — the one which the most amount of miners trusted and continued to work on.

![](/assets/images/2018/m2/eli5-what-do-we-mean-by-blockchains-are-trustless10.png)

Every new block that’s added to the blockchain in this manner adds more security to the system because an attacker who wants to create new blocks that overwrite a party of history would need to consistently solve for the puzzle faster than anyone else in the network. This is practically impossible to do, making it’s impossible to reverse engineer or alter the data inside these blocks. This is why users trust continue to trust the system.

So when we transact with one another on the blockchain, we are***anchoring our trust***in the miners who are giving up their resources to do some work to ensure no double spending.

#### Social Consensus (Governance)

Of course, even if the machine consensus works perfectly, we can never guarantee a 100% probability of reaching consensus on other important aspects required to maintain trust in the network. For example, when the underlying network needs to be upgraded, improved, or repaired, we need some way to trust that the network and all its constituents can appropriately handle the changes. In such cases, it’s very much a coordination effort amongst constituents, or what I would call a “social consensus” (e.g. governance).

For example, if the blockchain requires an improvement (e.g. better transaction logs), we need a governance mechanism that coordinates the interests of all parties involved (users, developers, investors, etc.) in coming up with the best solution. Or if there’s a controversy on the best path forward (e.g. a contentious fork), then a community needs to form a consensus on what to do next. If an agreement can’t be reached, the network forks, and people are forced to choose one side over another instead of everyone believing in a shared truth. Users would lose trust in the system because they would be unable to reasonably determine which chain was the “valid” chain.

As I described in a [previous post](https://medium.com/@preethikasireddy/fundamental-challenges-with-public-blockchains-253c800e9428) (bullet #6), there are many different models for blockchain governance and it remains an area of active research in the community. Blockchain governance is an incredibly tricky problem and finding a balance between centralized and distributed control will be essential to maintaining everyone’s trust in the system.

#### Conclusion

**When we say blockchains are “trustless,” what we mean is that there are mechanisms in place by which all parties in the system can reach a consensus on what the canonical truth is. Power and trust is distributed (or shared) among the network’s stakeholders (e.g. developers, miners, and consumers), rather than concentrated in a single individual or entity (e.g. banks, governments, and financial institutions)**.

Perhaps a more accurate way to describe blockchains is not as “trustless,” but as built on the basis of ***distributed trust:*** ***We are trusting everyone in aggregate.***

Of course, this assumes that we trust that a majority of the power held in the system belongs to stakeholders who share similar values. Unfortunately, I don’t think we can claim — at least, not yet — to have figured out exactly what those shared values consist of. Hence the proliferation of blockchains and contentious forks in the past year … but that’s a long-winded topic for another day! 😊

***

{% include signup.md %}
