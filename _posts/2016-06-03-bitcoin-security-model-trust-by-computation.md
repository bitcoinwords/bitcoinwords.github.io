---
title: "Bitcoin security model: Trust by computation"
permalink: "/bitcoin-security-model-trust-by-computation"

author: andreasmantonopoulos

tags:
  - Andreas M. Antonopoulos
  - 2016 Q2
  - Money
  - Security
  - Proof of Work

excerpt: Bitcoin security model: Trust by computation. Posted June 3, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin security model: Trust by computation](https://medium.com/@aantonop/bitcoin-security-model-trust-by-computation-d5b93a37da6e)
### By Andreas M. Antonopoulos
### Posted June 3, 2016

*First*[*published*](http://radar.oreilly.com/2014/02/bitcoin-security-model-trust-by-computation.html)*February 2014 in O’Reilly Radar*

Bitcoin is a distributed consensus network that maintains a secure and trusted distributed ledger through a process called “proof-of-work.”

Bitcoin fundamentally inverts the trust mechanism of a distributed system. Traditionally, as we see in payment and banking systems, trust is achieved through access control, by carefully vetting participants and excluding bad actors. This method of trust requires encryption, firewalls, strong authentication and careful vetting. The network requires investing trust in those gaining access.

The result is that such systems tend to be closed and small networks by necessity. By contrast, bitcoin implements a trust model of trust by computation. Trust in the network is ensured by requiring participants to demonstrate proof-of-work, by solving a computationally difficult problem. The cumulative computing power of thousands of participants, accumulated over time in a chain of increasing-difficulty proofs, ensures that no actor or even collection of actors can cheat, as they lack the computation to override the trust. As proof-of-work accumulates on the chain of highest difficulty (the blockchain), it becomes harder and harder to dispute. In bitcoin, a new proof-of-work is added every 10 minutes, with each subsequent proof making it exponentially more difficult to invalidate the previous results.

Here’s the most important effect of this new trust model of trust-by-computation: no one actor is trusted, and no one needs to be trusted. There is no central authority or trusted third party in a distributed consensus network. That fact opens up a completely new network model, as the network no longer needs to be closed, access-controlled or encrypted. Trust does not depend on excluding bad actors, as they cannot “fake” trust. They cannot pretend to be the trusted party, as there is none. They cannot steal the central keys as there are none. They cannot pull the levers of control at the core of the system, as there is no core and no levers of control.

As a result, the network can be open to all; the transactions can be broadcast on any medium, unencrypted; and applications can be added at the edge without vetting or approval. In other words, bitcoin is not just money for the Internet, it is the Internet of money — an open, de-centralized, standards-based network where innovation can occur at the edge without permission and where the network itself is simply a neutral and open transport layer.

Like the Internet and other open networks, blockchain-based crypto-currency networks are susceptible to denial-of-service and other nuisance attacks. Attacks that cannot violate the trust of the distributed asset ledger, but can clog the pipes and attempt to confuse the participants. When such attacks occur, they can cause deep concern among those who have a predilection for the security model of access control. If a bad actor gains access to a closed financial network, the results are catastrophic. Open access and trust are fundamentally at odds in a closed centralized network based on access control. Therefore, within that context, a denial of service attack or any bad actors on the network have dire consequences and signify a compromise of security and a failure of the trust model.

On bitcoin and other open crypto-currency networks, however, bad actors on the network are inconsequential because the trust model does not depend on excluding them. The bad actors are not trusted any more than any other user of the network and their access does not grant them any special rights. The trust model depends on computation and the demonstration of computation through proof-of-work. As long as good actors form the majority of the computation used for forming consensus, the bad actors cannot change the trusted ledger.

It will take time for the idea of decentralized trust through computation to become a part of mainstream consciousness, and until then, the idea creates cognitive dissonance for those accustomed to centralized trust systems. With thousands of years of practical use, centralized systems of trust are accepted unconditionally and without much thought as the only model of trust.

Until recently, decentralized trust at scale was not possible. Now that it is, it conflicts with most people’s understanding of the world. That’s why when you explain crypto-currencies to people, they immediately search for the central actor or authority that establishes the trust, establishes the value or has the control: “Yes, I see it is decentralized, but who runs it? Who controls it? Can’t someone take over?” These questions reveal the context of trust centralization, which is deeply embedded in our culture and our thinking. We’ve been taught to fear the bad actor and look for self-interested “trusted” individuals; we no longer have to do that.

Gradually, decentralized trust will be accepted as a new and effective trust model. We have seen this evolution of understanding before — on the Internet. The Internet led to the decentralization of authority-of-opinion, by making it possible for anyone to be a publisher without a multi-story building-sized printing press. At first, this challenged our expectations and forced us to reconsider the source of authority. If anyone could have an opinion and publish it, how can we tell which opinions are important? We had used the centralization of printing presses and distribution and the purchasing of ink by the barrel as a proxy metric of authority, to help us filter our news and opinions. Suddenly, we were thrust into a new world in which these anchors of authority were swept away and each opinion had to be judged by its merits, not the size of the publisher’s press.

Now, we must rethink the source of trust in networks and the source of monetary value of currencies, disconnected from the issuer, without a central authority and without the need for access control. The trust model has already changed, but it will take a while for society to accept that a new model is possible.

***

{% include signup.md %}
