---
title: "Bitcoin Security: a Negative Exponential"
permalink: "/bitcoin-security-a-negative-exponential"

author: jordanmckinney

tags:
  - Jordan McKinney
  - 2018 Q3
  - Mining
  - Money
  - Technology

excerpt: Bitcoin Security: a Negative Exponential. Posted August 29, 2018.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin Security: a Negative Exponential](https://medium.com/coinmonks/bitcoin-security-a-negative-exponential-95e78b6b575)
### By Jordan McKinney
### Posted August 29, 2018

![](/assets/images/2018/m8/bitcoin-security-a-negative-exponential1.jpg)

[Photo Credit](https://unsplash.com/photos/cAq3crYmgno)

#### Intro

I’ve long been skeptical that Bitcoin would win out as future-money, but in light of the recent increase in pro-Bitcoin sentiment on Twitter I decided I should try to figure out how I’m wrong.

During research I ran into the question of how Bitcoin will maintain security as the block reward declines. Despite a lot of searching (and pestering people on Twitter) I was surprised at how little discussion I found, and how *bad* the proposed solutions seemed.

Unless I’ve completely missed something, **I can’t see how Bitcoin security does not decline with block rewards — which follow a negative exponential**!

This problem *has* been discussed elsewhere ([0](https://en.bitcoin.it/wiki/Tragedy_of_the_Commons), [1](https://bitcointalk.org/index.php?topic=67900.0), [2](https://bitcointalk.org/index.php?topic=6284.0), [3](https://bitcoin.stackexchange.com/questions/3111/will-bitcoin-suffer-from-a-mining-tragedy-of-the-commons-when-mining-fees-drop-t), [4](https://cryptofundamental.com/21-done-will-bitcoin-survive-the-tragedy-of-the-commons-271a6cd21b04)), but I haven’t found any source which lays out the problem *and* critically assesses the commonly proposed solutions. So, that is the purpose of this post.

If I *have* missed something important then this post can serve as an application of [Cunningham’s Law](https://meta.wikimedia.org/wiki/Cunningham%27s_Law) and someone can enlighten me.

#### Basics of Proof-of-Work

Value is stored on the Bitcoin network — that is its purpose.

The network uses proof-of-work (PoW) to (among other things) protect against [51% attacks](https://en.bitcoin.it/wiki/Majority_attack). PoW protects against 51% attacks by making them **expensive**to pull off — not impossible!

To successfully do a 51% you need to acquire slightly more than half the hash power of the network. If the network has a lot of hash power then this will probably be expensive because hash power has a real world cost (hardware and electricity).

#### The Security Budget

The security of a PoW network depends on the cost to 51% it. The cost to 51% it depends on how much money the miners are collectively spending. How much miners are spending depends on how much they’re being paid.

Therefore the security of a PoW network depends on how much money the network is paying out to miners — which is why I’m calling this amount the “**security budget**”. The security budget directly determines security.

#### Simplest Example

A new ASIC-resistant, PoW cryptocurrency appears. It pays out *exactly* $1M/day (the security budget!) to miners regardless of total hash power etc.

At first, one person mines. Total money spent mining is low, hash power is low, difficulty is low, and they earn the entire $1M/day.

New miners join. Total money spent mining rises, hash power rises, difficulty rises, and the $1M/day is spread across more people.

**As the system approaches equilibrium, the combined cost expended by miners (“total spend”) approaches, *but is always less than*, $1M/day.**

Why?

If the total spend were *more* than $1M/day the less efficient miners would lose money and soon quit — lowering total spend. If the total spend were much *less* than $1M/day new miners would join, eat those profits, and total spend would creep upward.

Now, since the size of that $1M/day pie that miners fight for depends on how much hash power they contribute, they constantly compete to output more hash power per dollar spent.

Therefore the $1M/day security budget will tend to get the network *close to* the maximum total hash power *that can be had* for $1M/day. This is good!

##### The Attack

Let’s attack this network. To 51% any PoW network we just need a bit more than half the hash power, right? So, how much do we need to spend?

Well, we know the protocol pays out $1M/day. So, the miners can’t be spending more than $1M/day mining. Competition should squeeze them to produce close to the *maximum* total hash that can be had for $1M/day — but that’s OK, it’s still capped at $1M/day.

So we can kill the network for about $1M/day.

##### Defense

How could our attack be prevented? Well, all you can do with PoW is make attacks more expensive, so you increase the security budget.

Suppose the network doubles the security budget to $2M/day. New miners join, total spend increases, hash power increases, and a new equilibrium is reached just like before. Now total spend is close to, but less than, $2M/day. And the network has close to the maximum hash power you can get for $2M/day.

OK. Now we can kill the network for $2M/day.

It also works in the other direction. If the amount paid to miners were halved from $1M/day to $500K/day we could kill the network for $500K/day.

##### Security Budget Determines Security!

We know that PoW protects against 51% attacks by making them expensive.

Now, we’ve seen that the cost to attack depends on how much miners are *spending,* and this is capped by the amount the network pays out to miners — the “security budget”.

Therefore, we can see that **security budget determines network security**.

#### ASIC Example

In the example above, the network was ASIC-resistant and we concluded that security budget determines security.

Does this conclusion change if we add ASICs? Bitcoin has ASICs after all, and this post is (supposedly) about Bitcoin.

— — —

A new *ASIC-mined* cryptocurrency appears. It pays $1M/day ($365M/year) to miners. Miners must purchase, and periodically upgrade, the ASICs used to mine on the network — this can be amortized into an ***annual hardware cost***. They also incur an ***annual operating cost*****(the usual electricity, etc).

Maybe it works out that miners spend $250M/year on hardware and $100M/year on operating cost. Whatever the break down is, they can’t *sustainably** spend *more* than they earn. So, the sum of these will approach, but generally be *less than*, annual miner revenue — aka the ***annual security budget***:

***annual hardware cost + annual operating cost ≤ annual security budget***

As before, the pool of miners will tend to produce the maximum hash power that can be had given the security budget. To maximize hash power they must figure out how much to spend each year upgrading hardware. Miners don’t like upgrading hardware, but competition eats their operating margins as hardware ages. Eventually some equilibrium hardware-spend is found.

The result of all of this is that, if the protocol spends $365M/year on miners it gets close to a “true” $365M/year worth of hash power, regardless of how the hardware-spend works out. So, it all tends to work out same as before.

* **I say “sustainably” because if revenue were high miners might spend a lot on hardware expecting it to stay high. Then it drops and they are over-budget on hardware for this lower revenue level. But they keep mining as long as revenue exceeds operating costs. Therefore you could have $300M worth of hardware mining when current revenue only justifies $250M. This over-allocation would gradually adjust downward though as hardware is refreshed. This should take no longer than one full hardware refresh period.*

##### The Attack

The cost to attack will vary somewhat depending on how long the hardware refresh period is. Suppose miners spend $300M/year on hardware, $65M/year ($178K/day) on operating costs, and hardware has a 3 year useful lifespan.

This means at any given time there is $900M worth of hardware mining, and it’s burning $178K/day. So, to attack the network we must spend $900M on ASICs and $178K/day.

##### Defense

The community anticipates our attack. How can they prevent it? Once again, all they can do is increase the security budget.

The network doubles the security budget to $2M/day. New miners buy ASICs and start mining, hash power increases, and after some time a new equilibrium is reached.

The ratio of hardware spend to operational spend should stay *roughly*the same so now we can expect to spend twice as much on ASICs and twice as much per day to attack.

**And, just like before this works the other way too**. If the security budget were halved to $500K/day, and equilibrium were reached, we could expect to spend half as much on ASICs and half as much per day to attack.

##### Security Budget (Still) Determines Security

ASICs make 51% attacks more expensive — assuming we are comparing relatively short-lived attacks — but the **attack cost is still bound and determined by the security budget**. How could it be otherwise?

ASICs or not, the network *must* have a high security budget if it’s going to have high security.

#### Absolute Hash Rate

Notice that we didn’t need to care about *absolute*hash rate in these examples. The ultimate determinant of cost to attack was how much miners were *spending —*which was capped by how much they were earning.

So the *absolute* hash rate produced by the pool of miners is *not* a direct measure of security — it is a sort of *proxy* for security, even a red herring.

**Example**: Imagine a network that pays out a constant $1M/day to miners no matter what, forever. It has a **constant level of security** — whether we attack today, or one year from now, we can expect to pay $1M/day.

But, what would the hash power graph look like for this network? It would go up and to the right. Hardware is always advancing. You can get more hashes per dollar next year than you can today.

It would be a **mistake** to look at the rising hash power and simply conclude that the network is becoming more secure with time (see next section for Bitcoin-specific illustration).

Cost expended (security budget!) — not absolute hash rate — determines security… This is why statements like the one below make **no** sense.

> As ASICs become more efficient we can reduce the overall cost spent mining!

![](/assets/images/2018/m8/bitcoin-security-a-negative-exponential2.jpg)

[Photo Credit](https://unsplash.com/photos/RWD07TnE7bQ)

#### Bitcoin (Finally)

*One more thing* before getting to Bitcoin’s security budget and the problem motivating this whole post.

##### Absolute Hash Rate

The graph below shows Bitcoin **hash rate** for the past year. The graph right after shows **miner revenue** for the past year.

![](/assets/images/2018/m8/bitcoin-security-a-negative-exponential3.png)

*Bitcoin Hash Rate*

![](/assets/images/2018/m8/bitcoin-security-a-negative-exponential4.png)

*Miner Revenue(Security Budget!)*

Which graph is the better indicator of network security? Assuming an efficient mining market, the second graph is the better indicator — absolute hash rate is a red herring.

Remember the example above. Absolute hash power will always tend to increase due to hardware advancements — even if the security budget (and cost to attack) are fixed.

Hash rate only *declines* with time if the security budget is falling *faster* than the cost per hash/sec — this is bad! Even a *constant* hash rate indicates declining security.

##### Bitcoin Security Budget

OK. So we’ve established that, ASICs or not, PoW networks must have a high security budget in order to have high security (I know I’ve said that 50 times).

This applies to Bitcoin (it being a PoW network), so how is Bitcoin’s security budget funded?

100% of miner revenue (the security budget) in Bitcoin comes from block rewards and transaction (tx) fees.

**Bitcoin security budget = block rewards + tx fees**

So if Bitcoin is going to remain secure we need to make sure *block rewards + tx fees* always equals a large amount of money.

#### The Problem

Block rewards make up **~98%** of Bitcoin’s security budget at present* and they get**cut in half**every 210,000 blocks (~4 years)* until they’re *gone*.

**Bitcoin’s security budget, and therefore the security of the network, gets (roughly) halved every 4 years.** **The network becomes *less* secure over time!**

* **Current tx fees =*[*$200K/day*](https://www.blockchain.com/charts/transaction-fees-usd)*, current block reward = ~$12.6M/day (at $7000/BTC). 12.6/(12.6+.2) = 0.984*
* **At present 12.5 BTC are issued per block (~10 minutes). This will halve to 6.25 BTC/block sometime in*[*May 2020*](https://www.bitcoinblockhalf.com/)*(and again in 2024 and so on)*

![](/assets/images/2018/m8/bitcoin-security-a-negative-exponential5.jpg)

[Photo Credit](https://unsplash.com/photos/sz3AWACktLc)

#### Solutions/Responses

As the integrity of Bitcoin depends on it being resistant to 51% attack, this issue is absolutely central to Bitcoin’s very *survival.* Surely there is a rock-solid, game-theoretically sound, non-hand-wavey solution to this problem?

These are the responses I’ve come across. Unattributed quote blocks are either general forms of arguments I’ve heard, or me arguing against myself.

##### Continually Rising Price

> If Bitcoin price rises as block rewards fall, then the security budget could actually remain constant, or even grow.

First of all, relying on price to ***increase continually*** at some specific cadence in order that absolute security doesn’t ***decrease*** is truly terrifying. No one knows what price is going to do. We can’t *count on it* going up.

Also, price just *can’t* double every 4 years for very long:

* 4 doublings: $110K/BTC. OK sure…
* 7 doublings: $900K/BTC. Not so sure.
* 9 doublings: $3.6M/BTC. [Bitcoin market cap now exceeds world GDP](https://bitcoin.stackexchange.com/a/6090).
* 12 doublings: $26M/BTC. Well into silly-territory now.
* 31 doublings (year 2140) : $15T/BTC. *_*

##### Security Factor

But it gets worse. Let’s suppose Bitcoin price (and therefore market cap) *did* in fact double every 4 years in pace with the block reward halving, while cost-to-attack remained constant.

Then cost-to-attack *relative* to overall network value would fall over time, but *absolute* cost-to-attack would stay constant. Seems OK?

It’s not OK!

**The cost to attack a network must be proportional to the value of the network!**Networks must maintain what I’m calling a “**security factor**”.

If it cost $10M to kill a network worth $100M then its security factor is 10%. Networks should maintain a constant ***security factor*** as they become more valuable — that way their ***security budget*** scales with the value of the network.

**Example**: Imagine you could kill Joe’s Plumbing, which does $100K/year revenue, for $1M. Probably no one would bother. Now imagine you could kill *Google/Amazon/Facebook* for $1M. *Countless* parties would happily pay that cost for many, many reasons (think competitors, nationstates, terrorists, hedge funds, even crazy rich people).

Bitcoin is worth about $100B (by market cap) and the cost to attack it is about $10B ([$8.8B hardware + $6M/day electricity](https://gobitcoin.io/tools/cost-51-attack/)). So, Bitcoin’s security factor is about **10%** right now (cost-to-attack/network-value).

All else equal, if BTC price doubles when the block reward halves in 2020, then the network is worth $200B while cost-to-attack is still $10B — security factor has *dropped* to ~**5%**. This keeps happening every 4 years.

Imagine the cost to [spawn camp](https://twitter.com/VitalikButerin/status/827783678910558208) Bitcoin to death remained a constant $10B, while price, and therefore market cap, continued to rise.

You think no government/competing chain/conspiracy of banks/shorting hedge fund/etc. would be willing to pay that $10B at some point? Bitcoin would keep growing, displace fiat’s all over the world, and become the global reserve currency with a $10B un-pushed “kill-this-currency” button on it?

Nobody knows how big the security factor needs to be to protect Bitcoin, but it kind of seems like we are running an *experiment to find out*.

##### Rapidly Rising Price

> Well, BTC price increase could actually outpace the block reward decrease. Then absolute security budget would increase.

Sure BTC price *could* outpace block reward decrease (for a while) — though again, it would be insane to rely on this happening — but even then we would still have a declining security factor!

Assuming fees stay constant (or increase in pace with price) the only way to have a *constant*security factor would be to steadily *increase* block rewards in proportion to total supply so that Bitcoin had a constant X% inflation rate — which the community would never accept.

##### Transaction Fees Will Save Us

> As block rewards decline transaction fees will increase to make up the difference.

As far as I can tell this is the leading solution in the Bitcoin community to this problem, even Satoshi seemed to support this solution:

> In a few decades when the reward gets too small, the transaction fee will become the main compensation for nodes. I’m sure that in 20 years there will either be very large transaction volume or no volume. —
>
> Satoshi

But why would total fees paid suddenly increase as the block reward drops? Users **always** want to pay minimal fees. Based on current figures, fees would need to go up **37x** to compensate for the halvening in 2020.

> Maybe the fees don’t need to 37x, maybe the current fee level is enough?

If fees stayed at their current level *relative* to market cap we would see a 98% reduction in security budget as block rewards went away. This would be equivalent to being able to kill today’s Bitcoin for 200M — a security factor of 0.2%. Is this enough? Who knows. I wouldn’t want to bet on it.

> Miners will demand higher fees.

**This isn’t how mining works**. Total fees paid is a function of user demand for block space. Miners do not control this. Miners can only push fees up if they collude to exclude low fee tx’s. Surely *this* cannot be our security solution?

Also, the system was designed to prevent this.

If you are a miner excluding tx’s that do not meet a minimum threshold fee, I can come along as a selfish miner and make *more money than you* by including *all* tx’s sorted highest fee to lowest.

Miners and users alike may benefit from high security and high fees being paid to miners, but no one wants to actually pay this cost. We have a [**tragedy of the commons**](https://en.wikipedia.org/wiki/Tragedy_of_the_commons) problem.

Even the [Bitcoin wiki](https://en.bitcoin.it/wiki/Tragedy_of_the_Commons) points this out:

> Miners will accept transactions with any fees (because the marginal cost of including them is minimal) and users will pay lower and lower fees (in the order of satoshis)

So, miners can’t enforce high fees…

> How about we hardcode a minimum fee into the protocol?

Not only does this just seem truly*bad,*but it still**doesn’t solve the tragedy of the commons problem.

> Transaction volume will increase and therefore generate more revenue.

Relying on an increase in tx volume to prevent a *decrease* in security is bad for the same reason relying on a price increase for security is bad. We can’t know what tx volume will look like in the future (especially with layer-2 scaling complicating things).

Also, this seems to imply that increasing tx *supply* will bring in more fee revenue. But users **always**pay the lowest fee they can, and miners are selfish — they simply include as many tx’s as possible sorted high to low fee. In order for users to pay more total money in tx fees there must be a true increase in *demand* on their side.

Even if tx revenue increases how can we *know* it will increase enough to protect the network?

##### Dont’ Worry, This is all Decades Away

> Block rewards won’t go to zero until 2140!

This is maybe the second most common response I’ve heard to this problem.

First of all, saying that a problem is “far off” is not reassuring at all — especially when we’re talking about a **long-term store of value(!)**. *Maybe* we could let things slide if this truly were not a problem **at all** until 2140, but that’s not the case.

Block rewards hit **zero** in 2140, but in just 2 years they halve, in 10 years they’re down **88%** to 1.5625 BTC/block. In 14 years they’re down **97%** to 0.390625 BTC/block.

Just look at the chart. The blue dashes are block reward amount. We are currently on the **3rd one from the left**. After 4 or 5 more halvings we are pretty much at zero block reward.

![](/assets/images/2018/m8/bitcoin-security-a-negative-exponential6.png)

*Controlled Supply*

Again, the scary thing is that no one knows how big Bitcoin’s security factor (and security budget) needs to be. Apparently 10% and $10B are adequate for now. But the next halving is in 2020. Will 5% security factor be enough? What if BTC price 10x’s and some big institutions feel threatened? Then it halves again in 2024, and again in 2028…

Also, it’s not like people can’t look into the future and see where things are headed. How can Bitcoin holders be confident in Bitcoin’s ability to store value without a super solid, bullet-proof, economically-sound, long-term solution to security?

##### Dominant Assurance Contracts

> I have lots of Bitcoin, so I benefit from high hash rate. Therefore I
>
> pledge
>
> 0.1 BTC to the miner of the next block so long as the total amount pledged hits 10 BTC.

So, donations? [We’re going to fund the security of the 21st century’s global reserve currency via donations?](https://en.wikipedia.org/wiki/Tragedy_of_the_commons)

##### Charity Mining

> Bitcoin will be so important that miners will mine at a loss.

Again, [donations](https://en.wikipedia.org/wiki/Tragedy_of_the_commons)?!?

> Some people will always be willing to mine for fun/research/good will.

Sure, *some* people will mine “for free”. But there is no way on Earth we can *rely*on charity mining to provide the $10M/day (or whatever it happens to be) miner-spend that we need to secure Bitcoin — never mind maintaining a security factor.

##### Defensive Mining

> Miners with a stake in Bitcoin may mine at a loss to defend the network.

If a well-funded attacker starts mining they are adding a bunch of hash power to the network. If the market was relatively efficient, and margins were somewhat thin, then some miners will now be losing money every second that they mine.

These miners must choose to either drop out and cut their losses, or continue mining at a loss in order to “do their part” and save the network. Again there is a tragedy of the commons problem here.

But even worse, if miners believe the attacker is well-funded and will probably win eventually, they should cut their losses now (and try to sell their hardware and coins) rather than mine at a loss for the next month only to give up then having spent much more money.

##### Ethereum has this Problem too!

This is the “[you too](https://en.wikipedia.org/wiki/Tu_quoque)” logical fallacy since Ethereum having the same problem doesn’t help Bitcoin. But I don’t think the situation is as bad for Ethereum.

For one, Ethereum has not yet committed to deflationary issuance, while Bitcoin certainly has. In fact, I think Bitcoin supporters would agree that Bitcoin’s 21 million supply cap is absolutely non-negotiable at this point.

Ethereum has also long been planning to move to proof-of-stake, which *should* allow for greater security per dollar of security budget, and therefore lower security budget and lower issuance — though perhaps never zero issuance.

But either way, Ethereum’s security doesn’t really matter to Bitcoin.

##### Proof of Stake?

Speaking of Ethereum, maybe proof-of-stake (PoS) can solve this problem for Bitcoin? From the [Bitcoin wiki](https://en.bitcoin.it/wiki/Proof_of_Stake):

> Some argue that methods based on Proof of Work alone might lead to a low network security in a cryptocurrency with block incentives that decline over time (like bitcoin) due to
>
> Tragedy of the Commons
>
> , and Proof of Stake is one way of changing the miner’s incentives in favor of higher network security.

As far as I can tell this is the only solution that seems like it could work. According to the [Ethereum PoS wiki](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQs#what-are-the-benefits-of-proof-of-stake-as-opposed-to-proof-of-work) it might even be possible to have *zero* (or negative) issuance with PoS (don’t ask me how), which would allow Bitcoin to stick to the 21 million BTC hard cap.

But is this an active area of research in the Bitcoin community? Would the community even tolerate a move to PoS? It certainly [doesn’t seem like it](https://bitcointalk.org/index.php?topic=2050869.0). It looks like Bitcoin is committed to PoW for the foreseeable future, for better or worse.

![](/assets/images/2018/m8/bitcoin-security-a-negative-exponential7.jpg)

[Photo Credit](https://unsplash.com/photos/h7bQ8VEZtws)

#### Conclusion

I don’t have a vendetta against Bitcoin, but I also don’t care if Bitcoin *specifically* wins the crypto-war. Nor do I care if Ethereum or Dogecoin wins.

I care that cryptocurrencies deliver on what I believe to be their tremendous potential. I hope the **best**, most **secure**, most **useful** one wins (and if I can spot the winner and place some bets that would be fine too :).

We should be hyper-critical of all our cherished cryptos because the last thing we need is for society-at-large to adopt one of these things only to have it blow up in their faces and set the whole field back 10 years.

As I said at the top, if I’ve missed something and this problem isn’t really a problem, or there is some great solution that I completely missed, please let me know *exactly*what I’ve missed, I want to know.

**That being said I’m going to keep looking for an answer to this question until either: I find one, or I’m blocked by every Bitcoin maximalist on Twitter due to Tweeting this post at them!**

— — —

Thanks to [@dinocellotti](https://twitter.com/dinocelotti) and [@adampwilkinson](https://twitter.com/adampwilkinson) for the feedback on this post.

My Twitter: [@jordanmmck](https://twitter.com/jordanmmck)

##### **Update:**

I made a [Tweetstorm for this post](https://twitter.com/jordanmmck/status/1035216406952861696) that resulted in a lot of interesting back and forth. The fee-market is clearly the preferred solution to this problem on the part of Bitcoiners.

(Check out [this post](https://medium.com/@matteoleibowitz/bitcoin-disinflating-to-death-b4ba7b691969) for a more in-depth refutation of the fee-market solution to this problem.)

I did *not* hear any compelling arguments for why tx fee revenue as a percentage of network value should increase — so an extremely low security factor looks likely.

Nor did I hear any argument for why we should expect Bitcoin to survive with a much, much lower security factor. It looks to me like the Bitcoin community is going to more or less just **hope that the fee-market is adequate**.

**Part II**: [Bitcoin Security in One Chart](https://medium.com/coinmonks/bitcoin-security-in-one-chart-694ee3ed8c2d)

***

{% include signup.md %}
