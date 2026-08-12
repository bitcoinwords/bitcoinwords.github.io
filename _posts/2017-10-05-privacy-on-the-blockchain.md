---
title: "Privacy on the blockchain"
permalink: "/privacy-on-the-blockchain"

author: jordanclifford

tags:
  - Jordan Clifford
  - 2017 Q4
  - Money
  - Privacy
  - Cypherpunk

excerpt: Privacy on the blockchain. Posted October 5, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Privacy on the blockchain](https://hackernoon.com/privacy-on-the-blockchain-7549b50160ec)
### By Jordan Clifford
### Posted October 5, 2017



![](/assets/images/2017/m10/privacy-on-the-blockchain3.jpg)

> Privacy in an open society requires anonymous transaction systems. Until now, cash has been the primary such system… An anonymous system empowers individuals to reveal their identity when desired and only when desired.

> — Eric Hughes, [1993](https://www.activism.net/cypherpunk/manifesto.html?ref=hackernoon.com)

> Co-founder of the cypherpunk movement, [UC Berkeley](https://medium.com/@UCBerkeley?ref=hackernoon.com) mathematician

##### Background

There’s a popular misconception that Bitcoin is anonymous and untraceable. It’s an understandable mistake given Bitcoin’s first popular use case was the infamous Silk Road — a market known for dealing in illicit substances. The truth is that Bitcoin is *pseudonymous* and *fully traceable*. In fact, every transaction in Bitcoin maps inputs to outputs, allowing anyone to follow the money trivially.

Satoshi even went so far as defining a bitcoin — literally — as a history of its custody:

> We define an electronic coin as a chain of digital signatures.

> — Satoshi Nakamoto, 2009

Bitcoin’s transactions are tracked as a graph that resides on the blockchain permanently. If someone learns of information that links your identity to your bitcoin address, they can learn a ton about you. It’s possible to infer your spending patterns (where you spend, how much, how often), your wealth and income, whom you associate with. How do you feel knowing those whom you transact with may be able to learn so many personal facts about you?

There are countless ways that identities can be linked to a wallet address. Some people share their address publicly. The exchange you bought your bitcoin from has both your identity and your addresses. Merchants you pay can make the association. Two companies, [Elliptic](https://www.elliptic.co/?ref=hackernoon.com) and [Chainalysis](https://www.chainalysis.com/?ref=hackernoon.com), are in the business of linking identities to addresses, and compiling all their insights into commercialized databases that track all bitcoin activity in an effort to de-anonymize Bitcoin.

##### So what? I’ve done nothing wrong

It’s easy to fall into the trap of thinking that you, presumably a law abiding citizen, have nothing to gain from privacy. There are a few problems with this line of thinking:

First, the government isn’t the only entity out there trying to snoop on you. Unsavory attackers are also collecting as much information as they can to identify marks. Second, your government may be fine and trustworthy, but many governments in the world are not. Financial tools are needed to help citizens of these nations express their financial self sovereignty and find financial inclusion. Third, a lack of privacy actually has a chilling effect on a monetary system. It can even destroy the money.

##### Fungibility

Money — at a minimum — must be [scarce, divisible, transferrable and *fungible*](http://money.visualcapitalist.com/infographic-the-properties-of-money/?ref=hackernoon.com). Fungibility is a fancy way of saying all units are worth the same amount. If you have a ten dollar bill and I swap it out for another ten dollar bill, you don’t mind. They have the same value, and thus ten dollar bills are considered fungible.

Fungibility is dependent on money carrying no history. If cash could speak, suddenly a bank note that was received from selling drugs or stolen goods would carry extra risk. This risk would cause that note to be worth less, breaking fungibility. Please note that this is a problem not only for criminals, but also for innocent individuals and merchants who are accepting payment. Suddenly, they’re responsible for doing diligence on incoming payments to ensure they won’t be looked at funny, or worse — called in for questioning by law enforcement— when it comes time to spend their money.

Recall that a bitcoin is defined literally as its chain of custody. Each and every bitcoin has a fully transparent history recorded on the blockchain. Many are now in the business of understanding the flow of the bitcoin stock. Requiring everyone to check various lists adds significant friction, damaging bitcoin’s utility. Breaking fungibility has a chilling effect on bitcoin acceptance, and it’s [not a theoretical threat](https://www.forbes.com/sites/kashmirhill/2013/11/13/sanitizing-bitcoin-coin-validation/?ref=hackernoon.com#5e43f4e34e0f).

#### Remedies

Financial privacy means being able to transact without revealing or leaking identifying information. The goal is to make it as difficult as possible for others to profile your crypto use. Privacy puts the user in charge of their data. They can remain compliant by selectively revealing themselves without revealing their activity to the entire world.

When making a payment, it’s of course impossible to avoid creating observable information. At a minimum, the recipient must be able to confirm the funds are now theirs. It is however possible to limit how much information is created, how identifying it is, how long the information lives, how far it spreads, and who has the ability to interpret this information.

It’s important to note that following are just a sampling of efforts to improve privacy on the blockchain. More technologies are being proposed and developed all the time.

##### **Bitcoin**

Today, most bitcoin wallets and users are atrocious at privacy. The following are common and damaging for privacy:

* Wallet address re-use, linking your transactions together into a single profile. Note: Ethereum is designed to encourage this behavior.
* IP address re-use, hinting to the world that a single party — you — controls various addresses.
* Combining inputs from multiple transactions, revealing the contours of addresses you control.
* Using lite clients, effectively revealing to a third party your full set of addresses.

Using bitcoin privately is an expert level undertaking, and an uphill battle. Each bitcoin’s history is permanently etched in a transparent ledger. Therefore, even if the tools to de-anonymize don’t exist now, they can be developed and deployed later — publicizing previously thought private activity. However, that doesn’t mean broken fungibility will doom bitcoin as a medium of exchange.

Many schemes have been devised to erase a bitcoin’s history — restoring privacy and preserving fungibility.

**Existing**

* [CoinJoin](https://bitcointalk.org/index.php?topic=279249.0&ref=hackernoon.com) offers the ability to join transactions together creating ambiguity about who is paying whom. [JoinMarket](http://joinmarket.io/?ref=hackernoon.com) takes it a step further and commercializes this process on a decentralized market place. CoinJoin violates [clustering heuristics](https://arxiv.org/pdf/1107.4524.pdf?ref=hackernoon.com) used by blockchain analytics companies to identify wallets, creating a modicum of plausible deniability for ordinary bitcoin users. One drawback is that these technologies are interactive, requiring all participants be online.
* [Commercial mixers](https://themerkle.com/top-4-reliable-bitcoin-mixers/?ref=hackernoon.com) (offshore altcoin exchanges can serve the same purpose) can be used to exchange bitcoins tied to your identity for ones that are not. One weakness with this approach is that it requires trust in the entity performing the mixing. The mixer can steal your funds and they also may keep logs that link your transaction history. These entities are also heavily targeted by governments and could even be [honey pots](https://en.wikipedia.org/wiki/Honeypot_%28computing%29?ref=hackernoon.com).

**Proposed**

* [Confidential Transactions](https://people.xiph.org/~greg/confidential_values.txt?ref=hackernoon.com) is a scheme invented by Gregory Maxwell for hiding the transaction amounts. It uses incredible math called [homomorphic encryption](https://en.wikipedia.org/wiki/Homomorphic_encryption?ref=hackernoon.com) along with range proofs to completely obscure transaction amounts while still verifying that no coins are created out of thin air. This improves privacy by preventing others from learning your account balances and also prevents analysts from tracing funds based on amounts. By hiding the amounts, it greatly strengthens transactions using CoinJoin.
* [TumbleBit](https://eprint.iacr.org/2016/575.pdf?ref=hackernoon.com) improves on existing mixers by preventing the mixer itself from being able to link the payer and payee. It accomplishes this in a way that does not require trusting the mixer.
* [Schnorr Signature Aggregation](https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/?ref=hackernoon.com) + CoinJoin takes CoinJoin to the next level by providing an economic incentive to participate. Wider adoption improves the privacy benefits for everyone. Schnorr signatures allow a fixed size signature to authorize an arbitrary number of inputs. When users combine their transactions, they’ll not only gain privacy, but also shrink the size of their transactions, reducing fees.
* [Lightning Network](https://en.wikipedia.org/wiki/Lightning_Network?ref=hackernoon.com) is a payment layer built on top of bitcoin. It’s essentially [write caching](https://www.reddit.com/r/Bitcoin/comments/3k3c8m/nick_szabo_if_banks_want_benefits_of_blockchains/cuv01z4/?ref=hackernoon.com) and aids in privacy by preventing many transaction details from ever reaching the blockchain, limiting the scope of who’s able to observe them. Payments are aggregated off chain and details are learned only by people directly involved.

##### DASH

[DASH](https://www.dash.org/?ref=hackernoon.com) is a fork of Bitcoin that was originally called Darkcoin. It was pitched as a more anonymous version of Bitcoin. DASH uses incentivized nodes called masternodes to operate the CoinJoin protocol at the protocol level. One weakness in this approach is that the masternodes are able to trace funds, and many believe that law enforcement are running honeypot masternodes.

Since the privacy features are weaker than other coins and Darkcoin sounded a bit nefarious, the coin was rebranded to DASH which stands for Digital Cash. It remains an interesting coin thanks to its better than nothing privacy and its efforts to become the easiest to use cryptocurrency in the world.

##### ZCash

[ZCash](https://z.cash/?ref=hackernoon.com) offers privacy through a scheme using a technology called Zero Knowledge Succinct ARguments of Knowledge, or [zk-SNARKs](https://z.cash/technology/zksnarks.html?ref=hackernoon.com). A zk-SNARK is a proof that something is true without revealing anything ([zero knowledge](https://en.wikipedia.org/wiki/Zero-knowledge_proof?ref=hackernoon.com)) about what specifically makes it true.

This scheme, called Zerocash, was [first proposed for Bitcoin](http://zerocash-project.org/media/pdf/zerocash-extended-20140518.pdf?ref=hackernoon.com). The basic idea is that rather than publishing the transaction graph transparently on the blockchain, we instead give each coin a serial number and deposit it into a pool with many other coins. When it comes time to spend, we [prove ownership of our coin with a zk-SNARK](https://z.cash/blog/zcash-private-transactions.html?ref=hackernoon.com) without revealing which one. It’s a theoretically perfect global mixer.

Bitcoin protocol development remains quite conservative, and ambitions to incorporate Zerocash into Bitcoin have been largely abandoned. ZCash is the first production use of this technology, and continues to be a promising experiment.

##### Monero

[Monero](https://getmonero.org/?ref=hackernoon.com) is a fork of the [CryptoNote](https://cryptonote.org/whitepaper.pdf?ref=hackernoon.com) protocol. The protocol aims to achieve privacy through a its use of [traceable ring signatures](https://www.researchgate.net/profile/Koutarou_Suzuki/publication/225724409_Traceable_Ring_Signature/links/5436791b0cf2dc341db31f24/Traceable-Ring-Signature.pdf?ref=hackernoon.com), [stealth addresses](https://getmonero.org/resources/moneropedia/stealthaddress.html?ref=hackernoon.com), and most recently an adaptation of Confidential Transactions called [RingCT](https://lab.getmonero.org/pubs/MRL-0005.pdf?ref=hackernoon.com).

Monero obfuscates the transaction graph through ring signatures. When a payment is made, a passive (can be done offline) form of mixing is used to combine the input being spent with decoy inputs. A ring signature proves one of the inputs is controlled by the user, but the real input and decoy inputs are indistinguishable without further information. To prevent double spending an input, the ring signature also emits a key image that is unique to the input being spent, without revealing which input. This set of key images must be retained forever making Monero a bit more difficult to scale than other protocols.

Stealth addresses are random single use addresses that prevent users from being able to identify who the recipient is or whether any two given payments are being sent to the same recipient. The newest tool in Monero’s arsenal, RingCT takes the Monero to the next level by concealing the amounts and allowing spenders to mix with inputs of any denomination.

#### Conclusion

Hiding one’s financial affairs from a motivated nation-state will likely be out of reach for all but the most careful and skilled. However, hiding one’s affairs from the average cashier at the local corner store should be possible, and my preference is that it is easy and handled for the user by default.

Privacy and fungibility are inextricably linked and needed for a frictionless and sound money system. Privacy is not binary, but rather a smooth continuum and a protracted arms race between privacy seekers and destroyers. Over the next decade, it should be fascinating to watch this story unfold.

Thanks to [Adam Back](https://medium.com/@adam3us?ref=hackernoon.com) and [Linda Xie](https://medium.com/@linda.xie?ref=hackernoon.com) for reviewing drafts of this post.

***

{% include signup.md %}
