---
title: "The Nature of Bitcoin"
permalink: "/the-nature-of-bitcoin"

author: zanepocock

tags:
  - Zane Pocock
  - CY20 Q1
  - Speech
  - Money
  - Regulation

excerpt: Zane Pocock shares an overview of Bitcoin as he sees it. Posted February 13, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Nature of Bitcoin](https://medium.com/knox-blog/the-nature-of-bitcoin-66d4e285041b)
### By [Zane Pocock](https://twitter.com/zanepocock) from [Knox Custody](https://www.knoxcustody.com/)
### Posted February 13, 2020

![](/assets/images/2020/m2/zp1.png)
*(Photo by [Taylor Vick](https://unsplash.com/@tvick?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/servers?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)*

With the notion of Bitcoin as a security dispelled, [including by American regulators themselves](https://www.cnbc.com/video/2018/06/06/sec-chairman-cryptocurrencies-like-bitcoin--not-securities.html), the other common ways people attempt to wedge Bitcoin into legacy frameworks — and regulation — is as either a commodity, property, or the ultimate goal: money.

But Bitcoin is at odds with these concepts at a fundamental level. Because “bitcoins” don’t exist.

As [Beautyon has popularized in his case that Bitcoin is speech protected by the first amendment](https://hackernoon.com/why-america-cant-regulate-bitcoin-8c77cee8d794), the definition of Bitcoin can be simplified to a distributed internet protocol that relays text messages between voluntary/free participants.

## That’s all Bitcoin is — a means of communication.

The unique value proposition of the Bitcoin communication protocol is that these messages can be used by participants to communicate an interpretation of _value_. How this works is through a mechanism called the “unspent transaction output” (UTXO). UTXOs can be a little difficult to understand, but [Investopedia describes it well](https://www.investopedia.com/terms/u/utxo.asp):

_“UTXO stands for the unspent output from bitcoin transactions. Each bitcoin transaction begins with coins used to balance the ledger. UTXOs are processed continuously and are responsible for beginning and ending each transaction. Confirmation of transaction results in the removal of spent coins from the UTXO database. But a record of the spent coins still exists on the ledger.”_

![](/assets/images/2020/m2/zp2.png)
Bitcoin is a means of communication

It’s these UTXOs that are measured in a unit called “bitcoin”, but this is more akin to measuring how space is used on a hard drive than bars of gold in a vault. UTXOs are just the occupants of Bitcoin’s information space.

One of Bitcoin’s utilities is popularly described as “digital gold” because this information space comes in a limited quantity. The network-wide UTXO balance will only add up to a certain scarce amount with the [current outstanding supply](https://bitcoin.clarkmoody.com/dashboard/) summing to 18.2M BTC out of the 21M BTC hard cap it will reach sometime next century. But this analogy — Bitcoin as digital gold — is not the actual definition of Bitcoin, only one subjective interpretation.

### What controls these UTXOs?

Bitcoin private keys are another type of Bitcoin information. Through cryptographic processes outside the scope of this article, private keys can derive a corresponding public key that acts as an address for receiving UTXOs. The private key then exercises control over all the UTXOs it has received. UTXOs are transferred as inputs in messages when they are cryptographically signed by the private key with authority to do so.

![](/assets/images/2020/m2/zp3.png)
Private keys exert control over Bitcoin’s information space

## Energy, Value and Settlement Assurances

Another viewpoint commonly employed to explain Bitcoin is to say that it is “backed by energy”.

The reason why is that roughly every ten minutes, blocks of Bitcoin “messages” are confirmed by competing computers (“miners”) employing a huge amount of energy to meet the rules set out by the protocol. These ten-minute blocks are Bitcoin’s bandwidth. Only a certain amount of Bitcoin “messages” can be transmitted in each block, called the block-weight. Taken together, this process of adding message blocks to increment the “block height” by miners is called proof-of-work, and to simplify it gives the Bitcoin network some important features:

*   The rules the miners follow to update the distributed network state require that UTXOs must be unspent (as the name suggests). This solves the so-called “double-spend” problem in the digital world where [information had previously always been non-scarce](https://github.com/MaxHillebrand/Anarchy-in-Money/blob/master/Scarcity.asciidoc). What value would a UTXO accrue if a user could reuse it? It means that absolute mathematical scarcity now exists for the first time, a discovery that can’t be achieved again.
*   These value-transfer messages are then effectively buried under each new block of messages: to undo them, an attacker would need to prove the same amount of work to the protocol as has been applied to each successive block — and from all the competing computers, not just the successful ones. This is a proxy for energy and means that expended energy is a key requirement to ensure transaction finality, or [settlement assurances, as Nic Carter writes](https://medium.com/@nic__carter/its-the-settlement-assurances-stupid-5dcd1c3f4e41). It is a security feature that to attack Bitcoin, inordinate amounts of energy must be employed.
*   The competition between miners, resulting in a distributed ledger that they all contribute to, means that this global value-transfer network does not rely on any trusted third party. Clearance and settlement happen according to strict rules on the Bitcoin protocol that tens of thousands of independent users verify for themselves.

Because expended energy is so core to Bitcoin’s security and viability, the concept that “Bitcoin is backed by energy” has emerged as a useful concept for understanding why this communication protocol works at all. Taken to its literal conclusion, this line of thought has led some to argue that this energy creates Bitcoin’s value and that Bitcoin is therefore a commodity — captured energy.

Rather, it is the energy expended for security in combination with Bitcoin’s use of information space that is why the network accrues value. Put another way, if the information space occupied by Bitcoin UTXOs could be classified as a commodity, then space rented on Amazon’s AWS servers would also be a commodity. Like the Bitcoin network, AWS relies on expending a lot of energy to function, and the computing resources rented by businesses and individuals represent information space in the virtual world. But it would be absurd to classify AWS as a commodity, and so it is with Bitcoin.

Indeed, it’s the separation of value from commodities that makes the Bitcoin communication protocol so uniquely valuable. As Conner Brown has written, [Bitcoin has no intrinsic value](https://medium.com/coinmonks/bitcoin-has-no-intrinsic-value-and-thats-great-e6994adbfe0f) as a commodity — an observation often used as a criticism — but that is a feature, not a bug. A commodity-based value transfer system, such as the gold standard, not only finds its value subject to the market fluctuations caused by changes in supply and industrial demand, but it also inflates the price of the underlying commodity by increasing its demand. This monetary premium means that a commodity like gold is much more expensive than it otherwise would be, and this distortion in the price signal hampers its use in goods such as cheaper electronics.

## The Most Tradable Information

Without needing to grasp for financial definitions, commerce enabled by the Bitcoin value-transfer protocol will still be commercial activity. If the distributed Bitcoin ledger helps to conduct commercial activity between a shop and a consumer, that shop is still going to file a tax return with profit based on the fiat value of goods sold.

Monetary systems are savings technologies that ultimately serve to transfer value in time and space, a tool for the farmer selling his year’s output in Fall to be able to purchase new shoes six months later when he has nothing to sell. Having lacked a logical system to keep track of everyone’s market contributions until now, this value transfer role has traditionally fallen to the economy’s “most tradable good” — typically something exhibiting beneficial properties such as durability, portability, divisibility, and hardness (hard to produce more of it and debase it).

Monetary theorists such as [Carl Menger](https://mises.org/library/origins-money-0), [Nick Szabo](https://nakamotoinstitute.org/shelling-out/) and [Saifedean Ammous](https://saifedean.com/the-book/) argue that the emergence of a new money has historically gone through various stages. Starting as either a collectible (such as shells or family heirlooms) or a commodity (flint blades or gold), a monetary good first accrues value in the subjective eyes of an increasing number of people. Given enough time, this accrued value gains permanence, allowing the good to successively function as a store of value then as a medium of exchange when it reaches a certain level of liquidity and price equilibrium.

Similarly, Bitcoin’s communication protocol and scarce information space have piqued the interest of human minds such that their uses and perceptions of it have gone through [evolving narratives](https://medium.com/@nic__carter/visions-of-bitcoin-4b7b7cbcd24c) and led many to collect the scarcity of the information space into UTXOs only they have the authority to spend. These narratives have ranged from a crypto-anarchist collectible and “private” darknet currency, to current interpretations such as “digital gold”. But just as price is an interpretation of value, these human narratives — Bitcoin as gold, Bitcoin as commodity — are an interpretation of the fundamental nature of Bitcoin: information.

![](/assets/images/2020/m2/zp4.png)

If something becomes the most tradable good, it can function as money. Bitcoin is text, but its properties might allow it to fulfill a monetary role for those demanding scarce information space in the form of UTXOs. We can’t say exactly where Bitcoin might be on its way to being used as a monetary system — that’s for each individual market participant to decide for themselves — but early adopters are using it in that role already. With Bitcoin’s help, the economy might just become a little more like entering a global barter system — a ledger system to keep track of everyone’s market contributions. Rather than being the world’s most tradable good, Bitcoin is the world’s most tradable information.

So, what of the other aspects of financialization? [One of Trace Mayer’s seven anticipated network effects](https://www.tracemayer.net/investments/) of Bitcoin, it is becoming apparent that because Bitcoin’s information space has accrued value, it can be used as the base value of financial instruments built around it. Control of UTXOs is being transferred as collateral against lines of credit, and Bitcoin key storage providers like KNØX are [attaining insurance policies](https://www.coindesk.com/in-rare-deal-crypto-custodian-wins-insurance-on-full-value-of-client-assets) for the fiat value of the information space they guard. Even futures markets are being built, enabling participants to hedge and bet on fluctuations in the accrued value and energy costs of the network. These instruments — insurance, credit, futures — appear to be financial products. But again, the way the communication protocol is used does not define Bitcoin. An orange is an orange, but that doesn’t stop the market trading on its future value from dealing in derivatives to hedge risk against orange production rate fluctuations.

Similarly, the properties of Bitcoin’s communication protocol present opportunities to natively automate tasks with parallels to traditional financial services, but that doesn’t make Bitcoin a financial service. For example, Bitcoin allows for unique audit solutions without the use of a third party audit. As an open communication protocol, the value transferred in each message is visible to all participants, meaning that scripts can be written to prove that a participant possesses the keys exerting control over particular UTXOs. This idea — that a custodian can demonstrate “[proof of reserves”](https://blockstream.com/2019/02/04/en-standardizing-bitcoin-proof-of-reserves/) — is yet to gain wide adoption, but it has drawn much anticipation and demonstrates the power arising from Bitcoin’s nature as a pure communication protocol.

Because Bitcoin is text, it fundamentally sits outside of existing financial definitions and regulations. But that doesn’t preclude its information space from exhibiting monetary characteristics. In fact, it’s in part because of all of this that Bitcoin _is _so valuable. And things that are valuable need to be protected.

## How to Keep a Secret

At the protocol level, the nature of Bitcoin’s information space means that private keys function like a digital [bearer instrument](https://www.investopedia.com/terms/b/bearer-instrument.asp): there is no inherent difference between possession, control and ownership.

Remember there are no bitcoins _per se_; there are private keys that permit spending UTXOs via signed messages on the network. Bitcoin private keys are also information. You can write them down, speak them, print them, memorize them in your head. Thousands of people can hold the exact same key; if you have [Andreas Antonopoulos’ _Mastering Bitcoin_](https://github.com/bitcoinbook/bitcoinbook) on your shelf then you share several Bitcoin private keys printed in its pages with all the other thousands of people who have access to it. By US constitutional law, this means that creating, spending, or otherwise using Bitcoin private keys constitutes [speech protected by the first amendment](https://hackernoon.com/why-america-cant-regulate-bitcoin-8c77cee8d794). But unlike the scarce information space occupied by UTXOs, when it comes to Bitcoin private keys we are dealing with non-scarce information.

Obviously, since Bitcoin’s information space has accrued value, it is in the best interest of those who exercise control over a portion of it to keep the private key out of others’ hands. To exercise exclusive control over replicable information requires competence at protecting a secret.

If the Bitcoin carnivores will excuse a fast food analogy, this is why [KFC doesn’t have a patent](https://en.wikipedia.org/wiki/KFC_Original_Recipe) on its 11 secret herbs and spices, information that has accrued such value it contributed to the growth of a global fried chicken empire. Rather, they have a vault at their headquarters that very select individuals can access, inside of which is the only known certified copy of the recipe. They even have their own multisignature scheme, with two companies each responsible for supplying half of the ingredients.

This demonstrates the “not your keys, not your coins (UTXOs)” meme. Possession of the secret enables the bearer to exercise control over the valuable information space; at the protocol level, possession, control and ownership can not be separated. As Daskalov, CEO of KNØX, put it, “[the Bitcoin protocol is necessarily amoral, governed by an uncompromising set of rules.](https://medium.com/knox-blog/towards-trust-minimization-in-bitcoin-custody-343a2a9a37aa)”

This is creating demand for an optional Bitcoin key storage layer that might allow businesses to delegate possession to a trusted key storage provider while maintaining unquestionable ownership in the legal sense, and control in the technical sense. Such is the burden of holding these secrets that exercising control over private key information is more a liability than an asset. Most companies holding Bitcoin keys are required to do so out of operational necessity but would rather offload that liability from their books, as they do not monetize it.

Private key storage is more like managing a password than anything else. When a hard drive is locked by ransomware, most people without an adequate backup are likely to pony up the ransom to retrieve access to their information. This digital information is not property in the legal sense, but it’s certainly valuable to the individual who previously exercised possession and control over it.

## Storing Bitcoin Keys Responsibly

Bitcoin is just information, so it is difficult to place it inside existing financial definitions and regulations. But with its information space being the first example of truly scarce information, it has accrued substantial value thanks to evolving narratives.

If you want to learn about responsible Bitcoin private key custody for your fund, exchange, or other vehicles, have strict LP and risk management requirements, or otherwise appreciate a trust-minimized profile, [we’d love to talk](https://www.kn0x.io/contact-us).

Please email us at [custody@kn0x.io](mailto:custody@kn0x.io)

* * *

_Under no circumstances should any material on this post be construed as an offering of securities or investment advice. The reader should consult with their professional investment advisor regarding investments in securities referred to herein._

_Services and products are offered through KNØX Industries Inc., headquartered in Montreal, Canada. KNØX Industries Inc. is not engaged in the offer, or sale of securities or bitcoins, and does not provide investment, tax or legal advice._

_Investments and holdings of bitcoins are speculative and highly volatile, involving a substantial degree of risk, including the risk of complete financial loss. ‍_

_© 2020 KNØX Industries Inc. All rights reserved._

*Thanks to Thib.*

***

{% include signup.md %}