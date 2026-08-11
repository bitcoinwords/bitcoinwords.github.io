---
title: "Why Token Velocity Matters"
permalink: "/why-token-velocity-matters"

author: edendhaliwal

tags:
  - Eden Dhaliwal
  - 2017 Q4
  - Economics
  - Money
  - Value

excerpt: Why Token Velocity Matters. Posted December 5, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Why Token Velocity Matters](https://medium.com/outlier-ventures-io/why-token-velocity-matters-1ad459435e33)
### By Eden Dhaliwal
### Posted December 5, 2017

**First published on**[**Hacked.com**](https://hacked.com/token-velocity-matters/)*****

These are still the early days in understanding token based crypto-economies. Whilst many of the principles of economics used aren’t new; the ability to hardcode rules into a system offer unparalleled opportunities to experiment with behavioural economics and game theory to try to make markets behave in certain ways.

At Outlier Ventures, we work with our partners at [Imperial College London](http://www.the-blockchain.com/2017/09/08/outlier-ventures-deepens-partnership-imperial-college-crypto-economic-token-design/)’s Business School and computer science department, to assist the open source projects we invest in, to design sustainable, efficient and orderly digital economies. This is the first in a series of regular posts where I, as Head of Cryptoeconomics, and the wider Outlier team will share with you some of the principles and learnings from this work.

Whether it’s designing token economies for implementation or evaluating cryptoassets for investment,**token velocity** is a key factor in guiding our thinking on the future value of tokens. This post aims to introduce token velocity as a principle and discuss some of its implications for economic design and valuation.

**The Basics: MV = PT**

Today, most tokens aim to represent a network-based [**medium of exchange**](https://www.investopedia.com/terms/m/mediumofexchange.asp). This means a network is created whereby sellers can offer digital services to buyers interested in acquiring them. A token is issued as a means of value in this digital economy and is required in order to facilitate the exchange of these services.

To begin understanding token velocity, we must refer to traditional economic concepts like the [**velocity of money**](https://www.investopedia.com/terms/v/velocity.asp) and the [**equation of exchange**](https://en.wikipedia.org/wiki/Equation_of_exchange):

The**velocity of money**, is the number of times money is exchanged from one transaction to another over a period of time, or in other words, how often money is turned over. This is important because velocity is useful for assessing the health of an economy.

The**equation of exchange**, is used to demonstrate the relationship between money supply, velocity of money, price levels and an index of real expenditures on newly produced goods and services. It is expressed as:

**MV = PT**

where:

M = money supply

V = velocity of money

P = average price level of goods

T = index of expenditures (such as the total number of economic transactions) Note: As this is usually difficult to measure. it’s often substituted by Y=national income.

#### Connecting Token Velocity & Token Value

Likewise, for token economies, the velocity of a token offers us insight into the economic health of a network. Token velocity can inform the level of hoarding within a system, speculative trading, utility value of a token and the broad efficiency of the digital economy. For cryptoeconomies, token velocity can be determined through modifications of the equation of exchange (courtesy of Chris Burniske and Vitalik Buterin respectively).

Burniske has applied the equation of exchange for [cryptoassets](https://medium.com/@cburniske/cryptoasset-valuations-ac83479ffca7) as such:

**MV = PQ**

where:

M = size of the asset base,

V = velocity of the asset

P = price of the digital resource being provisioned,

Q = quantity of the digital resource being provisioned

The token value would be determined by solving for M and dividing by the number of tokens in supply.

Meanwhile, Vitalik has his alternate modification of the equation of exchange for [medium of exchange tokens](http://vitalik.ca/general/2017/10/17/moe.html):

**MC = TH**

Where:

M = total money supply (or total number of tokens),

C = price of the currency (or 1/P, with P being price level),

T = transaction volume (the economic value of transactions per time),

H = 1/V (the time that a user holds a token before using it to make a transaction)

To determine token value, one must solve for C in this case.

The implied takeaway from these different equations is that token velocity has an inverse relationship with the value of a token. More succinctly, the longer participants hold onto their tokens, the higher the price of their tokens.

#### Layered Economics

When examining token economies, we essentially look for the merged optimization of two sets of economics:

* ***ledger layer economics***
* ***market layer economics***

As the market exchanges digital services, the ledger layer is where key attributes of each transaction need to be verified and simple contracts need to be executed. The main goal of the ledger layer is to drive costs of verification to as low a level as possible, ideally as near to costless as possible. Cost reduction and disintermediation is the primary advantage of blockchain based services over traditional intermediary or audit based economies where substantial value is lost in the process. Common examples of where a token is used to facilitate low cost transactions for digital resources in payments, computation, and data storage are Bitcoin, Ethereum and Filecoin, respectively. We can associate this layer of economics more closely to protocol tokens.

![](/assets/images/2017/m12/why-token-velocity-matters1.png)

Source: ‘Some Simple Economics of the Blockchain’ — [https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2874598](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2874598)

Christian Catalini, MIT & Joshua Gans, University of Toronto, Rotman School of Management

At the market layer, economics are designed to realign the distribution of value to achieve a more efficient market that also leverages powerful network effects. The token is used as an incentive or disincentive to participants to behave both in their best interest and the greater good of the economy at large. This layer is generally exhibited as an app token.

An example of market layer economics is illustrated below by the Basic Attention Token (BAT), where users, publishers and advertisers are re-aligned to disintermediate middlemen, eliminate the economic waste and generate new value. In this blockchain based digital advertising market, the Brave browser blocks ads to the user and records where users spend their time.

Meanwhile, BAT is used as a unit of account between advertisers, publishers and users and to directly measure, exchange and verify attention.

The result is a system that is transparent and efficient. Publishers generate more revenue because middlemen are removed. Users that opt in receive fewer, better targeted ads (with far less malware). Lastly, advertisers receive better data for their spend.

**Basic Attention Token (BAT)**

![](/assets/images/2017/m12/why-token-velocity-matters2.png)

Basic Attention Token: [https://basicattentiontoken.org/BasicAttentionTokenWhitePaper-4.pdf](https://basicattentiontoken.org/BasicAttentionTokenWhitePaper-4.pdf)

#### Economic Implications of Token Velocity

Velocity can have significant impact on the economics layers of a token economy, based on the following:

**Ledger Performance:** If a ledger is suboptimal in facilitating exchange because of low throughput, latency, etc, this can cause service providers to become unmotivated to leverage the ledger for their offerings. Such problems can be particularly exacerbated, when transaction volumes are high but token holders are also hoarding for speculative purposes. This results in transaction verifiers suffering by being required to complete more costly work at a slower pace, thereby limiting their economic gains. As shown below, the Bitcoin network has been attempting to deal with these important [scalability issues](https://en.wikipedia.org/wiki/Bitcoin_scalability_problem) for some time now.

![](/assets/images/2017/m12/why-token-velocity-matters3.png)

Source: [https://blockchain.info/charts/avg-confirmation-time?timespan=1year&daysAverageString=7](https://blockchain.info/charts/avg-confirmation-time?timespan=1year&daysAverageString=7)

**Speculative Holding:** When too many tokens are held by purely speculative investors (otherwise known as [Hodlers](https://bitcointalk.org/index.php?topic=375643.0)), tokens generally do not get utilized within the market for their designed purpose. Instead, investors are simply waiting for the right time to sell off tokens for profits, and this causes low velocity in the system. Furthermore, speculative holding affects the system’s throughput, latency, etc putting pressures on the ledger layer as less tokens are available to facilitate transactions.

Note: Early on, a healthy amount of speculation is often advantageous in generating network effects and rewarding early adopters and contributors. In fact, what makes token economies so ripe with potential, is that they combine the two most powerful examples of [network effects](https://en.wikipedia.org/wiki/Network_effect), financial exchanges and software, within a new digital economy.

**New Equilibrium:**As token economies progress or regress, new price equilibriums are set through behavioral feedback loops that are ultimately driven by token price itself. As Ethereum’s [Vitalik](http://vitalik.ca/general/2017/10/17/moe.html) points out, when the token price starts to increase, crypto traders begin to acquire and hold tokens based on expected returns, which are assumed to be higher than other cryptoassets. This increases the price of token and often closely resembles****[**Elliott’s Wave Theory**](https://www.investopedia.com/articles/technical/111401.asp) (a form of technical analysis) in setting a new token price equilibrium.

Provided the ledger layer can efficiently verify transactions, a price increase could also greatly benefit the market layer economics by making fees cheaper and further stimulating the economy. Both of the above positive feedback loops create a new token price equilibrium.

This chart of Monero illustrates new equilibriums in July ’17 and again in October ‘17.

![](/assets/images/2017/m12/why-token-velocity-matters4.png)

Source: [https://coinmarketcap.com/currencies/monero/](https://coinmarketcap.com/currencies/monero/)

Conversely, if the token price starts to decline, the token suffers as an opportunity cost to other seemingly more attractive tokens investments. As the sell off continues, the further the token price decreases, this time suffering from a negative feedback loop.

**Stagnant Utility:** Early adopters of a token will often hold the belief that a given decentralized market will be able to offer unique value propositions for digital services yet to be developed. If these services are too limited, tokens will be exchanged at a substandard velocity. Although the equations above suggest lower velocity would increase the value of the token, in this case, declining transaction volumes will lead to economic collapse and token price crash.

Another scenario derived from lack of utility, is when a token serves as an optimal medium of exchange for a dominant, high-demand service between a buyer and seller, where neither party has any motivation or incentive to keep the token for further use. Instead, opting to convert into a more desirable speculative or usable currency (like fiat). In these cases, velocity of a token would be high and drive down the price of the token, which further reinforces this behavior.

***

{% include signup.md %}
