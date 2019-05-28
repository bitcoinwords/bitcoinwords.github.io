---
title: "Satoshi's vision for bitcoin as told by its predecessors"
permalink: "/satoshis-vision-for-bitcoin-as-told-by-its-predecessors"

tags:
  - Tony Sheng
  - CY19 Q2

excerpt: Tony Sheng explores attempts at digital currencies before the Bitcoin experiment and how those projects influenced Bitcoin. Posted May 28, 2019.

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

# [Satoshi's vision for bitcoin as told by its predecessors](https://www.tonysheng.com/design-goals-bitcoin-predecessors)
### By [Tony Sheng](https://twitter.com/tonysheng)
### Posted May 28, 2019

While bitcoin often gets credit for being "first"<sup>[1](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fn:poll)</sup> , there were a number of predecessors<sup>[2](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fn:ht)</sup> that contributed to Satoshi's thinking. Most notably:

* David Chaum's [E-cash](http://blog.koehntopp.de/uploads/Chaum.BlindSigForPayment.1982.PDF) in 1982
* Haber & Stornetta's [Linked Time-stamping](https://sci-hub.tw/10.1007/3-540-38424-3_32) in 1991
* Wei Dai's [b-money](http://www.weidai.com/bmoney.txt) in 1998
* Adam Back's [Hashcash](https://nakamotoinstitute.org/literature/hashcash/) in 2002
* Szabo's [Bit Gold](https://nakamotoinstitute.org/bit-gold/) in 2005


