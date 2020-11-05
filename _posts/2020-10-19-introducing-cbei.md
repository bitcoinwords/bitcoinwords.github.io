---
title: "Introducing CBEI: A New Way To Measure Bitcoin Network Electrical Consumption"
permalink: "/introducing-cbei"

author: tylerbain

tags:
  - Tyler Bain
  - 2020 Q4
  - Mining
  - CPBI
  - Energy
  - Index
  - Electricity Consumption

excerpt: Tyler Bain shares the CBEI as a way to measure network energy consumption. Posted October 19, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Introducing CBEI: A New Way To Measure Bitcoin Network Electrical Consumption](https://bitcoinmagazine.com/articles/introducing-cbpi-a-new-way-to-measure-bitcoin-network-electrical-consumption)
### By [Tyler Bain](https://twitter.com/blockbain)
### Posted October 19, 2020

![Using the Composite Bitcoin Energy Index (CBEI), we can determine how much electrical power Bitcoin draws and how much electrical energy it has used.](/assets/images/2020/m10/tb1.png)

There have been many claims in recent years that bitcoin and the miners securing the network via SHA-256 proof of work use an unconscionable amount of energy. But what data are these claims based on, are the source calculations using flawed or sound approaches and assumptions? How much electrical _power_ does the network draw and how much electrical _energy_ has the Bitcoin network used historically?

## Methodologies And Misconceptions

Due to the vast, globally distributed topology of the Bitcoin network, the amount of electrical power and energy that miners consume isn’t exactly verifiable, instead it must be estimated. Among the [energy](https://arstechnica.com/tech-policy/2018/05/new-study-quantifies-bitcoins-ludicrous-energy-consumption/) [consumption](https://www.financemagnates.com/cryptocurrency/news/btcs-energy-consumption-problem-may-be-much-worse-than-we-thought/) [hysteria](https://www.bbc.com/news/technology-48853230) over the previous few years, a surprisingly large number of reputable sources have weighed in and attempted to estimate Bitcoin’s network energy consumption in more level-headed and data-derived ways:

*   [University of Cambridge, Judge Business School (JBS)](https://cbeci.org/)
*   [The International Energy Agency (IEA)](https://www.iea.org/newsroom/news/2019/july/bitcoin-energy-use-mined-the-gap.html)
*   [Electric Power Research Institute (EPRI)](https://www.epri.com/#/pages/product/3002013910)
*   [Coin Center](https://coincenter.org/entry/evaluating-estimates-of-bitcoin-electricity-use)
*   [CoinShares](https://coinshares.com/research/)
*   [Marc Bevand](http://blog.zorinaq.com/bitcoin-electricity-consumption)
*   [Hass McCook](https://www.academia.edu/37178295/The_Cost_and_Sustainability_of_Bitcoin_August_2018_)
*   [Alex de Vries](https://digiconomist.net/bitcoin-energy-consumption)
*   [Myself](https://twitter.com/blockbain/status/1170719577660985350)

Estimation methodologies seem to fall into two major categories: **_economics-based_** approachesrooted in financial assumptions, as well as **_physics-based_** approaches planted in engineering principles. These two estimation approaches were thoroughly compared and contrasted at [BTC2019](https://www.youtube.com/watch?v=X4_zXcbErGo).

It’s important to understand when digesting all of these yearly usage estimations that electrical consumption is typically measured in two ways: instantaneously ([power](https://en.wikipedia.org/wiki/Electric_power), watts, kilowatts, etc.) and that same instantaneous power measurement integrated over time ([energy](https://en.wikipedia.org/wiki/Electrical_energy), joules, kilowatt-hours (kWh), etc.)

![Image for post](/assets/images/2020/m10/tb2.png)

_Small Bitcoin miners draw about 1,300 watts of power and use about 31,200 watt hours of energy over a 24-hour period._

## The Problems With Economics-Based Network Energy Estimations

Economics**–**based approaches that estimate the Bitcoin network energy consumption generally assume perfectly rational market behavior, and can easily be manipulated with a few input variable misassumptions.

In theory, the Bitcoin mining industry is rational, [profit maximizing](https://en.wikipedia.org/wiki/Profit_maximization) and [perfectly competitive](https://en.wikipedia.org/wiki/Perfect_competition): mining marginal revenue should tend to equal marginal cost (MR = MC). Meaning, on long enough time horizons, the market should find an equilibrium, where the cost of energy consumed in a unit of bitcoin’s production should be roughly equivalent to the unit’s market value at the time of minting. This calculation methodology can be distilled as, “How much can Bitcoin network miners _afford_ to spend on electricity?” 

Typically, these types of estimations are too dependent on a single volatile variable: the market exchange price of bitcoin. Below is a quick, simplified example of this type of estimation:

`[MR] = [MC]`

`[(Blocks/Day)*(Reward/Block)*(BTC Price) ]=[(kWh/Day)*($/kWh)]`

`[(Blocks/Day)*(BTC/Block)*($/BTC)]/($/kWh) = (kWh/Day) = Energy/Day`

Let’s try this estimation. Bitcoin blocks are generated roughly every 10 minutes — a rate of 6 per hour, or 144 every day. Currently, a single bitcoin block contains 6.25 BTC of coinbase block subsidy; that’s 37.5 BTC per hour, or 900 newly-minted bitcoin rewarded to miners daily. With bitcoin’s current market exchange price of about $10,750 at the time of this writing, that is roughly $9,675,000 earned per day that bitcoin miners have available to spend on electricity.

![Image for post](/assets/images/2020/m10/tb3.png)

_Average U.S. electrical costs in cents per kWh by state, per_ [_EIA data_](https://www.eia.gov/electricity/state/)

`[(144)*(6.25/Block) * $10,750] / ($0.10/kWh) = (96.75 GWh/Day)`

This amount of daily energy equates to roughly 35.3 TWh of yearly usage that the bitcoin miners could _afford_ to consume, if we take a snapshot today and assume constant bitcoin price for a year and U.S. average electrical costs.

While this method is overly reliant on bitcoin price, it is also heavily dependent on the assumed electrical energy cost for miners. The calculations and conclusions of this kind of estimate can be drastically different or even manipulated depending on the assumptions used as inputs: energy costs ($/kWh) and the price of bitcoin ($/BTC).

Here we used the average U.S. electrical cost of $0.10/kWh. However, in the U.S., electrical costs actually vary seasonally, from state to state, city to city and, in some cases, neighborhood to neighborhood. [Global electrical costs](https://www.iea.org/data-and-statistics/charts/electricity-price-distribution-across-countries-2018) have the same incongruence. This isn’t even including wide-ranging industrial, commercial or residential [electrical energy rates](https://medium.com/r/?url=https%3A%2F%2Fwww.iea.org%2Fdata-and-statistics%2Fcharts%2Felectricity-price-distribution-across-countries-2018), adding even more sources of error to these economics-based estimation techniques. And, in fact, this calculation’s heavy energy price dependence has yet another flaw: some miners’ high in ingenuity have near-zero fuel cost as they harvest excess, otherwise wasted, inaccessible or curtailed energy sources.

This quick exercise highlights, in my opinion, why this type of economics-based estimation approach is a gross oversimplification fraught with the following issues:

*   Bitcoin mining, hash rate and, therefore, network energy consumption isn’t as responsive to sudden price movements as these economics-based estimation methods are.
*   The economics-based model claims energy usage is cut in half along with network miner rewards after each bitcoin block reward halving cycle, which is every 210,000 blocks or about four years, while difficulty and proof-of-work-based data disproves this.
*   This type of model assumes a single average global energy cost ($/kWh); [electrical energy costs](https://en.wikipedia.org/wiki/Electricity_pricing) vary widely by region, seasonally and even by energy source.
*   This is likely to be an upper-bound estimation.

## The Benefits Of Physics-Based Network Energy Estimations

Physics**–**based network energy estimation approaches, on the other hand, tend to be a very rigorous type of “_running of the numbers”_ that the Bitcoin community is accustomed to.

These methods use independently verifiable on-chain difficulty, proof-of-work data and original equipment manufacturer (OEM) -published heat rate specifications to more accurately estimate historical energy inputs into the bitcoin mining system. The physics estimation attempt may best be described as a “bitcoin stoichiometric ratio unit analysis calculation:”

`Bitcoin Difficulty (Unitless) → Bitcoin Hash Rate (Daily Average TH/s)`

`Daily Average Hash Rate (TH/s) → Yearly Hashes (TH/Year)`

`Yearly Hashes (TH/Year) * Yearly Hash Heat Rate (Joules/TH) = (J /Year)`

`Energy Per Year (Joules/Year) → (kWh/Year) → (TWh/Year) → (ktoe/Year)`

So, let’s try out this style of estimation using bitcoin proof-of-work difficulty data and OEM-published data. Bitcoin network [difficulty](https://en.bitcoin.it/wiki/Difficulty) self-adjusts once every 2,016 blocks, or roughly once every two-week period. This difficulty adjustment is to compensate for block production speed discrepancies and, thus, network hash rate fluctuations.

![Image for post](/assets/images/2020/m10/tb4.png)

_Bitcoin network hash rate (Th/s) compared to difficulty, April 2015 to April 2020._

This difficulty and proof-of-work relationship allows us to derive an estimate for network [hash rate](https://en.bitcoinwiki.org/wiki/Hashrate) based on the block production rate and the associated difficulty level. From the amount of work done at the various difficulty levels over the previous decade, we can roughly estimate the amount of SHA-256 hashes computed per year on the Bitcoin network, shown below in terahashes per year (Th/year) or a trillion hashes per year. We can also do this same type of exercise with daily data to produce more granular calculations (spoiler: keep reading).

![Image for post](/assets/images/2020/m10/tb5.png)

_Estimated total Bitcoin network terahashes by year._

Bitcoin is on pace to have roughly 3,934 yotahashes computed on the network in 2020 or  about 3,934 septillion hashes (“yota” and “septillion” are the largest of the Scientific International [(SI) prefixes](https://en.wikipedia.org/wiki/SI_prefix) to date, (10²⁴)),

![Image for post](/assets/images/2020/m10/tb6.png)

_Scientific International (SI) unit prefixes, based on NIST data_ [_here_](https://physics.nist.gov/cuu/Units/prefixes.html)_._

Now that we have an estimation for the amount of hashes per year, next we must compile mining rig efficiency data over the past 11 years to understand how much energy would have been required to produce that amount of work.

Here it is important to understand the different types of mining equipment that have provided work toward the Bitcoin blockchain over the years. Each era and year has distinctly different proof-of-work efficiency characteristics, which change the network’s energy consumption values over time. From the humble beginnings of the Bitcoin genesis block being built by work derived from CPUs (central processing units), to blocks eventually being constructed with GPUs (graphics processing units), then on to FPGAs (field programmable gate arrays), and finally ASICs (application-specific integrated circuits) the Bitcoin network has evolved at a stunning pace.

![Image for post](/assets/images/2020/m10/tb7.png)

_Bitcoin network hash rate colored by general device type eras, in terahashes per second._

_Important note:_[_efficiency_](https://en.wikipedia.org/wiki/Efficiency)_is defined as useful work performed over energy expended to complete that work (terahash/joules — Th/J). However, ASIC original equipment manufacturers typically cite a type of_[_heat rate_](https://en.wikipedia.org/wiki/Heat_rate_(efficiency)) _specification, or the inverse of efficiency, showing energy expended over useful work (joules per terahash — J/Th)._

As you can see in the log scale chart below, over the past eight years, bitcoin mining ASICs’ heat rates have been steadily marching lower every year, meaning network mining efficiency has been increasing.

![Image for post](/assets/images/2020/m10/tb8.png)

_Manufacturer published SHA-256 ASIC energy per hash heat rate in joules/terahash by bitcoin mining rig._

Translating this data into an average yearly heat rate (chart below) shows a similar steep decline during the entire history of bitcoin mining. CPU, GPU and FPGA benchmarks along with published OEM power usage data was used to estimate 2009 to 2012 network average heat rate. ASIC miners announced in 2020 were visualized above and below to show the continued decrease in hash heat rate, but they were discarded from the energy estimations as they are not yet publicly available.

![Image for post](/assets/images/2020/m10/tb9.png)

_Bitcoin mining equipment average yearly heat rate, the inverse of efficiency (j/Th)_

So, now that we have compiled all of the necessary data (yearly hashes and yearly hash heat rate), let’s combine them via an engineer’s attempt at bitcoin mining energy [stoichiometry](https://en.wikipedia.org/wiki/Stoichiometry):

`Yearly Hashes (TH/Year) * Yearly Hash Heat Rate (Joules/TH) = (J /Year)` See Also

`Energy Per Year (Joules/Year) → (kWh/Year) → (TWh/Year)`

Simply multiply the yearly work completed (terahash/year) by the yearly estimated heat rate (in joules/terahash) for miners on the system and you arrive at a joules/year estimation. We will convert from joules/year to kWh/year (a kWh is equal to [3.6 megajoules](https://en.wikipedia.org/wiki/Kilowatt-hour)) and below those yearly energy estimates are charted.

![Image for post](/assets/images/2020/m10/tb10.png)

_Yearly estimates For Bitcoin network energy consumption, in kWh_

However, this physics-based estimation method also has some issues:

*   The quantity of active miners by level of efficiency isn’t known, and this physics-based model assumes equal participation from all miner models available on the market by year released.
*   This model also uses a step function for yearly heat rate data as in input. That yearly data abruptly changes at the first of each year, a gradual heat rate decline would be more realistic as older miners steadily retire and new ones fire up.
*   It assumes old miners retire after a year, which is also unlikely as equipment life cycles are now ranging for two or more years.
*   This is likely to be a lower-bound type of estimation.

## Comparing Different Network Energy Estimations

Where do these yearly energy consumption estimates fall among the previously-cited calculation attempts? Interestingly enough, both of our calculations, even using drastically different methodologies and with all of the shortcomings discussed above — the _economic-based_ estimation (35.3 TWh) and the _physics-based_ estimation (40.17 TWh) — are very similar in value. They also fall within the range of a variety of other popular estimations from noteworthy individuals, entities and institutions shown in the chart below. That all of these estimations are fairly similar in magnitude lends credibility to the various different estimators as well as the wide variety of methodologies and different assumptions used.

_Noteworthy below: it appears that the Bitcoin network hash rate (EH/s) is beginning to decouple from the general yearly energy (TWh/year) estimation trend. This may be due to the decreasing heat rate of SHA-256 ASIC mining equipment if the estimate is physics based, or due to the halving and price stagnation if the estimate is economics based._

![Image for post](/assets/images/2020/m10/tb11.png)

_Bitcoin network hash rate (EH/s) and yearly electrical energy (TWh/year) estimates from various sources_

This chart above shows yearly energy estimation snapshots at time of publishing in TWh/year, but a few of these sources ([University of Cambridge](https://cbeci.org/) \[C-BECI\] and [Alex de Vries](https://digiconomist.net/bitcoin-energy-consumption) \[D-BECI\]) actually publish these yearly estimates on a daily graph going back a few years. This gets back to the previous _energy vs. power_ discussion: logic should prevent plotting yearly energy estimations on a daily axis. 

Regardless, I thought it would be worth comparing these published estimates with our above calculations using more continuous time series data going back to late 2017 (the previous market all-time high). The economic and physics calculations, the [Cambridge](https://cbeci.org/) estimates, as well as [Digiconomist‘s](https://digiconomist.net/bitcoin-energy-consumption/) results are all fairly similar in magnitude over time, again adding some peer review and validity to these different estimation techniques.

![Image for post](/assets/images/2020/m10/tb12.png)

_A yearly energy estimation comparison (TWh/year)_

Our above estimation methodologies appear to align nicely with the other various daily interval yearly energy estimates, so they were averaged together to create a sort of **_Composite Bitcoin Energy Index (CBEI)_** as shown below in TWh/year. Each of these estimations have different assumptions, varying levels and sources of inaccuracy, and thus their composite may be more accurate. This composite of estimations (CBEI) has just recently retested the 60 TWh threshold for total yearly Bitcoin network energy consumption.

![Image for post](/assets/images/2020/m10/tb13.png)

_A yearly energy estimation average, Composite Bitcoin Energy Index (CBEI)_

How does this composite energy index compare to Bitcoin network hash rate over time? The CBEI shows a similar decoupling as hash rate and energy around early 2019 with hash rate continuing to rise and energy consumption staying relatively steady as ASIC heat rates and bitcoin mining incentives have shrunk.

![Image for post](/assets/images/2020/m10/tb14.png)

Interestingly, snapshot bitcoin consumption estimations are commonly extrapolated for an entire year, expressed as an _energy_ value in TWh/Year without supporting time data or evidence. Daily network _power_ estimations would be much preferred to all of these _yearly_ energy consumption estimates plotted on a _daily_ chart. The chart crime in this case is the egregious graphical error that makes folks massively misinterpret the data: yearly energy estimates graphed on a daily axis. So, I took the liberty of converting these daily interval estimates into a daily power estimation chart to correct for these above chart errors that force data misinterpretations.

I present the **_Composite Bitcoin Power Index (CBPI)_** compiled from the [D-BECI and Minimum](https://digiconomist.net/bitcoin-energy-consumption/), [the C-BECI Maximum, Minimum and Estimated](https://cbeci.org/), as well as our above _economics- and physics-based estimates_. 

This CBPI composite estimates for Bitcoin’s instantaneous electrical usage as expressed in _watts,_ the unit of [_electrical power_](https://en.wikipedia.org/wiki/Electric_power)_._ The CBPI peaked recently at nearly 7.58 GW, or about [6 DeLorean time machines](https://en.wikipedia.org/wiki/DeLorean_time_machine) at 1.21 Gigawatts (or should I say [jigawatts](https://en.wikipedia.org/wiki/Talk%3AJigawatt)?).

## CBPI In Context

![Image for post](/assets/images/2020/m10/tb15.png)

Energy values that large are difficult to digest, especially in a yearly context, so let’s put these estimations in perspective with some quick comparisons:

*   650 TWh/year consumed by the banking system
*   200 TWh/year used in gold mining
*   75 TWh/year used on PC and console gaming
*   60 TWh/year on bitcoin mining (CBEI)
*   11 TWh/year used on paper currency and coin minting
*   7 TWh/year used on Christmas lights in the U.S.

![Image for post](/assets/images/2020/m10/tb16.png)

_A comparison of our index to other popular energy usage_ [_estimates_](https://www.coindesk.com/microscope-conclusions-costs-bitcoin)_._

Based on our estimations above, the Bitcoin network consumes roughly 40 to 60 TWh/Year or around 0.15 percent of global yearly _electricity_ generation [(26,700 TWh)](https://en.wikipedia.org/wiki/World_energy_consumption) and only about 0.024 percent of global _total energy_ production [(14,421,151 ktoe)](https://www.iea.org/data-and-statistics/data-tables?country=WORLD). (A [ktoe](https://en.wikipedia.org/wiki/Tonne_of_oil_equivalent) is also a unit of energy: a kiloton of oil equivalent, 11.36 MWh.)

So, Bitcoin energy consumption today is only a very tiny portion of what many consider to be a significant civilization-level problem: ever-increasing human energy consumption. Check out [interesting solutions](https://www.goodreads.com/book/show/892360.The_Problem_of_Increasing_Human_Energy) to this problem outlined a century ago by Nikola Tesla. As recently as September 2020, a [study](https://www.jbs.cam.ac.uk/faculty-research/centres/alternative-finance/publications/3rd-global-cryptoasset-benchmarking-study/) claimed that nearly 76 percent of the Bitcoin network is powered by clean energy sources. Also, remember that once Einstein discovered [mass-energy equivalence](https://en.wikipedia.org/wiki/Mass%E2%80%93energy_equivalence) and humanity harnessed the energy embedded in the atom, energy for the advancement of mankind has become materially abundant.




***

{% include signup.md %}