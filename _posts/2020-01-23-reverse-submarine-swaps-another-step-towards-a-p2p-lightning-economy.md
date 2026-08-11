---
title: "Reverse Submarine Swaps: Another Step towards a P2P Lightning Economy"
permalink: "/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy"

author: roysheinfeld

tags:
  - Roy Sheinfeld
  - 2020 Q1
  - Economics
  - Money
  - Monetary Policy

excerpt: Reverse Submarine Swaps: Another Step towards a P2P Lightning Economy. Posted January 23, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Reverse Submarine Swaps: Another Step towards a P2P Lightning Economy](https://medium.com/breez-technology/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy-bacb040fdca7)
### By Roy Sheinfeld
### Posted January 23, 2020

In any evolutionary process, members of each new generation keep some of their ancestors’ traits and gain some new — hopefully improved — ones. When looking at the system of fiat money, there are some traits we’d like to keep while surpassing the rest. For example, fiat is universally acceptable. It’s *the*medium of exchange. The UX is also hard to beat. It’s what users are accustomed to and expect.

![](/assets/images/2020/m1/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy1.jpg)

*Don’t hate your ancestors; learn from them. (Source:Wikimedia)*

We’d like to preserve both of those traits in the Lightning economy. But there are also several features of the fiat system we’re actively working to surpass, in particular its ***centralization*** and its reliance on ***trust***.

## (De)Centralization

The fiat system is roughly hierarchical. The mints, central banks, and regulators are at the top. They issue the currency, set the terms of its use, and define who can participate in the system and how. Then come the “systemically relevant” (i.e. too-big-to-fail) financial institutions, including banks, credit card companies and such, which distribute and circulate the fiat.

Those at the top of the hierarchy like this centralized structure because big, isomorphic entities are easier to control than a rich ecosystem of smaller-scale innovators. The problem with this system is its abundance of [choke points](https://medium.com/breez-technology/why-bitcoin-needs-to-become-a-medium-of-exchange-80d5c9e1de65).

Choke points are a problem, first of all, because they make the system more vulnerable. The more centralized a network is, the more it relies on a few key nodes/edges, which are simultaneously the natural targets for an attack and sources of internal instability.

Second, choke points foster censorship in centralized systems. Censorship doesn’t have to mean some Orwellian scheme in a surveillance state (though it can!). It can simply mean any third-party interference between peers on the network. Those at the top of the fiat hierarchy can’t do much about billions people worldwide exchanging bitcoin on a P2P basis, but impeding mass adoption by squeezing a few regional operators is both viable and potentially profitable.

![](/assets/images/2020/m1/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy2.png)

*Or, as I like to call them, “Meh,” “Better,” and “Best.” (Source:Wikimedia)*

[LSPs](https://medium.com/breez-technology/introducing-lightning-service-providers-fe9fb1665d5f), done right, solve both problems. As [a network of dozens, hundreds, thousands of LSPs](https://medium.com/breez-technology/envisioning-lsps-in-the-lightning-economy-832b45871992), Lightning will be robust. No single LSP will be able to decide the fate of the whole. And from the perspective of potential censors or regulators, the network will appear more like a reality to be reckoned with than a cow to be penned and milked. If there’s an LSP in every neighborhood, it would be like regulating cats. The more LSPs we have, the more our decentralized network will look and work like a distributed one, and the more bitcoin, Lightning, and each individual user will be able to resist censorship.

## How Much Trust Do We Want?

Trust sounds like a good thing, and it often is. It’s a sign of things like love, reliability, honesty, and integrity. Because it’s so precious, trust should be handled carefully. The more a relationship relies on trust, the stronger the bond will be, and the greater the risk of those involved getting hurt one way or the other.

![](/assets/images/2020/m1/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy3.jpg)

*When trust is violated…*

![](/assets/images/2020/m1/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy4.jpg)

*…people get hurt. (Source:acosmicfragment)*

Indeed, regulators agree. That’s why special regulations apply to the institutions users have to trust when dealing with fiat, like banks, investment firms, insurance brokers, and so on. Whoever is entrusted with users’ money is liable for it, as they should be. Users have *entrusted* it to them.

So there are two reasons for us to avoid relying on users’ trust:

1. We don’t want to be in a position to lose users’ money and violate their trust.
2. We don’t want regulators getting any more involved in bitcoin than necessary. They bring higher costs, slower operation, more choke points and more centralization — in other words, less bitcoin.

If you ask me how much trust is right for the Lightning economy, the answer will always be *less*.

That’s why we’ve always used Submarine Swaps to help users top up their Breez balances from their on-chain wallets. Submarine Swaps use [HTLCs](https://blog.muun.com/a-closer-look-at-submarine-swaps-in-the-lightning-network/) like any other Lightning transaction, so they’re as trustless as any peer-to-peer Lightning transfer. No violation, no regulation.

![](/assets/images/2020/m1/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy5.jpg)

*The face of a user nervously waiting for his funds to show up in his on-chain wallet. It’s okay. You can relax now. (Source:pxhere)*

Until recently, however, trust has been required for transactions in the other direction. To move funds from their Breez balances to an on-chain wallet, users have had to send us the funds and the address of the on-chain destination, and we transferred the funds for them, eating the fees for the on-chain transaction. Users had to trust us to broadcast an on-chain transaction. It was only lasted a moment, but still we had access to the users’ funds, and we could have potentially violated their trust.

That’s why we’ve changed how transactions work between Breez and on-chain addresses. Now they use HTLC-based *reverse* Submarine Swaps, with the same privacy and autonomy users deserve and expect.

## The Nuts and Boltz of Reverse Submarine Swaps

To provide this service, we’ve joined forces with [Boltz](https://boltz.exchange/), an awesome non-custodial exchange run by like-minded crypto developers. Together, we’re developing a reverse Submarine Swap service that works seamlessly with all of Breez’s other great functions.

And since no introduction of a new Lightning function would be complete without Alice, it’s time for her big entrance, with Breez playing the role of Bob and Boltz standing in for Carol:

1. Alice opens her Breez client and wants to send her funds to an on-chain address. She enters the desired amount and the destination address. Behind the scenes, her client also creates a preimage and sends its hash to Boltz.
2. Boltz creates a [hodl invoice](https://wiki.ion.radar.tech/tech/research/hodl-invoice) using the preimage hash and returns it to Alice.
3. Alices pays the hodl invoice *in Breez* (Yes! Breez now has seamless support for hodl invoices!). This transaction is held by Boltz without being settled yet because Alice’s preimage is required for settlement.
4. Boltz broadcasts an on-chain transaction using a script that requires Alice to reveal her preimage in order to claim the funds.
5. After the “lock” transaction is confirmed, Breez prompts Alice to open the app and claim her funds. Another on-chain transaction is broadcast by Breez to claim the funds and send them to the on-chain address Alice had previously specified. At this point, Alice must reveal her preimage to Boltz (since it’s a part of the broadcasted transaction).
6. Boltz uses the revealed preimage to settle the Lightning payment they’ve received from Alice.

Alice’s funds are transferred, but she never loses custody, and she never has to rely on trust.

![](/assets/images/2020/m1/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy6.jpg)

*“Drink Me? I just found it in a pit! And it’s not even certified organic!” Alice is learning about trust. Way to go Alice! (Source:pxfuel)*

The advantage of integrating [Boltz service](https://medium.com/boltzhq/brewing-boltz-hold-reverse-swaps-fea0fadbf041) is that they’re non-custodial like us, which also means that they too evade much of the custody-regulation spiral. And since [Boltz is open source](https://github.com/BoltzExchange), just [like Breez](https://github.com/breez), users don’t need to trust the code. They can *audit it*.

In the old, trust-based withdrawal procedure, Breez carried the cost, because charging people for their trust is a path to supervillainy. Boltz provides a valuable service that carries a fee, part of which is just the regular mining fee to process an on-chain transaction (the “lock” transaction fee) and another part (0.5%) goes to Boltz for committing capital and operating Lightning nodes.

How does it look in practice? Simple, elegant, functional, seamless — like everything in Breez:

![](/assets/images/2020/m1/reverse-submarine-swaps-another-step-towards-a-p2p-lightning-economy7.jpg)

For all the improvements to its architecture, there is one thing Lightning seriously needs: transactions. After all, we’re not building a *model* network for bitcoin payments. Lightning is the *real thing*. Increasing the transaction flow will induce a chain reaction of other benefits, like more routing possibilities and more liquidity. For that to happen, the chain-to-Lightning Submarine Swaps will remain the core function. To get *on*board, users need to spend *off*-chain.

Fostering LSPs and implementing reverse Submarine Swaps is hard, but rewarding, work. We do these things because we believe people are stronger when they’re autonomous, and networks are stronger when they grow from the bottom up. We’ve seen what happens in a centralized system based on trust: institutions that are too big to care propping up other institutions that are too big to fail. We’ve learned from our ancestors.

***

{% include signup.md %}
