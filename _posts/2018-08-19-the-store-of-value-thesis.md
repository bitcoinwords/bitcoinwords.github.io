---
title: "The Store of Value Thesis"
permalink: "/the-store-of-value-thesis" 

tags:
  - Qiao Wang
  - Dan McArdle
  - CY18 Q3

excerpt: Qiao Wang and Dan McArdle explore their cryptoasset Store of Value Thesis. Posted August 19, 2018. 

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


# [The Store of Value Thesis](https://tokeneconomy.co/the-store-of-value-thesis-42d3cfde50a9)
### By [Qiao Wang](https://tokeneconomy.co/@QwQiao) and [Dan McArdle](https://medium.com/@robustus) 
### Posted August 19, 2018

## Introduction

One way of thinking about cryptoasset valuation says that only assets that can become a store of value (SoV) are deserving of high network value. This is a mental model that has been around for a while, and one that we largely hold when making investment decisions. So let's unpack it.

You might think that high usage leads to high network value, i.e., if millions of people use a coin as cross-border payment or as gas for dapps, it must be valuable, right?

Generally, this can only be true if users want to hold the coin for a while, in addition to actually using it. If you want to use a coin that you don't already own, but everyone who has the coin today just wants to hang on to it, you have to offer people a high enough price for it that they'll let go. Conversely, if users are willing to get rid of the coin right after they're done using it, there's almost always more than enough to go around and no one has to bid up the price in order to use the network.

**So whether or not a cryptoasset will become a SoV boils down to the following question: why would people want to hold an asset for a long time versus a short time?**

## First-order properties

We believe that a cryptoasset must satisfy three properties in order to become a SoV that people are willing to hang on to.

* Immunity to theft
* Credibly low inflation
* Low cost of conversion

**1) Immunity to theft**

For a network to have this property, it needs to be immune from malicious actors who may wish to steal from accounts/balances. For instance, they could exploit buggy smart contracts you interact with, reverse a transaction that was sent to you, prevent you from making transactions, or obtain your private key.

**2) Credibly low inflation**

Not wanting to be inflated away is obvious, but the word "credibly" here is key. Many monies or cryptoassets may claim to have low or no inflation, but they aren't necessarily structured so that that's believable. Is the network technically secure against an attacker who might try to change its rules by force? Outside of attack scenarios, who sets the monetary policy and are they incentivized to modify it?

**3) Low cost of conversion**

Axiomatically, a SoV is something which we don't need now but can expect to be able to convert to another product or service that we need at some point in the future. As such, it's not a good SoV if conversion is expected to be expensive.

If you think about it, a SoV really is just a combination of three things. 1) You can store it securely. 2) It cannot be reproduced easily. 3) You can trade it or use it cheaply.

## Second-order properties

Those are three first order properties of a good SoV. But we can further deduce second-order properties that lead to these first-order properties. In order words, what are the means to these ends?

1) Immunity to theft requires

* **Small software attack surface**. For instance, Ethereum has larger attack surface than Bitcoin does, as it can perform more complex smart contracts. As such, Ethereum holders have endured hacks like those of [the DAO](https://en.wikipedia.org/wiki/The_DAO_%28organization%29) and [Parity](https://blog.zeppelin.solutions/on-the-parity-wallet-multisig-hack-405a8c12e8f7).
* **High cost of 51% attack**. The attacker could reverse a transaction that was sent to you. Here's a [comparison of cost of attack between DCR and BTC](https://blog.usejournal.com/apples-to-apples-decred-is-20x-more-expensive-to-attack-than-bitcoin-68bafeb4546f).
* **Decentralization**. Similarly to the above, centralization increases the risk of transaction reversals .
* **Privacy**. Government or malicious individuals could physically force you to surrender your coins if they can easily identify your blockchain activity with your addresses.

2) Credibly low inflation requires

