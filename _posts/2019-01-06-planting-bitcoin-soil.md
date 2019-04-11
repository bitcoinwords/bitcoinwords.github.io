---
title: "Planting Bitcoin — Soil"
permalink: "/planting-bitcoin-soil" 

tags:
  - CY19 Q1
  - Dan Held

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

# [Planting Bitcoin — Soil (3/4)](https://medium.com/@danhedl/planting-bitcoin-soil-3-4-d3cd47fcfa3a)
### By [Dan Held](https://twitter.com/danheld)
### Posted January 6, 2019

**This is part 3 of a 4 part series**

* [Part 1: Planting Bitcoin - Species](https://cryptowords.github.io/planting-bitcoin-species)
* [Part 2: Planting Bitcoin - Season](https://cryptowords.github.io/planting-bitcoin-season)
* [Part 3: Planting Bitcoin - Soil](https://cryptowords.github.io/planting-bitcoin-soil)
* [Part 4: Planting Bitcoin - Gardening](https://cryptowords.github.io/planting-bitcoin-gardening)

<br>

***
## Introduction

In my last article, "[Season](https://www.danheld.com/blog/2019/1/6/planting-bitcoin-seasonnbsp24)," I covered the precise moment in which Satoshi planted Bitcoin, the 2008 Financial Crisis. In this article, I cover the Cypherpunks or the "Soil" in which he planted the Bitcoin seed giving it the best chance for survival.

## Cypherpunks

Sending the Bitcoin whitepaper to the cryptography mailing list on October 31, 2008 was the obvious choice. This was the right group to gather feedback from, the right channel to engage with. The list was predominately populated by the [Cypherpunks](https://www.coindesk.com/the-rise-of-the-cypherpunks/) * who were activists advocating widespread use of strong cryptography, as a route to social and political change.

> "Cypherpunks" is a play on the word 'cipher' or 'cypher', for encryption; and cyberpunk a genre of sci-fi.

The group was originally comprised of Eric Hughes, Tim May, and John Gilmore. At first, the meetings were in-person meetings in the San Francisco Bay Area, but they decided to expand the group via the cryptographer mailing list which would allow them to reach other Cypherpunks. The mailing list was a place to exchange ideas freely through the use of encryption methods, such as PGP, to ensure complete privacy. The basic ideas behind this movement can be found in the [Cypherpunk manifesto](https://www.activism.net/cypherpunk/manifesto.html) written by Eric Hughes in 1993. The key principle which underpins the manifesto is the importance of privacy and finality in transactions — [PetriB](https://medium.com/@Petri.basson)

> "Therefore, privacy in an open society requires anonymous transaction systems. Until now, cash has been the primary such system." — [A Cypherpunk's Manifesto](https://www.activism.net/cypherpunk/manifesto.html)

We want the ability to ensure that others cannot use the information in the history of our transactions [against us](https://research.stlouisfed.org/publications/review/2018/07/16/payment-systems-and-privacy) . For example: a purchase indicating that someone is wealthy, an embarrassing purchase, or one that would make you subject to spam or harassment. We do not want our financial purchase to haunt us further down the road. We want an endpoint beyond which we do not have to worry about further contingencies. **In the world of payments, this is closely related to the concept of "finality**" — ideally we want to be able to state with certainty that at some point the payment has been made, the debt has been cleared, and the funds are secure. But recent developments have increased the ability for more powerful parties to clawback funds (via trusted third parties, legal funds, etc).

We hope that existing laws would provide protection against these difficulties. However, we can remove that moral hazard by not having to trust third parties or more powerful adversaries which can revert transactions solely based on their capabilities. This is what the Cypherpunks were fighting for with cryptography. They were the "[Men of words](https://www.tonysheng.com/mass-movement)," or anti-establishment intellectuals that laid the foundation for individuals like Satoshi to come along.

> "The words of **anti-establishment intellectuals sow the seeds for revolution** . They present ideas and sometimes discredit the establishment, **paving the way for a charismatic leader to package their thinking into a movement** ." — [Tony Sheng](https://medium.com/@tonysheng)

Elliot Alderson, the "Cypherpunk" in the fictional show "Mr. Robot." He joins a group that aims to destroy all debt records by encrypting the financial data of the largest conglomerate in the world, E Corp.

Elliot Alderson, the "Cypherpunk" in the fictional show "Mr. Robot." He joins a group that aims to destroy all debt records by encrypting the financial data of the largest conglomerate in the world, E Corp.

The first attempts at making an anonymous transacting system were made by Cypherpunks on that cryptographer mailing list, including:

* Adam Back, the inventor of [hashcash](https://en.wikipedia.org/wiki/Hashcash), the proof-of-work (PoW) system used by several anti-spam systems. A similar PoW system is used in bitcoin
* Nick Szabo, designed a mechanism for a decentralized digital currency he called "bit gold." Bit gold was never implemented, but has been called "a direct precursor to the Bitcoin architecture"
* Wei Dai, who published "b-money", an "anonymous, distributed electronic cash system"
* Hal Finny, who created the first reusable proof of work system before Bitcoin (And in January 2009 he became Bitcoin network's first transaction recipient). He was also a developer of the secure communication method known as Pretty Good Privacy (PGP)
* David Chaum, founded DigiCash (1989) as a form of centralized "electronic money" that deployed the same kinds of cryptographic protocols — public key cryptography — that support the nature of bitcoin transactions. It is often called "Chaumian eCash."

Satoshi cites many of these Cypherpunks in the Bitcoin whitepaper and references their influence on Bitcoin's development in public statements made post code launch.

> "Bitcoin is an implementation of **Wei Dai's b-money** proposal... and **Nick Szabo's Bitgold** proposal" — [Satoshi Nakamoto](https://bitcointalk.org/index.php?topic=342.msg4508#msg4508)

In fact, Satoshi thought he was late to cryptocurrency! While the Cypherpunks had attempted many times to genetically code a species of money that would survive, none had been successful.

> "A lot of people **automatically dismiss e-currency as a lost cause because of all the companies that failed since the 1990's** . I hope it's obvious it was only the centrally controlled nature of those systems that doomed them. I think this is the first time we're trying a decentralized, non-trust-based system." — [Satoshi Nakamoto](http://p2pfoundation.ning.com/forum/topics/bitcoin-open-source?commentId=2003008%3AComment%3A9493)

He had written the whitepaper to fit his target audience, the Cypherpunks. That's why he uses the words "electronic cash", "proof-of-work," etc. which was previously used terminology in the other Cypherpunk whitepapers. He uses an ecommerce example to make it easier for everyone to comprehend. He's crafting a narrative that will resonate with the Cypherpunks, to get them interested and involved. **Bitcoin was the holy grail** **—** **it had solved the problem of finality and provided a small measure of privacy.** The source code implementation was his product spec.

> "The **functional details** are not covered in the paper, but the sourcecode is coming soon." — [Satoshi Nakamoto](http://www.metzdowd.com/pipermail/cryptography/2008-November/014863.html)

The following things not described in the whitepaper, but are included in the source code: 21M hard cap, 10 minute blocks, 1 MB block caps. Those were incredibly important components of Bitcoin. The whitepaper was merely a teaser.

> "If the Bitcoin Whitepaper is the **Declaration of Independence**, the Source Code is the **Constitution**" — [Pierre Rochard](https://medium.com/u/1206face71fc)

In true Cypherpunk fashion, the publication of Satoshi's whitepaper (October 2008) was quickly followed by code release in January 2009. The notion that good ideas need to be implemented, not just discussed, is very much part of the culture of the mailing list.

> " **Cypherpunks write code** . We know that someone has to write software to defend privacy, and since we can't get privacy unless we all do, we're going to write it. **We publish our code so that our fellow Cypherpunks may practice and play with it** . Our code is free for all to use, worldwide... **We know that software can't be destroyed and that a widely dispersed system can't be shut down** ." — A Cypherpunk's Manifesto

Importantly, Satoshi didn't [premine](https://blog.picks.co/bitcoins-distribution-was-fair-e2ef7bbbc892) any Bitcoins. Satoshi gave the Cypherpunks a two month heads up before mining the Genesis block. To prove fairness, he included a proof of no [premine timestamp](https://blog.picks.co/bitcoins-distribution-was-fair-e2ef7bbbc892) in the [Genesis Block](https://en.bitcoin.it/wiki/Genesis_block) of the Bitcoin blockchain. It carried a strong political message. What he was trying to accomplish was clear — they were building a new financial system. Bitcoin wasn't merely digital cash, it was an alternative to banks.

> " The Times 03/Jan/2009 Chancellor on brink of second bailout for banks" — [Genesis Block](https://en.bitcoin.it/wiki/Genesis_block)
