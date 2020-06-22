---
title: "The State vs. Bitcoin"
permalink: "/the-state-vs-bitcoin"

author: stevebarbour

tags:
  - Steve Barbour
  - 2020 Q1
  - Censorship
  - Mining
  - The State
  - Censorship Resistance
  - Privacy
  - Security
  - Sovereignty
  - Politics

excerpt: Steve Barbour shares an essay that examines Bitcoin's resistance to the State. Posted March 15, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***


# [The State vs. Bitcoin](https://medium.com/@stevegbarbour/the-state-vs-bitcoin-dbc044f23ea6)
### By [Steve Barbour](https://twitter.com/SGBarbour)
### Posted March 15, 2020

## – The sustainability of censorship resistance –

**_Foreword_**_: As with freedom and oppression, Bitcoin and State money may exist in a perpetual tug of war between ideals. Where State money relies on compulsory participation, Bitcoin offers completely voluntary entry and exit and thus represents the antithesis of State money. In this essay I will explore the mechanisms in which Bitcoin may resist State attack._

### **Notes to the reader:**

> · The term ‘Bitcoin’ with a capital ‘B’ refers to the Bitcoin network or economy, while the term ‘bitcoin’ refers to the unit of money.
> 
> · Please refer to the definitions section at the end for clarifications

![](/assets/images/2020/m6/sb1.png)

## **Introduction**

Bitcoin’s ability to resist censorship has a necessary security assumption in that honest mining is more profitable than dishonest mining [^sb1]. For this to hold true censorship must meet adequate resistance by the honest economy to ensure that dishonest behavior and censorship is not sustainable. This may be achieved by depleting the attacker’s investment capital by either minimizing their mining reward or maximizing their mining cost. While it is not possible to prove one way or another whether dishonest mining can be overcome, we will outline some of the factors that may give honest miners an edge to resist censorship and support the sustainability of honest mining.

## **Bitcoin**

Bitcoin is engineered money. Its design is unique in that any interested participant is able to join and leave consensus [^sb2] on a voluntary basis without having to receive permission from any authority. It offers superior monetary properties over legacy State monies. For example, bitcoins are impossible to counterfeit or arbitrarily debase and are very difficult to confiscate. There is no other money today that offers such freedom, so it’s no surprise there are many people interested in protecting its value proposition, though others feel threatened by it.

Sound engineering must consider not just steady state conditions, but also the upset conditions. A properly designed system must anticipate the unlikely but catastrophic scenario and build in appropriate safety factors to prevent disaster. A bridge may average fifty vehicles crossing at any given time but it still must be designed for many hundreds of vehicles stuck bumper to bumper in traffic, or for the thousands of pedestrians who may congregate. We cannot afford to have the bridge collapse and kill everybody when an upset condition rears its ugly head.

As engineered money, what exactly are the upset conditions in which Bitcoin was designed to mitigate? What are the worst case scenarios with the greatest impact? Is Bitcoin engineered to resist catastrophe?

## **Censorship Threats**

A bitcoin miner may gain a majority of the network hashrate at any given time, given enough external capital investment. If a single bitcoin miner, or a colluding cartel of smaller miners, gain over 50% of the total network hashrate then they become the network majority and gain the option to censor the network completely.

A majority miner may choose to censor in the following ways:

1.  Deny blocks and block rewards to the minority miners
2.  Deny merchant transactions and fees
3.  Reorganize history and attempt double spends

A majority miner may simply choose to mine honestly rather than upset the integrity of the network with censorship, but how would you even know if a majority miner existed? It is trivial for a miner to hide their hashrate among many different pools or to solo mine. Mining is by nature and necessity anonymous, so the possibility of a majority miner persists as an ever present threat to network trade.

Possibly most concerning to some is the fact that each of these methods of censorship represents _valid_ behavior which no bitcoin node on the network would reject. There is no state, now or in the future, in which the risk of censorship can be eliminated altogether, but it can be resisted.

## **Denials of Service**

There are plenty of good reasons that we could consider as to why a majority miner might decide to stay honest but we will not be contemplating them here. Instead we will assume a majority hashrate, once achieved, will attempt to upset the economy in the most disruptive manner possible. This is the upset condition that the network must resist and may indeed be the censor’s objective. Let’s explore the censorship threats listed above.

