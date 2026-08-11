---
title: "The Hashing Heart Attack"
permalink: "/the-hashing-heart-attack"

author: paulsztorc

tags:
  - Paul Sztorc
  - 2015 Q4
  - Mining
  - Economics
  - Inflation

excerpt: The Hashing Heart Attack. Posted October 28, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Hashing Heart Attack](http://www.truthcoin.info/blog/mining-heart-attack)
### By [Paul Sztorc](https://twitter.com/truthcoin)
### Posted October 28, 2015

Special thanks to Marshall Long, Greg Maxwell, Mark Freidenbach, and Adam Back for related discussion.

### The Problem

This issue is one which *might disable Bitcoin completely*, requiring a (simple) hard fork to get it “unstuck”. This issue becomes more dangerous over the next 20-30 years (likely most dangerous in 2020-2028), but then quickly declines.

I’ll break it into two subproblems:

#### SubProblem 1: The blockreward halving instantly cuts miner revenues by a huge fraction.

Of course, this assumes [1] that transaction fees are negligible and [2] the Bitcoin exchange rate never increases in response to the difficulty halving.

Transaction fees are currently around 1% of miner-revenues, and no one expects this proportion to significantly increase anytime soon. Even if transaction fees were 50% of revenues (wildly optimistic), the reward-halving would still cut total revenues by (1/4), a sizable proportion.

The Bitcoin exchange rate ([important to miners](https://blockchain.info/charts/miners-revenue?timespan=all&showDataPoints=false&daysAverageString=1&show_header=true&scale=0&address=)) shouldn’t change in response to the difficulty halving, at all. By [Weak Efficient Markets](https://en.wikipedia.org/wiki/Efficient-market_hypothesis), anyone who believes that “the USD/BTC price will imminently double”, should be buying immediately (and bidding up the price). I’ve previously written that, [because of “saturation”, Bitcoin might have some immunity to the EMH](http://www.truthcoin.info/blog/deflation-the-last-word/#the-long-run-belongs-to-the-best-savers), but (like all EMH-resistance) this immunity is constantly hard at work, canceling itself out.

![](/assets/images/2015/m10/the-hashing-heart-attack1.png)

Figure. On the left, the reward-halving dominates the block-reward; on the right, transaction-fee variance dominates.

#### SubProblem 2: The difficulty adjustment process causes miner homogeneity.

Every two weeks, the total costs of mining (namely, the difficulty) reset such that the average miner achieves an expected [economic profit](http://www.investopedia.com/terms/e/economicprofit.asp) of zero. Those in the bottom half can no longer afford to operate, and they (eventually) switch their miners off and drop out of the system.

Of course, this is an academic simplification of actual mining. It ignores [1] uncertainty (in all factors) and [2] ‘permanent advantages’ (“free” power, geographic distribution of energy sources, ASIC engineering secrets), but those artifacts merely slow the inevitable: this is an ever-present, fundamentally underlying process of filtration.

As the lower-quality miners get filtered out, [the filter reacts to the increase in quality](https://en.wikipedia.org/wiki/Red_Queen_hypothesis) by becoming more intense. Eventually, only a few top quality miners will remain. These miners might follow *different* best-practices (all the solar-power miners might have a different set of best practices than the hydro-power miners), but **all miners should eventually have tiny, and equal economic profit margins**.

![](/assets/images/2015/m10/the-hashing-heart-attack2.png)

Because an average is just a single number, it necessarily contains less total information than the distribution from whence it came.

#### Combined

The problem is when these two effects happen at the same time.

![](/assets/images/2015/m10/the-hashing-heart-attack3.png)

In short, we will reach a day when all miners have small profit margins, and then a blockreward-halving will slash their revenues in half. **The result will be that not half, but *all* miners will shut off their mining rigs.**

You see, the difficulty won’t re-adjust (decrease) until (on average) 1008 blocks later. (In fact, we always [know exactly](http://bitcoinclock.com/) the number of blocks.) So, even miners who plan to turn their mining rigs back on, post-difficulty-decrease, would have them off for this brief unprofitable period.

The problem is that it might not be brief. The difficulty adjustment period, which would normally last two weeks, is counted in *blocks*, not human-time. So it could actually last forever.

(Or, until someone manually hard-forked the network [to something with 60% difficulty], thus giving the stalled engine a jump.)

But that’s not all: even if most of the miners stayed on, the resulting uncertainty (or merely the increase in confirmation times) might cause a Bitcoin currency crisis. Abnormal tx-fee and exchange-rate volatility would increase Bitcoin’s risk premium, harming Bitcoin’s value-proposition as money. One example: were the USD/BTC price to fall by half, the blockreward-halving would have an effect more-resembling a blockreward-*quartering*. A falling USD/BTC price widens the gulf between mining costs and revenues, and makes the problem *even worse*, potentially resulting in a death spiral.

In the near term, miners are different enough (and the exchange rate is already volatile enough) such that most will survive the halving, and in the long term, Bitcoin might be sufficiently important such that transaction fees simply increase (in step with the higher confirmation times) to offset the problem. However, in the medium term, namely the year 2020, it is potentially disastrous.

### Solution

#### What Won’t Work

##### Do Nothing

We might hope that miners, out of the kindness of their hearts, would simply keep mining (at a loss) to prevent Bitcoin from dying (and prevent their specialized hardware from depreciating to zero).

This isn’t acceptable to me - in equilibrium, miners consume all of their BTC revenues (which are all spent on operating or capital costs), and it is easy to imagine miners who plan their capital investments to align with the 4 year Bitcoin halving cycle (“we’re going to run these into the ground until the reward halves, and then replan from there”). Mining hardware itself rarely lasts longer than 2 years, anyway.

The cost of altruistic mining can be roughly estimated. Currently, miners collectively earn 2016*25*300 = over $15 million dollars in revenue each difficulty cycle. These inputs might all change, of course, but, if they didn’t, the 2016 halving would slash this revenue by over $7,000,000. If miners were already running at cost, this 7M figure is the cost of keeping 10 minute blocks. Worse still, such altruism would *prevent* the subsequent difficulty adjustment from being representative; miners would only keep themselves trapped in Altruism Prison, losing money the whole time.

Moreover, “we” are increasingly unable to “help” the miners…ongoing professional hardware-specialization makes our “civilian hardware” (home PCs, phones) overwhelmingly irrelevant.

##### Upon Each Blockreward Halving, Also Halve the Difficulty

Clearly the intent was to cut profits in half, not revenues. Unfortunately, there’s no clear way for the protocol to learn about miner’s profit margins.

One (hard fork) idea is to simultaneously halve the difficulty (with the reward); this *might* work, but instead it might simply delay the problem for 2016 blocks (which might all mined in one week, instead of two), at which point the difficulty would double…landing us right back where we started. If ‘halving the difficulty’ perfectly halved the total costs of mining (including overhead and labor), and the blockreward perfectly halved the revenues (ie, transactions fees were nonexistent and the exchange rate never changed), then it might work, but difficulty has a stronger relationship with **time** than it does with cost (and revenues are driven mostly by Bitcoin’s exchange rate).

![](/assets/images/2015/m10/the-hashing-heart-attack4.png)

It seems that there’s only one way to guarantee that the problem be removed.

#### Smooth the Disinflation Out

The only ironclad solution is to replace the sudden halving of the Bitcoin coinbase with a continuous, gradual decrease.

Something like this:

![](/assets/images/2015/m10/the-hashing-heart-attack5.png)

Where r refers to the quantity of BTC released per block, t refers to the block number (ie, “time”), and lambda is some parameter. (Little t is used to index on r, but big T refers to the actual number itself).

##### Fork Types

This can be done either with a hard fork or with a soft fork.

While any hard fork can replace one issuance policy with another, a soft fork must obey the original issuance rules. This can be done by storing coins in a kind of “softfork reserve account”, with special rules allowing only *future* block-finders to withdraw. Because the bank can never have a negative balance under soft fork, such a change would involve some sacrifice on the part of the miners (they’d be losing coins that they’d otherwise be able to keep). A hard fork, freed from the original rules, can reduce this problem.

##### Details

I did some [preliminary Excel math](http://www.truthcoin.info/images/impact-of-reward-change.xlsx) to take a first look at the potential issuance schedule and its effect on miners. This analysis is oversimplified (a year spans just a single row, instead of 6*24*365 = 52,560 rows), and I would (obviously) improve it before making a formal proposal. The specific numbers are, of course, irrelevant; only the concepts are relevant.

.

Original

Hard Fork

Soft Fork

Lambda (Annual)

N/A

.012

371160

.012

166134

PV Impact (BTC, at 5%)*

N/A

-81,442.1

-119,080.3

BTC in Year 2168

21,038,400.0**

21,038,399.7

20,973,054.6

*Obviously, I used math to minimize this value in each case. **This value is not 21 million, because of leap years (and other simplifications, which are consistent across scenarios). So, “Hard Fork” is accurately recreating “Original” (and not a second error).

![](/assets/images/2015/m10/the-hashing-heart-attack6.png)

![](/assets/images/2015/m10/the-hashing-heart-attack7.png)

The soft fork eventually starts accumulating larger-and-larger proportions of tinier-and-tinier blockrewards, such that ~65,000 BTC remain trapped in the bank forever.

##### Costs

Most of the damage (~ 81/119 ~= 68%) is done whether the fork is soft or hard.

This damage (the cost to miners, of loaning these coins to the bank without compensation) would be substantial: at a market price of $250/BTC, the 119K BTC are worth nearly $30,000,000 USD.

Of course, mining revenues are mostly driven by the exchange rate itself, so we have to weigh this cost against any BTC appreciation that might occur as a result of this change.

##### How the Soft Fork Might Work

As mentioned, the soft fork would still allow miners to “mine” 25 BTC per 10 minutes. Some portion of these 25 would simply be ‘frozen’ (metaphorically, they would be “placed” into a “miner-bank”).

We might require the “bank” to be an [‘ANYONE-CAN-SPEND’](https://en.bitcoin.it/wiki/Script#Anyone-Can-Spend_Outputs) BTC address, yet with miners enforcing a pre-specified policy for spending from this address. Later, when someone mines a block that needs to ‘withdraw’ from the bank (during the 2020-2038 years, where the smooth curves are above the blue jagged line) the refined protocol can simply agree to allow a certain number of BTC to be transferred from this address to anywhere (knowing that the winning miner will give it to him or herself).

This would be the first soft fork which is not obviously a [Pareto improvement](https://en.wikipedia.org/wiki/Pareto_efficiency): it harms a subset of individuals (the miners) –if we neglect to consider that miners would also be harmed by Bitcoin’s collapse as a result of this unfixed problem. This is particularly interesting because miners are the very group which turn soft forks on and off. At around year 2020, the ANYONE-CAN-SPEND address will have accumulated over 450,000 BTC (today, worth over $120 million).

To prevent an interesting situation might emerge where miners attempt to raid those funds, possibly by bribing users to upgrade their software, or by lobbying in some other way, notice:

1. Regular users would almost certainly have upgraded their software by then (making this a little more like a hard fork).
2. An un-forked block is too valuable for its own good. Worth more than surrounding blocks by a factor of 72,000 ( = 450,000/6.25), The Block that rewards all these coins would be fought over endlessly (as new miners will most certainly jump online to mine this single block, and then refuse to participate in a chain that does not allow them to win). So, threats to start a fight aren’t very credible.

#### How did this happen?

It seems strange to see a design flaw in Bitcoin, something which was otherwise so perfectly-crafted. I’m inclined to think that the inherent fairness of the static “50 BTC per block” appealed to Satoshi; that he anticipated a great deal of criticism off the bat, and didn’t want to be hearing “I don’t want to join this! You’ve already started mining and got all the easiest blocks for yourself!”.

And, it certainly is easier to explain “you get 50 of them with each block, but this number drops by half every four years” than it is to say “ ‘a formula’ determines how many BTC you get”.

Or, [perhaps I have misunderstood](http://imgur.com/t2sfuot)? What do you think?

zzz The source of the flaw (and other "difficulty oscillation") is really the clunky 2 week difficulty adjustment, which, by definition, can only forecast 2 weeks into the future, using data from 2 weeks in the past. the difficulty adjustment *had* to be a little clunky, because of the way that Satoshi measured "time".

Add Disqus comments.

comments powered by

Disqus

***

{% include signup.md %}
