---
title: "What is Lighting?"
permalink: "/what-is-lighting"

author: aleksandarsvetski

tags:
  - Aleksandar Svetski
  - 2019 Q4
  - Money
  - Security
  - Scaling

excerpt: What is Lighting?. Posted December 14, 2019.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [What is Lighting?](https://medium.com/the-bitcoin-times/what-is-lighting-50edf410110e)
### By Aleksandar Svetski
### Posted December 14, 2019

A high level primer on Bitcoin’s most well known second layer tech.

![](/assets/images/2019/m12/what-is-lighting1.png)

*We’re now in the home stretch of the first edition of the Bitcoin Times.*

*In the last chapter, we closed out with comparisons between Bitcoin & the internet. In the next few, we’ll give some high level understanding of the concepts of second layer tech, with the focus being on Lightning.*

***

Giving Lightning the explanation and time it deserves is out of the scope of this paper, but I’ll attempt to give you enough of an understanding to go further down the rabbit hole with….

Imagine a network, where each of the participants are not only route ‘users’, but also route operators. Where every participant becomes a node, that strengthens and broadens the network for not only themselves, but for everybody using it.

The best analogy I can think of is the internet (once again). The internet really exploded, when we became not only ‘consumers of content’, but also creators and routers of this data and content.

Testament to this explosion is the company which arguably capitalized on this the most. Facebook is barely 15yrs old and is one of the largest in the world. It gave everyone a forum to consume, create and share content; in other words — everyone was a node that made Facebook more valuable (and not just in relation to its market cap).

![](/assets/images/2019/m12/what-is-lighting2.jpg)

*Conceptual way to understand the network effect layers have*

What happens when you apply that same concept of read / write / route to money and payments?

*In short — it changes the game.*

Whilst not entirely accurate: Bitcoin is like the internet (one transformed information, the other money) and Lightning is a little like Facebook in that it makes money a content type that everyone can collectively participate in.

Money has never had that kind of fluidity, and it’s this fluidity that Lightning represents at a high level.

BUT…You might say: “Wait a minute. Not everyone can route money. They’re not a bank! How can we trust them”? That’s where Bitcoin comes in.

Lightning is technically able to be applied or “anchored” onto other networks, but its maximum utility comes from doing so on a network that gives the highest guarantee of immutability.

*That’s the entire point, and how we unlock Lightning’s potential.*

If you can refer back to something that has prioritized security, stability, resistance to censorship and shutdown, then you can begin to really abstract and build financial complexity on top of it; without worrying about the potential of error, compromise, fraud or failure. Bitcoin + Lightning is where the future is at.

Lightning enables:

1. Instant Payments: Because we’re not worrying about block confirmation times, payment speed is measured in milliseconds to seconds. It’s truly peer to peer, and as fast as data can move.
2. Scale: When all participants are also nodes, you don’t get the congestion we have in today’s archaic, centralised payment networks. You get true scale; capable of millions to billions of transactions per second across the network. This blows away any high-speed blockchain or any other legacy payment rails by many orders of magnitude.
3. Low Cost: Non custodial micro payments (e.g: pay per action/ click) are truly possible at fractions of cents. This is foundation for the set of use cases yet to emerge
4. Security: By anchoring to a source of truth (aka; Bitcoin) with simple, robust “smart contracts” one can ensure the integrity of the second layer without recording them on chain (via a complex version of netting).

![](/assets/images/2019/m12/what-is-lighting3.jpg)

## **How does Lightning work?**

Lightning is a second layer technology. By using the native smart-contract scripting language of a network (such as Bitcoin) to anchor or connect to, it’s possible to create a secure second layer ‘network’ of participants who are able to process and route transactactions at high volume and high speed.

For example:

Dingus & Wingus decide they want to transact. Lots of times. Instead of bothering everyone on the core network and having every single validator on the core network have to record their transactions, they decide to open up what’s called a “payment channel”. Think of it like putting some money on your transaction account.

They can then transact between each other, back and forth, as much as they want — each time netting off against the prior transaction. After a certain period of aggregating these transactions, and updating the final net state; they could choose to close out the channel by broadcasting the final, net result to the underlying network (e.g: Bitcoin) and settle.

It’s important to note that this final, net entry can be closed out at any time by either party — without any trust or custodianship — by broadcasting the most recent version to the blockchain.

![](/assets/images/2019/m12/what-is-lighting4.jpg)

*A very sophisticated, technical diagram.*

Closing a channel is also how the network deals with cases of attempted fraud or “bad acting”. The last valid, signed set of transactions between both parties wins - and there are some incentive / disincentive rules that help to ensure it’s in everyone’s economic self-interest to do the right thing (i.e.; attempt to defraud the other user, but last signature shows otherwise, you lose the funds you committed to the channel).

This is all similar to how legal contracts function.
One does not go to court every time a contract is made (that’s analogous to doing ‘everything on the blockchain’). Only in the event of non-cooperation is the court involved, and by making the transactions and scripts parsable and thus “anchoring” to the underlying network, these smart-contracts can be enforced and the result settled.

## **The potential**

A payment channel between two participants is just the beginning. It’s a building block for a larger network. In fact,
the network only forms when numerous payment channels join to form a web. In this way, two participants who are not directly connected can transact with each other.

Let’s say Dingus wants to pay Pingus. He can still do it even if he doesn’t have a direct connection (payment channel) with him, but as long as Wingus from earlier can connect them via a chain, i.e. route.

![](/assets/images/2019/m12/what-is-lighting5.jpg)

*Another… very sophisticated, technical diagram.*

The exciting part is that as the network grows, you won’t necessarily even need to set up a dedicated channel to send funds to a certain person. Instead, you will be able to send payment to someone using channels that you’re already connected with. The system will automatically find the shortest route.

By creating an entire network of these two-party ledger entries, it’s possible to find payments paths across the network similar to how packets are routed on the internet.

As all the pieces of the puzzle come together, one starts to see the magnitude of this innovation.

This is how everything else in nature works, along with the functional systems of cooperation we’ve built throughout the millennia.

You abstract the small, you settle when you need to — whether that be at closure, or on disagreement.

In fact, it’s a big part of how modern banking evolved (because it’s more efficient).

The difference (and beauty) with Bitcoin is that you can’t influence or manipulate it (remember: immutability as a service) so it will be the ultimate arbiter & settle as per the original rules.

It’s time to move to a new model where the arbiter / settlement function is digital and owned by the commons, not by the few.

## **The Future is on Lightning**

What could the future hold?

Aside from the potential of doing billions of transactions per second (seeing as though speed is what everyone wants), and transforming payments and value transfer from things that happen at a time and place, to something that “streams” over time and space, perhaps something a little easier to imagine is the launch of a Bitcoin bank.

One where anyone, anywhere in the world could set up an account in seconds, and begin participating in global commerce.

Where all reserves are held and denominated in Bitcoin, on Bitcoin — and the organisation can be held 100% accountable because it’s all transparent and able to be queried.

Could we open up the ability to lend, borrow, spend, save, trade and interact globally — without worrying about exchange rates, inflation and manipulation?

I don’t know. Maybe.
Or maybe I’m thinking way too small. I don’t know.

What I do know is that the real innovation is yet to come — and those innovations (like Facebook and cat videos on the internet) will not be skeuomorphic.

They will not be something we can predict or even imagine today. Myself and my team at Amber are making inroads in the new world, and we’ll continue to be at the cutting edge — but we are well and truly at the beginning — and all we can do is keep pushing the envelope.

![](/assets/images/2019/m12/what-is-lighting6.jpg)

*Sometimes images speak louder than words*

***

In the next & final section of The Bitcoin Times Edition 1, we’ll review Money as the fabric of society, how money functions, and we’ll close out the paper with some final thoughts.

Thankyou for sticking with us along this journey.

***

### Download the full guide at:

[https://bitcointimes.news](https://bitcointimes.news)

### Follow The Bitcoin Times on Twitter @TimelessBitcoin:

### The ₿itcoin Times

#### The latest Tweets from The ₿itcoin Times (@TimelessBitcoin). Facts over Fiction. Practice over Theory. Timeless…

##### twitter.com

***

## Created by the team @ Amber Labs:

### Amber | Invest Anywhere

#### Dollars have cents, bitcoin has satoshis. Where 100 cents equals $1, one bitcoin (1₿) is made up of 100,000,000 sats…

##### getamber.io

### Amber #stackingsats ⚡️

#### The latest Tweets from Amber #stackingsats ⚡️ (@theamberapp). Making Bitcoin easy by Stacking Sats on Autopilot. Dollar…

##### twitter.com

## Written by:

### Aleksandar Svetski [₿]

#### The latest Tweets from Aleksandar Svetski [₿] (@AleksSvetski). Hairless chimp interested in Money, Bitcoin, ⚡️…

##### twitter.com

### Aleksandar Svetski — Medium

#### Read writing from Aleksandar Svetski on Medium. CEO @ www.amber.app. Editor @ https://bitcointimes.news. Bitcoin…

##### medium.com

## Designed by:

### Chantelle De la Rey

#### The latest Tweets from Chantelle De la Rey (@rey_chantelle). co-founder of @theamberapp Creator of…

##### twitter.com

***

{% include signup.md %}