* **Small software attack surface.** Are there bugs that attackers can exploit to create a large number of coins?
* **Decentralization**. Are there one or a few powerful actors who can change the monetary policy?
* **Collective commitment to low inflation**. This is almost tautological, but different cryptonetworks do exhibit different levels of commitment. Early Bitcoin adopters' uncompromising commitment to a fixed monetary supply attract like-minded people.

3) Low cost of conversion requires

* **Utility**. Higher utility means there are more opportunities to directly transact in the cryptoasset, and that more people need to trade their fiat for crypto in order to use it, leading to higher market liquidity.
* **Decentralization.**Greater decentralization makes it harder for anyone to censor transactions that involve a conversion of SoV for something else.

As a side note, interestingly, decentralization is required for all three. This is why the crypto community values decentralization so much. It is the only obvious means by which a network can make credible statements about its properties of immunity to theft, low inflation, and uncensorable transactions.

## Deeper Look at "Low cost of conversion"

1) Immunity to theft and 2) credibly low inflation, as well as the second-order properties associated with them, appear to be commonly accepted by the community. But 3) low cost of conversion is the one that doesn't seem to have gotten much attention. Let's take a deeper look at it and its second-order properties: utility and decentralization.

**Utility**

As previously mentioned, an asset is not a good SoV if the cost of conversion is high. Furthermore, there are two ways to convert cryptos to something else: indirectly via fiat or directly.

Indirect conversion cost is determined by crypto-fiat liquidity. The latter, among other things, is a function of the current utility, as one must trade fiat for the crypto to in order to use it, and the level of speculation on future utility.

But ultimately, cryptonetworks should aim for as much direct conversion as possible (e.g., purchase with BTC, run dapps with ETH), because by definition it's cheaper than indirect conversion. And direct conversion is, indeed, current utility.

This line of reasoning suggests that utility is important for both indirect conversion and direct conversion and, by extension, SoV. As an illustrative question, will gold depreciate over time as new technologies like fiat and crypto become more widely utilized as as media of exchange? Our hunch is yes.

**Decentralization**

But cost of conversion doesn't have to be financial. It can also be opportunity cost or mental cost.

In both indirect conversion and direct conversion, censoring transactions and uncertain monetary policies leads to opportunity cost and mental cost. Decentralization improves censorship-resistance and monetary policy stability, thereby reducing cost of conversion.

At the extreme, if network validators can [censor transactions from certain addresses indefinitely](https://www.coindesk.com/eos-blockchain-arbitrator-orders-freeze-of-27-accounts/), i.e., the cost of conversion is infinite, then the owner has practically forfeited their assets.

## Conclusion

We believe that value will ultimately accrue to SoV cryptoassets, and we provide a framework for thinking about SoV properties. In particular, we reason from the ground up by laying out three first-order properties, which in turn are induced by multiple second-order properties.

But the framework doesn't stop here. One can build up from these second-order properties to discover even higher-order properties. Each of these merits a essay that is beyond of the scope of this one.

Take "decentralization" for instance. Higher-order properties that lead to greater decentralization include:

* Founder myth
* Gini coefficient
* Independent development teams
* Cost of operating a node

What about "utility"? Examples of higher-order properties that contribute to utility are:

* Programmability
* Development infrastructure
* Scalability

A second-order property could even be a third-order property associated with another second-order property. For instance, in [the False Dichotomy of Utility and Store of Value](https://medium.com/@QwQiao/the-false-dichotomy-of-utility-and-store-of-value-27fe12bf3bdb), we argue that utility leads to greater decentralization and higher cost of majority attack.

![](/assets/images/cy18/cy18q3m8/qw-1.png){: .align-center}

In short, valuing an early-stage cryptoassets boils down to the question of how likely it will acquire and maintain the first, second, and higher-order properties of SoV described in this post. By way of example, BTC is arguably the best at immunity to theft and credibly low inflation, but will it achieve more utility than say, ETH? EOS has a shot at surpassing ETH utility-wise, but will it ever be as decentralized?
