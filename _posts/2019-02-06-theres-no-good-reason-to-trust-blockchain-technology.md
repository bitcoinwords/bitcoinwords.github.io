---
title: "There's No Good Reason to Trust Blockchain Technology"
permalink: "/theres-no-good-reason-to-trust-blockchain-technology"

author: bruceschneier

tags:
  - Bruce Schneier
  - 2019 Q1
  - Mining
  - Money
  - Privacy

excerpt: There's No Good Reason to Trust Blockchain Technology. Posted February 6, 2019.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [There's No Good Reason to Trust Blockchain Technology](https://www.schneier.com/essays/archives/2019/02/theres_no_good_reaso.html)
### By Bruce Schneier
### Posted February 6, 2019

[Italian translation](https://dr0.ch/blockchain-e-fiducia/)

In his 2008 [white paper](https://bitcoin.org/bitcoin.pdf) that first proposed [bitcoin](https://www.wired.com/tag/bitcoin/), the anonymous Satoshi Nakamoto concluded with: “We have proposed a system for electronic transactions without relying on trust.” He was referring to [blockchain](https://www.wired.com/story/guide-blockchain/), the system behind bitcoin cryptocurrency. The circumvention of trust is a great promise, but it’s just not true. Yes, bitcoin eliminates certain trusted intermediaries that are inherent in other payment systems like credit cards. But you still have to trust bitcoin—and everything about it.

Much has been written about [blockchains](https://www.wired.com/tag/blockchain/) and how they displace, reshape, or eliminate trust. But when you analyze both blockchain and trust, you quickly realize that there is much more hype than value. Blockchain solutions are often much worse than what they replace.

First, a caveat. By blockchain, I mean something very specific: the data structures and protocols that make up a *public* blockchain. These have three essential elements. The first is a distributed (as in multiple copies) but centralized (as in there’s only one) ledger, which is a way of recording what happened and in what order. This ledger is public, meaning that anyone can read it, and immutable, meaning that no one can change what happened in the past.

The second element is the consensus algorithm, which is a way to ensure all the copies of the ledger are the same. This is generally called mining; a critical part of the system is that anyone can participate. It is also distributed, meaning that you don’t have to trust any particular node in the consensus network. It can also be extremely expensive, both in data storage and in the [energy required](https://www.wired.com/story/bitcoin-mining-guzzles-energyand-its-carbon-footprint-just-keeps-growing/) to maintain it. Bitcoin has the most expensive consensus algorithm the world has ever seen, by far.

Finally, the third element is the currency. This is some sort of digital token that has value and is publicly traded. Currency is a necessary element of a blockchain to align the incentives of everyone involved. Transactions involving these tokens are stored on the ledger.

Private blockchains are completely uninteresting. (By this, I mean systems that use the blockchain data structure but don’t have the above three elements.) In general, they have some external limitation on who can interact with the blockchain and its features. These are not anything new; they’re distributed append-only data structures with a list of individuals authorized to add to it. Consensus protocols have been studied in distributed systems for more than 60 years. Append-only data structures have been similarly well covered. They’re blockchains in name only, and—as far as I can tell—the only reason to operate one is to ride on the blockchain hype.

All three elements of a public blockchain fit together as a single network that offers new security properties. The question is: Is it actually good for anything? It’s all a matter of trust.

Trust is essential to society. As a species, humans are wired to trust one another. Society can’t function without trust, and the fact that we mostly don’t even think about it is a measure of how well trust works.

The word “trust” is loaded with many meanings. There’s personal and intimate trust. When we say we trust a friend, we mean that we trust their intentions and know that those intentions will inform their actions. There’s also the less intimate, less personal trust—we might not know someone personally, or know their motivations, but we can trust their future actions. Blockchain enables this sort of trust: We don’t know any bitcoin miners, for example, but we trust that they will follow the mining protocol and make the whole system work.

Most blockchain enthusiasts have a unnaturally narrow definition of trust. They’re fond of catchphrases like “[in code we trust](https://www.nytimes.com/2017/12/18/opinion/bitcoin-boom-technology-trust.html),” “[in math we trust](https://www.amazon.com/Math-We-Trust-Bitcoin-Cryptocurrency-ebook/dp/B07C7TPXMD?tag=w050b-20),” and “[in crypto we trust](https://cryptoclothing.org/product/crypto-shirt/).” This is trust as verification. But verification isn’t the same as trust.

In 2012, I wrote a book about trust and security, [*Liars and Outliers*](https://www.schneier.com/books/liars-and-outliers/). In it, I listed four very general systems our species uses to incentivize trustworthy behavior. The first two are morals and reputation. The problem is that they scale only to a certain population size. Primitive systems were good enough for small communities, but larger communities required delegation, and more formalism.

The third is institutions. Institutions have rules and laws that induce people to behave according to the group norm, imposing sanctions on those who do not. In a sense, laws formalize reputation. Finally, the fourth is security systems. These are the wide varieties of security technologies we employ: door locks and tall fences, alarm systems and guards, forensics and audit systems, and so on.

These four elements work together to enable trust. Take banking, for example. Financial institutions, merchants, and individuals are all concerned with their reputations, which prevents theft and fraud. The laws and regulations surrounding every aspect of banking keep everyone in line, including backstops that limit risks in the case of fraud. And there are lots of security systems in place, from anti-counterfeiting technologies to internet-security technologies.

In his 2018 book, *[Blockchain and the New Architecture of Trust](https://mitpress.mit.edu/books/blockchain-and-new-architecture-trust)*, Kevin Werbach outlines four different “trust architectures.” The first is peer-to-peer trust. This basically corresponds to my morals and reputational systems: pairs of people who come to trust each other. His second is leviathan trust, which corresponds to institutional trust. You can see this working in our system of contracts, which allows parties that don’t trust each other to enter into an agreement because they both trust that a government system will help resolve disputes. His third is intermediary trust. A good example is the credit card system, which allows untrusting buyers and sellers to engage in commerce. His fourth trust architecture is distributed trust. This is emergent trust in the particular security system that is blockchain.

What blockchain does is [shift some of the trust](https://hbr.org/2017/04/who-controls-the-blockchain) in people and institutions to trust in technology. You need to trust the cryptography, the protocols, the software, the computers and the network. And you need to trust them absolutely, because they’re often single points of failure.

When that trust turns out to be misplaced, there is no recourse. If your bitcoin exchange [gets hacked](https://www.wired.com/2014/03/bitcoin-exchange/), you lose all of your money. If your bitcoin wallet [gets hacked](https://www.ccn.com/breaking-numerous-bitcoin-wallets-may-have-been-compromised-by-rogue-developer), you lose all of your money. If you forget your login credentials, you lose all of your money. If there’s a [bug in the code](https://medium.com/new-alchemy/a-short-history-of-smart-contract-hacks-on-ethereum-1a30020b5fd) of your smart contract, you lose all of your money. If someone successfully [hacks the blockchain security](https://boingboing.net/2019/01/08/ethereum-classic-blockchain-su.html), you lose all of your money. In many ways, trusting technology is harder than trusting people. Would you rather trust a human legal system or the details of some computer code you don’t have the expertise to audit?

Blockchain enthusiasts point to more traditional forms of trust—bank processing fees, for example—as expensive. But blockchain trust is also costly; [the cost is just hidden](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3074070). For bitcoin, that’s the cost of the additional bitcoin mined, the transaction fees, and the enormous environmental waste.

Blockchain doesn’t eliminate the need to trust human institutions. There will always be a big gap that can’t be addressed by technology alone. People still need to be in charge, and there is always a need for governance outside the system. This is obvious in the ongoing debate about [changing the bitcoin block size](https://techcrunch.com/2015/08/22/money-and-politics-bitcoins-governance-crisis/), or in [fixing the DAO attack](https://www.coindesk.com/ethereum-executes-blockchain-hard-fork-return-dao-investor-funds) against [Ethereum](https://aeon.co/essays/trust-the-inside-story-of-the-rise-and-fall-of-ethereum). There’s always a need to override the rules, and there’s always a need for the ability to make permanent rules changes. As long as hard forks are a possibility—that’s when the people in charge of a blockchain step outside the system to change it—people will need to be in charge.

Any blockchain system will have to coexist with other, more conventional systems. Modern banking, for example, is designed to be reversible. Bitcoin is not. That makes it hard to make the two compatible, and the result is often an insecurity. Steve Wozniak was [scammed out of $70K](https://www.marketwatch.com/story/steve-wozniak-had-70000-in-bitcoin-stolen-after-falling-for-a-simple-yet-perfect-scam-2018-02-28) in bitcoin because he forgot this.

Blockchain technology is often centralized. Bitcoin might theoretically be based on distributed trust, but in practice, that’s just not true. Just about everyone using bitcoin has to trust one of the few available wallets and use one of the few available exchanges. People have to trust the software and the operating systems and the computers everything is running on. And we’ve seen attacks against wallets and exchanges. We’ve seen Trojans and phishing and password guessing. Criminals have even used flaws in the system that people use to repair their cell phones to steal bitcoin.

Moreover, in any distributed trust system, there are backdoor methods for centralization to creep back in. With bitcoin, there are only a few miners of consequence. There’s one company that provides most of the [mining hardware](https://techcrunch.com/2018/08/10/crypto-mining-giant-bitmain-on-target-for-10b-revenue-this-year/). There are only a few dominant exchanges. To the extent that most people interact with bitcoin, it is through these centralized systems. This also allows for attacks against blockchain-based systems.

These issues are not bugs in current blockchain applications, they’re inherent in how blockchain works. Any evaluation of the security of the system has to take the whole socio-technical system into account. Too many blockchain enthusiasts focus on the technology and ignore the rest.

To the extent that people don’t use bitcoin, it’s because they don’t trust bitcoin. That has nothing to do with the cryptography or the protocols. In fact, a system where you can lose your life savings if you forget your key or download a piece of malware is not particularly trustworthy. No amount of explaining how SHA-256 works to prevent [double-spending](https://medium.com/innerquest-online/how-does-a-blockchain-prevent-double-spending-of-bitcoins-fa0ecf9849f7) will fix that.

Similarly, to the extent that people do use blockchains, it is because they trust them. People either own bitcoin or not based on reputation; that’s true even for speculators who own bitcoin simply because they think it will make them rich quickly. People choose a wallet for their cryptocurrency, and an exchange for their transactions, based on reputation. We even evaluate and trust the cryptography that underpins blockchains based on the algorithms’ reputation.

To see how this can fail, look at the various [supply-chain security systems](https://www.wired.com/story/following-a-tuna-from-fiji-to-brooklynon-the-blockchain/) that are using blockchain. A blockchain isn’t a necessary feature of any of them. The reasons they’re successful is that everyone has a single software platform to enter their data in. Even though the blockchain systems are built on distributed trust, people don’t necessarily accept that. For example, some companies [don’t trust the IBM/Maersk system](https://www.coindesk.com/ibm-blockchain-maersk-shipping-struggling) because it’s not *their* blockchain.

Irrational? Maybe, but that’s how trust works. It can’t be replaced by algorithms and protocols. It’s much more social than that.

Still, the idea that blockchains can somehow eliminate the need for trust persists. Recently, I received an email from a company that implemented secure messaging using blockchain. It said, in part: “Using the blockchain, as we have done, has eliminated the need for Trust.” This sentiment suggests the writer misunderstands both what blockchain does and how trust works.

Do you need a public blockchain? The answer is almost certainly [no](https://medium.com/@kaistinchcombe/decentralized-and-trustless-crypto-paradise-is-actually-a-medieval-hellhole-c1ca122efdec). A blockchain probably doesn’t solve the security problems you think it solves. The security problems it solves are probably not the ones you have. (Manipulating audit data is probably not your major security risk.) A false trust in blockchain can itself be a security risk. The inefficiencies, especially in scaling, are probably not worth it. I have looked at many blockchain [applications](https://www.oreilly.com/ideas/blockchain-applications), and all of them could achieve the same security properties without using a blockchain—of course, then they wouldn’t have the cool name.

Honestly, cryptocurrencies are useless. They’re only used by speculators looking for quick riches, people who don’t like government-backed currencies, and criminals who want a black-market way to exchange money.

To answer the question of whether the blockchain is needed, ask yourself: Does the blockchain change the system of trust in any meaningful way, or just shift it around? Does it just try to replace trust with verification? Does it strengthen existing trust relationships, or try to go against them? How can trust be abused in the new system, and is this better or worse than the potential abuses in the old system? And lastly: What would your system look like if you didn’t use blockchain at all?

If you ask yourself those questions, it’s likely you’ll choose solutions that don’t use public blockchain. And that’ll be a good thing—especially when the hype dissipates.

Categories: [Trust](https://www.schneier.com/essays/trust/)

***

{% include signup.md %}
