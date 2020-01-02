---
title: "Bitcoin's Production Cost"
permalink: "/bitcoins-production-cost" 

author: charlesedwards

tags:
  - Charles Edwards
  - CY19 Q4
  - Technical Analysis
  - Financial Models
  - Price
  - Production
  - Mining

excerpt: Charles Edwards shares his model for Bitcoin valuation based on production cost. Posted December 13, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin's Production Cost](https://medium.com/capriole/bitcoins-production-cost-88d889462ea7)
### By [Charles Edwards](https://twitter.com/caprioleio)
### Posted December 13, 2019

## An Estimate of Bitcoin’s Production and Electrical Cost — a Historic Floor in Bitcoin’s Price.

![](/assets/images/cy19/cy19m12/ce-7.png)


## **Takeaways**

*   **Bitcoin’s electricity consumption can be used to estimate Bitcoin’s Production Cost**
*   **Bitcoin’s Production Cost can be used to estimate Miner profitability**
*   **Bitcoin Mining has historically been a very profitable business**
*   **2019 has been the worst year for Bitcoin Miners in all of the last 5 years**
*   **Bitcoin Miners are currently taking on losses from the 4th quarter price drop**
*   **The Bitcoin Electrical Cost has been a concrete price floor in the Bitcoin market price**
*   **A pessimistic price floor for mid-2020 is estimated at $8,000**
*   **However, miner influence on supply and demand is dropping, with Bitcoin’s inflation rate at 3.8% and falling**

This article links Bitcoin’s electrical consumption to the cost of Bitcoin production. In doing so we gain insight into the historical profitability of Bitcoin mining and an indication to when Bitcoin mining businesses are struggling. Over the last 5 years, Bitcoin’s Electrical Cost has been a floor in Bitcoin’s exchange traded market price, proving Satoshi’s theory that price gravitates to the cost of production.

## **Commodity Prices and Production Costs**

The relationship between Bitcoin miner production costs and the price of Bitcoin is summarised best by no other than Satoshi himself:

