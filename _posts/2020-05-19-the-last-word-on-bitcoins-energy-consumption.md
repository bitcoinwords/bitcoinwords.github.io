---
title: "The Last Word on Bitcoin’s Energy Consumption"
permalink: "/the-last-word-on-bitcoins-energy-consumption"

author: niccarter

tags:
  - Nic Carter
  - 2020 Q2
  - Energy
  - Mining
  - Environmental
  - Energy Consumptions
  - Proof of Work

excerpt: Nic Carter looks at the state of Bitcoin mining and the energy mix used for hash generation. Posted May 19, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Last Word on Bitcoin’s Energy Consumption](https://www.coindesk.com/the-last-word-on-bitcoins-energy-consumption)
### By [Nic Carter](https://twitter.com/nic__carter) on [Coindesk](https://www.coindesk.com/the-last-word-on-bitcoins-energy-consumption)
### Posted May 19, 2020

**CoinDesk columnist Nic Carter is partner at Castle Island Ventures, a public blockchain-focused venture fund based in Cambridge, Mass. He is also the cofounder of Coin Metrics, a blockchain analytics startup.**

Much ink has been spilled on the question of Bitcoin’s energy footprint. But amid the clarifying details and the energy mix calculations we have lost sight of the most important questions. Anyone who wades into this muddy debate must consider the fundamentals before making a final assessment.

## Energy: a local phenomenon

Let’s start with the basics. Many people, when decrying Bitcoin’s energy footprint, point out its energy consumption and presume that someone, somewhere is being deprived of electricity because of this rapacious asset. Not only is this not the case, but Bitcoin’s presence in many jurisdictions doesn’t affect the price of energy at all because the energy there isn’t actually being used. How could this be?

The first thing to understand is that energy is not globally fungible. Electricity decays as it leaves its point of origin; it’s expensive to transport. Globally, about [8 percent](https://data.worldbank.org/indicator/EG.ELC.LOSS.ZS) of electricity is lost in transit. Even high-voltage transmission lines suffer “line losses,” making it impractical to transport electricity over very long distances. This is why we talk about an energy grid — you have to produce it virtually everywhere, especially near to population centers.

When you consider Bitcoin’s energy intake, interesting patterns emerge. New data from the [Cambridge Center for Alternative Finance](https://cbeci.org/mining_map) has confirmed what we effectively already knew: China is the epicenter of Bitcoin mining, with specific regions like Xinjiang, Sichuan and Inner Mongolia dominating. With the cooperation of mining pools, the Cambridge researchers were able to geolocate the IPs of a sizable fraction of active miners, creating a novel dataset giving us new insight into Bitcoin’s energy mix.

And the results are revealing: Sichuan, second only in the hashpower rankings to Xinjiang, is a province characterized by a massive overbuild of hydroelectric power in the last decade. Sichuan’s installed hydro capacity is [double what its power grid can support](https://www.reuters.com/article/us-china-hydropower/dam-nation-big-state-projects-spared-in-chinas-hydro-crackdown-idUSKCN1LF2RG), leading to lots of “curtailment” (or waste). Dams can only store so much potential energy in the form of water before they must let it out. It’s an open secret that this otherwise-wasted energy has been put to use mining Bitcoin. If your local energy cost is effectively zero but you cannot sell your energy anywhere, the existence of a global buyer for energy is a godsend.

There is historical precedent for this phenomenon. Other commodities have been employed to export energy, effectively smoothing out ripples in the global energy market. Before Bitcoin, aluminium served this purpose. A huge fraction of aluminum’s embodied cost is the cost of electricity involved in smelting bauxite ore. Because Iceland boasts cheap and abundant energy, in particular in the form of hydro and geothermal, smelting bauxite was a natural move. The ore was shipped from Australia or China, smelted in Iceland and shipped back to places like China for construction.

**_See also: [Bitcoin Miners, US Energy Producers and Moore’s Law](https://www.coindesk.com/bitcoin-mining-energy-producers-moores-law-and-a-new-class-of-bitcoin-miners)_**

This led to an Icelandic economist [famously stating](https://www.latimes.com/business/la-xpm-2011-mar-26-la-fi-iceland-economy-20110326-story.html) that Iceland “export[s] energy in the form of aluminum.” Today, Iceland is hoping it can replicate this model with the [export of energy via data storage](https://www.technologyreview.com/2012/04/11/186812/iceland-exports-energy-as-data/). This is why smelters are located in places where electricity is abundant, and where the local consumers may not be able to absorb all that capacity. Today, many of these smelters have been converted into Bitcoin mines – including an old Alcoa plant in upstate New York. The historical parallels are exquisite in their aptness.

> ULTIMATELY IT’S JUST A MATTER OF OPINION AS TO WHETHER THE EXISTENCE OF A NON-STATE, SYNTHETIC MONETARY COMMODITY IS A GOOD IDEA.

So to sum up, part of the reason Bitcoin consumes so much electricity is because China lowered the clearing price of energy by overbuilding hydro capacity due to sloppy central planning. In a non-Bitcoin world, this excess energy would either have been used to smelt aluminum or would simply have been wasted.

My favorite way to think about it is as follows. Imagine a topographic map of the world, but with local electricity costs as the variable determining the peaks and troughs. Adding Bitcoin to the mix is like pouring a glass of water over the 3D map – it settles in the troughs, smoothing them out. As Bitcoin is a global buyer of energy at a fixed price, it makes sense for miners with very cheap energy to sell some to the protocol. This is why so many oil miners (whose business results in the production of lots of waste methane) have [developed an enthusiasm](https://trib.com/business/energy/the-unlikely-marriage-of-cryptocurrency-and-crude/article_b6e3fd6c-e485-5e22-9a16-3e292dc79cfc.html) for mining Bitcoin. From a climate perspective, this is actually a [net positive](https://bitcoinmagazine.com/articles/oil-field-alchemy-how-bitcoin-can-turn-waste-emissions-proof-work). Bitcoin thrives on the margins, where energy is lost or curtailed.

## It’s about the energy mix

Another common mistake energy detractors make is to naively extrapolate Bitcoin’s energy consumption to the equivalent CO2 emissions. What matters is the type of energy source being used to generate electricity, as they are not homogenous from a carbon footprint perspective. The academic efforts that get breathlessly reported in the press tend to assume either an energy mix which is invariant at the global or country level. Both [Mora et al](https://www.nature.com/articles/s41558-018-0321-8) and [Krause and Tolaymat](https://www.nature.com/articles/s41893-018-0152-7) generated flashy headlines for their calculations of Bitcoin’s footprint, but rely on naive extrapolations of energy consumption to CO2 emissions.

Even though lots of Bitcoin is mined in China, it’s not appropriate to map China’s generic CO2 footprint to Bitcoin mining. As discussed, Bitcoin seeks out otherwise-curtailed energy, like hydropower in Sichuan, which is relatively green. Any reliable estimate must take this into account.

## Silver linings

The prospects look even sunnier when you consider the changing nature of Bitcoin security spend. Eighty-seven percent of Bitcoin’s terminal supply has been issued already. Due to the path Bitcoin’s price took during the heavy-issuance phase, miners will have been collectively rewarded just over $17 billion in exchange for finding those coins (assuming simply that they sold their coins when they mined them), even though the coins are worth $160 billion today. This is because most of those coins were issued at cheaper price points.

If Bitcoin ends up being worth substantially more in the future than it is worth today (say, by an order of magnitude), then the world will actually have received a discount on its issuance. The energy-externality of pulling those Bitcoins out of the mathematical ether will actually have been very low, due to the historical contingency of when, price-wise, those Bitcoins were actually mined. In other words: Bitcoin’s energy expenditure may end up looking rather cheap in the final analysis. Coins only need to be issued once. And it’s better for the planet that they be issued when the coin price was low, and the electricity expended to extract them was commensurately low.

**_See also: [Bitcoin Halving 2020: How the World’s Largest Mining Pool Is Helping Miners ‘De-Risk’](https://www.coindesk.com/bitcoin-halving-2020-how-the-worlds-largest-mining-pool-is-helping-miners-de-risk)_**

As any Bitcoin observer knows, issuance as a driver of miner revenue will decline with time. Last week’s halving cut the issuance side of miner revenue by half. If I had to make a guess, Bitcoin’s periodic halvings will at least offset its appreciation long term, making runaway growth in security spend unlikely. Fees will necessarily grow to account for a much larger fraction of miner income. Fees have a natural ceiling to them, as transactors must actively pay them on a per-transaction basis. If they become too onerous, users will look elsewhere, or economize on fees with other layers that periodically settle to the base chain.

Thus it’s unlikely that security spend results in the world-eating feedback loop that has been posited in the popular press. In the long term, Bitcoin’s energy consumption is a linear function of its security spend. Like any other utility, the public’s willingness to pay for block-space will determine the resources that are allocated to providing the service in question.

## Is it worth it?

Now, despite all the caveats listed above, it’s undeniable that Bitcoin not only consumes a lot of energy but produces externalities in the form of CO2 emissions. This is not under debate. What Bitcoiners are often confronted about is whether Bitcoin has a legitimate claim on _any _of society’s resources. This question relies on a kind of utilitarian logic about which industries should be entitled to consume energy. In practice, no one actually reasons like this. The Bitcoin-energy supplicants are mum when it comes to the energy used to illuminate Christmas lights, to power the data centers behind Netflix or to distribute untold millions of single-serve meal kits. It’s clear that because Bitcoin’s footprint is so easy to quantify — and an object of revulsion among the chattering classes — it is singled out for special treatment.

Ultimately it’s just a matter of opinion as to whether the existence of a non-state, synthetic monetary commodity is a good idea. The truth is that blockspace is a service which is paid for, and that’s where its resource cost is derived. Something duly purchased cannot, by definition, be a waste. Its buyer derives benefit from its existence, regardless of anyone else’s subjective opinion of the merit of the transaction. These same arguments have been made countless times about [perceived “costs” of the gold standard](http://webhome.auburn.edu/~garriro/g4gold.htm), and rebutted on similar grounds before. Fundamentally, millions of individuals the world over still value physical, bank-independent savings, so it still gets pulled out of the ground with regularity. As long as people value Bitcoin, so, too, will the block-space auction continue in perpetuity.

The Bitcoin-energy worriers need not despair, however. There is a solution. All they must do is persuade Bitcoin fans to use and value an alternative settlement medium. Their best bet will be to devise a system that is even more secure, offers stronger assurances, settles faster, is more privacy preserving and is more censor resistant – all without using Proof-of-Work. Such a system would be miraculous. I’m waiting with bated breath.

_**NOTE: The paragraph beginning “Now, despite all the caveats listed above..” has been updated.**_

***

{% include signup.md %}