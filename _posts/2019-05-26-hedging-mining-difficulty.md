---
title: "Hedging mining difficulty"
permalink: "/hedging-mining-difficulty"

author: tamasblummer

tags:
  - Tamas Blummer
  - 2019 Q2
  - Mining
  - Mining Difficulty
  - Difficulty Adjustment

excerpt: Tamas Blummer 

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***


# [Hedging mining difficulty](https://medium.com/@tamas.blummer/hedging-mining-difficulty-42f0f8652d7c)
### By [Tamas Blummer](https://twitter.com/TamasBlummer)
### Posted May 26, 2019

_Future mining difficulty has the most significant impact on mining investment return. I show how to calculate and hedge the associated risk with a fully collateralized Bitcoin bet that requires no 3rd party or oracle._

The times where mining Bitcoin was a fun for geeks is over, long ago. Investment into mining is nowadays rationally evaluated. Those who do it must have good reasons to assume their production costs are competitive and therefore profits are likely. Their cost advantage may come from access to cheap electricity, advanced research and other very unique considerations. There is however a single variable that profoundly influences their profitability, no matter where they work and what cost advantages they secured, the Mining Difficulty.

## Mining Difficulty

The work required to produce a block (aka. Difficulty) adjusts every two weeks such that new blocks will be produced about every 10 minutes in a joint effort of all miner. Re-calibrating to this frequency is crucial to control the inflation rate of Bitcoins, since every new block adds to supply. The approximate number of new Bitcoins within a time frame can therefore be estimated quite precisely even over a longer time horizon using the formulae I collected and derived for you in [this earlier publication](https://medium.com/chainalysis/bitcoin-mining-calculations-ff90dc958dba). For an example: 657,000 Bitcoins are expected to be produced in total within a year from now (May 2019), that is 1800 daily.

The number of Bitcoins a particular miner is expected to earn is proportional to its share of computing capacity within the aggregate capacity of all miner.

The computing capacity of all miner totals today to ~45.6 EH/s. Let us assume that a miner has a production plant with devices of 1 EH/s total computing speed, then that plant is expected to produce around 39.47 Bitcoins today. This income can however not be assumed for many days to come as the aggregate capacity of all miners is expected to change, usually increase with time, at least for advances of technology. The same plant is expected to represent a lower share of aggregate capacity with time and at some time point the market value of daily production will no longer cover the daily operating cost of its devices at which point they will be turned off.

The increase of aggregate capacity has been quite substantial in the past. It was approx. 0.17% on daily basis during the last year. Which is somewhat above the 0.13% implied by [Moore’s law](https://en.wikipedia.org/wiki/Moore's_law). If we assume this rate of increase continues for next year, the example 1 EH/s plant’s daily output will be just 21.4 Bitcoin/day in a year from now and the [production](https://medium.com/chainalysis/bitcoin-mining-calculations-ff90dc958dba) over the year is expected to sum up to around 10,750 Bitcoins.

What if the average daily rate of difficulty increase turns out to be a bit higher next year, let’s say 0.2%? Then the actual production would be sum up to 10,240 Bitcoins. Which means a shortfall of 510 Bitcoins or 5% of expectations.

![](/assets/images/cy19/cy19q2m5/tb1.png)
*Yearly production for varying assumptions for the average daily rate of difficulty increase*

## Actual work performed

The previous estimate used a rate of difficulty increase, that is appropriate for forecast but does not reflect precisely the actual effect of difficulty movements on mining output within a longer period of time on Bitcoin production.

A precise effect of difficulty adjustments can be calculated in retrospect by observing the cumulative work required by the network. The actual production of the miner is proportional to the fraction of work it was able to perform from total required by the network.

The work required to produce a block is proportional to difficulty. The expected number of hashes all miners have to execute until they find a block is Difficulty * 2³² , which is currently ≅ 2.47 * 10²² hashes. These per block requirements, that move with difficulty, add up to a total work requirement over a longer time period.

The Bitcoin Core software reports cumulated work requirement in its log file as log2_work. For the block height 577839 it reports 90.675556 which means Bitcoin required miners to perform 2⁹⁰.⁶⁷⁵⁵⁵⁶ ≅ 1.98*10²⁷ hashes since the creation of the genesis block.

The work that was required over any time interval can be calculated as the difference of total work reported for the last and first block of the period.

## Hedging

Let’s assume a miner would want to buy an insurance against stronger than expected increase of difficulty. Following our example the miner anticipates an average daily difficulty increase of 0.17% for the next year, that would bring log2_work at the end of the year to 91.068.

Provided there is a speculator who would want to take the other side of the bet, they would create two bitcoin transactions:

With the first transaction the miner and speculator would deposit a Bitcoin amount into a joint escrow (multi-sig). The speculator would contribute X Bitcoins, the miner an amount smaller than X that they both agree is the fair price of the insurance.

The second transaction would be time locked such that it can not be included into the blockchain before end of the year, but then allow one of the parties to take the entire escrow amount depending on the level of total work observed by that time point. The miner gets access to the escrowed amount if total work is above the anticipated level, the speculator otherwise.

These set of transactions build a fully collateralized (no counter party risk) bet that requires no 3rd party or an oracle to settle fairly.

For this to be possible a new opcode needs to be added to Bitcoin for which I am drafting a BIP, that will contain also the exact transaction scripts.

The bet entered by miner and investor is a digital call option which is well known in finance, such that pricing the insurance should be possible by both parties.



***

{% include signup.md %}