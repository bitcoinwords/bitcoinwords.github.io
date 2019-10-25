---
title: "Managing Bitcoin and Private Keys"
permalink: "/managing-bitcoin-and-private-keys" 

tags:
  - Thib
  - CY19 Q1

excerpt: Thib runs through the various ways to secure your Bitcoin. Posted April 1, 2019.

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

{% include donation.md %}

# [Managing Bitcoin and Private Keys](http://thibm.net/managing-bitcoin-and-private-keys)
### By [Thib](https://twitter.com/thibm_)
### Posted April 1, 2019

## Owning a bitcoin means controlling the underlying private key that secures it.** If lost, no recovery is possible. No third-party can help. It's irrevocably gone.

Private keys must be kept secret and protected at all times. This is non-trivial for most users, with many severe financial losses in the past attesting to such unfortunate reality ([here](https://www.wired.com/story/i-forgot-my-pin-an-epic-tale-of-losing-dollar30000-in-bitcoin/?mbid=BottomRelatedStories_Sections_3), [there](https://www.cnbc.com/2017/12/20/man-lost-127-million-worth-of-bitcoins-and-city-wont-let-him-look.html), [over here](https://nypost.com/2018/05/26/i-accidentally-threw-away-60m-worth-of-bitcoin/) and more [there](https://mashable.com/article/bitcoin-millionaire-scammed/)).

Private keys govern how bitcoins are spent (or moved between [UTXOs](https://coincentral.com/utxo-beginners-explainer/), to be precise). Bitcoins are securely stored on a globally distributed ledger. The ledger is replicated and synced across anyone who wants access to it to verify how bitcoins are moved within the network. This is usually done by running a full node (more on that later). Private keys unlock bits of this ledger, called addresses (or UTXOs), where bitcoins are stored.

## Managing private keys
A Bitcoin private key is a 256-bit data unit, often represented as an hexadecimal string, which can be understood as a digital bearer asset with intrinsic financial value. It is code with a price tag. Money is now pure software. Anyone in possession of a private key is deemed the rightful owner of the associated bitcoins.

From generation, to storage and utilization, private keys deserve delicate care and extreme caution for Bitcoin to be utilized securely as a global value communication protocol on the Internet.

Generating new Bitcoin private keys requires randomness to ensure no one can easily guess what it is. Once it is created, it must be stored securely, sometimes offline, to reduce the possibility of loss or theft. When used to approve or sign Bitcoin transactions, private keys must be cautiously managed to avoid introducing risks of loss. Secure backups may also be used with additional security to recover compromised or lost private keys.

This is an oversimplification of [private key management](https://en.wikipedia.org/wiki/Key_management), applied to Bitcoin.

## Security issues are real
Exclusive control of private keys, echoing with rightful ownership, is primordial for bitcoin owners. But self-managing private keys brings an unusual responsibility that can be problematic to most people. Cutting trusted third parties, such as banks for credential recovery, requires full accountability over private key management. Not an easy feat for most.

In many countries, consumers are [legally protected](https://www.investopedia.com/ask/answers/08/fdic-insured-bank-account.asp) from any liability in traditional banking as most transactions are traceable and reversible. Bitcoin transactions while traceable are [irreversible](https://en.bitcoin.it/wiki/Irreversible_Transactions), leading to permanent losses with no legal recourse to authorities or financial protections.

Users who manage their own bitcoin private keys rely on setups that often require technical skills, an advanced dedication for security and a high risk tolerance as simple errors are still quite common.

Over the last decade, multiple improvements were released by individuals, open source projects and companies, making bitcoin private key management much easier and minimizing safety trade-offs, while ensuring users retain full control of their funds in the best cases.

Full control means bitcoin owners can be sovereign in how they manage their wealth, independently from trusted third-parties, which is essential for bitcoin's long-term morphing from a value communication protocol on the Internet into a [global peer-to-peer economic system](http://thib.ca/bitcoin-and-us).

## Custodial wallets
Today, most bitcoin owners still leave private keys on online custodial wallets such as exchanges after having acquired bitcoins, delegating full control of their private keys to trusted third parties.

There isn't comprehensive data on the third-party custodied proportion but it is public knowledge that Coinbase, a popular cryptocurrency exchange, recently announced they possess [5% of bitcoin's circulating supply under custody](https://blog.coinbase.com/a-behind-the-scenes-look-at-the-biggest-and-quietest-crypto-transfer-on-record-682ff4a6d9e4), drawing attention to the large portion of bitcoin holders giving away full control of their assets.

Exchange platforms make it ridiculously easy for people to acquire and store bitcoins, reducing the anxiety that comes with the self-custody responsibility. They are one of the most essential and valuable products to onboard new users. But simplicity is often mistakenly associated with security.

Multiple custodial exchanges have lost customers' bitcoins in the past due to hacks, as they turn into honey pots for hackers or internal collusion jobs. User credentials have been stolen, 2-factor authentications have been spoofed and private keys were compromised with no recourse for affected users.
[Mt. Gox](https://blockonomi.com/mt-gox-hack/) is the obvious illustration with 850,000 BTC lost, but there was also [Coincheck](http://fortune.com/2018/01/31/coincheck-hack-how/) with over $500M stolen, and most recently [QuadrigaCX](https://bitcoinmagazine.com/articles/court-grants-quadrigacx-bankruptcy-protection/) that lost $190M of customers' funds. Lots of other cases ([here](https://www.coindesk.com/bithumb-exchanges-31-million-hack-know-dont-know), [there](http://hackingdistributed.com/2016/04/25/shapeshift-hack-simply-incredible/) or [here](https://www.coindesk.com/hacked-exchange-cryptopia-discloses-estimate-of-stolen-crypto)) have happened, totalling hundreds of millions of customers' funds that are gone forever.

Many web, mobile and desktop wallets also have full custodial control of their users' bitcoins, which introduces similar risks as with exchanges. Aesthetically-pleasing user interfaces with highly usable experiences lure users into trusting them.

Often these products are developed by small teams of developers or early-stage companies with light governance, fragile security models and no credit history, making these counterparties highly risky to delegate full control of your funds.

Some custodial wallets may let users control a portion of their private keys but still force users to rely on trusted third-party full nodes to verify Bitcoin transactions. More on that later.

## Non-custodial wallets
Self-custody of bitcoin private keys is therefore the most advisable alternative to eliminate reliance on unproven third parties. "Not your keys, not your bitcoins" is being thrown around over and over in the community but it often takes some time (rightfully so) to fully grasp why that concept truly matters.

Efforts in the Bitcoin community, such as the [Proof Of Keys](https://www.proofofkeys.com/) movement initiated by [Trace Mayer](https://twitter.com/tracemayer), are attempts to make more people care about controlling their own keys to protect their bitcoins, asking bitcoin holders to withdraw their private keys from custodial exchanges into the non-custodial alternatives described below.

Bitcoin's architecture design using public key cryptography allows users to be sovereign by self-managing their wealth in an effort to cut the overwhelming dependence on trusted financial institutions such as banks.

With that principle in mind, non-custodial wallets have been developed to help users safekeep bitcoins on their computers, mobile devices, specialized hardware and even paper.

Non-custodial desktop wallets can be "lightweight", meaning they need to be connected to a full-node of the Bitcoin network to verify transactions.

Full nodes are used in Bitcoin to transparently verify the transactions that are happening in the network, without trusting an intermediary to report information. All the Bitcoin transaction history since the network was born on the Internet on January 3rd, 2009 are stored and accessible in any active full node.

Using [Simple Payment Verification (SPV)](https://en.bitcoinwiki.org/wiki/Simplified_Payment_Verification), non-custodial desktop wallets ask full nodes to verify specific transactions, which diminish privacy if done with a trusted third-party full node, but is fine if it is user-owned. Using this method, bitcoin holders are truly sovereign in how they manage their private keys and verify that their transactions went through.

Lightweight desktop wallets include [Electrum](https://electrum.org/#home) or [Wasabi](https://wasabiwallet.io/), which rely on their corporate servers to verify user transactions as trusted full nodes, reducing user privacy.

For lightweight desktop wallets that don't rely on third-party full nodes, users need to set up and operate their own [Bitcoin full node](https://bitcoin.org/en/full-node) and have the patience to perform the initial block download from the [genesis block](https://en.bitcoin.it/wiki/Genesis_block) to today, which may take several days or weeks depending on technical limitations such as bandwidth and processor speed.

This makes desktop wallets easier to use for regular users who may not have sufficient computer disk space to store the entire Bitcoin blockchain history directly on their computer, or enough network bandwidth to download the 215GB of transactions. Some companies such as [Nodl](https://www.nodl.it/nodlbox/), [Casa](https://store.casa/lightning-node/) and [Samourai's Dojo](https://samouraiwallet.com/dojo) are making full node plug-and-play products to help onboard less tech-savvy users.

Other desktop clients have "full-verification nodes," which requires users to download Bitcoin's entire blockchain transaction history without requiring any external full node for verification.

Besides the technical specifications required for the computer to perform such operations (at least 500GB of disk space as Bitcoin's blockchain is 215GB now and growing, with high network bandwidth and reasonable CPU), users need to have this wallet connected to the Internet constantly.

This is to prevent the in-app full node from disconnecting from the network and having to re-sync to download the latest blocks, which introduces delays until the full node is fully synced again to the tip of Bitcoin's blockchain.

Full node desktop clients include [Armory](https://btcarmory.com/) or [Electrum](https://electrum.org/#home). Unfortunately, hardware failure risk and Internet connectivity via Wi-Fi for desktop computers and laptops make users prone to a wide range of online security risks on desktop wallets.

## Mobile
Similar to desktop clients, mobile wallets store private keys on user devices, which are connected to the Internet via Wi-Fi and cellular networks such as LTE. They are available on either Android, iOS or Windows Phone.

Bringing better usability, mobile wallets are by default "lightweight" wallets due to the hardware memory and bandwidth constraints tied to mobile devices. Mobile wallets also use SPV and either rely on trusted third-party servers providing transaction verification (which isn't favorable) or connecting to user-owned full nodes.

As noted, SPV wallets can introduce privacy concerns for users when there is a trusted third-party full-node involved in providing transaction verification. For users operating their own personal full node, privacy concerns using SPV are diminished.

Mobile devices are reasonably more secure than desktop computers with data encryption but still face hardware failure risks, social engineering and physical losses. Strikingly, they are ubiquitous and can be useful in other multi-party configurations that we will cover later on.

Mobile wallets using trusted third-party full-node servers include [Mycelium](https://bitcoin.org/en/wallets/mobile/android/mycelium/) and [Blockstream Green](https://bitcoin.org/en/wallets/mobile/ios/greenaddress/). Some rely on one core corporate server, which is the least favorable option for privacy and security, while other configurations randomly select verification servers from a trusted list, which reduces privacy concerns.

Other mobile wallets connecting to user-owned full nodes include [BRD Wallet](https://brd.com/support/articles/360000244733) and [Zap](https://zap.jackmallers.com/) on iOS, [Electrum Wallet](https://bitcoin.org/en/wallets/mobile/android/electrum/) with [Samourai Wallet](https://samouraiwallet.com/) on Android. [HODL Wallet](https://hodlwallet.co/) is available on both iOS and Android and lets advanced users choose between connecting to their own full-node or using their third-party server.

## Specialized hardware
Dedicated companies have developed specialized hardware products to make it safer and easier for owners to store their bitcoins independently of any trusted third parties, while reducing risks of traditional desktop and mobile wallets.

Hardware wallet providers such as [Trezor](https://trezor.io/), [Ledger](https://ledger.com/) and [Cold Card Wallet](https://coldcardwallet.com/) are the most popular manufacturers. Specialized hardware in the form of USB-like devices store private keys offline to reduce the potential attacks from hackers that users may face but require users to trust the hardware providers and their full-node APIs to verify transactions.

Specialization of hardware devices is an attempt to prevent physical extraction of private keys. Hardware wallets are either connected to desktop or mobile apps to execute operations in tandem with a trusted interface built-in on the device. Users need to have these specialized devices physically each time they want to move funds to and from their wallet, which is not the most convenient.

Even with added security features, multiple cases of losses and thefts occurred in the past due to people buying reused hardware wallets (always buy directly from verified manufacturers) or loosing the device with its recovery ([here](https://www.reddit.com/r/Bitcoin/comments/a4hvsv/i_just_lost_my_170k_wallet_secure_your_wallets/) or [here](https://news.bitcoin.com/mans-life-savings-stolen-from-hardware-wallet-supplied-by-a-reseller/)).

In case of physical loss or destruction, hardware wallets have backups that need to be stored separately to recover the private keys they contained.

## Physical backups
Backups of private keys must be stored by users who are advised to write them down on a piece of paper. Backups, also called seed, recovery or [mnemonic phrase](https://en.bitcoinwiki.org/wiki/Mnemonic_phrase), are the ultimate option for users to recover funds in case private keys get lost or compromised via a web, mobile, desktop or hardware wallet.

Storing backups is a responsibility that is outside the scope of hardware, web, mobile or desktop wallet providers. This introduces potential user errors and likely loss events if backups are lost or compromised. It is the ultimate recovery material. If lost or compromised, there are no recourse.

Backups must be stored offline to minimize risk exposure to theft and loss, which involves operational and physical security. Preventive measures must be considered to avoid physical theft of recovery material, which would lead to the compromise of the entirety of the associated private keys and funds.

Floods, fires, earthquakes and other catastrophic events may very well destroy the backups users are storing in their homes or workplaces. Companies such as [Cryptosteel](https://cryptosteel.com/?gclid=CjwKCAjw-OHkBRBkEiwAoOZqlzaNF0XGp0EcaicZBpFguCDDAJ30CMw7Ry488B9D4_qh5wDKyciV8xoC-KMQAvD_BwE), [Hodlinox](https://hodlinox.com/) or [Billfodl](https://billfodl.com/) are developing heat-resistant steel plates to prevent long-term degradation of backups.

Redundancy of backups across geographies is advisable, which introduces other risks and dependencies. Sharding, or splitting, backups into multiple sub-parts help reduce the likelihood of a malicious actor compromising the funds. Vault providers can help store redundant or partial copies of backups for maximum security but introduce third-parties.

Operational complexity and cognitive burden rise dramatically as a direct cost of extended security measures. Today this is the state-of-the-art for backups and recovery of bitcoins.

## Open-source frameworks
Open-source software and procedures, such as [Glacier](https://glacierprotocol.org/), a protocol for high-security bitcoin storage have been released by the community in an attempt to create an industry standard. It is a highly-involved operational procedure, which require redundant, quarantined and special-purpose hardware.

Physical dice are used to generate true randomness that algorithms on [computers aren't capable of creating properly](https://curiosity.com/topics/why-computers-can-never-generate-truly-random-numbers-curiosity). Combined with purpose-limited offline computers, truly random private keys are generated, and stored on offline paper wallets.

This is a deep cold storage, which involves machines that have never been connected to the Internet and never will with one-time disposable hardware that gets burned after having generated private keys.

All these operations must happen in a faraday cage to nullify the exposure to potential [radio-wave side attack channels](https://wallet.fail/). Not a procedure for your casual user securing his bitcoins. Minimum expense for that configuration is roughly $600 and takes 5-7 hours of initial set up.

## Institutional custodians
With the rise of Bitcoin's market cap in 2017, institutions have showed interest in the safekeeping of bitcoins with novel configurations. As fiduciaries, institutions are forbidden to self-custody bitcoins and are required to hold funds using dedicated third-party custodians that are regulated under the appropriate regulatory regimes, licenses and supervising entities.

With the segregation of duties between investing and custody, custodians have emerged as a quality interim solution to bring institutional liquidity in the market until regulations and technology mature sufficiently to have reliable non-custodial infrastructure deployed mass market.

Custodians often provide bespoke governance, internal controls, proof of reserves and insurance guarantees for fiduciaries with multi-party authorizations, where many signatories are registered to collectively approve transactions on bespoke governance rules.

Multiple companies are working towards getting a share of the market, with notable entities such as ICE's [Bakkt](https://www.bakkt.com/index) (still pre-launch), [Fidelity Digital Assets](https://www.fidelitydigitalassets.com/overview), [Anchorage](https://anchorage.com/product), [Xapo](https://xapo.com/) or [KNØX](https://www.kn0x.io/).

## Multi-signature
Multiple signing authorities can be required to execute Bitcoin transactions. Multi-signature is a built-in feature of [Bitcoin's P2SH (pay-to-script hash)](https://en.bitcoin.it/wiki/Pay_to_script_hash) at the base protocol layer that has been available since the early days. This design reduces single points of failure and enable bespoke transaction governance rules based on amounts, time locks and specific use cases.

Multi-signature schemes, where 2 authorizers out of 3 registered would be required to execute on a transaction, allow users to retain full control of their bitcoins, controlling 2 keys, while ensuring continuity in case of loss with other parties controlling the remaining key. The architecture of such system is non-trivial to design and implement securely while abstracting away the complexity from the end-user experience.

Companies such as [Casa](https://keys.casa/) has recently released multi-signature wallets for users, letting consumers store keys across their devices, and a few with Casa creating a "seedless" configuration, where users can get their private keys recovered using other keys securely held by Casa in case of loss events.
[BlockstreamGreen](https://blockstream.com/2019/03/19/the-all-new-blockstream-green-wallet/) has been updated recently with a new multi-signature mobile wallet for consumers using "2-of-2 multisig by default, with one key held on the device, and one key held on Blockstream's servers." BlockstreamGreen send pre-signed transactions to users, which only need the user signature to be treated as valid transactions.
[Muun](https://muun.com/) is the another multi-signature mobile wallet for Bitcoin. "As a non custodial service, Muun helps users fulfill Bitcoin's be-your-own-bank promise, and protect their funds from trusted third parties, attackers and human error [...] transactions are protected with 2-of-2 multisig and theft detection. A personal key is stored in your phone. Muun holds a co-signing key."

On the institutional side, [Unchained Capital](https://www.unchained-capital.com/collaborative-custody/) has recently announced their "collaborative custody" product, as "a superior approach to security that combines the control of self-custody with the benefits of a managed financial service.
[Ledger Vault](https://www.ledger.com/pages/ledger-vault) was released in 2018 as a "multi-authorization cryptocurrency wallet management solution enabling financial institutions to safekeep their funds [...] looking for convenience and streamlined operations with zero compromise on security."
[Ciphrex](https://ciphrex.com/), is an open-source, free to use multi-signature desktop wallet. "It supports the best security practices in the industry and is rated amongst the most secure wallets by bitcoin.org."
[MuSig](https://blockstream.com/2019/02/18/musig-a-new-multisignature-standard/), was released by Blockstream earlier in 2019, as a new multi-signature standard to offer "provable security, even against colluding subsets of malicious signers, and [producing] signatures indistinguishable from ordinary single-signer Schnorr signatures." Blockstream has proposed their code implementation to be deployed into Bitcoin development environments, which may happen later on should it pass community standards.

## An ongoing quest...
Multiple developments are currently happening for bitcoin private key management in an effort to blend security with usability and user sovereignty. A [peer-to-peer, country-agnostic and economic system built on Bitcoin](http://thib.ca/bitcoin-and-us) deserves novel solutions to onboard the next millions of consumers and businesses without introducing reliance on trusted third parties.

It has only been 10 years since Bitcoin's birth so the industry still deserves additional infrastructure development for Bitcoin private key management. Safekeeping private keys and utilizing public key cryptography has proven to be a non-trivial but ever-evolving endeavour.

Perhaps in 10 years, most Bitcoin hodlers will be able to securely manage their private keys without knowing how the system operates in the back-end, collectively storing a portion of the world's growing Bitcoin wealth.

***

Owing a lot to [Antoine](https://twitter.com/anbuteau), [Ben](https://twitter.com/mrcoolbp), Allen who reviewed early draft versions of this writing, and specifically to [Sun](https://twitter.com/sunknudsen) and [Zane](https://twitter.com/ZanePocock) with whom we're trying to make bitcoin private key management better for us three. Learning everyday from the best, who are helping us shape a better understanding of Bitcoin, for private key management, security, privacy, usability and so many other important things:
[@JackMallers](https://twitter.com/JackMallers) 
[@giacomozucco](https://twitter.com/giacomozucco) 
[@francispouliot_](https://twitter.com/francispouliot_) 
[@LukeDashjr](https://twitter.com/LukeDashjr) 
[@lopp](https://twitter.com/lopp) 
[@starkness](https://twitter.com/starkness) 
[@valkenburgh](https://twitter.com/valkenburgh) 
[@nic__carter](https://twitter.com/nic__carter) 
[@fernandoulrich](https://twitter.com/fernandoulrich "Link: https://twitter.com/fernandoulrich") 
[@LarryBitcoin](https://twitter.com/LarryBitcoin "Link: https://twitter.com/LarryBitcoin")
