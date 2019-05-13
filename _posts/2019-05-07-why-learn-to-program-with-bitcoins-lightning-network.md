---
title: "Why learn to program with Bitcoin's Lightning network?"
permalink: "/why-learn-to-program-with-bitcoins-lightning-network" 

tags:
  - Pierre Rochard
  - CY19 Q2

excerpt: Very simple fundamentals on why you should pick up Lightning Network. Posted by Pierre Rochard on May 7, 2019. 

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

# Why learn to program with Bitcoin's Lightning network?
### By [Pierre Rochard](https://medium.com/@pierre_rochard)
### Posted May 7, 2019

## Send and receive payments

Enabling payments in your software is often a business necessity

Common consumer web application use cases include:

1. Receiving SaaS revenue
2. Payments between marketplace participants, including escrow
3. In-app purchases for premium features

Until now, the only choice for developers has been integrating proprietary, trusted, centralized, third-party digital credit systems like PayPal or Stripe.

Bitcoin's Lightning network offers developers an open source, trustless, decentralized, self-hosted digital cash system.

## What is Bitcoin's Lightning network?

The Bitcoin digital cash system uses proof-of-work over time to provide transaction finality. This proof-of-work function is currently paid for by new cash emission and transaction fees. Full verification of every transaction is necessary for users to trustlessly determine that the expected cash emission schedule to 21 million bitcoins is correctly being followed. To keep the cost of full verification reasonable, the system's consensus rules have a number of resource-usage limits.

Bitcoin's scaling challenge is to maximize the efficient use of its limited resources. One approach is to transfer cash by privately updating one transaction many times "off-chain" before publicly broadcasting the last version of the transaction for final settlement "on-chain".

Off-chain updates to transactions instantly transfer cash, and the cost of on-chain transactions are amortized over many off-chain updates. Lightning is an off-chain scaling protocol, often called "layer 2" or "state channels". Peers on the Lightning network send cash payments to each other by updating Bitcoin transactions.

Lightning uses smart contracts (spending conditions) embedded in Bitcoin transactions to prevent cheating by a malicious peer broadcasting a superseded version of a Bitcoin transaction.

Payments are instant and inexpensive, with a few manageable trade-offs:

* Your server should have high uptime. For almost all web applications, this was already the case.
* You must secure a hot wallet. For services that already send cash with on-chain transactions, this is not a new requirement. To minimize risk, cash can be regularly transferred from the hot wallet to a cold wallet.
* You must continuously backup Lightning data. This is a new requirement as on-chain wallets only need to be backed up once, but it is easy to implement. Almost all applications already have data which needs to be continuously backed up.

With these conditions met, Lightning is a subset of the Bitcoin digital cash system and thus shares its trustlessness and sound monetary properties.

For most software developers, using off-chain Lightning payments to enable sending and receiving cash in their application is a strict improvement over using on-chain transactions for the same purpose.

## Digital Cash

Legacy solutions are trusted, centralized credit systems

Lightning is a trustless, decentralized cash system

* No counter-party credit risk
* No personally identifiable information is required
* No need to securely store other people's credit card numbers
* No charge-backs

## **Open Access**

Lightning is self-hosted

* No need to "apply" for an account
* No unexpected account closures
* No bank holidays
* No geographical limitations

You don't need to ask for permission to use the Lightning network

## Open Source Bazaar

The Lightning protocol and implementations are open source and being developed in public. Any developer is welcome to contribute to the lightning-rfc GitHub repository, which is home to the protocol spec:

[**lightningnetwork/lightning-rfc** _Lightning Network Specifications. Contribute to lightningnetwork/lightning-rfc development by creating an account on..._ github.com](https://github.com/lightningnetwork/lightning-rfc/pulls "https://github.com/lightningnetwork/lightning-rfc/pulls")

Discussion of changes is open to the public, you are free to participate as much or as little as you want.

There are no executives or salespeople forcing their decisions on developers, but a business perspective is very helpful for developers working on a cash payments system.