### 1. **Deny block rewards**

A majority miner may choose to build selfishly on top of his own blocks and to exclude any of the honest miners’ blocks from the strongest chain. This means the dishonest majority would be censoring all competing hashrate, earning 100% of all block rewards while the rest of the honest minority would earn nothing. This could be achieved with even a simple majority of 51% of network hashrate. In such a case any honest blocks that are mined on the network would lose the race to the majority miner and go stale, thus wasting the energy and capital consumed by the honest minority. The majority would have complete control and have the ability to tax the minority miners up to and including 100% of the block reward. To resist censorship the honest minority must either increase their hashrate to overtake the censoring majority or they must reduce it in order to preserve their capital and live to fight another day.

It is notable that the censor may choose to tax honest miners less than 100% and to allow some arbitrary percentage of honest blocks to confirm. Doing so may be in an effort to enforce a white market mining regime under a State mandate, where a tax is enforced on the economy. This may seem far-fetched but the reality is this is what the State does today; they do not tax 100% as that would invariably kill the economy and likely spark a revolt. The parasite does not want to kill its host.

### 2. **Deny trade**

Majority hashrate also gives the censor the ability to choose which UTXOs are allowed to move with a white list or a black list. The censor could also arbitrarily tax merchants by increasing the minimum fee levels to confirm their transactions. Any honest minority blocks that allow a low fee to confirm could be made stale by the censor. The censor could also decide to only allow a white-list of transactions through, presumably a list of UTXOs in which the owner has passed through a proper KYC process mandated by the State. This may be a State objective [^sb3] as a mechanism to control the money and enforce a ‘Statecoin’.

The worst case scenario for merchants is the majority censor could ban trade altogether and mine empty blocks exclusively. This would be a complete denial of service attack on merchants and the Bitcoin network in general, not allowing any trade to occur on the network at all. The downside of such an attack for the majority miner is that they would not be earning any transaction fees and the fee pressure supporting honest miners, discussed later, would increase substantially. Such behaviour would absolutely require an external subsidy, which only the State could provide by consuming taxes brought in externally from increased taxation or seigniorage.

### 3. **Double Spend**

A majority miner can not only keep people from participating, but they can also trick them into believing their transactions have settled, opening up an opportunity to steal from them.

If a majority miner has enough of a hashrate advantage over the minority of honest miners then they can mine on top of previously confirmed blocks in which transactions have previously settled. In doing so they can mine a new chain in secret and reveal the chain to the network once they surpass the tip of the chain of the honest minority, which ‘resettles’ previously confirmed transactions. If the majority miner had made a transaction that was confirmed in the chain tip that gets resettled then they can re-spend their coins again on the newly mined chain causing the merchant who accepted their coins originally to lose the balance. The end result is the merchant had sold their goods in return for coins that disappear — a theft.

Double spend behavior, while theft, is _valid_ behavior and even anticipated by the system [^sb4]. The network has no choice but to accept such behavior in order to maintain consensus rules, otherwise a new consensus model would be in place which negates the value proposition of Bitcoin altogether. The ‘DAO fork’ on Ethereum, where a social consensus was used to over-rule the Bitcoin consensus property, is an example of tossing out the value proposition that Bitcoin offers.

_The censorship threats listed above are not meant to be an exhaustive list, only to outline some of the more serious attack vectors in Bitcoin._

## **Censorship Objectives**

An obvious risk of censoring the Bitcoin network is the assumed loss in value of the coin and in the mining hardware of the attacker, as presumably the economy reacts negatively to censorship. Some people have referenced this loss in value as a ‘security cost’ to attacking the network and a strong preventative incentive against an attack. However, this is not necessarily a reasonable assumption to make.

The potential depreciation of the hardware and coins due to censorship may or may not matter to a censoring majority depending on his or her objectives. Indeed, the censor may not even own any hardware or coins at all, any person with a gun can walk into an industrial bitcoin mine and take over the hashrate. Many men with guns, e.g. an army, can do so at minimal cost and capture or destroy all mines they can identify. All that is required is the word of law to co-opt all identifiable bitcoin mines within a given jurisdiction. Therefore, relying solely on lost value of coin or of the hardware as a defense against censorship is an error — the censor may wield powerful resources.

