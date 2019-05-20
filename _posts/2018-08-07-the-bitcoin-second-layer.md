---
title: "The Bitcoin Second Layer"
permalink: "/the-bitcoin-second-layer" 

tags:
  - Nik Bhatia
  - Cy18 Q3

excerpt: Nik Bhatia lays out a the baseline for a 4 part series on Lightning Network. In this post, he draws similarities between LN and paper gold, with differences. Posted August 7, 2018.

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

# [The Bitcoin Second Layer](https://medium.com/@timevalueofbtc/the-bitcoin-second-layer-d503949d0a06)
### By [Nik Bhatia](https://medium.com/@timevalueofbtc)
### Posted August 7, 2018

1. **[1/4 The Bitcoin Second Layer](https://medium.com/@timevalueofbtc/the-bitcoin-second-layer-d503949d0a06)**
2. [2/4 The Time Value of Bitcoin](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2)
3. [3/4 The Bitcoin Risk Spectrum](https://medium.com/@timevalueofbtc/the-bitcoin-risk-spectrum-949f6abec290)
4. [4/4 The Lightning Network Reference Rate](https://cryptowords.github.io/the-lightning-reference-rate)

***

<br>

![](/assets/images/cy18/cy18q3m8/nb-1.png){: .align-center}

Bitcoin's antifragile protocol and its exponentially increasing network effects make it a behemoth, gradually swallowing up global economic activity. The latest of these network effects is a second layer protocol called Lightning Network, which uses bitcoin's base layer protocol as its security. The concept of layered money is not new in monetary history. In this writing, I'll be using gold as an analogy to describe why bitcoin will evolve in layers on its way to world reserve currency status.

**Layered Money**

Gold has served as money for millennia due to its unique chemical properties and its global network effects. But gold has not acted as money only in its raw physical form, or on its first layer. Gold is a perfect example of how a layered money system evolves. Let's take a look at gold as money in a four layered example. I'll describe the rule set, or protocol, of each gold layer so the reader can imagine similarities to bitcoin's layered protocol approach.

The first layer of gold is the physical gold in its raw form after it is mined: gold nuggets. The protocol of gold's base layer has only one rule. The element must adhere to the properties of the periodic table's 79th element. If it does, it is gold; if it does not, it is not gold. Consensus around this "79th element" protocol is millennia old.

The second layer of gold is raw gold that has been melted and shaped into bars and coins following a standardized protocol of purity, weights, and measures. Mints can be controlled by governments or by private enterprise, but the coinage will only be considered money by users if the "79th element" first layer protocol is followed.

The third layer of gold is gold certificates. These are claims issued by banks that have taken gold on deposit. Third layer banks will only use gold coins and bars that follow the consensus second layer protocol of purity, weights, and measures and only from mints that are properly following the "79th element" protocol. These certificates can act as money but carry counterparty risk of the issuer.

The fourth layer of gold is certificates backed by bank-issued gold certificates. A liquidity provider can issue these certificates, which would require several layers of trust by the user. Somebody accepting fourth layer gold as money has to trust that the liquidity provider has real gold certificates, which are backed by physical gold at a bank that follows a standardized purity for gold deposits.

Each layer uses the layer beneath it for consensus and security. Money will always see a multiple layered expansion as it evolves, and each layer has costs and benefits. You can mine your own gold, but this process is very expensive with a high barrier to entry. You can buy gold coins and bars easily in most parts of the world, but using them for day to day commerce is unfeasible. As a merchant, you can accept gold coins but either have to trust the purity or assay the gold yourself. Once you're using the paper certificate layers, you now are engaged in counterparty risk, but have easier capacity for transactions. Each layer serves a different function. Base layers are for final settlement, while higher layers are for facilitation of economic activity.

**Bitcoin's First Layer**

Bitcoin's first layer, or base layer, is a protocol proposed in 2008 that has reached a global state of consensus as it approaches its tenth birthday. Bitcoin's unit of account, also called bitcoin, has exchange rates with currencies around the world in markets that are growing in depth and liquidity. The protocol itself has added vital updates in its young life that have strengthened both security and usability. The network's uptime and its ability to prevent double spends are relentless.

Critics of bitcoin often incorrectly identify a feature of bitcoin, its slow speed, as a flaw. Bitcoin's confirmation process is meant to be slow because of security reasons. The intent of bitcoin is censorship-resistant, scarce digital cash, not a speedy payments solution. The best way to think about bitcoin's base layer protocol is as a final settlements layer. The final settlement of physical gold is also a slow, clunky, and expensive process. Imagine, for example, companies in different parts of the world settling large balances of gold by loading ships with physical gold bars and sailing fortunes hundreds of miles across seas. Not only is the delivery an arduous process, but the verification process is also quite a task. In theory, every single piece of metal would have to be tested for purity. This process should be considered as historical context for what is required to have true final settlement of scarce money. The energy consumption required to find valid blocks has dramatically increased over time which increases security, but difficulty adjustments ensure bitcoin still averages six blocks per hour.

Centralization and attack vulnerability, while both permanent concerns to owners of bitcoin, have not prevented huge sums of capital to be stored in bitcoin's denomination. The denomination, commonly known as BTC, despite its commonly quoted exchange rates with fiat currencies, stands alone as a final settlement asset. With a secure and reliable final settlement layer firmly in place, development of higher layers can ensue: enter the Lightning Network.

**Bitcoin's Second Layer**

Lightning Network is a second layer protocol on top of bitcoin. The protocol uses bitcoin as its native denomination, meaning that Lightning can only be used by those with real bitcoin. Under the hood, Lightning Network is a web of bidirectional payment channels, but the protocol's functionality is beyond the scope of this writing. The important takeaway is that Lightning allows for the instantaneous transfer of bitcoin from peer to peer with one considerable difference from the first layer: channel balances can adjust but do not require immediate settlement on the base layer. Simply stated, Lightning transactions are unsettled bitcoin transactions.

Having unsettled bitcoin comes with risk, however. Bitcoin held in Lightning Network payment channels can be stolen by malicious actors if node operators are not properly monitoring the channels and the base layer. Malicious actors have a strong disincentive to steal, however, as fraudulent activity gives the victim ability to sweep all funds from the channel. Now that we have covered some of Lightning Network's basics, let's take a look at the importance and the significance of this new layer on top of bitcoin.

**The Importance of Lightning**

Firstly, the Lightning Network is a zero sum, fully reserved routing network. You may only use Lightning if you bring in real bitcoin, and all routing fees earned by liquidity providers are paid for by liquidity consumers. This allows Lightning Network to operate with one of the primary features of bitcoin, its limited supply.

Secondly, Lightning does not carry the burden of base layer confirmation. This allows for bitcoin to be exchanged ad infinitum without consuming precious block space. Lightning nodes can decide to take final settlement of their bitcoin by broadcasting the correct state of a payment channel to the base layer at any time, but they don't have to.

Lastly, Lightning transactions can be interpreted as financial agreements, making Lightning Network a capital market layer. The network's structure is built as a market for capital and liquidity. Bitcoin can now instantaneously fly around the world without having to wait an hour for final settlement. The two core components to any financial transaction, time value and risk premium, can be derived from Lightning transactions. Opportunity cost tradeoffs can be calculated, and bitcoin can be leased on a short term basis to the network without surrendering one's private keys. With gold, there is no way to accrue positive interest on capital without surrendering the physical metal. This makes Lightning Network an absolute game changer for the entire concept of capital markets: income without explicit counterparty default risk.

**Conclusion**

Bitcoin is often referred to as digital gold, but I'll propose a more specific analogy. Bitcoin's base layer is like digital physical gold, while Lightning Network is like digital paper gold but without the counterparty risk. The second layer is unsettled and less secure, but infinitely more usable. Bitcoin is incredible at censorship resistance and decentralization, but frankly terrible at speed and efficiency. Critics of bitcoin completely miss the fact that speed and efficiency should take place on higher layers, NOT on the base layer. Lightning's arrival will show the world bitcoin's true capabilities. If gold could only be used as a physical metal, global economic activity would have been prohibitive on a gold standard. Thankfully, paper gold satisfied the liquidity and capital market layer. Lightning Network ensures bitcoin's path to global reserve currency because it makes bitcoin come alive. Once bitcoin can be transacted around the world without the constraint of a slow confirmation process, it can graduate from reserve asset to reserve currency. Lightning Network finally frees bitcoin from its base layer shackles.

**Further Reading**

This article is a prelude to my previous work. I have decided to make this article Part 1 of 4 in my series "The Lightning Network Reference Rate." Please also check out the second and third parts of this four part series. In Part 2, "[The Time Value of Bitcoin](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2)," I introduce the concept of LNRR, or the Lightning Network Reference Rate. In Part 3, "[The Bitcoin Risk Spectrum](https://medium.com/@timevalueofbtc/the-bitcoin-risk-spectrum-949f6abec290)," I discuss the reasons why LNRR can be a monumental innovation for bitcoin denominated capital markets. Part 4, coming soon, will be titled "The Lightning Network Reference Rate."
