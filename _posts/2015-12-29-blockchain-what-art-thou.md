---
title: "Blockchain, What Art Thou?"
permalink: "/blockchain-what-art-thou"

author: davehudson

tags:
  - Dave Hudson
  - 2015 Q4
  - Mining
  - Technology
  - Markets

excerpt: Blockchain, What Art Thou?. Posted December 29, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Blockchain, What Art Thou?](http://hashingit.com/analysis/45-blockchain-what-art-thou)
### By [Dave Hudson](https://hashingit.com/)
### Posted December 29, 2015

Begin Content

Details   Published: 29 December 2015

As we approach 2016 there seem to be endless discussions about "blockchain". It's a term that is ever-more frequently cited in even mainstream journalism, while in the fintech space alone there are a slew of would-be suppliers and would-be users claiming that "blockchain" will revolutionize any number of applications. This now-common usage suggests it must be something precisely defined and well understood, but this seems to be more a matter of mantra than comprehension.

The echo chambers of the Internet reverberate to many opinions, but attempts to find a precise meaning seem to find a dismaying lack of agreement. To be anything more than marketing hyperbole we really need the answers some questions. What is it? What isn't it? What might it be? Can it be something that will allow us to build new and enduring systems? In short, what is the essence of blockchain?

![](/assets/images/2015/m12/blockchain-what-art-thou1.jpg)

*Image: The Menai Suspension Bridge, Bangor, North Wales, UK, completed in 1826 (almost 190 years ago), demonstrates how blocks and chains can create something quite remarkable and enduring (photograph taken by the author).*

#### The Satoshi Whitepaper

Almost every discussion of blockchains starts with the Satoshi whitepaper, but it is this very foundation that starts us on a path to confusion. Neither the terms "blockchain" or "block chain" appear there; there are 67 uses of "block" and "27" of chain, but 0 of "block chain" or "blockchain". This aside though, let's see where this origin leads us.

The whitepaper is short; it's just 9 page long. The first mention of "block" and "chain" starts at the bottom of page 2, section 3, where there is a discussion of a basic timestamp server. Prior to this the whitepaper describes a series of design goals associated with the Bitcoin design such as the ability to allow two parties to transact without needing to trust a third party.

The statement of the design goals are fundamentally important. They set the scene for an implementation to meet those goals in which characteristics are layered upon each other, but it is informative to look at what each new layer does. In our quest for the nature of a blockchain we need to be careful to look for things that are its attributes, rather than characteristics of this first implementation.

##### Transactions

Section 1 of the whitepaper is an introduction and it is with section 2 that we see anything really substantive. Section 2 sets a scene for a digital coin, but it is described as being a chain of transactions in which the "coin" is assigned to new owners. The coin is really a metaphor for a transaction history of linked transactions.

Interestingly, section 2 also describes how a centralized system doesn't actually need to do this.

##### Blocks And Chains

With section 3 we see the essence of the design pattern that might best describe the basis of a blockchain. It is given as something that is constructed from a series of incremental blocks of data, each of which can be identified by a cryptographic hash over its contents. In addition, each block incorporates the cryptographic hash of its predecessor block to ensure the construction of a chain. The block hashes are published as a form of widely witnessed evidence that demonstrate shows the existence of both the block data and the predecessor hash. Changing either the predecessor or the other data within the block would result in a different hash signatuare for the block that would not match the widely witnessed view.

These characteristics are all fundamental, and without them we cannot construct anything interesting. What is equally interesting though is what is not stated as necessary at this point. There are no mentions of coins, no mentions of peer-to-peer networks, no mentions of mining, etc. Instead the suggestion is that publishing hashes in any widely disseminated form would be sufficient, with the 2 examples being given as publication in a newspaper or publication via Usenet.

While we see some explicit characteristics these lead to a few implicit ones:

* Publication of the hashes is meaningless unless those same hashes can be independently recomputed by an external observer who is given just the data from the blocks in the chain. It is this characteristic that enables the observers to not have to trust the originator of the chain of blocks; instead they are able to compare historical hashes for themselves.
* Recomputing of the hashes requires that the algorithm by which the blocks is produced be deterministic and well specified. Without these our external observer cannot recompute the hashes.

##### Enabling Peer-To-Peer Operations

The next section, 4, of the whitepaper talks about proof-of-work. The first line is interesting: "To implement a distributed timestamp server on a peer-to-peer (P2P) basis, we will need to use a proof-of-work system similar to Adam Back's Hashcash". Proof-of-work is not required to construct a blockchain, just to enable the peer-to-peer implementation of the timestamp server. Subsequent cryptocurrency designs have shown there are potentially other approaches that can be taken here too (e.g. forms of proof-of-stake, or hybrids of both), but if we are happy with a client-server approach then none of these are actually necessary.

This is not to say that proof-of-work might not have some other uses with a blockchain design, but none seem fundamental to our quest.

##### Network And Beyond

Section 5 describes the implementation characteristics of the Bitcoin network. Nothing here explicitly extends the concept of what a blockchain is, or might require. Indeed, neither sections 6, 7, 8, 9, 10, 11 or 12 (the final section) go on to explicitly offer any new ideas about what a blockchain might be.

#### Answers To Our Questions

If the Satoshi whitepaper is the origin of the blockchain design we're left with a rather thin definition, but perhaps that is the most enlightening aspect. It is very explicit about particular design choices and their purpose, which tends to lead towards a realization that many of the claims about "blockchains" may actually be a matter of implementation rather than architecture.

Let's ask some specific questions then!

##### Must A Blockchain Have Coins?

There is an interesting discussion in the whitepaper about the need to provide incentives to those providing security to the P2P network to remain honest and as a means to introduce "coins" into the system, but the discussion is clearly in the context of the P2P network. The concept of coins themselves is noted as unnecessary with a trusted "mint".

A trusted mint is not something desirable in a cryptocurrency, but there seems to be no requirement for coins if we wish to construct a chain of cryptographically-linked blocks. There is an interesting question to ask about trust but we will return to that later.

##### Must A Blockchain Implement Smart Contracts?

From the perspective of the whitepaper this seems unlikely. The word "contract" does not appear anywhere.

Might a blockchain enable smart contracts? Yes, of course it might, but it might enable many other things too.

##### Must A Blockchain Be Programmable?

Again the answer seems to be no. Neither the words "program" or "script" appear in the whitepaper.

A blockchain does have a requirement to be interpretable by one or more indepdendent observers, so it is clearly built from one or more well-defined data structures. The block data structure must contain a previous block hash, and the cryptographic hash of the block must be performed in a very specific way, but none of these require that the data structure carry any notion of executable code.

Can a blockchain contain some form of program code? This is an implementation question and the answer is yes. Bitcoin includes a limited scripting language, and other systems, such as Ethereum, have subsequently attempted to support more elaborate programming models. The choice to support such concepts seems more to be either expedience, or, more ambitious design goals, but it seems a blockchain need no more be "programmable" than any other linked list data structure.

##### Is A Blockchain A Database?

Once more the answer seems to be no. As before, the word "database" does not appear in the whitepaper.

At its core a blockchain is a special type of data structure. The blocks within the chain contain data, but this does not make it a database; at best the blocks represent the transaction log of a specific database implementation. Similarly there are no semantics for querying a blockchain, any more than there are for querying a linked list. A specific implementation might allow for queries of either but the implementation does not define the thing itself.

As a point of comparison, the IP packets that for the TCP packets carrying this article are defined as data structures in a series of IETF (Internet Engineering Task Force) RFC (Request For Comments) documents. The documents describe the form of the packets and their behaviour when they are transported. Recipients of those packets are able to make their own determinations of their validity without regard to any part of the network implementation between them and the originator. An implementation of a router/firewall may offer a feature to capture those packets so that they can be analyzed later, and may offer database queries of those packets, but there is nothing in the nature of an IP packet that makes it a database, nor is there anything in the RFCs that would suggest otherwise. Implementation features and specification are very different things.

Is A Blockchain Trustless?

The answer here is no too, but that's because the question is too broad. A blockchain does allow us to require less trust than many traditional systems but any implementation still requires some level of trust.

A recipient of block data must trust that it has been delivered without being compromised by some intermediary. The P2P distribution of blocks within the Bitcoin and similar networks set out to try to minimize trust in peers, but even this model has potential failure points. Here are a few:

* We trust that the blockchain software that we are running has not been compromised to deliver falsified data.
* We trust that the operating system under which our blockchain software is running has not been compromised to deliver falsified data.
* We trust that the network processors providing connectivity to our system have not been compromised to deliver falsified data.

"In code we trust" makes for an interesting mantra, but 30+ years of malware, spyware, etc., informs us that this is a highly debatable strategy.

A blockchain design does make falsifications harder for an adversary, and makes accidental errors dramatically less likely. We are able to "trust but verify" (within bounds), but this is still a significant improvement over blindly trusting. Most importantly, none of these trust minimizing characteristics are aspects of the P2P network design, but are instead intrinsic to the block encoding.

##### Must A Blockchain Be Non-Permissioned Or Can It Be Permission-less?

A blockchain is just a data structure so really the question makes no sense. Who has the ability to read or write a data structure is a totally different question.

Let's ignore this subtle distinction for a moment, though, and act as if the question might make sense. Consider the case of Bitcoin; who writes the blockchain? The answer is that miners (or more precisely, block makers such a mining pool operators, not those who just hash blocks) get to write new blocks. Transactors on the network can provide candidate transactions to be included in blocks, but this does not guarantee blocks will ever contain those transactions. With Bitcoin we talk about this being "non-permissioned" because no-one needs any explicit permission to become a block maker.

If we consider other potential uses of a blockchain design, though, there are a often very well defined set of participants who we would wish to be able to write block data. In many cases this may even be one single participant. A critique levelled at such potential uses of a blockchain are that this makes it no better than a database, but a conventional database is something in which blind trust must be placed. Its internal state is generally unknowable. Even in its simplest uses a blockchain can at least provide a means to verify the state of such a system, and to do so in a way that enables histories to be validated. This is only the start of the possibilities, however!

##### Is A Blockchain The Internet Of Money (Or The Internet Of Anything Else)?

Realistically, no, or at least not on its own.

When we looked at "not a database" we also touched on why this claim doesn't really make sense. Superficially the argument seems seductive. The thought is that we can build lots of technology on top of a blockchain in the way that a network stack is layered.

There are many problems with this proposition, but the obvious one is that a blockchain is just a data structure. It makes a good candidate for being used to convey information across the Internet but doesn't enable anything in and of itself. Separating the blockchain from any transport of a blockchain, however, does give some hope that blockchains may enable more reliable financial applications over the Internet. A clear separation also allows experimentation at each layer of the system design and this is a key characteristic that has enabled the Internet to be so successful. With the Internet, candidates for all layers of the network stack are able to be trialled, replaced or modified, allowing the best designs to win. Similarly the standards-based approach has enabled disparate implementations to work together without preventing commercial advantages from being sought and monetized.

In the case of blockchains we have already seen that there is a requirement to support external observers and this mandates a level of interoperability.

Last Thoughts

We have looked at what a blockchain might or might not be, and perhaps seen some hints of what it might enable. The technology that underpins Bitcoin can be used to build many things, and Bitcoin's legacy should not just be Bitcoin itself, but that is has shown the viability of something far more fundamental. The debate over what constitutes a blockchain won't end here, but we need to move the discussion forward and we need to resist the urge to allow it be just another marketing buzzword.

To make that happen we need both clear terminology, and well reasoned usage. We need to avoid conflating many different ideas, and we need technology claims to be realistic and achievable. If we fail then, eventually, the term blockchain will be meaningless and have to be replaced. This seems like the wrong outcome. If we succeed then the idea of a blockchain will not be the end of the story. Instead it will take its place as a layer upon which better and ever-more useful systems can be built.

End Content

***

{% include signup.md %}
