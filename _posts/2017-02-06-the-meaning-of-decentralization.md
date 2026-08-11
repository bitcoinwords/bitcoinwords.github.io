---
title: "The Meaning of Decentralization"
permalink: "/the-meaning-of-decentralization"

author: vitalikbuterin

tags:
  - Vitalik Buterin
  - 2017 Q1
  - Politics
  - Technology
  - Altcoins

excerpt: The Meaning of Decentralization. Posted February 6, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Meaning of Decentralization](https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274)
### By Vitalik Buterin
### Posted February 6, 2017

“Decentralization” is one of the words that is used in the cryptoeconomics space the most frequently, and is often even viewed as a blockchain’s entire raison d’être, but it is also one of the words that is perhaps defined the most poorly. Thousands of hours of research, and billions of dollars of hashpower, have been spent for the sole purpose of attempting to achieve decentralization, and to protect and improve it, and when discussions get rivalrous it is extremely common for proponents of one protocol (or protocol extension) to claim that the opposing proposals are “centralized” as the ultimate knockdown argument.

But there is often a lot of confusion as to what this word actually means. Consider, for example, the following completely unhelpful, but unfortunately all too common, diagram:

![](/assets/images/2017/m2/the-meaning-of-decentralization1.png)

Now, consider the two answers on Quora for “[what is the difference between distributed and decentralized](https://www.quora.com/Whats-the-difference-between-distributed-and-decentralized-in-Bitcoin-land)”. The first essentially parrots the above diagram, whereas the second makes the entirely different claim that “distributed means not all the processing of the transactions is done in the same place”, whereas “decentralized means that not one single entity has control over all the processing”. Meanwhile, the top answer on the Ethereum stack exchange gives a [very similar diagram](http://ethereum.stackexchange.com/questions/7812/question-on-the-terms-distributed-and-decentralised), but with the words “decentralized” and “distributed” switched places! Clearly, a clarification is in order.

##### Three types of Decentralization

When people talk about software decentralization, there are actually *three separate axes* of centralization/decentralization that they may be talking about. While in some cases it is difficult to see how you can have one without the other, in general they are quite independent of each other. The axes are as follows:

* **Architectural (de)centralization**— how many **physical computers** is a system made up of? How many of those computers can it tolerate breaking down at any single time?
* **Political (de)centralization** — how many **individuals or organizations** ultimately control the computers that the system is made up of?
* **Logical (de)centralization**— does the **interface and data structures** that the system presents and maintains look more like a single monolithic object, or an amorphous swarm? One simple heuristic is: if you cut the system in half, including both providers and users, will both halves continue to fully operate as independent units?

We can try to put these three dimensions into a chart:

![](/assets/images/2017/m2/the-meaning-of-decentralization2.png)

Note that a lot of these placements are very rough and highly debatable. But let’s try going through any of them:

* Traditional corporations are politically centralized (one CEO), architecturally centralized (one head office) and logically centralized (can’t really split them in half)
* Civil law relies on a centralized law-making body, whereas common law is built up of precedent made by many individual judges. Civil law still has some architectural decentralization as there are many courts that nevertheless have large discretion, but common law have more of it. Both are logically centralized (“the law is the law”).
* Languages are logically decentralized; the English spoken between Alice and Bob and the English spoken between Charlie and David do not need to agree at all. There is no centralized infrastructure required for a language to exist, and the rules of English grammar are not created or controlled by any one single person (whereas Esperanto was originally invented by [Ludwig Zamenhof](https://en.wikipedia.org/wiki/L._L._Zamenhof), though now it functions more like a living language that evolves incrementally with no authority)
* BitTorrent is logically decentralized similarly to how English is. Content delivery networks are similar, but are controlled by one single company.
* Blockchains are politically decentralized (no one controls them) and architecturally decentralized (no infrastructural central point of failure) but they are logically centralized (there is one commonly agreed state and the system *behaves* like a single computer)

Many times when people talk about the virtues of a blockchain, they describe the convenience benefits of having “one central database”; that centralization is logical centralization, and it’s a kind of centralization that is arguably in many cases good (though Juan Benet from IPFS would also push for logical decentralization wherever possible, because logically decentralized systems tend to be good at surviving network partitions, work well in regions of the world that have poor connectivity, etc; see also [this article from Scuttlebot](http://scuttlebot.io/more/articles/design-challenge-avoid-centralization-and-singletons.html) explicitly advocating logical decentralization).

Architectural centralization often leads to political centralization, though not necessarily — in a formal democracy, politicians meet and hold votes in some physical governance chamber, but the maintainers of this chamber do not end up deriving any substantial amount of power over decision-making as a result. In computerized systems, architectural but not political decentralization might happen if there is an online community which uses a centralized forum for convenience, but where there is a widely agreed social contract that if the owners of the forum act maliciously then everyone will move to a different forum (communities that are formed around rebellion against what they see as censorship in another forum likely have this property in practice).

Logical centralization makes architectural decentralization harder, but not impossible — see how decentralized consensus networks have already been proven to work, but are more difficult than maintaining BitTorrent. And logical centralization makes political decentralization harder — in logically centralized systems, it’s harder to [resolve](http://www.coindesk.com/hard-fork-ethereum-dao/) [contention](https://en.bitcoin.it/wiki/Block_size_limit_controversy) by simply agreeing to “live and let live”.

##### Three reasons for Decentralization

The next question is, why is decentralization useful in the first place? There are generally several arguments raised:

* **Fault tolerance**— decentralized systems are less likely to fail accidentally because they rely on many separate components that are not likely.
* **Attack resistance**— decentralized systems are more expensive to attack and destroy or manipulate because they lack [sensitive central points](http://starwars.wikia.com/wiki/Thermal_exhaust_port) that can be attacked at much lower cost than the economic size of the surrounding system.
* **Collusion resistance**— it is much harder for participants in decentralized systems to collude to act in ways that benefit them at the expense of other participants, whereas the leaderships of corporations and governments collude in ways that benefit themselves but harm less well-coordinated citizens, customers, employees and the general public all the time.

All three arguments are important and valid, but all three arguments lead to some interesting and different conclusions once you start thinking about protocol decisions with the three individual perspectives in mind. Let us try to expand out each of these arguments one by one.

***

{% include signup.md %}
