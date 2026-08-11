---
title: "Bitcoin ideas worth pursuing"
permalink: "/bitcoin-ideas-worth-pursuing"

author: olegandreev

tags:
  - Oleg Andreev
  - 2014 Q3
  - Technology
  - Development

excerpt: Bitcoin ideas worth pursuing. Posted August 1, 2014.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin ideas worth pursuing](https://blog.oleganza.com/post/93530910878/bitcoin-ideas-worth-pursuing)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted August 1, 2014

Here are some ideas for services around Bitcoin that are highly interesting to me.

**1. Truly secure wallet & vault.** Protected from institutional risks, backdoors in software and hardware, losing backups and forgetting passwords. Works on regular computers (phones, laptops). Multisig with blind signatures for privacy. Authenticating with a circle of friends or arbitrary services instead of a single centralized institution. Only this can make people safely invest in Bitcoin and push the entire economies to it unlocking the rest of the features (low fees, autonomous agents, smart contracts etc.)

Btw, I have a working implementation of blind signatures already with a demo app: Code: [https://github.com/oleganza/CoreBitcoin/blob/master/CoreBitcoin/BTCBlindSignature.h](https://github.com/oleganza/CoreBitcoin/blob/master/CoreBitcoin/BTCBlindSignature.h) Paper: [http://blog.oleganza.com/post/77474860538/blind-signatures-for-bitcoin-the-ultimate-solution-to](http://blog.oleganza.com/post/77474860538/blind-signatures-for-bitcoin-the-ultimate-solution-to) Demo app: [https://github.com/oleganza/blindsignaturedemo](https://github.com/oleganza/blindsignaturedemo)

**2. Wallet API for web sites and native apps.** A standard way for any app to request user’s wallet to allocate and sign certain amount of bitcoins to be used in a custom transaction. The unified API would allow maximum flexibility for any sorts of schemes and contracts while preserving user’s keys secure and his financial details completely private. Wallet requests approval from the user and gives the absolute minimum of information to the app. Wallet will also sign its inputs only if all the change outputs are respected. Use case: your app does some fancy scripts and needs user’s coins. Today you have to make your own wallet in which the user must send coins (and you have to reinvent all security measures as described above). Tomorrow you could simply request what you need from an existing wallet without having user to do extra movements.

I helped to develop a draft of the spec: [http://bitcoin-wallet-api.github.io](http://bitcoin-wallet-api.github.io)

**3. Decentralized clearing mesh network for frequent and instant payments.** Similar to Ripple, but without made-up currency and without any trust. Nodes form point-to-point contracts using bilateral 2-of-2 deposits that put a limit on IOUs issued between two nodes. Thus nodes can connect anonymously without any trust. When two people pay each other, they simply find the cheapest path (every node may ask for any fee) between them and propagate an IOU denominated in BTC. There’s no global consensus and no single point of failure. If you owe 50% of the amount deposited, you have to clear the debt with real BTC transaction. Any amount of money can be moved back and forth and all IOUs are 200% insured. This mesh could be used to buy a latte or for one automated service to pay another automated service.

**4. Decentralized markets.** People can use the same bilateral insurance scheme to create a “nash equilibrium” escrow without any 3rd party. This makes free trade possible without risk of fraud or censorship. My friends in San Francisco already have a working prototype that uses Bitmessage to post products and bids. And it works great!

When released, the app will be published here: [http://voluntary.net/](http://voluntary.net/)

**5. Crowdfunding protocol and apps where majority vote controls the funds.** Bitcoin already allows some neat schemes to crowdfund money directly by the founders, but these schemes do not allow for X% (typically 50%) vote to unlock, or otherwise control funds. If that was possible, then founders could still have a comfortable guarantee of funds for their enterprise, but wouldn’t be able to waste them all at once. If their business plan is no longer aligned with the interest of majority of stakeholders, they could take the remaining money back or redirect to entirely different managers. This is a very big thing! If done in absolutely p2p manner, it will enable fantastic possibilities for mankind. For instance, non-targeted crowdfunding will become possible: “someone please repair our road and we’ll pay you $5000”. The funds can be directed to the guys who solved the problem by a majority vote of the backers (unless all backers turn out to be total jerks, of course).

The problem with modern corporations is that they are de-jure owned by stakeholders, but the real power to make decisions is on managers who are hired to manage the capital. In other words, it is really hard for thousands of small stakeholders to coordinate and affect decisions of the top management. More strict crowdfunding protocol with direct democracy built in would allow all stakeholders, small and large, to better control the flow of funds.

***

{% include signup.md %}
