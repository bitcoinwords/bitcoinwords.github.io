---
title: "Statechains: Non-custodial Off-chain Bitcoin Transfer"
permalink: "/statechains-non-custodial-off-chain-bitcoin-transfer" 

author: rubensomsen

tags:
  - Ruben Somsen
  - CY19 Q2
  - Technology
  - Off-Chain Transactions
  - Statechains
  - Scaling

excerpt: Ruben Somsen lays out his proposal for statechains, a novel way to transfer Bitcoin off-chain. Posted June 4, 2019.

defaults:
  - scope:
      type: posts
---

# [Statechains: Non-custodial Off-chain Bitcoin Transfer](https://medium.com/@RubenSomsen/statechains-non-custodial-off-chain-bitcoin-transfer-1ae4845a4a39)
### By [Ruben Somsen](https://twitter.com/SomsenRuben)
### Posted June 4, 2019

**This article introduces Statechains, a novel layer two scaling protocol for Bitcoin with some unique features. We'll go through its strengths and weaknesses, look at how it integrates with the Lightning Network, and discuss the privacy implications of combining it with Blind Signatures.**

I first unveiled my concept of Statechains by [presenting it at Scaling Bitcoin in Tokyo](http://youtu.be/FI9cwksTrQs?t=47m36s). Since it was a technical conference, my presentation was not focused on a general audience. As a result, it has largely gone under the radar, which is a shame because it's a unique layer two protocol with useful features that can strengthen the Bitcoin ecosystem. Hopefully this article can convince you of its merits. Note that this article is high-level and won't have all the technical details. If you want those, please refer to the [talk](http://youtu.be/FI9cwksTrQs?t=47m36s), [paper](https://github.com/RubenSomsen/rubensomsen.github.io/blob/master/img/statechains.pdf), and [mailing list post](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-June/017005.html).

Statechains are a layer two protocol, meaning it enables the transfer of value without burdening the Bitcoin blockchain. This can help with scaling and save fees. Unlike Lightning it is not trustless, but it maintains a high degree of censorship resistance (more so than federated sidechains) due to the fact that withdrawing on-chain is permissionless.

The basic idea behind Statechains is that you lock up money between two parties in a 2-of-2 multisig: the **Statechain entity** and the user. When the user wants to transfer the money (the entire UTXO), they simply hand over their private key, which we call the **transitory key**, to the intended recipient.

And that's basically it. There is a lot more complexity operating in the background to decrease the potential for cheating, but in a nutshell this is the core concept, and as you will later see, it's deceptively powerful.

![](/assets/images/cy19/cy19q2m6/rs-1.png){: .align-center}
*Non-custodial, because the Statechain and Bitcoin blockchain get updated in tandem (atomically)*

In essence, the money is controlled by the Statechain entity and _all_ the users who know the transitory key. The Statechain entity could theoretically move the money in cooperation with _any_of the users, but simply promises to only cooperate with the _last_user that received the transitory key. One thing the Statechain entity _cannot_do, is move the money on their own.

Let's take a look at the weaknesses. If the Statechain entity goes offline, loses their key, or refuses to cooperate, is the money gone? No. Every time the money changes owner, an off-chain transaction is also generated. This allows the last recipient of the transitory key to redeem their coins on-chain without the assistance of the Statechain entity. The Statechain entity simply cannot hold your money hostage.

![](/assets/images/cy19/cy19q2m6/rs-2.png){: .align-center}
*Each time the money moves on the Statechain (B to C), an off-chain Bitcoin transaction is created. We use [eltoo](https://blockstream.com/eltoo.pdf) to ensure that only the final recipient can withdraw the money, without the help of the Statechain entity.*

Can the Statechain entity still cheat by colluding with one of the previous users that know the transitory key? Yes they can, but chances of this happening are minimized for the following reasons:

* We keep the Statechain entity honest by making sure they disclose every signature they make (via clever use of [Adaptor Signatures](http://diyhpl.us/wiki/transcripts/layer2-summit/2018/scriptless-scripts/)). Any attempt to cheat by the Statechain entity would immediately become apparent.
* The Statechain entity isn't actually a single entity, but a federation — a group of members (e.g. 8-of-12 multisig) of which a majority has to agree in order to cheat. This security model is comparable to [federated sidechains](https://blockstream.com/sidechains.pdf) such as [Liquid](https://www.blockstream.com/liquid/), with the added benefit that users can withdraw _without_permission.
* Every UTXO has a different transitory key and a different set of prior users. To steal all the coins, the Statechain entity (or a hacker) would have to find prior users that are willing to collude for every UTXO. In the unlikely event of theft, it is therefore likely that only a subset of coins gets stolen.

Are Statechains custodial? Surprisingly, they are _not_. This is one of the key distinguishing features of Statechains. If a court ordered the Statechain entity to confiscate someone's coins, they simply wouldn't be able to comply, since they only have one of the two keys. They can't freeze the assets either, because the owner can always redeem the coins on-chain without their help. There is also no risk of fractional reserve, forcing hard forks upon users, or other issues that are commonly associated with custodial control.

One unique feature of Statechains is that it operates at the level of the UTXO. This has some interesting consequences:

* UTXOs are transferred in full: if you lock up 1BTC into a Statechain, you have to transfer that full amount, but bigger UTXOs can always be traded for smaller ones (e.g. 2x 0.5BTC for 1BTC)
* You can swap multiple same-value UTXOs with users, which is equivalent to a [coinjoin](https://en.bitcoin.it/wiki/CoinJoin) to increase privacy, particularly when done over Tor
* Lightning channels can be opened on top of Statechain UTXOs in order to enable smaller payments (see the next section for details)
* Betting/oracle protocols that require UTXO ownership can be performed efficiently (e.g. 2-of-3 multisig,[Discreet Log Contracts](https://adiabat.github.io/dlc.pdf))
* Non-fungible colored coins on the Bitcoin blockchain can be transferred off-chain via Statechains (e.g. [RGB](https://github.com/rgb-org/spec))
* User verification of payments scales better than sidechains, because coin history is linear, so you only need to verify the history of the exact coins that interest you

The key insight here is that anything that requires creating one or more new Bitcoin UTXOs, can now be done off-chain via Statechains. It's also worth noting that Statechains are chain-agnostic, meaning it's possible for a Statechain entity to manage UTXOs from different blockchains and allow users to trade between them (not unlike a DEX).

![](/assets/images/cy19/cy19q2m6/rs-3.png){: .align-center}
*An example of a swap with different assets. User B trades his 2BTC for 200LTC with C.*

As I recently [argued on Twitter](https://twitter.com/SomsenRuben/status/1115920063037497344), Bitcoin has no choice but to scale via the second layer. It is therefore absolutely crucial that this kind of technology gets built. We need many different layers that make different trade-offs, so people can pick the layer that best suits their needs.

Here is an (admittedly over-simplified) overview of where Statechains fit in:

![](/assets/images/cy19/cy19q2m6/rs-4.png){: .align-center}
*It could be argued that a layer cannot be truly censorship resistant if it isn't trustless — the coins could still potentially get stolen, even if unlikely.*

In short, Statechains are novel in the sense that they allow you to change UTXO ownership off-chain, while preserving a large degree of censorship resistance due to the ability to withdraw on-chain. It is non-custodial, which naturally reduces risk and makes it easier for the Statechain entity from a regulatory point of view. The end result is a unique layer two protocol with its own distinct strengths and weaknesses.

## Statechains and The Lightning Network

One particularly powerful feature which I already alluded to but deserves further examination, is the interoperability between Statechains and the Lightning Network. In order to open a channel on the Lightning Network, you need to obtain a UTXO on the Bitcoin network and share its ownership with someone via multisig. Statechains provide this exact functionality: any UTXO that exists on a Statechain can be turned into a Lightning channel at any time.

The beauty is that this is kept completely hidden from the Statechain entity. All the entity sees is that the entire UTXO got transferred, but they are entirely unaware that this is actually a 2-of-2 multisig Lightning channel. The two protocols are kept completely separate. The Statechain entity doesn't need to be involved, even when forced on-chain closure occurs.

![](/assets/images/cy19/cy19q2m6/rs-5.png){: .align-center}
*The channel can be opened on the Statechain without the help or awareness of the Statechain entity.*

By utilizing Statechains, you get to open and close channels off-chain at minimal costs. Is your channel too small? No problem. You can simply transfer your existing channel over to a larger UTXO. This can be particularly powerful considering it's hard to know ahead of time how much capacity will be needed in a channel. Now you can cheaply experiment, and once you have a stable channel, you could choose to effortlessly move the channel over to the base layer by exiting from the Statechain.

Another really potent consequence is that Statechains enable you to on-board people onto the Lightning Network instantly. If you have money on a Statechain, you can immediately send a portion of it to a friend by turning the Statechain UTXO into a shared Lightning channel. And if your friend prefers to minimize their exposure to the Statechain entity, you could directly move the channel on-chain.

One more interesting feature that [Anthony Towns](https://twitter.com/ajtowns) and [Olaoluwa Osuntokun](https://twitter.com/roasbeef) alerted me to, is that when you open a Lightning Channel factory via a Statechain, adding or removing people from the factory can occur without on-chain friction, making it far more flexible.

## Enhanced Privacy with Blind Statechains

Statechains, as described thus far, limit the control the Statechain entity has over its users, but does allow the entity to learn a lot about every transaction, and most of this information gets transparently published for the world to see. Engaging in the Statechains equivalent of coinjoin helps mitigate this to a large extent, but we can do even better!

[Blind signatures](http://diyhpl.us/wiki/transcripts/building-on-bitcoin/2018/blind-signatures-and-scriptless-scripts/) can make the Statechain entity completely unaware of what they're signing. The transactions would become entirely unseen — it would literally not be possible to tell whether the entity is facilitating the transfer of money, or if they're signing something else. You're essentially blindly changing the signing rights over a private key without changing the key itself, which undoubtedly has use cases other than cryptocurrency.

![](/assets/images/cy19/cy19q2m6/rs-6.png){: .align-center}
*The Statechain entity is signing blinded messages — it does not know whether these are Bitcoin transactions or something else entirely.*

Not only would this increase the privacy of the system, but it also really challenges the legal definition of what it means to "process" a payment. All the Statechain entity would do is blindly sign messages at the request of a chain of users. A user gets to request one signature and also appoints a new user that gets to request the next one. All requests and corresponding blind signatures are transparently published.

For those who are familiar with the details in the paper, the key difference compared to regular Statechains is that users are expected to unblind and verify the chain of signatures prior to accepting a payment, because the Statechain entity can no longer ensure that what it's signing is correct. If one of the previously requested signatures in the history is incorrect, the recipient simply rejects the payment. Unblinding can be done by anyone who controls the transitory key (thanks to [Jonas Nick](https://twitter.com/n1ckler) for checking my transitory key hashing method for unblinding).

In a sense, Blind Statechains are a variant of [Chaumian cash](https://bitcoin.stackexchange.com/questions/9544/how-does-chaum-style-e-cash-work-all-the-wiki-links-are-broken), but it actually manages to move one step beyond it. Chaumian cash makes it impossible for a server to know who is receiving the money, but if the server refuses you service, you essentially lose the asset. With Blind Statechains the server doesn't even know whether it's transferring money, it doesn't know who is receiving it (particularly when combined with coinjoin), AND it cannot stop you from redeeming its value on-chain on the Bitcoin blockchain.

Finally, it is worth noting that the Statechains protocol is the culmination of a bunch of technologies by many developers. As the author, my contribution was limited to creatively putting them together for the novel purpose of transferring UTXO ownership (more specifically: key signing rights) off-chain. Credit goes to the creators of [Sidechains](https://blockstream.com/sidechains.pdf), [Schnorr Signatures](https://github.com/sipa/bips/blob/bip-schnorr/bip-schnorr.mediawiki), [Adaptor Signatures](http://diyhpl.us/wiki/transcripts/layer2-summit/2018/scriptless-scripts/), [Blind Signatures](http://diyhpl.us/wiki/transcripts/building-on-bitcoin/2018/blind-signatures-and-scriptless-scripts/), [eltoo](https://blockstream.com/eltoo.pdf), [Graftroot](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-February/015700.html), and undoubtedly many more works that have inspired me but I am failing to recall.

_Thanks to_ [_Adam Gibson_](https://twitter.com/waxwing__) _,_ [_Bryan Bishop_](https://twitter.com/kanzure) _, and_ [_Calvin Kim_](https://twitter.com/kcalvinalvinn) _for the article review and comments._

My more in-depth [Statechains talk](https://www.youtube.com/watch?v=FI9cwksTrQs) from Scaling Bitcoin ’18 in Tokyo. Also check out the [paper](https://github.com/RubenSomsen/rubensomsen.github.io/blob/master/img/statechains.pdf).

***