> _“The price of any commodity tends to gravitate toward the production cost. If the price is below cost, then production slows down. If the price is above cost, profit can be made by generating and selling more. At the same time, the increased production would increase the difficulty, pushing the cost of generating towards the price._
> 
> _In later years, when new coin generation is a small percentage of the existing supply, market price will dictate the cost of production more than the other way around.”_
> 
> _- _[_Satoshi Nakomoto, 2010_](https://bitcointalk.org/index.php?topic=57.msg415#msg415)

Knowing this relationship and drawing on detailed investigations into the electrical consumption of Bitcoin, we can estimate the cost of mining Bitcoin.

## **The Cambridge Bitcoin Electricity Consumption Index (CBECI)**

In 2019, Cambridge University [published](https://www.cbeci.org/methodology/) a detailed study estimating Bitcoin’s energy consumption from November 2014 to present.

This study is likely the most detailed bottom-up calculation of Bitcoin’s global electricity consumption to date.

![](/assets/images/cy19/cy19m12/ce-8.png)
*[Cambridge Bitcoin Electricity Consumption Index (Dec 2019](https://www.cbeci.org/))*

Cambridge [estimates](https://www.cbeci.org/methodology/) Bitcoin’s electrical usage based on the assumption that miners will run the mining hardware as long as it remains profitable in electricity terms. Other key assumptions behind their calculations include:

1.  **The global average Bitcoin miner electricity price is $0.05 USD per kWh.** Based on interviews with miners globally and consistent with other research, including [CoinShares](https://coinsharesgroup.com/assets/resources/Research/bitcoin-mining-network-june-2019-fidelity-foreword.pdf)
2.  **The energy efficiency of over 60 mining hardware models since 2014.** Per manufacturer specifications and refined based on expert advice (to account for actual usage and overclocking)
3.  **The global average Power Usage Effectiveness (PUE) of Bitcoin Miners is 1.1**. PUE is a measure of the total energy required to operate mining facilities (including cooling) relative to the energy required for server operation. Cambridge came to this figure based on interviews with miners globally. It is also in-line with [Google’s average PUE of 1.11](https://www.google.com/about/datacenters/efficiency)

Cambridge’s calculation assumes an equally weighted basket of _profitable_ mining equipment which is perhaps the most thorough approach to assessing mining hardware utilisation, depreciation and therefore energy consumption globally today.

All references to Bitcoin’s electrical consumption in this article refer to [Cambridge’s “Best-guess” estimate](https://www.cbeci.org/methodology/) of Bitcoin’s electricity consumption.

## **Bitcoin’s Production Cost**

Bitcoin’s Production Cost is an estimate of the global average US dollar cost of producing one Bitcoin per day.

Every study into Bitcoin’s mining costs to date has found electricity to be the primary cost of operations, and it is used here as a base from which to estimate the Bitcoin Production Cost.

From Cambridge’s electricity consumption, Bitcoin’s Production Cost can be estimated by:

1.  Calculating number of Bitcoin Mined Per Day (based on Bitcoin’s Block Reward and block frequency)
2.  Calculating the Bitcoin Electrical Cost = daily electricity cost to mine a Bitcoin
3.  Estimating the global average “Elec-to-Total Cost Ratio” = (Bitcoin Electrical Cost) / (Daily Cost of running a Bitcoin Mining Business)

Bitcoin Production Cost is then found as (Daily Electrical Cost) / (Elec-to-Total Cost Ratio)

From Cambridge’s data one additional assumption is required — an estimate of the global average Bitcoin mining **Elec-to-Total Cost Ratio** (Item 3 above).While electricity is the major factor in Bitcoin mining operations, other costs in operating a Bitcoin mining business include:

*   Hardware Capital Expenditure
*   Bandwidth
*   Wages
*   Rent
*   Insurance
*   Cost of Capital

Varying estimates have been made for the Elec-to-Total Cost Ratio and include:

![](/assets/images/cy19/cy19m12/ce-8.png)
_Estimates of Bitcoin’s Electrical Cost to Total Mining Cost_

Well-funded businesses in a low-cost country such as China likely have low and negligible wages, rent, insurance and capital costs relative to the total cost of mining. China, for example, accounts for [approximately](https://coinsharesgroup.com/assets/resources/Research/bitcoin-mining-network-june-2019-fidelity-foreword.pdf) 60% of Global Bitcoin mining in 2019.

Based on the research available to date and noting that a number of the above estimates appear not to consider the general costs of business (rent, wages, etc) outside of electrical operating expenditure (OPEX) and hardware capital expenditure (CAPEX), **the Elec-to-Total Cost ratio is estimated here as 60%.**

Using Cambridge’s electricity data, this gives 5 years of the Bitcoin Production Cost.

![](/assets/images/cy19/cy19m12/ce-10.png)
*Bitcoin Production Cost*

## **Bitcoin Miner Price**

While it is interesting to compare Bitcoin’s price to the Bitcoin Production Cost, as each coin mined can be sold at the prevailing market price, this approach misses on another piece of miner revenue — transaction fees.

As well as each block reward’s freshly mined bitcoins, miners also receive transaction fees in each block. Transaction fees are determined by senders based on supply and demand. Additionally, with time transaction fees will represent a greater portion of miner revenue as block rewards reduce with each halving.

As a result, the Bitcoin Production Cost should be compared to the revenue one Bitcoin provides (Bitcoin’s market price) _and_ the transaction fee revenue.

**We term this the Bitcoin Miner Price and it is calculated here as the Bitcoin Price + (Daily Transaction Fees) / (Daily Bitcoin’s mined).**

![](/assets/images/cy19/cy19m12/ce-11.png)
*The Bitcoin Miner Price varies with demand for on-chain transactions*

Putting Bitcoin’s Production Cost and Miner Prices together, we can see when **Bitcoin Miners are struggling in recent times and potentially taking on short-term loses.**

![](/assets/images/cy19/cy19m12/ce-12.png)
*Bitcoin Production Cost versus Bitcoin Miner Price*

## **Bitcoin Electrical Cost — A Bitcoin Price Floor**

Bitcoin Production Cost provides insight into the profitability of Bitcoin mining businesses. Price drops below the Bitcoin Production Cost tend to be short lived. This makes sense as high-cost miners go out of business, the hash rate plateaus and falls and miners in general are less inclined to sell at a loss.

However, the Bitcoin _Electrical_ Cost offers a stronger price floor.

Over short periods, a number of miner business costs are “sunk” (e.g. already paid for hardware), contractually locked-in (e.g. rent) or can be deferred (e.g. hardware upgrades). This means that Bitcoin miners can operate at a loss over short periods.

This makes sense provided the Bitcoin Miner Price is above the Bitcoin Electrical Cost. If the cost of running your mining hardware is less than or equal to the revenue it generates, you may as well leave it turned on, until such a point that general business losses make this wasted effort unbearable and the opportunity cost too high. However, this scenario cannot continue indefinitely. Losing miner would not have any revenue left over for re-investment in the business (continual capex is required to keep up with generally growing hash rates), ability to pay rental contracts, wages and other business costs.

Using Cambridge’s data from 2014 alone, with no further assumptions, we can see that Bitcoin’s price never quite reaches the Electrical cost to produce a Bitcoin, despite coming very close in November 2018.

**Historically, the electrical cost to produce a Bitcoin has represented a price floor in the Bitcoin market price.**

In more recent years, the introduction of Bitcoin Futures has also potentially allowed Bitcoin Miners to lock in profits earlier, for example, by shorting when the Bitcoin Price is significantly greater than production cost. However, the effectiveness of such strategies is debateable. The introduction of Bitcoin Options in 2019 will also likely aid Bitcoin miners by providing certainty in their cash flows and the ability to effectively lock in a Bitcoin sale price floor.

**Miner Profitability Oscillator**
==================================

All of the above suggests Bitcoin Miners are struggling at present. Most are operating at a business loss in the short term, with an average daily profitability of 10% for 2019.

Even if the 60% Elec-to-Total Cost Ratio assumption is off by a wide margin, based on Cambridge’s electrical consumption data, **2019 is the least profitable year for Bitcoin Mining in all of the last 5 years.**

![](/assets/images/cy19/cy19m12/ce-13.png)
***Bitcoin Miner Profitability Oscillator** — Bitcoin mining has historically been a very profitable business*

**Outlook**
===========

It is worth noting that the Bitcoin Production Cost will double at the next Bitcoin halving (currently estimated for May 2020). When the Block Reward halves, the daily cost of Bitcoin Production is spread across half as many Bitcoins.

![](/assets/images/cy19/cy19m12/ce-14.png)
**Bitcoin Production Cost doubling at 2016 Halving. Estimated Production cost increase was tempered by the phase in of the significantly more energy efficiency Antminer S9**

From this figure, if Bitcoin’s Hash Rate and mining hardware efficiency were to remain unchanged from today, the Bitcoin Production price at Halving would be $17,800.

Although Hash Rates can fluctuate widely, they are historically much more stable than Bitcoin’s price. The weekly average Hash Rate has never dropped more than 47% from its peak (in 2011). The second largest drop was 37% in December 2018.

The second most varying input into Bitcoins Electrical Price is mining hardware efficiency, which has historically [improved every year](https://www.cbeci.org/methodology/).

Even if Hash Rates were to drop 40% below todays levels, and mining hardware efficiency were to improve 25% in the next 6 months, Bitcoin’s Electrical Cost would be approximately $8,000. **Suggesting a pessimistic case price floor of for mid-2020 of $8,000**. **8% higher than today’s Bitcoin price of $7350.**

Limitations to this model also include the reducing share of total Bitcoin supply which miners hold. **Bitcoin’s inflation rate, and therefore the relative portion of incremental Bitcoins that miners gain control of each year, is currently 3.8%** **and decreasing exponentially. **The influence of each new Bitcoin in 2020 onwards will drop significantly with the Halving. Therefore, as alluded to by Satoshi above, the reliability of the Bitcoin Electrical Cost as a price floor may reduce with time.

\*\*\*

_Chinese Translation: _[_https://my.first.vip/shareNews?id=2601&uid=5066_](https://my.first.vip/shareNews?id=2601&uid=5066)



***

{% include signup.md %}