## **Who is Motivated to Censor Bitcoin?**

Prior to discussing the mechanisms of censorship resistance let’s discuss who would want to censor bitcoin in the first place. Who would want to shut down a network offers greater freedoms of trade and prosperity to anybody that participates? We will assume that the entity who is most motivated to shut down the Bitcoin network is the entity that profits the most from doing so. Considering that we have not yet seen a single profit-driven miner censor the network in the first 11 years of operation — the easiest years to attack it, mind you — it is increasingly unlikely that we will see a profit driven miner attempt to censor it any time in the near future. Not to say they won’t try eventually. That being said, not all bitcoin miners are seeking on-chain profits, the greater risk comes from the miner who seeks to preserve their off-chain profits — the State.

## **State Money**

The ‘State’ is an organizational framework based upon an aggression enforced dominance hierarchy that begins with the control and issuance of ‘State money’. State money is a money that is not produced by any free market, voluntary or competitive means but instead issued and enforced via aggression and law. In this way, State money is unnatural, unlike monies which are produced by people in a voluntary and competitive manner — gold mining for example.

The State is made up of government, institutions, businesses and regular working class people like you and I. Indeed, as members of society, we _all_ play a role within the State and we are each vying for higher positions and leading roles within the dominance hierarchy. Not all State actors are equal, the higher you are in the hierarchy and cheaper you can acquire State money the more disproportionate the advantage you have. We see the disproportion manifested in the centralization of wealth in society today — “It takes money to make money”, as they say.

A monopoly on money issuance is the backbone of the State and those responsible for it are at the very top of the dominance hierarchy. Using the American State as the example, at the top sits the US Treasury and the Federal Reserve (central bank). They acquire money at the lowest cost and lend it out to those on the next level down the hierarchy. This may include investment banks, hedge funds, or other institutions. Eventually the money flows to commercial and retail banks followed by businesses and finally individuals, but each step down the hierarchy the cost of money goes up. The further you are from the top of the hierarchy, the longer it takes you to acquire the money and the more you are disadvantaged by the increasing prices of goods caused by the inflationary nature of the State money. This concept is described by the Cantillon Effect, units of inflationary State money are worth less tomorrow than they are worth today.

At the top of the State hierarchy money is not acquired through any competitive free market means, it is acquired through arbitrary issuance and enforcement via aggression. It is a fiat money. New units of fiat money are issued at negligible production cost and its value is accrued from the dilution of the remaining money that is already out circulating on the market, held primarily by those at the base of the hierarchy. In this way, the issuance of State money is a tax on the holders of the existing monetary base. This is known as seigniorage.

## **Anti-State Money**

Bitcoin does not need to rely on an aggression enforced hierarchy, instead money can be produced by anybody on a voluntary basis. It is based on market competition and all actors must suffer a cost to produce it (mining investment) or to acquire it by other means (trade).

The antithesis to State money, Bitcoin has a deflationary nature and the further away you are from the money issuance in time the more you are advantaged. People are motivated to hoard bitcoin because its purchasing power tends to increase over time. This ensures that any prospective investment has to out-compete the market rate of return of simply hoarding bitcoin, which is in stark contrast to the incentives behind State money in which hoarding is punished. In essence Bitcoin represents a reversal of the Cantillon Effect and is therefore a threat to State money and the State itself.

Bitcoin also benefits each State actor disproportionately depending on their position in the State dominance hierarchy. The individual who is furthest down the hierarchy is most advantaged by Bitcoin’s success relative to those further up the hierarchy in the same way that they are most disadvantaged by State money. An investment bank is disadvantaged relative to the individual, but is advantaged relative to a central bank. Generally, someone less wealthy, who has trouble accessing low interest rate loans, is advantaged relative to someone with better interest rates at their disposal. The top of the dominance hierarchy, who by definition have the lowest cost basis for State money, are the most disadvantaged by Bitcoin’s success — they simply have the most to lose and furthest to fall if State money collapses. As bottom-up money Bitcoin is inherently anti-State for these reasons.