Technological breakthroughs occur in context, and the context for bitcoin was in part shaped by these foundational works. This 2017 paper by Clark and Narayanan titled ["Bitcoin's Academic Pedigree"](https://queue.acm.org/detail.cfm?id=3136559) offers a wonderful synthesis of all the works that enabled Satoshi's design of bitcoin. They found:
> nearly all of the technical components of bitcoin originated in the academic literature of the 1980s and '90s. This is not to diminish Nakamoto's achievement but to point out that he stood on the shoulders of giants
The work of Satoshi's predecessors made bitcoin possible on the technical front, but how much did Satoshi's societal intentions for bitcoin mirror those of his predecessors?

In this post, I take a look at the stated intentions of foundational "cryptocurrency" work and compare that with bitcoin's original intentions. And then I reflect on where we are today.

## The stated objective of bitcoin


The first few lines of the [original bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf?) introduce the intentions of the technology: removal of trusted third parties.
> A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without going through a financial institution. Digital signatures provide part of the solution, but the main benefits are lost if a trusted third party is still required to prevent double-spending. We propose a solution to the double-spending problem using a peer-to-peer network.
Satoshi does not bury the lede. Bitcoin allows "online payments to be sent directly from one party to another without going through a financial institution." One no longer requires the help of a trusted third party to send and receive money.

Such a system would make non-reversible transactions possible and reduce fraud. Because users don't have to trust third parties and merchants don't have to trust users, a payment system based on bitcoin would minimize the quantity of personal information that gets captured to combat fraud. And less fraud would reduce costs.

In sum (taking the whitepaper at face value), Satoshi thought bitcoin would:

* Enable a new type of service: "non-reversible transactions"
* Reduce fees
* And increase privacy<sup>[3](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fn:priv)</sup>

## Bitcoin predecessors


How similar or dissimilar were the stated objectives of bitcoin's predecessors?

### E-cash (1982)


Compared with bitcoin, Chaum's E-cash focused less on removing third parties entirely and more on privacy. It tries to tackle the fundamental challenge with crypto-anarchy: a system where individuals are unlinkable to actions makes it impossible to marginalize any group (good) but also makes it impossible to punish evil actors (bad).

He writes:
> The ultimate structure of the new electronic payments system may have a substantial impact on personal privacy as well as on the nature and extent of criminal use of payments. Ideally a new payments system should address both of these seemingly conflicted sets of concerns.
His goals were to create a cryptocurrency with the:

1. "Inability of third parties to determine the payee, time or amount of payments made by an individual"
2. "Ability of individuals to provide proof of payment, or to determine the identity of the payee under exceptional circumstances"
3. "Ability to stop use of payments media reported stolen"


The paper itself focuses mostly on a concept called "blind signatures" which would allow accounting for transactions without revealing the behaviors of individual actors. It doesn't spend much (any?) time on the system's ability to stop use of payments or reveal personal data in exceptional circumstances.

But it's clear that Chaum wanted a digital cash that was as private as possible that still operated well within the bounds of legacy systems. In contrast, satoshi designed bitcoin to operate outside the legacy systems.

### Linked time-stamping (1991)


Haber and Stornetta observed that time-stamps were easy to forge and tamper with in the digital world.
> What is needed is a method of time-stamping digital documents with the following two properties. First, one must find a way to time-stamp the data itself, without any reliance on the characteristics of the medium on which the data appears, so that it is impossible to change even one bit of the document without the change being apparent. Second, it should be impossible to stamp a document with a time and date different from the actual one
They proposed a design called "linked time-stamping." Documents are created and broadcast to a network. Each new document asserts a time of creation and signs the document and the previously broadcast document, creating a linked list of documents, forming a sort of time-chain.

This data structure is the basis of bitcoin's ledger.

Haber and Stornetta were not focused on financial use-cases. They created their design to help with copyright and patent law, law enforcement, and verification of media authenticity. Still, their work was a breakthrough in trustless verification of data, and proved invaluable to the cypherpunks to follow.

### Hashcash (1997, updated in 2002)


_Note: while the original Hashcash paper was published in 1997, we review an updated version from 2002 that references b-money._

Back's Hashcash was originally proposed to prevent overuse of free internet resources like email, deterring "denial of service" attacks by making it costly. The paper focuses much more on the technical mechanisms than the potential applications. It doesn't have strong design objectives beyond a "proof of work" mechanism.

In the short "Applications" section of the paper, Back alludes to the possible application of Hashcash for cryptocurrencies:
> hashcash as a minting mechanism for Wei Dai's b-money electronic cash proposal, an electronic cash scheme without a banking interface
The clear parallel to the bitcoin whitepaper is a desire to disintermediate the "banking interface" or obviate "trusted third parties."

### b-money (1998)


_Note: discussed b-money in my popular post ["Let's ditch decentralization"](https://www.tonysheng.com/decentralized-definition). Also, while there are many common themes between bitcoin and b-money, there is no evidence that Satoshi was aware of b-money when he write bitcoin whitepaper._

Dai's b-money has many similarities to bitcoin: a peer-to-peer digital money that is minted through proof-of-work, held and used by pseudonymous accounts, and publicly verifiable by all.

The notable thematic difference between b-money and bitcoin is Dai's focus on privacy. He opens the paper with his fascination of "crypto-anarchy" (a fascination I share, as readers will know):
> I am fascinated by Tim May's crypto-anarchy. Unlike the communities traditionally associated with the word "anarchy", in a crypto-anarchy the government is not temporarily destroyed but permanently forbidden and permanently unnecessary. It's a community where the threat of violence is impotent because violence is impossible, and violence is impossible because its participants cannot be linked to their true names or physical locations.
To Dai, b-money was a way for crypto-anarchic societies to coordinate. It afforded a monetary system that did not require exposure of personal information.

(Of course, we know today that just because a system _can_ operate with perfect anonymity does not mean that it will. Users will dox themselves by linking their addresses to third-party gateways like exchanges. Or simply reveal their address to the public. There's also the possibility of systematic ["unraveling"](https://www.tonysheng.com/privacy-freedom-crypto-anarchy) of privacy and anonymity.)

### Bit Gold


The intention behind Szabo's Bit Gold is best articulated in the third paragraph<sup>[4](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fn:though)</sup> :
> it would be very nice if there were a protocol whereby unforgeably costly bits could be created online with minimal dependence on trusted third parties, and then securely stored, transferred, and assayed with similar minimal trust. Bit gold.
Unforgeably costly bits, minimal dependence on trusted third parties, securely stored, transferred, and assayed with minimal trust. Sounds like bitcoin!

The thematic difference between the Bit Gold and bitcoin papers is Szabo's relative focus on the societal implications of a trustless digital money and zero mention of privacy.
> In summary, all money mankind has ever used has been insecure in one way or another. This insecurity has been manifested in a wide variety of ways, from counterfeiting to theft, but the most pernicious of which has probably been inflation. Bit gold may provide us with a money of unprecedented security from these dangers.
Modern discourse of the benefits of bitcoin tend to build on the Szabo-ian focus on "secure" money or "sound" money. For this reason (and many others), many speculate Szabo is Satoshi or at least strongly influenced Satoshi.

### More similar than different


With the exception of E-cash, which prioritizes privacy over trustlessness, all of these papers tend to focus on trustlessness (or as Szabo would put it, trust minimization). Linked time-stamps introduces a data structure well suited for trustless digital money. Hashcash establishes technical foundations for proof-of work. B-money and Bit Gold apply concepts like proof-of-work to describe monetary systems where users can transact with one another without a trusted third party.

We can see strong influences from Timothy May's crypto-anarchy movement; explicitly in Dai's b-money and implicitly in the treatment of default pseudonymity in the others. However, with over a decade in hindsight, we we can see that pseudonymity at the account level is insufficient to protect the identities of most users given the proliferation of third-party gateways (like exchanges).

Interestingly, there's also almost no mention of "programmability" in these early works–a feature that spawned Ethereum and the many other "smart contract protocols." Perhaps this is a case of "walk before you can run," but many would argue this focus on just pure money features is intentional. Szabo describes it as limiting the [surface area of attack](https://twitter.com/nickszabo4/status/964212372624703488?lang=en) .

## How do we fulfill Satoshi's vision?


Most debates within bitcoin communities (inclusive of forks like BCash and Bitcoin SV) and between bitcoin communities and other cryptocurrency communities (e.g. bitcoin vs ethereum) are about vision. What properties should a cryptocurrency have to best satisfy Satoshi's true intentions? What would Satoshi want to see (how would they change their vision) if they knew what we knew today?

A coarse literature review reveals a shared focus on a single property: trust minimization. And perhaps an assumption of other properties like overall cost reductions to the system and user anonymity. There is no mention of "programmability" in these works, though we know early bitcoin communities (including Satoshi) discussed versions of programmability often. (I believe Satoshi had some ideas for more features on top of bitcoin like debt, lending, and gambling but Hal Finney convinced him against it. I can't find this source so if you have it, please send it to me and I'll revise.)

One can understand the nature of conflicts within bitcoin and between bitcoin and other cryptocurrencies as negotiating trade-offs between trust-minimization and other properties. Bitcoin Cash trades trust-minimization for bigger blocks, which theoretically leads to cheaper and faster transactions. Ethereum trades for programmability. Zcash and Monero trade for privacy (this one I'm less sure of, feedback welcome).

But while the vision for bitcoin core has [changed over the years](https://medium.com/@nic__carter/visions-of-bitcoin-4b7b7cbcd24c) , it seems to have remained true (at least in a relative sense) to the singular focus of trust minimization. And in doing so, bitcoin has achieved a [valuable strength](https://www.tonysheng.com/improving-strengths-weaknesses) unassailable by competitors<sup>[5](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fn:spots)</sup> .

parties involved and the trusted third party. The necessity to announce all transactions publicly precludes this method, but privacy can still be maintained by breaking the flow of information in another place: by keeping public keys anonymous." Keep your public keys anonymous and don't reuse addresses. I wonder whether he'd feel the same today given sophisticated chain analytics companies.

_Thanks to [Nic Carter](https://twitter.com/nic__carter?lang=en) for his valuable feedback on this post._

1. When I [asked twitter](https://twitter.com/tonysheng/status/1121489679478472704) for the irreplicable properties of Bitcoin, I got a lot of "first."[↩](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fnref:poll)
2. Hat tip to Multicoin Capital and other contributors to the very useful [Crypto Archives](https://github.com/multicoincapital/crypto-archives). [↩](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fnref:ht)
3. Something I hadn't noticed before in my dozens of readings of the whitepaper. Satoshi makes these comments on privacy: "The traditional banking model achieves a level of privacy by limiting access to information to the [↩](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fnref:priv)
4. Though Szabo is a joy to read and his historical set-up is worth reading. Particularly his three self-links on [trust in a third party](https://nakamotoinstitute.org/trusted-third-parties/),[private bank note issue](https://unenumerated.blogspot.com/2005/11/flying-money-brief-overview.html), and [precious metals and collectibles](https://nakamotoinstitute.org/shelling-out/) [↩](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fnref:though)
5. Which does not mean that others cannot find their distinct markets by offering distinct design spaces. I still think this adoption will follow a curve like I described [in this post](https://www.tonysheng.com/blockchain-user-adoption-curve). The big question for investors is will the singular focus on trust minimization yield the largest and most valuable market. [↩](https://www.tonysheng.com/design-goals-bitcoin-predecessors#fnref:spots)
