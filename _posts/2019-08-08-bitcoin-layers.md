---
title: "Bitcoin Layers"
permalink: "/bitcoin-layers" 

author: joerodgers

tags:
  - Joe Rodgers
  - CY19 Q3

excerpt: Joe Rodgers makes the case for defining Bitcoin scaling layers. Posted 8-8-2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

# [Bitcoin Layers](http://cryptowords.github.io/bitcoin-layers)
### By [Joe Rodgers](https://twitter.com/_joerodgers)
### Posted August 8, 2019

The past few weeks there have been several good threads about Bitcoin’s scaling layers. Two camps have emerged as they try to define the stack. While this has no real implications and the market will ultimately decide on the best way to define layers, I wanted to put a post together to show the two camps.

## Any Tech Stack
Any technology that allows you to move Bitcoin around without making a Bitcoin L1 transaction, and settles directly on L1.

![](/assets/images/cy19/cy19m8/jr-1.PNG){: .align-center}
[*link to tweet*](https://twitter.com/Mario_Gibney/status/1156021229255417857)

This is consistent with our friends at Blockstream, they have put out a simple graphic with their view on things.

![](/assets/images/cy19/cy19m8/jr-2.png){: .align-center}
[*link to tweet*](https://twitter.com/adam3us/status/1155959592536309760)

As you can see in this image, the “Any Tech Stack” approach shows Lightning Network and Liquid as Layer 2 solutions. With the recent update to Liquid where you can bring Lightning on top of Liquid, they are socializing the idea that Liquid is closer to Bitcoin L1 than Lightning, calling Liquid Layer 1.5. 

## Bitcoin Stack
On the other side of the spectrum is the camp of folks who believe Bitcoin scaling layers are trustless. These trustless scaling layers allow the transfer and control of Bitcoin. Products and services can be built upon these layers where no permission or trust is required.

Lightning Network is a Bitcoin L2 solution because it is trustless, that is you can retrieve your funds at any time and no one holds them for you.

![](/assets/images/cy19/cy19m8/jr-3.PNG){: .align-center}

* Bitcoin L1 (Layer 1) - The Bitcoin chain, upon which additional layers and trust solutions are built.
* Bitcoin L2 (Layer 2) - Allows you to move Bitcoin without making a L1 transaction.
* Bitcoin L3 (Layer 3) - Allows you to move Bitcoin without making a L1 or L2 transaction. Settles on L2.
* Sidechains – trusted solutions where users exchange Bitcoin for a product or service. These solutions have a cryptographic link to Bitcoin layers, which adds additional security. These products and services will help Bitcoin scale, however there are certain tradeoffs such as required trust. Examples: Liquid
* IOU Solutions – trusted solutions where entities hold Bitcoin for you. These solutions offer scalability to Bitcoin; however trust is required as they hold the Bitcoin for you. Examples: Exchanges, Custodial Wallets

The Bitcoin Stack is one piece of the Bitcoin scaling solution and can work with fantastic emerging Trust Solutions such as Sidechains and IOU Solutions. 

## Conclusion
I believe trust is a fundamental part of defining Bitcoin scaling technology. It’s my belief that it’s only Bitcoin L2 if the technology retains Bitcoin’s trustless nature. For this reason, I believe Sidechains and IOU Solutions should be defined as trust solutions in the trust stack for Bitcoin, rather than L2 scaling technology.

There is no doubt that Sidechains and IOU Solutions will play a vital role in the scalability of Bitcoin, but let's not call them L2.

**Markets clear.**

Thanks to [6102](https://twitter.com/6102bitcoin) for helping me think through this.