## **Money is Power, Power is Money**

As a parasitic organizational framework, the State exists to extract taxes from the economy to subsidize its own existence. Controlling the money is the easiest way for the State to enforce this objective, including taxation via seigniorage (a politically correct term for counterfeit).

The State does not want to lose its control on taxation so it will likely attempt to control Bitcoin. It is natural for the State to have this objective just as it is natural for any organization to resist that which threatens its growth or survival. The State is not by any means ‘evil’, it is simply an organization of people that has found success by leveraging aggression. In some ways it is the final manifestation and natural progression of mankind’s tribal nature. Remember, the State is an organization framework, not specific people — there’s nobody to blame here.

The State may attempt to destroy Bitcoin altogether in order to preserve the utility of State money or it may simply try to control it and attempt to turn it into Statecoin. Since Bitcoin is really just an idea and may not be possible to destroy, we can probably expect the latter. The best way for the State to control Bitcoin and enforce their objectives, as described in the censorship threats above, is by gaining majority hashrate.

## **Is Censorship Feasible?**

The true cost to gain a majority hashrate and censor Bitcoin is a function of how well honest miners are distributed and hidden. Let’s look at the two extremes:

**Extreme #1 — Distributed Hashrate:** _A network of hundreds and thousands of well distributed, anonymous miners, each having less than 1% of the network hashrate._

If the network consists of many independent miners, each with relatively equivalent hashrate and each mining with relative anonymity, then it becomes rather costly to acquire a majority hashrate and censor the network. In such a scenario the hopeful censor must invest his own capital to acquire a majority hashrate with no option of co-opting the existing miners and destroy competing mines since they are well hidden and well distributed. After all, if a mine cannot be identified then it cannot be bought, co-opted, or destroyed.

To reach 50+ percent of the network hashrate in this scenario would require an enormous capital investment and would also require a massive advantage on low cost energy supply. Presumably, because the network is well distributed precisely because of the lack of energy arbitrage opportunities, low cost energy may not even be an option. This might indeed be what the future of bitcoin mining looks like, as energy arbitrage opportunities continue to tighten.

When the censor is successful and gains majority hashrate he has now sunk a ton of capital in ASICs, farm build-outs, and in the coin. If he decides to censor the network and there is a market drop in price due to the censorship scare, then he loses a significant percent of his capital investment due to the depreciation of his hardware and coins. A prospective censor would much prefer a cheaper, more feasible option to censor the network.

**Extreme #2 — Centralized Hashrate:** _A network with a few dozen large 100+ MW industrial mining farms dominating the network by accounting for over 80 percent of the hashrate._

The bitcoin network today looks more like this scenario than the previous one, albeit probably not as extreme. In this example the hashrate distribution may consist of a mix of hobbyist and small commercial scale miners that make up an insignificant minority, and a few dozen massive industrial bitcoin mines that collectively dominate the network hashrate. The large mines might be located in different countries, but they are so large in size they are impossible to hide. Immense power consumption generates heat that can easily be spotted from satellites, among other surveillance means.

A State ban on mining comes to pass, likely as a wartime measure (which do tend to have the interesting characteristic of permanently shrinking human rights and liberties), and multiple States collude with each other and take control of several large mines within their respective jurisdictions. Laws are written and Bitcoin is banned or only allowed under strict KYC and AML laws and mining licenses, among other regulatory approvals.

Under a regulated regime, all of the large mines comply since they cannot hide and failure to do so is a crime. The smaller mines continue as before, hidden on the black market and circumventing the costs of compliance. In some cases the owners of the large mines decide they do not want to participate under the new regime and accept discounted buyouts for their interests in the mines to those who are willing to comply. In other cases the mines are simply taken over by force on the basis of illegal mining. Regardless, in this way and others the State gains control of majority hashrate with relatively little resistance or upfront capital cost.

## **Threat Avoidance**

