---
title: "My comments on the BitLicense"
permalink: "/my-comments-on-the-bitlicense"

author: petersurda

tags:
  - Peter Surda
  - 2014 Q4
  - Economics
  - Money
  - Politics

excerpt: My comments on the BitLicense. Posted October 20, 2014.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [My comments on the BitLicense](http://www.economicsofbitcoin.com/2014/10/my-comments-on-bitlicense.html)
### By [Peter Surda](http://www.economicsofbitcoin.com/)
### Posted October 20, 2014

I spent a lot of time researching the proposed BitLicense and associated issues, and today I submitted my comments to the NYDFS. Here it is.

Dear Superintendent Lawsky,

dear General Counsel Syracuse,

****

kindly allow me to add my own comments to the proposed regulation Title 23, Chapter I, Part 200, henceforth “BitLicense”.

### Introduction

****

I specialise in economic research of cryptocurrencies, with emphasis on the economic theory. My activities involve publications, lectures, reviews and consulting. I have started my research three years ago. Prior to that, my professional focus was in computer networks and security, for about fifteen years, including traditional payment processing, where I was mainly responsible for implementing security policies (PCI-DSS) and disaster recovery. This combination allows me a broad insight into the types of activities and problems of cryptocurrency companies. While my own business is unlikely to require to apply for the BitLicense, several of the companies that I have contractual relationships with might.

****

Even though it is customary to give recommendations in comments to proposed regulation, I typically try to stay neutral. I strive to help people to understand rather than to tell them what to do. In this spirit, I hope that my comments will cause the NYDFS to become more aware of the consequences of the proposed regulation, which, according to my impression, are not well understood.

****

I read many of the publicly available comments to the proposal, and used some of them as input for my own comment, in order to make my arguments more complete. Nevertheless, I think that I bring new important insights, and my comment should not be simply be treated as a duplicate of other comments. Links to some of the sources that I used can be found at the end of the comment.

****

My comment is divided into four sections. The first one lists two issues which, in my opinion, make the BitLicense proposal unworkable. The second one lists issues which, while possible to adapt to, nevertheless cause significant hindrances for cryptocurrency companies. The third one lists issues which are comparably minor, such as omissions and unclarities. The fourth one is an attempt to ascertain the goals of the proposed regulation, its efficacy and is perhaps more “meta” in nature.

### Grave issues

#### Affects unrelated companies

The grave issues follow from the nature of cryptocurrencies. Unlike with traditional monies and financial systems, cryptocurrencies are just numbers. In particular, private keys in the Bitcoin protocol (which I presume is what the “digital unit” in 200.2.m refers to) are 32 bytes long. For a more casual explanation, four of such keys comfortably fit into a single SMS or a tweet. 32 bytes can be stored on any object, digital or analogue, and transferred by a wide variety of means (I explain this in my master’s thesis). Once you realise this, the terms “transmission” (200.2.l) and “storing” (200.2.n.2) gain a whole new meaning. As long as this storage or transfer involves a third party, at least one of the participants is potentially subject to BitLicense. This has the perhaps unexpected consequence of a wide variety of businesses, not merely those who use cryptocurrencies in a non-financial way (as has been pointed out by others, such as Sean King), but who do not even have a cryptocurrency-specific business, being faced with BitLicense requirements. For a better emphasis, let me reformulate that. Anyone storing or transporting data or physical objects, on behalf of their customers, is potentially subject to BitLicense. Some examples of businesses that will unexpectedly be affected:

* warehouses
* vault providers
* physical transport (e.g. trucking companies, car rentals, moving companies)
* data centers, online hosting (e.g. DropBox) data processing (e.g. email), or ISPs. If I send an email to the superintendent and attach a private Bitcoin key, Microsoft, who process NYDFS’ email, will become subject to BitLicense. If he views my email on his mobile phone, his mobile phone provider will become subject to BitLicense.
* decentralised hosting systems like bittorrent (or newer ones like StorJ or MaidSafe). This affects all kinds of non-commercial entities who merely participate in the provision of online storage or data transfer

Companies have no good way to identify whether whatever they store or transport is or isn’t a private key unlocking a positive balance. Even if they realise that they store data that might be a private key, if the key is encrypted, they have no way of knowing the balance or what cryptocurrency it is related to.

****

What is, to me, surprising, is that this is not an unforeseeable problem. Other types of regulations do contain a variety exemptions, and they actually do exempt at least some of these business types. For example, federal regulation, 31 CFR 1010.100(ff)(5)(ii), has exceptions, among other things, for physical transport of cash, network services, payment processors, and facilitating sale of goods/services. California financial code, division 1.2, chapter 2, section 2010-2011 also has some exemptions. There are no equivalent exemptions in the BitLicense. BitLicense does not even exempt local, state or federal agencies, foreign governments, or the US Postal Service. These might also become subject to BitLicense. The police, if they, during exercising their duties, confiscate physical objects that store private keys (such as computers), will also become subject to BitLicense.

****

Even prior to cryptocurrencies, money transmitter laws already affected businesses in absurd ways. In “Regulating the New Cashless World”, professor Kevin V. Tu explains some of these problems. The proposed BitLicense makes no use of professor Tu’s analysis and only exacerbates the issue.

#### No way to comply with BitLicense

Even if a company realises it is subject to BitLicense and attempts to act according to it, they cannot comply with the identification requirements (200.12.a.1 and 200.15.d.1) or avoid “involving New York or a New York Resident” anyway. Once an address has non-zero balance, it is publicly visible on a ledger, and anyone can send transactions to that address, without identifying himself to anyone. The superintendent himself (being a “New York Resident”), if he desired so, could troll and send bitcoins to addresses of companies that try to exclude New York residents, forcing them to qualify their activities as “involving New York or a New York Resident” (200.2.n). The recipient cannot prevent this. If you think that I am exaggerating, similar things already happened in the past. Spammers sent small amounts of bitcoins to random addresses to advertise their products, for example the “Enjoy Sochi” or “Laxo Trade”.

****

The requirement to identify both of the parties involved in a transaction is akin to requiring a mail server or relay operator to identify the senders and recipients of each email. At least the mail server operator can reject an incoming email. A holder of a private key cannot prevent receiving a transaction, as required by 200.15.i. When Jeremy Allaire argued that the regulation is “technically impossible to comply with”, with other industry leaders (e.g. Wences Cesares) concurring, they were not exaggerating. My conclusion is actually that it is even more problematic than the comments of those gentlemen allege.

****

### Significant hampering

****

200.8.b requires the BitLicensee to invest retained profits in a few types of US-Dollar denominated investments. It is not clear whether this prohibits retaining profits in other fiat currencies (e.g. Euros or RMB). It however excludes investing into analogous types of investments issued in other countries and denominated in other currencies. Why should BitStamp or Huobi, who are not located in the US, be forced to interact with the US financial markets? Furthermore, here we have a paradoxical situation where most of the BitLicense treats non-financial uses of cryptocurrencies as financial, this restriction treats financial uses of cryptocurrencies as non-financial. Companies that use cryptocurrencies as functional currencies, for example to pay their suppliers or employees, might get cash flow problems due to this restriction. Some companies, such as CoinBase, need stashes of bitcoins to sell to their customers quickly. This could also be potentially hampered by this restriction.

****

Some companies do not use fiat money at all. In the past, blockchain.info presented itself as having no bank accounts (however, according to Jeremy Liew, who is or soon will be on their board, this is no longer the case). Purse.io, for example, is another company that, based on their business model, do not need a bank account (I do not personally know whether they do have one). Other types of businesses that do not require a fiat account are mining pools or sellers of physical bitcoin media, such as Casascius coins. Why should they be forced to obtain a bank account and/or services of a broker? What if they cannot find anyone that is willing to provide them such services?

****

This restriction also creates problems for companies that want to have more than 100% of reserves. According to audits published earlier this year, OKCoin, Kraken and Bitfinex were confirmed to have more than 100% reserves. This can be beneficial, for example, if the company wants to store 100% reserves in cold storage and a small amount in hot wallet. The additional reserves could also be used for other services, such as hedging or facilitating margin trading. If the company needs to liquidate excess reserves according to accounting deadlines rather than business demand, this would have negative impact on security and the provision of variety of business services.

****

Conversely, the requirement to hold no less than 100% reserves (200.9.a) is in conflict with certain business models (see the paper by Brito, Shadab and Castillo). It is also sometimes in conflict with other regulations, such as CFTC or SEC, as pointed out by Ryan Selkis in “Bitlicense letters #3”.

****

BitLicense seems to apply to certain type of intermediation services, for example escrow. This would include not only cryptocurrency businesses, but also others like notaries or lawyers. While I assume that in a typical escrow situation notaries and lawyers do identify the parties, why should they be subject to the other restrictions of the BitLicense?

****

BitLicense also applies to situations where encrypted keys are stored or transmitted by a third party and the holder/transmitter cannot use them in the financial sense (such as the aforementioned blockchain.info). Why?

****

Companies that bring together buyers and sellers are not specifically exempt. While they probably do not qualify as “Virtual Currency Business Activity”, perhaps they should be specifically exempt.

****

If I travel to New York, say for a conference, companies that I have contractual relationship with might become subject to BitLicense due to my trip. Why? Are these companies supposed to track my movements? My bank does not care whether I travel to US, why should a cryptocurrency company do?

### Minor issues and pointless requirements

All BitLicensees are required to have a cyber security program (200.16). This includes companies that do not deal with bitcoin electronically (e.g. sellers of Casascius coins) and in such case is pointless.

****

In some business models, the identity of the parties is known to another business involved in the transaction. In the case of purse.io, Amazon knows the identities of both the buyer and seller of bitcoins (it knows the credit card data of the bitcoin buyer and the shipping address of the bitcoin seller). If NYDFS wished to do so, they can obtain this information from Amazon by a court order. Why does purse.io also need to identify these two? This just makes the participants more vulnerable to identity theft.

****

Some companies act as an agent of the payee (e.g. payment processors). Why do they need to identify the payer? The payee can, with appropriate court order, provide the identity of the payer. During the Senate hearings in November 2013, Tony Gallippi of BitPay said that they do identify the merchant already, but as far as I know, none of the cryptocurrency payment processors identify the payer. The aforementioned professor Tu also uses the example of the agent of the payee, and the California financial code has an exemption in such as case.

****

It is unclear what happens with the customer’s funds after revocation of license (200.6.c) or denial for people already engaged in Virtual Currency Business Activity (200.21). Is the company supposed to return them to the depositors? How much time do they have for it? Will NYDFS confiscate the deposits?

****

If two BitLicensees facilitate transfers between the two of their respective customers, do they need to identify each others’ customers? E.g. if a payment processor sells bitcoins on an exchange, does the processor need to know the identity of the buyer (of bitcoins) and does the exchange need to know the identity of either the merchant or the buyer of the goods or services?

****

Storing and transferring the blockchain (as opposed to storing the private key) is not clearly exempted, yet might fall under “Virtual Currency” (200.2.m). This may affect thousands of non-commercial entities and private persons if not rectified.

****

“Fiat money” (200.2.d.) excludes commercial deposit accounts (only coins and notes are legal tender) and appears to be too narrow. On the other hand, “other value” and “retail conversion” (200.2.n.4) are not defined, can mean anything and appear to be too broad.

****

“Transmission” (200.2.l) excludes transmission from a person to that same person. I don’t know whether this was intentional, I however think it is interesting.

****

Exemption 200.3.c.2 does not include the use of Virtual Currency for something else than a payment, i.e. merchants and consumers using of Virtual Currency for non-payment purposes (e.g. document timestamping) are not specifically excluded. Perhaps they should be.

****

In 200.4.a.13 – “an explanation of the methodologies used to calculate the value of Virtual Currency in Fiat currency” should include “if applicable”. 200.19.e.4, for example, does contain “the exchange rate, if applicable”. Some businesses do not provide such valuation at all, so they should not be required to explain how they calculate it.

****

The requirement for a bond or trust account in dollars (200.9) causes a problem for companies that do not operate with fiat money. Perhaps NYDFS should consider signing up with one of the payment processors to alleviate this?

****

In 200.10 (material change to business), BitLicense does not specify how long the superintendent has to approve or reject it, whereas 200.11 (change of control, mergers & acquisitions) does.

****

In 200.12.a.1 (books and records), “transaction” is not defined.

****

In 200.12.c, “non-completed, outstanding or inactive” is not defined.

### Achieving goals

We all need to be aware that some of the purported goals of the BitLicense are, to a larger or smaller extent, in conflict with each other. For example, consumer protection and the requirement to conduct an AML/KYC program. If the BitLicensee is required to store personal identification of the customer, this increases the risk of identity theft. NYDFS needs to clarify their priorities. The superintendent’s remarks about not letting “a thousand flowers to bloom on the innovation side” gives us a bit of insight into his personal priorities. However, such attitude is more emotional than rational, and it is very dangerous, as explained by Adam Thierer in “Technopanics”. Jim Harper has been, for a long time, requesting a cost-benefit analysis from NYDFS, and has not received any yet.

****

NYDFS might consider that certain types of companies, in particular exchanges that deal with fiat, and payment processors, will increasingly tend to do AML/KYC irrespective of regulation. This is because they need good relationships with banks, and the presence or absence of AML/KYC policies at exchanges or payment processors significantly affects banks’ perceived risk.

****

NYDFS also does not appear to have given much merit to alternative methods to achieve the desired goals. The most obvious method is in my opinion the education of consumers (it is expected that the BitLicensees do this). NYDFS could also perform certification services of public keys or provide APIs for authenticating consumer identities, which would help BitLicensees to identify New York residents without having to store their identities themselves. In “Bitcoin Financial Regulation: Securities, Derivatives, Prediction Markets, and Gambling”,

Brito, Shadab and Castillo attempt to provide examples of many such alternative approaches.

****

My own impression is that, mirroring the proverb “if you have a hammer, everything looks like a nail”, NYDFS continued in doing what and how it has been doing, the result looking similar to traditional banking and money transmission regulation, and the hearings conducted by NYDFS were moot.

****

Sincerely,

****

Peter Šurda

Vienna, Austria, October 20th 2014

### Links:

BitLicense proposal: [http://www.dfs.ny.gov/about/press2014/pr1407171-vc.pdf](http://www.dfs.ny.gov/about/press2014/pr1407171-vc.pdf)

Jeremy Allaire: Thoughts on the New York BitLicense Proposal, [https://www.circle.com/en/2014/08/13/thoughts-new-york-bitlicense-proposal](https://www.circle.com/en/2014/08/13/thoughts-new-york-bitlicense-proposal)

Jerry Brito and Eli Dourado: Comments to the New York Department of Financial Services on the Proposed Virtual Currency Regulatory Framework, [http://mercatus.org/sites/default/files/BritoDourado-NY-Virtual-Currency-comment-081414.pdf](http://mercatus.org/sites/default/files/BritoDourado-NY-Virtual-Currency-comment-081414.pdf)

Jerry Brito, Houman B. Shadab, Andrea Castillo: Bitcoin Financial Regulation: Securities, Derivatives, Prediction Markets and Gambling, [http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2423461](http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2423461)

Wences Cesares: “[XAPO] WILL HAVE NO CHOICE BUT TO BLOCK NEW YORK CUSTOMERS FROM ACESSING SERVICES” AND WHY NEW YORK SHOULD CARE, [https://xapo.com/post/xapo-will-have-no-choice-but-to-block-new-york/](https://xapo.com/post/xapo-will-have-no-choice-but-to-block-new-york/)

Anthony Gallippi @ Senate Hearing, [https://www.youtube.com/watch?v=uJYBlROTswo](https://www.youtube.com/watch?v=uJYBlROTswo)

Jim Harper (on behalf of Bitcoin Foundation): comments on NYDFS BitLicense Proposal, [https://bitcoinfoundation.org/wp-content/uploads/2014/10/Bitcoin-Foundation-Comment-on-NYDFS-BitLicense-Proposal.pdf](https://bitcoinfoundation.org/wp-content/uploads/2014/10/Bitcoin-Foundation-Comment-on-NYDFS-BitLicense-Proposal.pdf)

Sean King: Here Are My Official Comments on the New York Department of Financial Services’ Proposed Bitcoin and Virtual Currency Regulations,

[http://wefivekingsblog.blogspot.co.at/2014/07/here-are-my-official-comments-on-new.html](http://wefivekingsblog.blogspot.co.at/2014/07/here-are-my-official-comments-on-new.html)

Sean Neville: Hammering on the BitLicense, [https://medium.com/@psneville/hammering-on-the-bitlicense-d00a81e4f5c0](https://medium.com/@psneville/hammering-on-the-bitlicense-d00a81e4f5c0)

Ryan Selkis: The BitLicense Papers #3, [http://two-bit-idiot.tumblr.com/post/94458273399/the-bitlicense-papers-3](http://two-bit-idiot.tumblr.com/post/94458273399/the-bitlicense-papers-3)

Peter Šurda: Economics of Bitcoin: is Bitcoin an alternative to fiat currencies and gold?,

[http://dev.economicsofbitcoin.com/mastersthesis/mastersthesis-surda-2012-11-19b.pdf](http://dev.economicsofbitcoin.com/mastersthesis/mastersthesis-surda-2012-11-19b.pdf)

Adam Thierer – Technopanics, Threat Inflation and the Danger of an Information Technology Precautionary Principle, [http://mercatus.org/sites/default/files/Technopanics-by-Adam-Thierer_MN-Journal-Law-Science-Tech-Issue-14-1.pdf](http://mercatus.org/sites/default/files/Technopanics-by-Adam-Thierer_MN-Journal-Law-Science-Tech-Issue-14-1.pdf)

Kevin V. Tu: Regulating the New Cashless World,

[http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2235937](http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2235937)

***

{% include signup.md %}
