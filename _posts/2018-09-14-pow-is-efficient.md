---
title: "PoW is Efficient"
permalink: "/pow-is-efficient" 

tags:
  - Dan Held
  - CY18 Q3

excerpt: Dan Held makes the case for PoW being an efficient use of energy. Posted September 14, 2019.

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---


# [PoW is Efficient](https://blog.picks.co/pow-is-efficient-aa3d442754d3)
### By [Dan Held](https://blog.picks.co/@danhedl)
### Posted September 14, 2019

## Foreword
Most people think #Bitcoin's PoW is "wasteful." In this article, I explore how everything is energy, money is energy, energy usage is subjective, and PoW's energy costs relative to existing governance systems. This article is a collection of direct thoughts from many individuals in the space — my value-add was in the aggregation, distillation, and combination of narratives.

## Work is Energy
The idea of "work" being energy started when the French Mathematician [Gaspard-Gustave de Coriolis](https://en.wikipedia.org/wiki/Gaspard-Gustave_de_Coriolis) introduced the idea of energy being "work done." A long time ago, the work done in the economy was entirely human. That work was powered by food.

About a million years ago, humans stumbled across fire. As a result, the energy available to us increased because now we could keep warm not just from what we ate but also from burning. So this added energy usage improved our standard of living.

Some thousands of years ago, our energy usage increased still further when we domesticated animals. Animals could labor in our place. Those new laborers also had to be fed. Large amounts of food were required to meet the energy demand, and our prosperity increased alongside.

In the last few hundred years, we built great machines. Those mechanized machines produced work, first from sources like water & wind, and then the cheaper sources like coal and gas, and now from nuclear sources (fission/fusion). Both machines and nature produce work through the utilization of energy. We have an economy based not on money, but on work and energy.

All things in our lives are closely linked to the price of energy. Purifying water requires energy. Transporting products requires energy. Manufacturing products requires energy. Cooking requires energy. Refrigerators and freezers require energy. In a free market, the cost of any good largely reflects the energy used in producing that good. Because free markets encourage the lowest priced goods, the energy used in producing any good is minimized. Money, which is the representation of the work required to generate goods and services, can also be viewed as stored energy.

![](/assets/images/cy18/cy18q3m9/held-1.png){: .align-center}
_World GDP in 2010$ compared (from USDA) compared to World Consumption of Energy (from BP Statistical Review of World Energy 2014)._

In the early 20th century, industry leaders like Henry Ford and Thomas Edison were interested in replacing gold or the dollar with "the energy dollar" or "units of energy" (commodity/energy currency). The concept was popular due to its sound money characteristics, including: a well-defined unit of account, easy measurement/not easily counterfeited, divisibility into smaller units, and fungibility (that these units would be equivalent to any other unit). However, energy money was flawed — it could not be transmitted or stored easily.


> _"that in order to make a man/woman covet a thing, it is only necessary to make the thing difficult to attain." —_ Mark Twain

Fast forward to October 31, 2008 — Satoshi publishes the Bitcoin whitepaper. Bitcoin's Proof of Work (PoW) was originally invented as a [measure against email spam](https://en.m.wikipedia.org/wiki/Proof-of-work_system). Only later did Satoshi adapt it to be used in digital cash. What PoW mining does under the hood, is use dedicated machines (ASICs) to convert electricity into Bitcoins (via block reward). The machine repeatedly performs hash operations (guesses/votes) until it solves a cryptographic puzzle and receives Bitcoins (block reward). The solution to the puzzle proves that the miner spent energy in the form of ASICs and electricity, a proof that a miner put in work. Bitcoin has a [capitalistic](http://www.truthcoin.info/blog/pow-cheapest/) voting mechanism, "money risked, votes gained" through the energy/ASICs used to generate hashes (votes). — [Hugo Nguyen](https://medium.com/@hugonguyen)

When Satoshi designed PoW, he was fundamentally changing how consensus between humans is formed from political votes to apolitical votes (hashes) via the conversion of energy. PoW is proof of burn, or the validation that energy was burnt. Why is that important? It's the most simplistic and fair way for the physical world to validate something in the digital world. PoW is about physics, not code. Bitcoin is a super commodity, minted from energy, the fundamental [commodity](https://mitpress.mit.edu/books/energy-and-civilization) of the universe. PoW transmutes electricity into digital gold.

The Bitcoin ledger can only be immutable if and only if it is costly to produce. The fact that Proof of Work (PoW) is "costly" is a feature, not a bug. Until very recently, securing something meant building a thick physical wall around whatever is deemed valuable. The new world of cryptocurrency is unintuitive and weird — there are no physical walls to protect our money, no doors to access our vaults. Bitcoin's public ledger is secured by its collective hashing power: the sum of all energy [expended](https://medium.com/@dergigi/bitcoins-energy-consumption-6dd7d7a2e463) to build the wall. And through its transparent costly design, it would take an equivalent amount of energy to tear it down ([unforgeable costliness](http://unenumerated.blogspot.com/2008/08/)).

## Energy Consumption

The cryptopocalypse is coming — Bitcoin's (PoW) is so bad that it's going to destroy the world in 2020! You may have noticed that most of the "doomsday" articles were based on the results of an analysis provided by Alex De Vries, a "financial economist and blockchain specialist" working for PWC Netherlands and author of the site [Digiconomist](https://digiconomist.net/). His estimation has already received a fair share of criticism due to its poor energy consumption calculation. But the KPI of his choosing was intentionally misleading: "the electricity consumption per transaction" for several reasons:

* The energy spent is per block, which can have a varying number of transactions. More transactions does not mean more energy
* The economic density of a Bitcoin transaction is always increasing (Batching, Segwit, Lightning, etc). As bitcoin becomes more of a settlement network, each unit of energy is securing exponentially more and more economic value.
* The average cost per transaction isn't an adequate metric for measuring the efficiency of Bitcoin's PoW, it should be defined in terms of the security of an economic history. The energy spend secures the stock of bitcoin, and that percentage is going down over time as inflation decreases. A Bitcoin "accumulates" the energy associated with all the blocks mined since its creation. [LaurentMT](https://medium.com/@laurentmt), a researcher, has found [empirically](https://medium.com/@laurentmt/gravity-10e1a25d2ab2) that Bitcoin's PoW is indeed becoming more efficient over time: increasing cost is counterbalanced by the even greater increasing total value secured by the system.

Now that we know what the right KPI is for ROI on energy consumption, let's take a look at how energy costs are trending for Bitcoin's PoW.

The rate of ASIC efficiency improvement is slowing. As efficiency gains slow we can expect an increase in manufacturer competition as margins narrow.

![](/assets/images/cy18/cy18q3m9/held2-.png){: .align-center}
[https://cseweb.ucsd.edu/~mbtaylor/papers/Taylor_Bitcoin_IEEE_Computer_2017.pdf_](https://cseweb.ucsd.edu/~mbtaylor/papers/Taylor_Bitcoin_IEEE_Computer_2017.pdf)

![](/assets/images/cy18/cy18q3m9/held-3.png){: .align-center}
[https://research.bloomberg.com/pub/res/d3bgbon7nESTWTzC1U9PNCxDVfQ](https://research.bloomberg.com/pub/res/d3bgbon7nESTWTzC1U9PNCxDVfQ)

All-in mining cost will shift from the upfront accessibility cost of ASIC hardware (capex) to the ongoing energy costs to operate (opex). Since the physical location of mining centers is not important to the Bitcoin network (they are movable), miners flock to areas generating surplus electricity for the lowest marginal costs. In the long-run, this has the potential to produce more efficient worldwide energy markets with Bitcoin miners performing an arbitrage of electricity between global centers. The cost of Bitcoin mining becomes the lowest (excess) value of electricity. This may solve a problem with renewable energy sources that have predictable capacity that is otherwise wasted, like hydro and [flared methane](https://medium.com/nodeblockchain/bitcoin-energy-b230a9d7dd5d). In the future, Bitcoin mining could help with renewable energy sources that have variable output — energy producers can plug in miners, and store the excess power as bitcoin.

Aluminum was a popular means of "[exporting](http://articles.latimes.com/2011/mar/26/business/la-fi-iceland-economy-20110326)" electricity from a country with abundant renewable energy resources that are stranded (ex: Iceland). Smelting bauxite (aka aluminum ore) has huge energy requirements, and converting that into aluminum is a one way function (just like a hash). The same concerns around "unfair" energy consumption existed for aluminum nearly 40 years ago — [1979](https://www.washingtonpost.com/archive/politics/1979/10/29/aluminum-industry-at-center-of-northwests-energy-fight/62fdb02f-ad72-4685-a450-490e12a58059/?noredirect=on&utm_term=.126a3788a2a4) (including concerns of centralization). All of these companies constantly scoured the planet for cheap power and other concessions. As aluminum manufacturing matured over the decades, the kWh per Kg of aluminum produced became more efficient.

![](/assets/images/cy18/cy18q3m9/held-4.png){: .align-center}
[https://www1.eere.energy.gov/manufacturing/resources/aluminum/pdfs/al_theoretical.pdf](https://www1.eere.energy.gov/manufacturing/resources/aluminum/pdfs/al_theoretical.pdf)
> "This global energy net liberates stranded assets and makes new ones viable. Imagine a 3D topographic map of the world with cheap energy hotspots being lower and expensive energy being higher. I imagine Bitcoin mining being akin to a glass of water poured over the surface, settling in the nooks and crannies, and smoothing it out." —[Nic Carter](https://medium.com/@nic__carter)

Bitcoin's PoW is the buyer of last resort for all electricity, creating a floor that incentivizes the building of new energy producing plants around disparate energy sources that would have otherwise been left untapped.

> "When will the energy used for PoW *stop* growing? Precisely when enough energy producers have started doing PoW directly that the marginal return from burning a kWh of energy through PoW = the marginal return from selling that kWh to the grid — when the "premium" on PoW is reduced to zero. I call this equilibrium the "Nakamoto point." I suspect PoW will use between 1–10% of the world's energy when this equilibrium is reached." —[Dhruv Bansal](https://medium.com/@shrubvandal)

Some complain that Bitcoin mining doesn't accomplish "anything useful" like finding [prime numbers](https://en.wikipedia.org/wiki/Primecoin). While introducing a secondary reward for doing the work might seem like a virtuous idea, it actually [introduces a security risk](https://youtu.be/ZDGliHwstM8?t=490). Splitting the reward can lead to a situation where "it's more worthwhile to do the secondary function than it is to do the primary function." Even if the secondary function was innocuous (a heater), instead of an expected $100 per x hashes, we'd move to $100 + $5 of heat per x hashes. The "Mining Heater" is just another increase in hardware-efficiency, resulting in a higher difficulty and an increase in (energy used/block). Luckily, Bitcoin will never have this problem as its security is guaranteed by the purity of its proof-of-work algorithm.

_Note: Bitcoin is already doing something immensely useful for society (mining wouldn't be profitable if it wasn't), and it isn't rational to ask miners to perform a function that is altruistic without incentives._

## Relative Costs

Everything requires energy (first law of thermodynamics). Claiming that one usage of energy is more or less wasteful than another is completely subjective since all users have paid market rate to utilize that electricity.

> "If people find that electricity worth paying for, the electricity has not been wasted. Those who expend this electricity are rewarded with the bitcoin currency." —[Saifedean Ammous](https://medium.com/@saifedean)

In thermodynamics, the universe is the ultimate closed system. Bitcoin's utilization of the excess electrical capacity consumes magnitudes less electricity than existing fiat systems which not only have power requirements banking infrastructure, but the military and political machina. The energy tradeoff for the utilization of that electricity to secure the financial system backbone is a "net positive" outcome. Below I make a rough comparison to the existing financial, military, and political systems (notes are at the bottom of the article)

![](/assets/images/cy18/cy18q3m9/held-5.png){: .align-center}

## Type I Civilization

In the hunt for cheap energy sources, we will unlock greater economic abundance in the real world. Bitcoin, through the harnessing of these new or disparate energy sources, not only moves us forward to a Kardeshev Type I economy but may bring us closer to a Kardeshev Type I energy civilization (We're ~ 0.72 on the Kardashev Scale). With Bitcoin mining as an incentive, it may shrink the time we get to T1 from 200 years to less than a few decades. After reaching Type I status, there is less of a need to restrict the growth of energy consumption, which increases the standard of living for everyone.

![](/assets/images/cy18/cy18q3m9/held-6.png){: .align-center}

The pressure to find cheap electricity sources will accelerate the effort to build fusion reactors. Nature is showing the way, powering the whole universe with nuclear fusion (stars). Humans are in the process of emulating nature by building fusion reactors. It is estimated that it will take ~ $80B in research over decades to finally unlock nuclear fusion. The fuel for fusion (primarily deuterium) exists abundantly in the Earth's ocean which could potentially supply the world's energy needs for millions of years. Fusion power has many of the benefits of renewable energy sources, such as being a long-term energy supply and emitting no greenhouse gases or air pollution. Fusion could provide very high power-generation density and uninterrupted power delivery. Another aspect of fusion energy is that the cost of production does not suffer from [diseconomies of scale](https://en.wikipedia.org/wiki/Diseconomies_of_scale). The cost of water and wind energy, for example, goes up as the optimal locations are developed first, while further generators must be sited in less ideal conditions. With fusion energy, the production cost will not increase much even if large numbers of stations are built, because the raw resource (seawater) is abundant and widespread.

> "Water, water, everywhere, Nor any drop to drink." — Samuel Taylor Coleridge

Fusion power and other cheaper energy sources will solve major problems for humanity like [fresh water shortages](https://en.wikipedia.org/wiki/Water_resources). We are surrounded by seawater, but desalination stations, which remove salt from the seawater, require large amounts of energy. Costs of desalinating seawater are currently higher than freshwater, groundwater, water recycling, and water conservation.

Humankind's will to explore, up the mountains, down to the sea floors, to the heart of the atom, to the very fabric of space-time; to grow, not be stifled by a limit to energy. We will reach for the stars.

**Is the trustless** [**settlement**](https://twitter.com/nic__carter/status/1028698889153593344) **of $1.34T between counterparties annually with the added benefit of cheaper energy for all, worth the $4.5B in current mining costs? I think the answer is a resounding yes.**

If you enjoyed reading this please:

1/ Follow me on [Twitter](https://twitter.com/danheld).

2/ Sign up for my [weekly newsletter](https://goo.gl/forms/UUrEnbKDaOhZnki02) which contains my distilled thoughts of the week

3/ Check out my other articles 👇
* [**Planting Bitcoin** _Sound Money (sanum pecuniam)_ medium.com](https://medium.com/@danhedl/planting-bitcoin-56bd1459cb23 "https://medium.com/@danhedl/planting-bitcoin-56bd1459cb23") 
* [**Bitcoin's Distribution Was Fair** _ Debunking FUD_ blog.picks.co](https://blog.picks.co/bitcoins-distribution-was-fair-e2ef7bbbc892 "https://blog.picks.co/bitcoins-distribution-was-fair-e2ef7bbbc892") 
* [**Hodlers are the revolutionaries** _My reflections on the important role hodlers play in developing Bitcoin's network (and other cryptocurrency networks)._ tokeneconomy.co](https://tokeneconomy.co/hodlers-are-the-revolutionaries-66c8362ef9eb "https://tokeneconomy.co/hodlers-are-the-revolutionaries-66c8362ef9eb")

Notes:

* All costs are in USD
* "Governments" are the total annual expenditures including military spending
* In 2006, the DoD [used](https://en.wikipedia.org/wiki/Energy_usage_of_the_United_States_military) almost 30,000 gigawatt hours (GWH) of electricity, at a cost of almost $2.2 billion
* Global military [spending](https://www.sipri.org/media/press-release/2018/global-military-spending-remains-high-17-trillion) annually is ~$1.7T
* Initial [research](https://drive.google.com/file/d/1TIma781rLFjr-dqeJmL2KN06OpoRkSsj/view) this analysis was based on
* Gold mining, banking system, gold recycling costs are all estimates from 2014
* Banking system and government estimates are a combination of annual expenses which includes electrical cost
* US energy [usage](https://www.americangeosciences.org/critical-issues/faq/how-much-worlds-energy-does-united-states-use) as % of world
* US federal government energy [expenditures](https://www.eia.gov/todayinenergy/detail.php?id=19851)
* Bitcoin Mining [Costs](https://docs.google.com/spreadsheets/d/e/2PACX-1vTL1a6Nn0RPgNRAruJh1tkgdntFP3D9LXkaHbyegXONaaOU5agCc2DwN42ppAHk57NnC3vhEuWESEZ7/pubhtml?gid=108252637&single=true)
* $63.8B a year is spent on electricity alone for the banking system
* Bitcoin has had 0 recorded worker deaths, whereas gold has had 50,000 recorded deaths over the last 100 years
* Inflation for fiat currency has been approximately 2–3% annually which is a stealth tax that erodes savings. The costs are enormous to calculate and are not included
* Bitcoin isn't issued by a government, there is little to no corruption involved in distribution