In the animal kingdom we observe the survival instinct when facing a predator — the decision of fight or flight — but a greater defence yet is avoiding the threat altogether. If the predator cannot identify the prey which is camouflage with its environment, the decision does not need to be made at all. Like a chameleon, remaining hidden requires no energy input and is therefore an optimal threat avoidance strategy. It is therefore the ability to mine covertly that best protects the miner from aggression, in the same way that anonymity is the best defence against any violent act — you cannot attack someone you cannot identify.

Any entity with enough capital can become the majority miner, whether they build it out themselves or buy and take over existing mines. For the State who can call upon legal aggression, it is even easier. There can be no doubt that obtaining majority hashrate is feasible, so the question is whether or not censorship is sustainable.

> “It is not the size of the mine that matters, it is whether or not you can hide it.”
> 
> -Sun Tzu, maybe

## **Mechanics of Censorship Resistance**

Censorship is anticipated by the system, it was designed precisely to anticipate a dishonest miner attempting to gain control [^sb5]. However, we have not yet experienced a censorship attack on the network by a majority hashrate so we can only speculate as to the sustainability of honest mining. What stands in the way of a dishonest majority confiscating all future block rewards? What kind of strategy might a censor employ to attack the bitcoin network?

### **Censorship Optimization**

If a majority miner censors an honest miner’s block by not building upon it, then the honest miner’s work ends up wasted. This is because the proof of work completed by the honest miner, whose block was censored (made stale), is not included in the strongest chain. The result of censorship of honest blocks is longer block times and a network Difficulty adjustment downwards to compensate.

As an example, if a censor gains control of 85% of the total hashrate and rejects all blocks from the remaining honest 15%, then the difficulty will adjust down 15%. The censor may choose to reject only a subset of honest blocks — perhaps only the blocks that do not provide an approved signature under a ‘white list’ regime — or he may choose to blacklist all honest blocks entirely.

Notably, the majority miner only needs just over 50% of total network hashrate to blacklist all other honest blocks entirely and earn 100% of rewards. Let’s call this the ‘minimum majority rule’. Therefore, if a dishonest majority is interested in complete censorship of the network then** any investment beyond 50% by the majority censor ends up being a waste of capital and energy**. Our majority censor with 85% of total network hashrate would be burning 35% of their hashrate and energy for no reason, which would lessen their ability to continue censoring by depleting their capital.

Since we have assumed a sustainable attack must also be profitable, one could expect the censor to choose to optimize accordingly and limit their hashrate investment to the minimum majority hashrate. In this case they still earn 100% of rewards but have preserved capital by not burning the extra energy for no extra reward. If the honest minority of miners manage to find some lucky blocks and outpace the censor, presumably he can simply bring on more hashrate to deny their blocks and win the race.

In fact we would expect the censor to only broadcast blocks at a rate that honest blocks are found, thus continuing to make them stale but not increasing the Difficulty for no good reason. The censor is better off shelving all excess hashrate beyond the minimum majority and using it only to overtake honest blocks, if he wants to censor optimally. Therefore if honest hashrate increases or decreases for any reason, then so will the censor’s hashrate in order to optimize to the minimum majority requirement. At any given time, under an optimized censorship regime, all honest hashrate is being matched by the censor. The censor is even able to automate censorship and ramp up or down hashrate as needed. Honest hashrate has no means of colluding to mine in secret because this would be dishonest behaviour and would result in coordination problems which proof-of-work consensus was invented to solve, defeating the purpose.

The only choice an honest miner has to resist a censorship regime is when to mine and when to go offline. By mining, an honest miner forces the censor to increase their hashrate by at least as much, but doing so can only be expected by an honest miner if a reward is obtainable. **Mining ‘ideologically’ implies mining at a loss and doing so is an error because it wastes capital and prevents the ideological miner from mining profitably in the future.** Once made aware that his blocks are being censored, an honest miner may decide to go offline until such a time that resuming is profitable, such as in response to fee pressures discussed below

Honest mining is required to overcome censorship, but the honest miner cannot be expected to mine at a loss, it is by definition unsustainable. Since the honest miner cannot affect the magnitude of the mining reward, which is a function of trade, he must attempt to mine the reward or to go offline and live to fight another day.

