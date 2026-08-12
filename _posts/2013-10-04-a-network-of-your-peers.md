---
title: "A network of your peers"
permalink: "/a-network-of-your-peers"

author: mikehearn

tags:
  - Mike Hearn
  - 2013 Q4
  - Technology
  - Decentralization

excerpt: A network of your peers. Posted October 4, 2013.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [A network of your peers](https://medium.com/@octskyward/a-network-of-your-peers-d3f9f299f729)
### By Mike Hearn
### Posted October 4, 2013

![](/assets/images/2013/m10/a-network-of-your-peers1.jpg)

*Photo by Petr Kratochvil*

##### How P2P networks on the internet can define and shape their communities.

In the last few days two peer to peer systems have been making headlines: Tor and Bitcoin. Both of these networks are characterised by a lack of central control and the (optional) anonymity of their users. It is often assumed that networks such as these must inherently be free-for-alls, in which the lack of a central co-ordinator implies the lack of any kind of enforced ground rules.

In this article, I will argue that many P2P networks define and enforce particular rules upon their users. I will examine the case of Tor hidden services in particular. Finally, I will also explore how proofs of sacrifice can help create decentralised communities that nevertheless have working codes of conduct.

#### A brief history

The internet has always, at its core, been decentralised infrastructure. As a result, throughout its brief history, the people operating that infrastructure have had to find ways to define acceptable behaviour and enforce it despite the absence of any central, controlling authority.

Perhaps the best example of this is the SMTP protocol that powers email. Email is the original P2P network — relays talk directly to each other, with no central control. In the early days of the internet, email was run primarily by universities and governments. Good behaviour was defined by common sense, with the threat of being fired (and thus disconnected) providing the rarely needed stick.

Once the net opened up commercially enormous numbers of users started getting online and it rapidly became infeasible for ISPs to police their own user base. Spam was born. Whilst theoretically every email provider has an abuse@site.net address which other network admins can use, in practice they stopped working. The combination of millions of paying customers who might be considered abusive, along with a complete lack of any formal rulebook, meant ad-hoc enforcement rapidly became useless.

![](/assets/images/2013/m10/a-network-of-your-peers2.gif)

When governments are faced with such problems, their first reaction is to pass laws defining what seems like the consensus on reasonable behaviour, force service providers to ID their clients to ensure attribution and then punish people who break the rules.

But the early internet was largely unregulated, so the community came up with a different way to police itself: the spam filter.

What, exactly, is spam? The blunt reality is that there is no clear definition for spam. Gmail uses a definition that is simultaneously very clear and impossibly vague — spam is whatever the users say it is. If enough users push “Report spam” on a message, then it’s spam. In practice, users report mail for all kinds of reasons, like:

* it being old fashioned mail abuse such as bulk mailed adverts for generic Viagra
* they couldn’t figure out how to unsubscribe from a mailing list
* their uncle sends them unfunny jokes and they feel it’d be impolite to ask him to stop
* the mail is obnoxious and irritated them, like “newsletters” sent by legitimate companies with whom the user interacted once, 5 years ago.

Spam filters differ. The best ones don’t rely purely on rules of thumb but rather calculate reputations for senders based on whether people want to receive their mail. As we can see, the email community has learned to police itself without any kind of formal law making and without introducing centralisation. It can handle fuzzy grey areas by measuring the consensus of large populations of users.

Now let’s look at another example.

![](/assets/images/2013/m10/a-network-of-your-peers3.png)

*Example of a Tor network map, from Vidalia*

#### Controlled chaos

Tor is one of the best known examples of a P2P network in which users are anonymous: anyone can use it, and no attribution of users to their traffic is possible by design. Tor is used to host drug markets, forums for trading child porn, and many other things. It would seem to be the canonical example of a network in which anything goes.

But this impression is misleading. Tor *does* have ways to impose rules upon its community. Here are some examples of the rules the Tor community has decided upon:

* Tor is not for BitTorrent users.
* Tor is not for spammers.
* Tor exits may not lie about their advertised bandwidth.

These rules may seem arbitrary and strange — why crack down on piracy and spamming but not drug trading sites? One reason is that the BitTorrent prohibition isn’t primarily about piracy but rather bandwidth. The Tor community has some shared goals, and file downloading takes up bandwidth that they’d rather be used for other things, like anonymous speech, communicating with journalists or just plain old surfing for porn. The DMCA complaints that inevitably follow allowing BitTorrent also don’t help.

Another reason is that the above rules can be enforced very easily using what are known as *exit policies*. Each Tor node that chooses to relay traffic onto the open internet (an *exit node*) is allowed to announce to the rest of the network what types of traffic it’s willing to accept. A default exit policy is used out of the box, thus all nodes have one, but the project provides an [even more conservative policy](https://trac.torproject.org/projects/tor/wiki/doc/ReducedExitPolicy) for operators who desire that.

Exit policies are extremely simple and can only achieve a very limited set of things, as they’re expressed in terms of acceptable IP address ranges and ports (i.e. applications/services). Some apps like BitTorrent which are frequently blocked have code designed to evade these policies, which in turn simply makes them more aggressive — typically they now work by listing acceptable services, rather than forbidding unacceptable services.

#### Policing hidden services

Could Tor go further with these kinds of self enforced community rules? Arguably, yes.

The Tor network allows *hidden services*. A hidden service is a server that is identified by a public key rather than an IP address. The public key can be written down as characters, in which case it might look like this:

```
silkroadvb5piz3r.onion
```

![](/assets/images/2013/m10/a-network-of-your-peers4.jpg)

*Logo of a shop*

In technical terms, that is the ASCII representation of an 80-bit hash of the public key of what was the Silk Road web server. The junk on the end is because you aren’t really supposed to be able to choose a name for your hidden service — they normally look entirely random. In this case Ulbricht ran a program that kept trying different random keys until he found one that started with the name of his site, but it would have taken a lot of computing power to generate such an address.

A hidden service still actually *has* an IP address of course, you can’t receive internet traffic without one, but it doesn’t advertise that address in DNS like a normal website would (or indeed anywhere at all). Instead a hidden service works by contacting some randomly selected Tor nodes via a regular Tor connection, so those nodes don’t find out the services IP address, and then it asks those nodes to act as *introduction points*. Once it found a bunch of introduction points, it uploads them along with its public key to a distributed hash table so other Tor users can find it.

Introduction points don’t actually relay traffic to the hidden service. That’s handled by randomly selected *rendezvous points*. However, they are still required for initiating connections.

![](/assets/images/2013/m10/a-network-of-your-peers5.png)

Because the introduction points find out the identity of the hidden service they are being asked to do work on the behalf of, there is no reason they could not simply refuse to help out hidden services which the node operator disagrees with. In the same way that exit nodes choose to allow or disallow certain services, other nodes could do the same for hidden services. Because a hidden service may change its public key (and therefore web address) from time to time, nodes could choose to subscribe to service policies that are updated by some third party.

In this way, the Tor community could collectively choose what kind of hidden services it wishes to provide shelter for. Does that make the feature pointless? No. Hidden services, contrary to initial appearances, actually have many uses beyond running illegal websites. Some examples:

1. **Security.**They can make ordinary websites harder to hack, by running the most sensitive core on a hidden service separate from the primary website. As an example, Bitcoin pools have in the past been hacked and had money stolen not through any security failing of their own, but by through compromise of the entire datacenter that hosted the servers. By running the code that held the private keys and made payouts on a hidden service whose real location was known only the operator it would become much harder to pull off such attacks.
2. **Privacy from risky customers.** Consider camgirls, who perform strip shows in front of web cams for money. Such shows are legal and frequently have thousands of viewers, but performers have to rely on expensive centralised sites that shield their identity from creepy customers who might try and track them down and make the show into reality. Tor and Bitcoin give them the tools they need to engage in their business without fear.
3. **Fighting totalitarian surveillance.** It’s an open question what kind of capabilities the NSA and GCHQ have built against Tor. The latest leaks from Snowden are based on 6 year old presentations and provide little insight. But it is without a doubt that Tor makes their job significantly harder and raises the bar for engaging in pointless, global surveillance of ordinary citizens. Running more traffic over Tor is something everyone should do, even if that traffic is by itself quite harmless and uninteresting. By increasing the cost to watch people who are doing no wrong, we force the intelligence agencies to focus on the truly bad apples.

Nodes refusing to act as introduction points for a particular hidden service would not immediately shut down that service — as long as at least a few nodes are willing to do it, the site will remain operational. But typically the behaviour of other people is not what concerns a node operator; they care about how their own resources are used, and whether their expenditure is furthering their goals or acting against them.

#### Sacrifice and hard work

A *proof of work*is an answer to a difficult mathematical problem which can only be solved by brute force: trying lots of possible solutions until you find a working one by chance. Proofs of work are great because anyone can find one just by burning electricity, and they can be checked very quickly (checking does not require any significant effort).

It might seem like we could use these proofs to restrict abuse: I can anonymously create a new proof of work,and present it when I wish to do something abusable like sending a mail. And in fact that’s how they were first envisioned, by a cryptographer named Adam Back in 1997. He proposed that each mail sent could have an attached proof of work, thus stopping spam.

But unfortunately proofs of work are not by themselves enough to curb abuse. Back’s scheme was flawed because it mixed up “sending spam” with “sending lots of mail”, when in fact there are lots of legitimate reasons to do the latter.

Can a proof of work be used as an identity? That is, if I let my computer crunch for a week, can I use that proof of work as a bond against bad behaviour and risk it being blacklisted if I misbehave? The answer is yes: a simple approach is to require a public key that is/hashes to a value that is lower than a certain target value. The lower the value, the harder it is to find a qualifying key. Once a key has been found, it acts as a newly minted identity and if that identity breaks some community defined rules, it can be blacklisted.

But such a scheme is unsatisfying. People with powerful computers can generate new identities easier than people with cheap, slow computers. That would bias the system towards people with workstations or servers instead of tablets and phones. Worse, computing power can easily be stolen via botnets. In practice criminals would find it easier to mint new identities than law abiding people.

A better approach is called *proof of sacrifice*, and it became possible only recently due to the advent of Bitcoin. In a proof of sacrifice, some bitcoins that were obtained by the user are “sacrificed”, which means they are given to random users in a provable manner. In practice what this means is that a transaction is created that spends all of its money on miner fees — some miner claims the fees for itself, and as almost all miners are pools those fees will typically be split amongst all the users who are taking part in the pool. The user can prove that the all-fee transaction was accepted by the Bitcoin network and thus that they lost the money. Like all Bitcoin transactions, the sacrifice transaction contains a public key owned by the user. This key can then act as their new identity and loaded into a web browser or email client. If the user behind the key misbehaves, it can be blacklisted and the sacrifice becomes useless.

Proofs of sacrifice are just a theoretical idea today, nobody has implemented them. But by allowing anyone who is able to obtain some Bitcoins to create a new identity without needing any serious computing power, they create a new paradigm for distributed, anonymous communities that nevertheless have a coherent set of shared values.

***

{% include signup.md %}
