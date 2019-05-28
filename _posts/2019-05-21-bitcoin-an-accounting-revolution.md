---
title: "Bitcoin: an Accounting Revolution"
permalink: "/bitcoin-an-accounting-revolution" 

tags:
  - Permabull Nino
  - CY19 Q2

excerpt: Permabull Nino explains why cryptocurrencies are fundamentally valuable from the absolute first principles.

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      read_time: true
      comments: false
      share: true
      related: false
---

# [Bitcoin: an Accounting Revolution](https://medium.com/@permabullnino/bitcoin-an-accounting-revolution-40efcb903d7b)
### By [Permabull Nino](https://twitter.com/ImacallyouJawdy)
### Posted May 21, 2019
[Decentralized Credit (DR/CR)](https://medium.com/@permabullnino)<time>May 21</time>

_Building Accounting Systems, Triple-Entry, & Absolute Assurance_

Bitcoin is an accounting revolution. This accounting revolution enables a monetary revolution. Another way to look at this is:

Accounting Revolution = Technological

Monetary Revolution = Social

Disruptive technologies spark social movements. If they didn't spark social movements, then they would (by definition) not be disruptive. Facebook, YouTube, and Airbnb are all technologies that changed the way we understood and interact with friends, content creation, and travel, respectively. Bitcoin is no different in this regard, as it is an accounting technology that is in the process of transforming our understanding +usage of money.

This piece will provide a detailed discussion on Bitcoin and how it provides a simple, yet revolutionary step forward in the field of accounting. With this in mind — wrapping our heads around Bitcoin as an accounting phenomenon requires some build up. Our game plan goes as follows:

1. Brief History of Accounting + Audit
2. Historical Trends of Accounting + Audit
3. Introducing Bitcoin + Triple Entry Accounting in Depth
4. Bitcoin Accounting vs Double Entry Accounting
5. Bitcoin + Lightning vs Double Entry Accounting
6. Implications + Conclusions

## _1: Brief History of Accounting + Audit_

Accounting and audit both have rich histories that are worthwhile exploring for purposes of our discussion. It's important that we understand how these fields advanced over the long arc of time because this understanding will allow us to appropriately frame Bitcoin and its design. It is common to cite the cypherpunks and their compelling works as the beginning of Bitcoin's story. However, what we will see through our historical lens is that Satoshi's invention was thousands of years in the making. Below we will walk through each historical point / accounting advancement and attempt to concisely elaborate on its relative significance:

### **Counting**

Before concerning ourselves over value-recording capabilities we needed the ability to communicate numbers at the most basic level. These communication building blocks included (1) signaling numbers non-verbally, (2) verbal communication of numbers, and (3) written communication of numbers. All three historically occurred in the order as presented and originate from a single descendant: the human body. Quite naturally — humans used parts of their body to communicate early on, and this habit even continues until this day. Popular body parts leveraged for counting included fingers, toes, knuckles, and even ears. Different groups of people built numerical systems + created numerical language using certain body parts, and the body part of choice determined the numerical layout. For this reason, it seems more than appropriate that 2 & 5 are such important numbers within our contemporary counting system. Just look at your own body and you'll find the answer to be self-evident.

### **Private Record Keeping**

As human exchange evolved, a need to track such dealings emerged. Until the 14th century this generally involved jotting down rough "notes" which described in a sentence / paragraph format the nature of an exchange, including counterparties, goods, and amounts. During this time period "accounts", which are merely a batching of transactions based on type to arrive at an easily digestible balance, did not exist (categorization of receipts & disbursements, however, did exist). Organizing the numbers for the transactions in a column to the right of the description hadn't been popularized either, with amounts just included within the written transaction description.

In this era single entry accounting reigned supreme, and with this accounting scheme the complexity of exchange sat stationed in a form of financial purgatory. How so? Well — simply put, only 1 half of each transaction found its way into the accounting books of each party under single entry. This weakness heavily impacted the auditability of transactional records, and this deficiency naturally made it substantially more difficult to settle disputes. Lack of recourse and an absent "safety net of truth" in the form of reliable accounting records made stakeholders much less inclined to expand their transactional reach, and rightfully so. Fortunately, a solution emerged to fix these problems...

### **Double-Entry Accounting**

The accounting quality standards through the private record keeping era left a lot to be desired. This was the case for good reason, as the records being kept were only for the eyes of the party doing the transacting. However — a great leap finally occurred that led to the need for systematic bookkeeping: accountability to external parties. Recording a transactional history with an external user in mind requires an effective, easy to follow approach, that ultimately provides an auditable trail of evidence to identify errors / fraud in the case of dispute. Double-entry accounting fulfilled this need in a simple, yet elegant fashion. The genesis of double entry as we know it emerged in Genoa, Italy during the 14th century before spreading to the rest of Italy and neighboring European countries. Luca Pacioli, a Florentine friar-mathematician, is known for popularizing double-entry via his treatise _Summa de Arithmetica_, which included a chapter on the newly discovered double-entry scheme.

Following the publication of Luca's treatise the world witnessed a viral spread of double-entry bookkeeping, but not without opposition. On multiple occasions accountants dispersed throughout various parts of Europe attempted to debunk double-entry or invent a "new and improved" bookkeeping system, to little avail. Double-entry survived peer-review and was here to stay. The fact of the matter is that it withstood the test of time because double-entry captured the true essence of transacting, by recording the "give" and the "take", so to speak. Early success and basic accounting framework aside, double-entry did require iterations over the years. A couple instances that exemplify this need to iterate include:

(1) Checking that debits and credits balanced (i.e. netted to zero) wasn't initially understood. This needed to be discovered later.

(2) Transferring residual income into a capital account at the end of a reporting period (Net Income →Retained Earnings) wasn't always obvious and required time for discovery.

Those that are accountants by training understand these 2 iterations as a given nowadays, which is a testament to the advancements in double-entry in the past ~ 600 years. Despite these large strides, double-entry and the reporting systems such as GAAP & IFRS built on top of it are still works in progress.

_Note: Double-entry adoption also introduced formal audits of accounting records to the mainstream._

### **Triple-Entry Accounting**

The turn of the millennium welcomed a once in 1,000 years evolution of accounting: triple-entry. Particularly of interest for purposes of our discussion is Ian Grigg's suggested implementation of triple-entry, which he describes as a "...system [that] creates bullet proof accounting systems for aggressive uses and users". This bullet proof accounting system supposedly was to bring together "financial cryptography innovations such as the Signed Receipt with the standard accountancy techniques of double entry bookkeeping". Further, the system was to create 3 sets of entries: two of which that are included as a part of the standard set of double entries, and additional entry to be provided by the issuer. This entry was provided by the issuer in the form of a digital receipt of the transaction, signed by the issuer, to create a "dominating record of the event" to be stored by all 3 parties.

![](/assets/images/cy19/cy19q2m5/perma-1.png){: .align-center}
_(A Signed Receipt, i.e. the "dominating record of the event")_

_Note: Alice + Bob = transacting, Ivan = "issuer"_

Grigg makes several noteworthy observations such as the importance of transparency within the system to track the "clear relationship of participants", which would in turn require pseudonymity. He also touches on the digital receipt's dominance in information terms, but its relative weakness in processing. Overall, his handle on the triple entry scheme is mind-bendingly strong for someone who wrote this Christmas Day 2005. If I'd have to guess — this paper written by Mr. Grigg went unnoticed by most of the world at the time of its publication. However, speculatively speaking, it seems likely this paper served as the final spark to create the ultimate accounting scheme which would support decentralized, digital cash 3 years later. This gap in time between Grigg's piece and a very famous whitepaper published on Halloween 2008 seems hardly coincidental.

## _2: Historical Trends of Accounting + Audit_

Our short run through the history of accounting + audit helps track our progress as a species in synthesizing and documenting value. In this section we will list trends that have persisted throughout the history of accounting + audit to provide additional context to such history. By doing this we will much better understand the core pieces to building accounting systems and thus be capable of comparing various accounting schemes along with their respective pros / cons. Without further delay, standout trends through history include:

### **§ Tamper Resistance:** Accounting cannot serve its purpose for tracking value through time if records are easily reversed / changed.

o Example: Dating all the way back to 2600 B.C., Babylonian scribes used to record business dealings on clay slabs. These clay slabs were subsequently baked or sundried to preserve permanence of the documentation.

### **§ Redundancy:** This feature of accounting systems serves as the backbone of error + fraud prevention. Redundancies such as financial controls aid in maintaining internal accounting quality and audits from independent third parties provide an extra layer for identifying issues.

o Example: Ancient Egyptians implemented redundancy into their financial dealings by assigning two separate officials the task of recording independent accounts of each transaction.

### **§ Transparency:** Accountability cannot be ensured without transparency in some sort of capacity.

o Example(s): In Ancient Greece elected officers of finance had their accounts engraved on stones, which were available for scrutiny to the public. A more contemporary case of transparency / accountability can be found in publicly traded stocks, and their public release of quarterly / annually reviewed and audited financial statements.

### **§ Adaptability:** Accounting as a technology has had a great track record of adapting to satisfy the needs of its contemporary period. A lack in adaptability would stunt future growth in any economy as entrepreneurs would trip over themselves attempting to scale their value-recording capabilities with their business operations.

o Example(s): Pacioli used a book for recording entries called the "Memorial", which preceded entries in the Journal. This book was treated as a "conversion journal" of sorts, as there was very little uniformity of monetary systems during the Medieval period. Amounts in the Memorial were converted to a single unit of account, and subsequently recorded in the Journal. For something more contemporary — today GAAP & IFRS are constantly changing to account for complex, newly identified issues.

### **§ Enabling:** There's a degree of reflexivity in accounting systems and the economies they're created to support. Accounting systems need to adapt to support entrepreneurs, but once they do, they enable further economic expansion and prosperity.

o Example: Double-entry bookkeeping's birth occurred right as the Renaissance was beginning, an era which marked the transition to modernity as we know it. Albeit not a popular opinion, there's an argument to be made that the creation of such a bookkeeping system provided a strong undercurrent for pushing the world ahead during this period.

### **§ Exclusive:** Accounting has historically been a field dominated by the educated, with high barriers to entry.

o Example(s): In the early days of double-entry, the number of accountants within a country could be counted on two hands. Later, accountants were prohibited from practicing for not possessing enough apprenticeship / educational hours. These standards in some respects persist today.

### **§ Simplicity:** An unspoken rule in accounting / audit is that the procedures used to account for a transaction should only be as complicated as the situation demands. Simplicity is key in error prevention (before the fact) and detection (after the fact). Additionally, simplicity greases the wheels for adoption of an accounting scheme.

o Example: Edward Thomas Jones, an English accountant, created a bookkeeping system in the late 18th century that he claimed would upend double-entry. His so-called groundbreaking system used 10 columns, instead of 2, and supposedly provided stronger assurances surrounding error / fraud prevention of ledger data. Needless to say, the system was overly complex for the little, if any, improvements in ledger integrity the system offered.

## _3: Introducing Bitcoin + Triple Entry Accounting in Depth_

Of the characteristics used to describe accounting systems in the previous section, the 3 most important are arguably (1) Tamper Resistance, (2) Redundancy, and (3) Transparency. With Grigg's instantiation of triple-entry, real-time transparency emerged as an obvious improvement from the well-established double-entry scheme. A degree of additional redundancy showed itself as another innovation within his proposed system by creating the receipt ("dominant record of events"), which was to be stored by the 2 transacting parties + the "issuer" (third party verifier). However — with only 3 parties storing the receipt, the possibility of losing it remained. In addition, purposely disposing of the receipt loomed as a "what could go wrong" as well. At risk of sounding repetitive, some work remained to make Grigg's system truly "bullet proof", as the tamper resistance and redundancy pillars were not fully resolved as of his 2005 paper.

This is where Satoshi comes in. Using a small tweak to Grigg's system, Satoshi fully solved the remaining tamper resistance and redundancy issues within the triple entry scheme. How did he/she pull this off? By gamifying the process for providing the signature on the issuer receipt. Via gamification, competing for verification + signature rights became explicitly profit-incentivized. The opportunity to profit gave outside parties a selfish want / need to provide third party verification services, and with this desire came a gigantic redundancy upgrade. In astounding fashion, the redundancy enabler within Satoshi triple entry also provided the engine for mitigating the remaining tamper resistance problems. The mechanism leveraged for accomplishing this is called "Proof of Work" (PoW).

Simply (and generally) stated, PoW requires an unforgeable, costly amount of effort to prove work was performed in order to reach a certain conclusion. Within the Satoshi scheme, Bitcoin, work is carried out via *repeatedly* hashing a subset of relevant block data + a random number (nonce), to find a hash below the required network difficulty target. This hash itself can be verified by other third-party verifiers within the Bitcoin network and ultimately serves as the "receipt signature" for each published receipt i.e. blocks. The cost to hash comes in the form of electricity used to fuel hashing machines (ASICs), and this cost makes it expensive to tamper with the dominant record of events (i.e. the blockchain). The coinbase rewards (newly minted coins) of each block that is published / accepted by the network + transaction fees serve as the profit motive. To cleanly summarize the solving of the tamper resistance and redundancy issues:

![](/assets/images/cy19/cy19q2m5/perma-2.png){: .align-center}

## _4: Bitcoin Accounting vs Double Entry Accounting_

The differences in Bitcoin's triple entry scheme and Pacioli's double entry go beyond the 3 characteristics mentioned in the previous discussion. Within this section we will explore in detail the differences between the two systems, the implications of Bitcoin's existence as it relates to accounting, and whether the two systems represent substitutes or complements to each other. Below is a table listing out the primary differences between Bitcoin and double entry:

![](/assets/images/cy19/cy19q2m5/perma-3.png){: .align-center}
Double-Entry vs Bitcoin

At a high level, the differences between these systems can be summarized into 3 categories: (1) Flexibility, (2) Scalability, and (3) Intensity of Assurances Offered. However — these categories are not all created equally. Flexibility + scalability characteristics of each respective system are what ultimately yield a difference in intensity of assurances offered. The prior reflects specific means of differentiating Bitcoin from the traditional accounting system, and the latter more so illustrates the "grand innovation" when you put all the pieces together. This grand innovation will be our focus for the rest of this section...

With this in mind — the whole world runs on double entry accounting. This double entry dominance is to be expected, as it is a highly flexible, scalable, and simple system for recording / communicating value. Furthermore, in the event of errors / fraud there also exists an audit trail for identifying what went wrong. Financial controls in some capacity provide a means to prevent these problems (before) and external auditors perform their role in detecting (after). All things considered, double entry has been a raging success and continues to serve us very well. However — there is one glaring flaw with it: the assurances that it offers its users over data integrity. In the accounting profession, the intensity of the assurance that double entry offers is known as "reasonable assurance". Although reasonable assurance does suggest a high degree of reliability post-audit, it by no means is a guarantee that the ledger is completely accurate, only accurate "enough". Take the accounting / auditing of cash balances as an example, a relatively low-risk area of any audit engagement (and the most comparable asset to bitcoins on any balance sheet). External audit gains confidence over the cash balances by requesting bank confirmations, which are paper / digital reports that take anywhere from 24 hours to a few weeks to get from the bank holding the client's funds. Reports from external third parties such as these are considered highly reliable pieces of audit evidence, as collusion would be the only manner of which fake balances could be hypothetically supported. Collusion is very difficult to detect because the auditors have no reason to suspect foul play, they do not have access to the bank's accounting system, and there might not be any signs of fraud in the report(s) provided. The purpose of this example is to show that even in the simplest cases, it is impossible to attain _full guarantees_ over the integrity of accounting data under the double entry scheme. Herein lies the pinch, and where Bitcoin makes one of the greatest leaps in the history of accounting...

Bitcoin is the first accounting system to ever provide _absolute assurance_over ledger data. Unlike double entry, Bitcoin accomplishes this by providing _expedient third-party verification_ via its inflexible, highly redundant protocol + network. From an accounting perspective, the speed at which this verification from independent parties occurs is incredibly significant, as it reflects a paradigm shift from an overhead intensive and slow verification regime to one that is lightweight for users and only "a click away" at all times. To put more simply, it disintermediates the old and separate internal accounting + external audit functions by combining them into a single, inseparable product.

It is worthwhile noting that absolute assurance is not an "out of the box" feature with all public blockchains and can only be earned with enough resources committed to the network. These resources strengthen the tamper resistance and redundancy pillars we discussed earlier, and very few (if not only Bitcoin) public blockchains meet this criterion. This ability to provide absolute assurance is mission critical for the longevity of any crypto network, as entrepreneurs will only rally around accounting schemes that prove to be highly reliable.

It's likewise important to note that double entry and Bitcoin triple entry are complementary in nature. A quick glance at the table provided within the section should show that Bitcoin fills some gaps in the double entry scheme that are welcomed additions to the accounting offerings available on the market today. It is of equal importance to note that bitcoins (the unit of account) are compatible with both the Bitcoin network and a locally run double entry software. The same cannot be said of competing fiat monies such as the US Dollar, the Euro, or British Pounds, which only have access to one part of the full accounting suite (double entry). In a later section we will further explore the implications of such a distinction.

## _5: Bitcoin + Lightning vs Double Entry Accounting_

Detractors have long argued that Bitcoin would never be anything more than a fledgling network due to its inability to scale. These same naysayers have further posited that layer 2 solutions were a pipe dream and would never come to fruition. Fortunately, this has proven not to be the case as of early 2019, with the rapid expansion of Lightning Network in terms of users, nodes, channels, and BTC capacity. On the surface Lightning looks like an additional payment rail that will help expand Bitcoin's transactional reach. This description is accurate, but the real question is "why does it enable higher transactional throughput?". From an accounting standpoint, the answer is that Lightning represents an iteration on old school double entry, and more specifically, a Bitcoin-native double entry scheme. Before discussing Lightning any further, let's present the table from the previous section with a new column attached:

![](/assets/images/cy19/cy19q2m5/perma-4.png){: .align-center}
Double-Entry vs Bitcoin vs Lightning

What we start to see from the table above is that Lightning represents a middle ground between double entry and Bitcoin triple entry from an assurance perspective. This trade off for establishing a middle ground is accomplished at the expense of simplicity and flexibility that old school double entry offers. As such, double entry remains relevant and useful in an accounting universe where Bitcoin + Lightning exist. Dually important is what the layered approach to scaling represents: an adherence to accounting + audit principles. During any financial statement audit, amounts that are below a certain materiality threshold individually + summated are ignored, as assurance over the small balances would generally provide trivial amounts of additional confidence in the state of the financials in question. Bitcoin and Lightning leverage this rationale for scaling Bitcoin, by moving smaller transactions to a less redundant accounting + audit layer, with the option of always using Bitcoin's on-chain absolute assurance at the click of a button when closing out a Lightning channel.

## _6: Implications + Conclusions_

### **Bitcoin as the Ultimate Accounting Tool**

Bitcoin has the potential to become the center of the accounting universe. Why? Because bitcoins (the unit of account) are fully compatible across all 3 parts of the accounting suite, whereas fiat monies only have access to a single part. Visually speaking, we can illustrate this difference as follows:

![](/assets/images/cy19/cy19q2m5/perma-5.png){: .align-center}

Since fiat monies are not natively crypto based, they are incapable of accessing the full depths of the accounting + utility assurances offered by cryptocurrencies. Stablecoins do not qualify as they have huge centralized dependency issues and, the stablecoin merely represents dollars that only exist off-chain (or in some cases, "supposedly" exist off-chain). What this difference implies is that when Bitcoin comes of age it will be more useful than fiat, as there will be more ways to reliably account for value for prospective entrepreneurs. More ways to account for value with different accounting models that are strong in different arenas suggests that there will be new types of businesses created with a Bitcoin-centric viewpoint, while fiat sits watching on the sidelines.

Lastly, "The Full Bitcoin Accounting Suite" graphic might provide some clues to lingering concerns over a low block subsidy future. If Bitcoin becomes the center of the accounting universe and the ultimate source of value-based truth, there's a high chance that demand will capably support security of the network. Those who argue "high fees will kill adoption" fail to understand the intensity of assurances Bitcoin offers, and the ease at which it does this. Put lightly — Bitcoin is insanely cheap compared to alternative options for obtaining high degrees of assurance. Bitcoin is a vehicle built for moon missions, but we are giving it similar treatment to a scooter.

Extra thought: Bitcoin might not be considered a "Unit of Account" from a monetary perspective, but it is already the ultimate Unit of Account in the most important sense of the phrase — from the accounting viewpoint.

### **Blockchain Model is Here to Stay**

This point isn't something many people spend much time thinking about. However, there are still some out there that are looking to speculate on alternative forms of Distributed Ledger Technology (DLT). If these other distributed accounting models aim to upend the blockchain model, they need to equally / stronger provide (1) simplicity in accounting for value or (2) intensity of assurances that the blockchain model already offers. I for one consider this unlikely, as the blockchain model is quite simple (Satoshi explained it in 6 sentences in the Bitcoin whitepaper) and the assurances blockchains provide are almost absolute in their guarantees under the correct implementation + resource commitment to the network.

### **Bitcoin's Most Fundamental Value Proposition**

We hear a variety of reasons for why bitcoins might be valuable. Some of these reasons include sound money, a hedge against central banking, etc. These are all true but provide reasons that are external to the network itself. To date I have not seen the true value proposition for Bitcoin and its unit of account, bitcoins, described anywhere at the most fundamental level. By establishing the fundamental value proposition, we can work our way into the more social realms that are popularly discussed. So, before concluding, we will attempt to concisely explain it below:

_Bitcoins are valuable because they are the irreplaceable, scarce incentive token that serve as the glue to a distributed, novel, triple-entry accounting scheme that disintermediates money + accounting + third party verification by combining them into a single, software-based product. Demand exists to use this software because it offers absolute assurance in accounting for value transfer / storage, which is a proposition that no other accounting system on the planet is capable of offering. Bitcoin's accounting scheme is also unique in that it possesses the properties that enable intense utility-based assurances for users such as censorship resistance and asset seizure resistance. These very features make bitcoins a popular value storage vehicle for "aggressive uses and users", who also have the benefit of easier access to it as a result of its digital + open build. The combination of accounting + utility based assurances + digital / open build makes bitcoins an ideal tool for protection against the current monetary regime, and ultimately a quality candidate for a market-selected "sound money"._

### **Final Thought**

Double entry accounting has survived 600–700 years and has more than capably supported a wide variety of enterprises, ranging from textile firms of the industrial revolution to space travel companies of today. This accounting scheme has outlived 99% of the businesses built on top of it and has provided such a large amount of value that it would be futile to attempt to make the calculation. With this in mind — it's still worth wondering what an investment in double entry within its first 10 years would have amounted to today.

Why? Because the opportunity to invest in Proof of Work + Triple Entry accounting is available via Bitcoin. The ability to provide absolute assurance from an accounting perspective is unique historically and completely underappreciated by the market at large. Nonsense from the "Blockchain, not Bitcoin" era of 2015–2016 scared people off from the accounting side of the coin, but it's time we come full circle to fully appreciate Bitcoin for the accounting beast that it is. This robust accounting layer enables everything that we appreciate about Bitcoin and will likely propel it forward in the global money battle that is already well underway. For this reason it is imperative that all involved understand Bitcoin as a money AND accounting revolution.

_Big thank you to Oke Pearson ([@OkePearson](https://twitter.com/OkePearson) on Twitter) for his help in reviewing this piece + all accounting related material included within._

Sources:
1. [**Triple Entry Accounting** _The digitally signed receipt, an innovation from financial cryptography, presents a challenge to classical double entry..._ nakamotoinstitute.org](https://nakamotoinstitute.org/triple-entry-accounting/) 
2. [**Formalizing and Securing Relationships on Public Networks - Satoshi Nakamoto Institute** _Computers make possible the running of algorithms heretofore prohibitively costly, and networks the quicker..._ nakamotoinstitute.org](https://nakamotoinstitute.org/formalizing-securing-relationships/)
3. [**The Ricardian Contract** _Describing digital value for payment systems is not a trivial task. Simplistic methods of using numbers or country..._ nakamotoinstitute.org](https://nakamotoinstitute.org/the-ricardian-contract/) 
4, [**Money, Blockchains, and Social Scalability** _Blockchains are all the rage. The oldest and biggest blockchain of them all is Bitcoin, which over its eight-year..._ nakamotoinstitute.org](https://nakamotoinstitute.org/money-blockchains-and-social-scalability/) 
5. [**A History of Accounting and Accountants** _Edit description_ books.google.com](https://books.google.com/books/about/A_History_of_Accounting_and_Accountants.html?id=al7OAAAAMAAJ&printsec=frontcover&source=kp_read_button#v=onepage&q&f=false) 
6. [**Unpacking Bitcoin's Assurances** _Dis-aggregating the system's guarantees_ medium.com](https://medium.com/@nic__carter/unpacking-bitcoins-assurances-a3c98824d3f0)
7. [**#1: Assurances in Crypto** _A Breakdown of BTC, DCR, & Everything Else_ blog.goodaudience.com](https://blog.goodaudience.com/1-assurances-in-crypto-14c55a1fd616) 
8. [**Double Entry: How the Merchants of Venice Created Modern Finance** _"Lively history. . . . Show[s] double entry's role in the creation of the accounting profession, and even of capitalism..._ www.amazon.com](https://www.amazon.com/Double-Entry-Merchants-Created-Finance-ebook-dp-B007Q6XKA8/dp/B007Q6XKA8/ref=mt_kindle?_encoding=UTF8&me=&qid=1558387369)