A censor is not interested in a healthy economy and so he must be forced to abandon censorship by running out of the capital required to sustain his censorship regime. The Bitcoin economy may accomplish this by forcing the censor to mine at a loss, which can be achieved by minimizing his reward and maximizing his cost. Censorship must not be rewarded if it is to be resisted, so what are the resistance mechanics provided in Bitcoin’s design?

### **Censorship Resistance Mechanism — Difficulty Adjustment**

If a majority miner optimizes censorship by maintaining a minimum majority hashrate then it results in Difficulty drop equivalent to the censored hashrate. Previously we noted that the censor does not want to mine dishonestly at 85% hashrate because the 35% did not contribute to any further reward. However, by optimizing to the equivalent honest hashrate (which is 50% of total network hashrate at any given time) the difficulty necessarily adjusts downwards up to the maximum of 50% due to the same amount of honest hashrate being censored. This decreases the cost to mine a block and will entice more honest hashrate to come online in order to chase cheaper blocks.

Indeed, if the Difficulty adjusts downward enough then even older hardware that was previously ‘obsolete’ and too costly to mine economically (e.g. high electricity prices) may also attempt to come online if the risk to reward ratio is great enough. This is comparable to the case where the bitcoin price increases at a rate faster than the Difficulty, less efficient mining hardware becomes profitable again.

**Censorship optimization also results in the maximum Difficulty reduction and therefore provides the largest possible incentive for more honest hashrate to come online, increasing the cost to sustain censorship**. The effect is somewhat similar to how State mandated production cuts in the oil and gas industry cause the price to increase and in turn incentivizes more investment into new production.

Here we have identified how the Difficulty Adjustment mechanism optimizes the price of blocks to maximally incentivize honest mining.

### **Censorship Resistance Mechanism — Fee Premium**

If a majority miner is not accepting transactions from merchants then the censored merchants must either increase their fees or not transact at all. If a merchant cannot move their bitcoins then they effectively have no value for the duration in which they are being censored. We can deduce that, due to personal time preference, a merchant who is being censored will be willing to pay a higher confirmation fee proportional to the duration in which they are being censored, up to the theoretical maximum in which the fee is the entirety of the transaction.

If the merchant chooses to wait and simply ‘hodl’ then they are denying a reward to the censor for blocking their transaction, however this is clearly the censor’s objective. While the censor does not earn a reward to offset their mining costs, the merchant is suffering the cost of not being able to use their bitcoins in trade.

Inevitably all coins must be spent, so the merchant must eventually choose to increase their fee. The increased fee level will either entice the censor to mine the transaction or it will drive up honest hashrate who look to earn the fee. The fee premium either gets mined and breaks censorship or it increases the cost of censorship, in both cases the censor loses.

In the Difficulty Adjustment Mechanism we discussed what happens when a majority censor prevents honest miners from finding blocks — it results in extended block times and an eventual downward Difficulty adjustment. It turns out that the increase in block times also ends up driving up the fee premium to get into a block, presumably due to the market’s time preference and desire for rapid confirmation and settlement.

By censoring transactions and honest blocks the censor has effectively enabled a fee premium to honest miners. Honest miners always seek maximum reward and will attempt to mine the fee premium that the censor refuses. Therefore, the fee premium is an incentive to honest mining and increases the honest hashrate. As shown, this has a net effect of increasing the cost basis of censorship and **therefore a majority miner cannot censor a merchant without incurring a loss.**

Here we observe how the Fee Premium Mechanism results in a cost to the censor and incentivizes honest mining.

### **Censorship Resistance Mechanism — Confirmation Preference**

Earlier we discussed how a majority dishonest miner can attempt to double spend merchants and steal their goods and services. However, merchants are not helpless against this threat because they can protect themselves by changing their confirmation preference.

We often say in Bitcoin that zero-confirmation transactions are unsafe. This is true because a zero-confirmation transaction can be double spent even without majority miner reorganizing the chain because the transaction was never confirmed in the first place. We also say low confirmations are unsafe because single block reorganizations are a relatively frequent occurrence and a fundamental risk due to the probabilistic nature of bitcoin mining.

The more confirmations a merchant prefers the safer they are from a double spend. A merchant’s confirmation preference should rely on the value of the trade that is being conducted or the risk potential of a double spend.

