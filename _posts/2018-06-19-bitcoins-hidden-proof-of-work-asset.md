---
title: "Bitcoin’s Hidden Proof-of-Work Asset"
permalink: "/bitcoins-hidden-proof-of-work-asset"

author: rubensomsen

tags:
  - Ruben Somsen
  - 2018 Q2
  - Mining
  - Technology
  - Game Theory

excerpt: Bitcoin’s Hidden Proof-of-Work Asset. Posted June 19, 2018.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin’s Hidden Proof-of-Work Asset](https://medium.com/@RubenSomsen/bitcoins-hidden-proof-of-work-asset-4b4d086f73e2)
### By Ruben Somsen
### Posted June 19, 2018

## **Bitcoin’s Hidden**Proof-of-Work **Asset**

*TLDR: Miners buy bitcoins by creating blocks, and they pay for it in electricity. Interestingly, this data gets recorded on the blockchain as PoW. By allowing people to trade on this info, we have essentially created a new PoW-based asset.*

#### **Bitcoin Only Looks Within**

One of the limitations of Bitcoin is that the blockchain has no knowledge of real-world events. If you want to create a contract based on tomorrow’s weather, the blockchain cannot provide the answer.

The common solution is to use [oracles](http://goo.gl/Nvy1YJ). While this generally is an acceptable compromise to reach the desired outcome, it introduces an unfortunate point of centralization in an otherwise fully decentralized system. A blockchain will never be able to know by itself whether or not it is raining, but there’s one source of real-world data that it does have access to — Proof-of-Work (PoW).

#### **Ties To The Real World**

PoW is what ties the digital world to the real world. It is evidence that a certain amount of electricity was expended. We generally do not care about the exact amount — only that the PoW was high enough to produce a valid block.

> But the exact number of hashes tells us something interesting about the real world.

It is the amount of work that miners were willing to perform in order to receive a specific number of bitcoins. This is essentially a price discovery mechanism — miners are buying bitcoins with electricity. Unfortunately, the electricity cost of the work changes whenever more efficient ASIC hardware enters the market (hashing consumes less electricity). This means that we can’t know if an increase in hashrate is caused by an increase in price, or new ASIC hardware.

#### **The Limit of ASICs**

It will take many years, but ASIC hardware will eventually reach the [thermodynamic limit](https://download.wpsoftware.net/bitcoin/asic-faq.pdf) — a point where the efficiency can no longer be improved. The electricity cost of hashing will become fixed, and we can use that knowledge to more reliably derive the electricity cost of a single bitcoin from the PoW.

> In other words, the blockchain can tell us how much miners are willing to pay for a bitcoin in terms of electricity.

If the number of hashes per bitcoin goes up, it implies the electricity cost per bitcoin has increased. From this we can assume that either the available electricity became cheaper, or, perhaps more likely, Bitcoin went up in value.

#### **Hidden Asset Utility**

In terms of price volatility, the electricity cost is likely to be somewhat less stable than fiat. The price of electricity varies heavily [depending on the region](https://blog.bitmex.com/mining-incentives-part-2-why-is-china-dominant-in-bitcoin-mining/). It is also likely that the more expensive sources of electricity are going to stop mining first when the price goes down, which means the hashrate may drop less than expected (non-linear).

That being said, it is still useful that the Bitcoin network becomes aware of an “electricity” asset, and this asset may be more stable than Bitcoin. The result is very similar to [Hal Finney’s RPOW tokens](https://nakamotoinstitute.org/finney/rpow/index.html). In theory, it could be made available to Bitcoin scripts via a soft fork, enabling contracts that resolve based on the Proof-of-work Per Bitcoin (PPB).

The PPB can be calculated by the number of hashes that were performed over a certain period, divided by the coins that were mined in that period. There also needs to be a mechanism to disqualify outsized transaction fees, since otherwise miners have an easy way to manipulate the PPB by paying large fees to themselves.

#### **Trading The Asset**

Primarily, the PPB can be used to hedge against price volatility by shorting, which would have a similar effect to shorting Bitcoin against the dollar, albeit in a fully decentralized fashion. We’ll examine a possible futures contract between Alice and Bob:

* *Alice puts in 0.5 BTC (and keeps 0.5 BTC to herself)
and Bob puts in 1 BTC (together they have 1.5 BTC)*
* *If the PPB drops below 50%, Alice can claim the 1.5 BTC 
(plus the 0.5 BTC she kept, so 2 BTC)*
* *If the PPB goes past 200%, Bob can claim the 1.5 BTC 
(and Alice still has 0.5 BTC)*

The result is that in terms of PPB, Alice will always break even. She either ends up with 0.5 BTC which is now worth double the PPB, or 2 BTC which is worth half the PPB. Bob increases his risk/reward. He either gains 300% (as opposed to 200%) in PPB, or loses everything (as opposed to 50%).

Of course it could take a long time for the PPB to double or halve, but other percentages are also possible. Assuming both parties cooperate, it is also possible to close the contract early, or atomically swap in another person, and all of this can take place over the Lightning Network.

#### **Many Moons Into The Future**

It will take [a long time](http://boblansdorp.blogspot.kr/2014/02/the-thermodynamic-limit-of-bitcoin.html) before we reach the thermodynamic limit, but that doesn’t mean experimentation isn’t possible today. Exchanges could list futures based on the PPB, in order to gather actual data on the usefulness of such a contract. People may become more willing to engage in these types of contracts over time, assuming development of new ASICs slows down or becomes predictable enough to factor its growth into the contract.

Even after the thermodynamic limit is reached, the price discovery mechanism will not be perfect, but it’s worth examining whether it can potentially provide utility. Further research needs to be done on the potential for miners to manipulate the PPB, as this may very well undermine its usefulness.

*— Ruben Somsen*

![](/assets/images/2018/m6/bitcoins-hidden-proof-of-work-asset-ruben-somsen1.jpg)

*Created in1983or1997, depending on your perspective.*

***

{% include signup.md %}
