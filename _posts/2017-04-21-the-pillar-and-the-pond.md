---
title: "The Pillar and the Pond"
permalink: "/the-pillar-and-the-pond"

author: beautyon

tags:
  - Beautyon
  - 2017 Q2
  - Security

excerpt: The Pillar and the Pond. Posted April 21, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Pillar and the Pond](https://hackernoon.com/the-pillar-and-the-pond-9eea73318b92)
### By Beautyon
### Posted April 21, 2017



![](/assets/images/2017/m4/the-pillar-and-the-pond3.jpg)

![](/assets/images/2017/m4/the-pillar-and-the-pond4.jpg)

The Bitcoin Murmuration.

*A big Bitcoin exchange has just run into a problem with their bank making it impossible for customers to deposit or withdraw dollars. This sabotage is a symptom of a bigger problem; the design of Bitcoin businesses.* **TL;DR:** *“A swarm of bees is safer and more dangerous outside the hive. It is better to have 5,000,000 users using CoPay than it is to have 5,000,000 users in Coinbase.”*

What is *“The Pillar and Pond Problem”?* Inspired by [Eric Raymond’s famous piece](https://en.m.wikipedia.org/wiki/The_Cathedral_and_the_Bazaar?ref=hackernoon.com), It is a way of describing the advantages and disadvantages of different business architectures in Bitcoin. For example, if you have 5,000,000 users in a database with user names, passwords, KYC/AML documents, fiat balances and Bitcoin balances as MySQL entries, you are in a *Pillar Configuration:*

1. **All the users are siloed in your pillar.**
2. **You have one bank interface to serve your customers**
3. **You are on one hardware platform, at one network address**
4. **There is one place to attack the owners.**

In the *Pond Configuration*, things are very different…

1. **All the users are not on a single platform.**
2. **Each user has their own bank relationship.**
3. **Every user is on their own hardware, at many network addresses.**
4. **There is no single place to attack the users.**
5. **A business owner has no long term user care, custody or contract.**

A column is *immovable*. It stands very tall. It is heavy — made of stone. It is a landmark, a target that can be seen *for miles*. A column can be fenced off and pulled down or blown up with dynamite. A pond on the other hand, is *flat*, and s_pread out_ *over miles*. A missile shot into it makes a splash that is quickly covered over and smoothed by water. A pond cannot be pulled down or blown up; it is already at the lowest possible level in its constituents; the free molecule — *the single user*.

![](/assets/images/2017/m4/the-pillar-and-the-pond5.jpg)

The pillar is inherently weak.

Here are examples of services that are more or less in *Pond Configurations:*

1. **Bitsquare** [*https://bitsquare.io/*](https://bitsquare.io/?ref=hackernoon.com)
2. **LocalBitcoins** [*https://localbitcoins.com/*](https://localbitcoins.com/?ch=8zfz&ref=hackernoon.com)
3. **HodlHodl** [*https://hodlhodl.com/*](https://hodlhodl.com/?ref=hackernoon.com)
4. **Samurai Wallet** [*https://samouraiwallet.com/*](https://samouraiwallet.com/?ref=hackernoon.com)
5. **Bisq** [https://bisq.network/](https://bisq.network/?ref=hackernoon.com)
6. **Electrum** [*https://electrum.org/*](https://electrum.org/?ref=hackernoon.com#home)
7. **And others** [*https://bitcoin.org/en/choose-your-wallet*](https://bitcoin.org/en/choose-your-wallet?ref=hackernoon.com)

![](/assets/images/2017/m4/the-pillar-and-the-pond6.jpg)

Very flat. Nothing to knock down. Each molecule is a Bitcoin user. Find a particular one and stop her. If you can.

But what about [**Azteco**](https://azte.co/?ref=hackernoon.com)? Is it a Pond or Pillar service?

**It’s *neither*.**

Azteco **doesn't hold customer funds** and **doesn't have users**. It is simply a way to distribute Bitcoin. There are *no user accounts*. As soon as you redeem your voucher, you have no relationship with Azteco…until you buy another voucher. And another. It’s a rolling, disposable service, that doesn't tie you down, restrict you or require your long term trust.

![](/assets/images/2017/m4/the-pillar-and-the-pond7.jpg)

By removing “signed up” users, companies that are structured as flat Ponds have many advantages. They have a smaller attack surface, less burdensome administrative headaches, and are more agile. There is less to explain, keep tidy and manage; the cost of all of these problems is pushed on to other services, which if *they* are designed correctly, make the problems disappear entirely from the user network.

Pillars have big SPOF (Single Point of Failure) problems that they can’t make go away; they are built into the assumptions and business model.

![](/assets/images/2017/m4/the-pillar-and-the-pond8.png)

This diagram could be superimposed on any *“Pillar Bitcoin”* company from Coinbase down. That company is under a very nasty attack, where all of its user data has been unconstitutionally demanded. That attack is possible because *Coinbase is a Pillar;* a single, “SPOF” monolithic service.

![](/assets/images/2017/m4/the-pillar-and-the-pond9.png)

Completely redundant system without SPOFs.(Note: Assumes Generator and Grid sources are each rated at N, Each UPS is rated at N and “A/C” and “Electrical” are in themselves completely fault tolerant systems

This is a much better architecture. The system is entirely redundant, made of separate pieces. If any box (user or service) fails, the system carries on without interruption. In BitTorrent, it’s even better, and remember, this has been enough to prevent anyone stopping the vast majority from sharing files for over a decade, despite needing central search portals to find magnet links that hash the torrent locations.

![](/assets/images/2017/m4/the-pillar-and-the-pond10.jpg)

Not a BitTorrent diagram, but very pretty.

And in a fully decentralized network, The picture is even *better*, because there is no 2D line (underlying single owner services) that you can traverse and attack. An ideal Bitcoin would be like a *Murmuration of Starlings*. All the birds are connected by a protocol bound in nature, that cannot be changed. You can shoot a shotgun at it, and a hole will appear where the shot enters. It cannot be stopped, only *observed*. And marvelled at.

*It’s a sky pond.*

![](/assets/images/2017/m4/the-pillar-and-the-pond11.jpg)

##### They Can’t Win

Eventually, the bank problem will be gone forever, but in order to get there, you can’t use a Pillar to break the system; only a pond can dissolve it. New pieces of software like [*Bitsquare*](https://bitsquare.io/?ref=hackernoon.com) and the very interesting [*HodlHodl*](https://www.youtube.com/watch?v=OYtglu3ACaE&ref=hackernoon.com) by [Roman Snitko](http://romansnitko.com/?ref=hackernoon.com) are the future in the long term. Eventually a very resilient system of many redundant parts, more resilient than the BitTorrent ecosystem will emerge from the market, and everyone will live with it, and embrace it, just like they embrace the Internet, and accept it as a fact of life.

Finally, it should be clear to everyone that the ideal, if you are running a Bitcoin business, is to have total control over every part of your service, and to never rely on any third party for anything but the basics, like operating systems, ISPs and hardware. Any service you can get from an API, like Bitcoin network connectivity should be done “in house”, with your own software instances and equipment. As soon as you rely on someone else, the *Pillarization Process* begins.

Here are some off the cuff rules of thumb. Flatten and spread out. Reduce complexity. Absolutely reject all identity other than what Bitcoin provides by default. [Think UNIX](https://www.amazon.com/Think-UNIX-Jon-Lasser/dp/078972376X?ref=hackernoon.com). Reduce footprint. Increase speed. Make it disposable. Conform to the nature of the tools; completely reject *“Bitcoin* [*Skeuomorphism*](http://whatis.techtarget.com/definition/skeuomorphism?ref=hackernoon.com)*”* — making services that [mimic banks](https://medium.com/bitcoin-think/bitcoin-is-not-money-if-you-seek-compliance-you-are-asking-for-trouble-cbe9107e5298?ref=hackernoon.com) and other institutions.

And then…*we win.*

If you like the content and feel so obliged to send some love via BTC donations you can do so at the address below:↴

![](/assets/images/2017/m4/the-pillar-and-the-pond12.png)

***

{% include signup.md %}