For example, a small value transaction such as a movie ticket purchase might be OK to accept 1 confirmation because the likelihood of a double spend attempt on such a low value transaction is pretty much negligible and not worth waiting the extra time for more confirmations. However, if a majority miner is actively censoring the network and causing frequent block reorganizations then the merchant may prefer more confirmations beyond the average reorganization depth before giving over the goods. In this way a merchant can continue to trade during a period of high risk. Notably, once merchants are made aware of censorship and change their confirmation preference the costs of continued double spend attack increases proportionally. Realistically, a merchant’s confirmation preference is subjective based on the value of the trade, the anonymity of the purchaser (legal recourse may be an option if the thief can be identified), and the threat level of an active majority miner.

Here we observe how the Confirmation Preference Mechanism results in an increased cost to the censor.

## **Conclusion**

Bitcoin was designed as a tool for people to use to resist censorship. As a tool, it cannot offer any guarantees against a majority miner choosing to censor the network because the censor is always able to subsidize their operation with external capital or co-opt existing mines. However, it does provide the mechanisms required for honest miners to overcome censorship, we just cannot know if the censor has the resources to continue mining at a loss indefinitely. Since the State is the most likely censorship threat, all we can say is that they would have to consume taxes at a rate equivalent to their losses. It remains to be seen whether or not people would tolerate such behavior, as it would require off-chain resistance.

Satoshi Nakamoto understood what his design represented and wisely chose to enter consensus anonymously. Bitcoin is the antithesis of State money, the evidence to which Satoshi engraved in its genesis block — a political statement against widespread financial corruption within the State. We may expect to see the State attempt to control Bitcoin, or perhaps we, as actors within the State, will find a peaceful way to transition to better money.

Whether we find a peaceful transition or not, we can help others follow Satoshi’s example by building the tools that merchants and miners need to share the risks associated with resisting censorship. Together, honest action and honest intent may overcome and deplete the resources of the censor and quell the upset condition.

## **Acknowledgements**

I would like to thank Eric Voskuil whose work on cryptoeconomics — a compilation of which can be found in the Libbitcoin Wiki [^sb5] — was the source material and much of the inspiration for this piece. If you enjoyed this perspective on Bitcoin’s security model please consider contributing to the Libbitcoin Institute.

## **Definitions**

**AML**: Anti money laundering, a State regulation.

**Block Reward: **The sum of bitcoins from the block subsidy and transaction fees in each mined block.

**Difficulty**: A protocol variable that controls the frequency of block times due to a changing hashrate.

**Dishonest mining**: To reject one or more valid transactions or blocks; to censor.

**Honest mining**: To accept all transactions and build on top of all valid blocks.

**KYC**: Know your customer, a State regulation.

**Majority miner**: A miner who controls > 50% of hashrate.

**Merchants**: People who use bitcoin in trade and pay confirmation fees to miners.

**Miners**: People who produce confirmations in return for the block reward.

**Minority miner**: A miner who controls < 50% of hashrate.

**Stale block**: A valid block that is mined but is not included in the strongest chain.

**The State**: A set of people who profit through aggression in lieu of voluntary trade.

**UTXO**: Unspent transaction output; A merchant’s bitcoin balance.


[^sb1]: [https://github.com/libbitcoin/libbitcoin-system/wiki/Axiom-of-Resistance](https://github.com/libbitcoin/libbitcoin-system/wiki/Axiom-of-Resistance)
[^sb2]: [https://github.com/libbitcoin/libbitcoin-system/wiki/Consensus-Property](https://github.com/libbitcoin/libbitcoin-system/wiki/Consensus-Property)
[^sb3]: [https://github.com/libbitcoin/libbitcoin-system/wiki/Fedcoin-Objectives](https://github.com/libbitcoin/libbitcoin-system/wiki/Fedcoin-Objectives)
[^sb4]: [https://bitcoin.org/bitcoin.pdf](https://bitcoin.org/bitcoin.pdf)
[^sb5]: [https://github.com/libbitcoin/libbitcoin-system/wiki/Cryptoeconomics](https://github.com/libbitcoin/libbitcoin-system/wiki/Cryptoeconomics)
