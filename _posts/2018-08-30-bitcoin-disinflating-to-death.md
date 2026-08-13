---
title: "Bitcoin: Disinflating to Death"
permalink: "/bitcoin-disinflating-to-death"

author: matteoleibowitz

tags:
  - matteoleibowitz
  - 2018 Q3
  - Mining
  - Economics
  - Money

excerpt: "Bitcoin: Disinflating to Death. Posted August 30, 2018."

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin: Disinflating to Death](https://medium.com/@matteoleibowitz/bitcoin-disinflating-to-death-b4ba7b691969)
### By matteoleibowitz
### Posted August 30, 2018

![](/assets/images/2018/m8/bitcoin-disinflating-to-death1.jpg)

*The author owns roughly equal dollar amounts of $BTC and $ETH.*

Bitcoin’s disinflationary monetary policy will be its death sentence. The network’s security will become increasingly vulnerable to attacks as honest miners become priced out, with transaction fees failing to provide necessary revenue in an increasingly competitive mining market.

The second part to this piece, coming soon™, will explore the migration of Bitcoin’s network to an Ethereum Plasma Cash chain as a solution to the existential threat posed by a disinflationary monetary policy.

First, some context.

#### **Bitcoin’s Value Proposition**

Bitcoin’s (the asset, from here on noted as BTC) core value proposition stems from its censorship resistant properties.

Censorship resistance is significant because it allows an asset owner to resist requisition from malicious actors, often in the form of rogue governments like Putin’s Russia, Maduro’s Venezuela, and Erdogan’s Turkey.

For an in-depth discussion on the importance of censorship resistance I recommend reviewing Spencer Bogart’s thesis [here](https://medium.com/blockchain-capital/the-long-game-in-crypto-why-decentralization-matters-fd681ff5ed0).

BTC’s allure is further compounded by a core feature of its monetary policy: there will only ever be 21 million BTC in circulation.

#### **Bitcoin’s Monetary Policy**

Satoshi Nakamoto, BTC’s pseudonymous founder(s), settled upon a disinflationary monetary policy, whereby the rate of inflation would decrease exponentially until the year 2140, at which point all 21 million $BTC will have been released into circulation.

![](/assets/images/2018/m8/bitcoin-disinflating-to-death2.png)

*BTC Inflation Schedule (Kiran Vaidya)*

This disinflationary monetary policy has two important implications:

First, it provides BTC with a characteristic of scarcity.

Scarcity does not in itself confer BTC with value, but it certainly catalyzes the accrual of value: with a static supply curve, any shift in demand should reasonably lead to a higher price level. Moreover, as a scarce asset, BTC naturally appeals to an innate anthropological desire for the rare object. It is BTC’s scarcity characteristic that lends the digital asset to credible comparisons with gold, a historical store of value with a similarly (although not identical) element of scarcity.

The second implication of BTC’s disinflationary monetary policy should be understood in its rejection of that imposed by sovereign nations over their currencies, the latter often referred to as ‘fiat’.

Sovereign nations, like the United States, have monopoly power over the ability to print more currency. Currency is printed as a means to satisfy inflation targets or pay debts, and has the indirect effect of debasing the currency-denominated savings held by the population.

US monetary policy has led to a fairly low and steady rate of inflation, especially compared to more egregious suspects like Zimbabwe, which saw its dollar inflate 50%/month in 2007. However, even US Dollar (USD) inflation adds up over time, with $1 in 1900 having the [equivalent](http://www.in2013dollars.com/1900-dollars-in-2016?amount=1) purchasing power of $28.57 in 2016: that’s a 2,757.23% rate of inflation over 116 years, or an annualized inflation rate of 2.93%.

Analysts often [frame](https://medium.com/@muradmahmudov/the-many-faces-of-bitcoin-d144601050c6) this battle between BTC, a crypto asset, and USD, fiat currency, in the context of Austrian versus Keynesian Economics, with the former school of thought advocating for deflationary monetary policy, thereby increasing the value of savings, while the latter school of thought advocates for inflation, positing that it is necessary in order to incentivize consumption, which then leads to further economic growth.

This article does not intend to advocate for either Austrian or Keynesian monetary policies, but instead seeks to address the sustainability of a disinflationary policy in the context of the Bitcoin network’s security.

#### **Bitcoin’s Cryptoeconomics**

New BTC are minted every 10 minutes in the form of a block reward, or coinbase transaction. At the time of writing, the block reward is 12.5 BTC: it will fall to 6.25 BTC in late 2020. In simplistic terms, these newly minted $BTC are issued to the miner who first discovers and broadcasts the hash of the newest block, a process otherwise known as [Proof of Work](https://en.bitcoin.it/wiki/Proof_of_work).

The block reward is at the very heart of Bitcoin’s cryptoeconomic mechanism design, in that it is a monetary incentive for miners to provide hash power to the network, which thus secures the network from malicious actors: a malicious actor has to gain 51% control over the network’s total hash power in order to execute double-spend attacks and censorship-like behaviour. The block reward is a return on investment for the necessary hardware, electricity, real estate, and often employee expenditure required to mine.

*It is this security, derived from the high levels of expenditure required to gain 51% control of hash power in a free market of economically rational actors, that provides Bitcoin with its censorship resistant properties, the very core of its value and the key differentiator from fiat currencies.*

Accepting the above statement, one might reasonably question how the network can continue to incentivize miners to provide hash power without this block reward, or when the block reward has approached negligible levels. One might reasonably fear that this quadrennial distancing from the cryptoeconomic protocol will lead to undesired outcomes.

#### **Bitcoin After the Block Reward**

The answer proposed by Satoshi and his acolytes is that miners will comfortably rely on transaction fees, the fees attached to each transaction, for revenue. The key assumption here is that by 2140, if not before, the network will have permeated global society to such an extent that transaction volume, and its associated transaction fee volume, will be high enough to sustain miner profitability.

On further inspection, however, this argument lacks empirical rigor, and, moreover, largely conflicts with today’s zeitgeist, where, as a [Store of Value](https://medium.com/@nic__carter/visions-of-bitcoin-4b7b7cbcd24c), merely holding BTC, i.e. refraining from transactions, is considered a legitimate use case.

#### **Maths Behind Bitcoin Miner Revenue & Profit**

*Block rewards:*

The current block reward for Bitcoin is 12.5 BTC.

Blocks are produced every 10 minutes.

At the time of writing, 1 BTC = ~$6,600, so each block reward has a USD value of $82,500.

144 blocks are produced/day, with the corresponding block rewards containing a USD value of $11.88m.

So miner revenue from block reward alone is $11.88m.

Now let’s calculate miner revenue from transaction fees.

*Transaction fees:*

Transaction fees vary depending on the speed at which the transactor wishes to have their transaction processed. They also vary on a daily basis depending on levels of demand for transactions.

At the time of writing, the [cost](https://bitcoinfees.info/) of ‘next block fee’, ‘3 blocks fee’ and ‘6 blocks fee’ are $0.51, $0.48, and $0.24 respectively.

For this exercise I will use data from CoinMetrics, which shows that transaction fees have made up roughly 1.3% of miner revenue for the last 6 months.

![](/assets/images/2018/m8/bitcoin-disinflating-to-death3.png)

*Transaction fees as % of total miner revenue (CoinMetrics)*

At the time of writing, there are ~250,000 tx/day.

If transaction fees make up 1.3% of total daily revenue, this equates to an average of $0.63/transaction and $156,474.16/day of transaction fee revenue. Total revenue from transaction fees and block rewards is $12,036,474.

*Miner profitability:*

[Various](https://us3.campaign-archive.com/?e=745c258920&u=db45c09bdf20e1866bb32123f&id=1da0bd867e) [estimates](https://www.marketwatch.com/story/heres-how-much-it-costs-to-mine-a-single-bitcoin-in-your-country-2018-03-06) put mining costs at ~$3,000/BTC on the lower end and ~$5,000/BTC for less efficient mining operations. For the sake of this exercise I will take miner cost/BTC to be ~$4,000.

All this combined results in current miner profitability of $4,836,474/day: total revenue ($12,036,474) — total costs ($7,200,000). Represented as a percentage, this is 67% profit margin.

I have summarized the above in the table below (with BTC @ $6,600):

![](/assets/images/2018/m8/bitcoin-disinflating-to-death4.png)

*Miner revenue/cost/profit breakdown with block rewards present*

Now, what does miner profitability look like when you take out the block reward, as will happen by 2140?

Bitcoin blocks at 2mb/block can contain roughly 2,500 tx. At 250,000 tx/day, blocks are not full: 144 blocks * 2,500 tx would be 360,000, or over 110,000 more tx/day than we currently see.

For the sake of this exercise I will presume that blocks are at full transaction capacity. I have made this assumption because I imagine that as Bitcoin continues to grow in stature transaction volume will increase to capacity.

So we have 360,000 tx/day, with average transaction fee at $0.63, resulting in revenue from transaction fees at $226,800.

![](/assets/images/2018/m8/bitcoin-disinflating-to-death5.png)

*Miner revenue/cost/profit breakdown without block rewards*

You have probably noticed that $226,800 in transaction fee revenue/day falls short of mining costs/day, which we have calculated to be $4,000/BTC, or $7,200,000/day.

In fact, transaction fee revenue is just 3.15% of miner costs.

#### **Mining Landscape**

So far, this article has sought to address the state of the Bitcoin network after the block reward has disappeared.

However, it is worth noting that miner profit margins will likely fall well before block rewards disappear as the mining landscape continues to mature and professionalize.

[Basic economic theory](https://www.tutor2u.net/economics/reference/perfect-competition-economic-efficiency) would suggest that today’s 67% profit margins are unsustainable in the medium-long term, and new, larger players will enter the market and drive mining towards its equilibrium cost of production.

Bigger players entering the market means more hash power. And as the combined rate of hashpower increases the [marginal rate of returns per hash decreases](https://bitinfocharts.com/comparison/bitcoin-mining_profitability.html). Expected drastic global reductions in both electricity and hardware costs over time have no impact on profitability if we presume that costs will be cut for all miners. Those miners feeling the heat at today’s average margins will be squeezed out, leading to further centralization and dissolution of censorship resistant guarantees.

#### **Making Mining Profitable Again**

So now we must look at ways in which miners can increase revenue in the absence of block rewards.

This is an existential task considering the danger that miner withdrawal from the Bitcoin network would mean for the value proposition of BTC.

There are four ways to increase revenue:

1. Increase block sizes, therefore increasing transaction capacity.
2. Increase transaction fees.
3. A combination of increased transaction fees & increased block sizes.
4. Do away with a fixed, disinflationary monetary policy.

**Solution #1:**Increase block sizes:

This seems unlikely to be accepted in the context of the heated SegWit2x debate of 2017. At this point it is rather clear that those left in the BTC community will do anything to avoid increasing block sizes, which they argue leads to [centralization](https://media.consensys.net/the-state-of-scaling-ethereum-b4d095dbafae) as overheads increase dramatically.

The BTC camp has instead placed their eggs in the Layer 2 basket, primarily in the form of Lightning Network (LN), an off-chain payment channel. Ironically, LN only further compounds miner revenue issues: if transactions are executed off-chain, users no longer have to pay a transaction fee to miners every time they wish to transact BTC — instead, transaction fees are directed to LN routing nodes, with one-off fees paid to miners each time the LN channel is opened and closed. As [this](https://scalingbitcoin.org/stanford2017/Day2/HowToChargeLightning_ScalingBitcoin.pdf) research paper suggests, miner revenue from transaction fees with active use of LN is lower than today’s levels until a threshold of 20 million LN users, each transacting 10 times/day, is breached. For context, Visa processes 150 million transactions per day.

An analogue solution is to decrease block times, allowing for more transactions/time. However, decreased block times comes with several disadvantages — namely increased bandwidth overheads and more orphaned blocks, which is a waste of hashpower, and ergo lower security — and is unlikely to be supported by the BTC community, which has historically been adverse to significant changes to the protocol, especially those that catalyze further centralization.

**Solution #2:** Increase transaction fees.

This is more politically feasible than increasing block sizes, and is likely to be the predominant response from $\BTC disciples to this piece, but nevertheless is unlikely to be sustainable in the long term.

With the emergence of LN, one might assume that the average Joe will rely on Layer 2. The problem here is that if LN is to be used in a trust-minimized way — and remember, trust-minimization/verification is at the heart of BTC’s value proposition — then users will need to broadcast their txs on Layer 1 in order to open/close channels. Perhaps even more importantly, a counterparty in an LN channel can misbehave at any point and force a user to broadcast in order to maintain access to their funds: if fees are prohibitively expensive, this essentially negates the value of L2.

Now, what might these increased transaction fees actually look like? Here I defer to Eric Budish, Professor of Economics at the University of Chicago, Booth School of Business, and author of [*The Economic Limits of Bitcoin and the Blockchain*](http://faculty.chicagobooth.edu/eric.budish/research/Economic-Limits-Bitcoin-Blockchain.pdf), who estimates necessary transaction fees to avoid network attacks post-block reward ranging from a low end of $18,700 to an upper limit of $108,700. (As several commentators have [noted](https://medium.com/@hugonguyen/a-review-of-budishs-51-attack-theories-what-is-the-fair-price-of-an-old-asic-59a7dcf9ff94), Budish’s assumptions regarding cost of attack may be slightly misguided, but considering that no comprehensive rebuttal of Budish’s figures exists at present I will continue to use these numbers, albeit with a grain of salt.)

Now we must ask ourselves how attractive an $18,700 fee (on the lower end) *per transaction*will be to the banks and businesses using L1 as a settlement layer, let alone average Joe’s using LN wishing to close out channels, especially considering that cheaper alternatives are likely to exist?

Moreover, we must ask how fees would ever get that high in the first place. The transaction fee market is like any other, with price derived from the intersection of supply and demand. Miners do not propose fees themselves and any attempt to artificially fix fees at a minimum of $18,700 would, as game theory dictates, lead to selfish miners including all remaining transactions in the mempool from highest to lowest fee.

And if all this wasn’t alarming enough, what about the various [attack vectors](http://randomwalker.info/publications/mining_CCS.pdf) that open up as the structure of miner incentives changes shape?

**Solution #3**: A combination of increased transaction fees and increased block sizes.

This is unlikely to fly for the reasons discussed in Solution #1 — the BTC community is unlikely to ever agree to an increased block size — and Solution #2 — increased L1 transactions fees puts L2 users at risk of not being able to recover their funds.

**Solution #4:** Change $BTC’s monetary policy.

Reinstating a block reward after 2140 (if not before) likewise seems untenable, especially since the BTC value narrative has developed into one of ‘sound money’, rather than simply a censorship-resistant form of value.

Moreover, BTC’s value narrative is further driven by its ability to exist without active governance, its supposed antifragility, unlike something like Ethereum, which is currently going through a rapid development process involving several significant human-made decisions. A shift away from Satoshi’s monetary policy would be a monumental event and likely split the community, perhaps even more so than the block size debate of 2017. Indeed, like its block size, a disinflationary monetary policy may rightfully be considered to be a fundamental part of BTC’s ‘social contract’, its essence, and thus any update to the protocol should be thought of as an illegitimate claim to the BTC mantle.

Ironically, despite the inevitable resistance from BTC disciples, a change in monetary policy is likely to most reasonable and effective path to sustaining the network.

#### **The Road Ahead:**

There have been multiple times in the history of Bitcoin where miners have operated at a loss. Indeed, we can look at other [assets](https://twitter.com/PeterLBrandt/status/1029894756648677376), like silver and copper, to see that producers will operate at a loss for extended periods of time.

However, it seems reasonable to presume that miners will not operate at a loss forever. Indeed, it is mathematically impossible to operate at a loss forever — at some point you will run out of reserves and lack the necessary capital to continue operations.

So if transaction fees alone are unable to keep Bitcoin mining profitable, miners will stop mining. If miners stop mining, then combined hash power decreases.

If combined hash power decreases then the security of the Bitcoin network falls: it becomes [even easier](https://www.buildblockchain.tech/blog/eth-core-devs-block-reward) for an adversary, like a nation state, to purchase the necessary hardware and electricity . required to contribute 51% hash power and begin double spending and/or censoring transaction.

Once that guarantee of censorship resistance disappears, the Bitcoin network, and the native digital asset, BTC, collapses. And as much as I like to believe in forgiveness, it seems rather unlikely that the market or those relying on BTC as a store of value, will grant Satoshi’s masterpiece a second chance.

*Pt.2, Bitcoin on Ethereum: The Only Way Forward,*coming soon™

*Thanks to*[*Daniel Goldman*](https://twitter.com/DZack23)*,*[*David Beiner*](https://twitter.com/DavidCBeiner)*, and*[*Nic Carter*](https://twitter.com/nic__carter)*for taking time to review/provide feedback.*

*Sign up to CryptoChat, a weekly industry newsletter,*[*here*](http://cryptochat.us)*.*

***

{% include signup.md %}
