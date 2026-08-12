---
title: "Stablecoins: A Holy Grail in Digital Currency"
permalink: "/stablecoins-a-holy-grail-in-digital-currency"

author: nicktomaino

tags:
  - Nick Tomaino
  - 2017 Q2
  - Economics
  - Money
  - Monetary Policy

excerpt: Stablecoins: A Holy Grail in Digital Currency. Posted April 3, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Stablecoins: A Holy Grail in Digital Currency](https://thecontrol.co/stablecoins-a-holy-grail-in-digital-currency-b64f3371e111)
### By Nick Tomaino
### Posted April 3, 2017

### A global currency with no central bank and low volatility may be a key component of the decentralized web

One of the main characteristics of digital currencies that the mainstream media has focused on is volatility. While the volatility of Bitcoin has decreased significantly since it launched in 2009, it is still not a good unit of account or a stable store of value. Look no further than the price of BTC and ETH over the past month (BTC price moved over 10% in a day and ETH moved over 20% in a day several times).

> What if the volatility of a a digital currency could be minimized by a decentralized autonomous organization (DAO) with no central authority? This is the promise of an emerging category of digital assets called
>
> stablecoins.

A stablecoin is an asset that has price stability characteristics that make it suitable for short-term and medium-term use as a unit of account and store of value. The US dollar is the best example of a stablecoin in the world of fiat currencies. While USD does offer relatively low volatility for those that want a reliable unit of account and store of value, it doesn’t offer user control because it’s controlled by the Federal Reserve Bank and requires reliance on the US banking system for significant commercial use. **User control and minimized volatility is a holy grail in not just digital currencies but currencies broadly.**The [Maker](http://www.makerdao.com) project is seeking to reach this holy grail by creating the first viable stablecoin: the dai.

![](/assets/images/2017/m4/stablecoins-a-holy-grail-in-digital-currency1.png)

##### **Meet Maker**

The dai does not exist yet and is not much more than a vision. But the groundwork is currently being laid for a [stablecoin](http://stablecoin.technology/StableCoin) that could bring millions of more people into the blockchain ecosystem.

In 2015, [Rune Christensen](https://www.linkedin.com/in/rune-christensen-5b5220ab/) published the [white paper that describes the Dai Credit System](http://makerdao.com/docs/), a complex organizational structure designed to create a digital asset with minimized volatility and no central bank. Since then, Rune and the decentralized autonomous organization known as [Maker](http://www.makerdao.com) issued MKR tokens and built a lot of the infrastructure required to bring the vision to life, including a [decentralized exchange for ERC20 tokens](https://pro.oasisdex.com/), [developer tools for writing smart contracts,](http://dappsys.info) and [core splitting auction contracts](https://github.com/makerdao/token-auction).

The Maker team has significant security work left to do on the smart contracts, but the plan is to launch the dai by the end of 2017. The system the Maker DAO is building is complex but it is inspired by a lot of economic theory. If you’re an econ nerd like myself, you may enjoy the next section. If not, you may want to skip.

![](/assets/images/2017/m4/stablecoins-a-holy-grail-in-digital-currency2.jpg)

*Rune Christensen leads Maker*

##### Understanding the Dai Credit System

There will be two different tokens in the Dai credit system: **Dai (the stablecoin)** and **MKR (the counter coin)**. Dai is a free floating currency that derive its value from the fact that it’s backed by collateral (ETH to start, other digital assets later). MKR is a token that derives its value from the fact that it earns stability fees (interest) from the borrower of dai and has an active function in making the whole system work (governance). There are 1 million MKR tokens outstanding currently, but this will fluctuate in the future based on the performance of the system (if good then the total supply will decrease, if bad it will increase). The tokens have been continuously sold off in small batches by the Dai Foundation. Currently about 55% of the total supply has been distributed, with the foundation still having another 45% for future fundraising.

Another important value proxy to consider in the system is the **Special Drawing Right (SDR)**, which is an international currency basket maintained by the International Monetary Fund (IMF) that has low volatility against all major world currencies. The target price of dai will always be in terms of the SDR.

There are five different types of participants in the Dai Credit System that all play critical roles:

* **Dai borrowers:**Dai borrowers create dai by locking up collateral in ETH or other digital assets (which will be voted on by MKR holders). This is known as a collateralized debt position (CDP). A primary initial use case for borrowers is likely to be margin trading (traders can borrow dai by posting ETH as collateral and sell the dai in exchange for ETH to leverage ETH exposure). A borrower that wants their collateral back has to return dai + interest (which gets paid to MKR holders).
* **Dai holders:**Holders are individuals or companies that are motivated to use dai as a unit of account or store of value that they control**.**
* **MKR Holders (Governors):**MKR holders play two important roles in the system: they vote on decisions the Maker DAO makes (like what digital assets can be posted as collateral and what features should be prioritized) and they help keep the dai stable (meaning they act as the final backdrop for all collateralized debt positions). When CDPs hit their liquidation ratio (the equivalent of a margin call), new MKR is created and existing MKR holders step up and buy back the assets with DAI and returns to the borrower whatever is left over.
* **Keepers:**Keepers are economic agents that are incentivized to contribute to making the system run efficiently. Specifically, they perform two important functions in the system: participating in continuous splitting auctions and market making the dai around the target price.
* **Oracles:**Maker needs information about the market price of the dai and its deviation from the target price in order to adjust the deflation rate as well as the market price of the various assets used as collateral for the dai in order to know when liquidations can be triggered. Oracles provide that service in the system.

This is an extremely complex organizational structure with lots of moving parts. Like all blockchain projects, it’s an economic experiment that’s never been tested before and no one knows for sure how the different participants will react and if the system will work as designed. I’m personally excited to see it tested in the wild though. A decentralized currency with no volatility could ultimately become the backbone of the global economy.

##### How to learn more

* Read the Maker whitepaper: [http://makerdao.com/docs/](http://makerdao.com/docs/)
* Read the Maker purple paper: [http://stablecoin.technology/purple.pdf](http://stablecoin.technology/purple.pdf)
* Check out the Maker Subreddit: [https://www.reddit.com/r/MakerDAO/](https://www.reddit.com/r/MakerDAO/)
* Chat in the Maker Rocketchat: [https://chat.makerdao.com/](https://chat.makerdao.com/)
* Vitalik Buterin on Stablecoins: [https://blog.ethereum.org/2014/11/11/search-stable-cryptocurrency/](https://blog.ethereum.org/2014/11/11/search-stable-cryptocurrency/)

![](/assets/images/2017/m4/stablecoins-a-holy-grail-in-digital-currency3.jpg)

*The Token Summit is May 25th in NYC at the Paulson Auditorium at NYU Stern School of Business*

#### **Maker core developer**[**Andy Milenius**](https://twitter.com/cheesematic)**will be attending the**[**Token Summit**](http://tokensummit.com/)**and speaking about the Maker project.**[**Get your ticket now**](https://www.eventbrite.ca/e/token-summit-tickets-32569398949#tickets)**to meet Andy and other leaders from many of the leading blockchain projects in the world on May 25th.**

![](/assets/images/2017/m4/stablecoins-a-holy-grail-in-digital-currency4.png)

**About me:**I run [The Control](https://thecontrol.co/) and am an investor at [Runa Capital](http://www.runacap.com), an early stage venture fund. Previously, I worked on business development and marketing at [Coinbase](http://www.coinbase.com). Follow me on [Twitter](http://www.twitter.com/ntmoney), signup for our [newsletter](https://www.getrevue.co/profile/control), and support us by becoming a member:

[**Thank you for becoming a member of The Control!**
*Your support is much appreciated. As a member of The Control, you will receive:*thecontrol.co](https://thecontrol.co/thank-you-for-becoming-a-member-of-the-control-9b86cd688355)

***

{% include signup.md %}
