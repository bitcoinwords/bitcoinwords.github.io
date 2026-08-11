---
title: "Proof of Stake is Still Pointless"
permalink: "/proof-of-stake-is-still-pointless"

author: paulsztorc

tags:
  - Paul Sztorc
  - 2017 Q3
  - Technology
  - Security
  - Altcoins

excerpt: Proof of Stake is Still Pointless. Posted July 7, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Proof of Stake is Still Pointless](http://www.truthcoin.info/blog/pos-still-pointless)
### By [Paul Sztorc](https://twitter.com/truthcoin)
### Posted July 7, 2017

> I go line-by-line against Vitalik’s Proof of Stake FAQ. PoS is still just as expensive as PoW (but it may have different security features).

#### Proof of Stake is Back

Yesterday I noticed that someone from Ethereum [has responded](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ#doesnt-mc--mr-mean-that-all-consensus-algorithms-with-a-given-security-level-are-equally-efficient-or-in-other-words-equally-wasteful) to [my August 2015 article “Nothing is Cheaper than Proof of Work”](http://www.truthcoin.info/blog/pow-cheapest/) on their [Proof of Stake FAQ](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ).

…and now [I see](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ/_history?page=2) that it was written by Vitalik Buterin himself, almost a year ago (!).

*Oh, brother..*

I’m not sure it makes any difference at this point, but I started this so I suppose I may as well finish it.

Here we go!!

### The Claim

> Doesn't MC => MR mean that all consensus algorithms with a given security level are equally efficient (or in other words, equally wasteful)? > > This is an argument that many have raised, perhaps best explained by Paul Sztorc in this article. Essentially, if you create a way for people to earn $100, then people will be willing to spend anywhere up to $99.9 (including the cost of their own labor) in order to get it; marginal cost approaches marginal revenue. Hence, the theory goes, any algorithm with a given block reward will be equally "wasteful" in terms of the quantity of socially unproductive activity that is carried out in order to try to get the reward.

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless1.png)

Yep.

Vitalik’s phrase “equally efficient” is vague, but fortunately he clarifies it to mean “equally wasteful”. So, we’re back in business.

### Vitalik Seeks a Work-Independent Protocol

> There are three flaws with this: > It's not enough to simply say that marginal cost approaches marginal revenue; one must also posit a plausible mechanism by which someone can actually expend that cost. For example, if tomorrow I announce that every day from then on I will give $100 to a randomly selected one of a given list of ten people (using my laptop's /dev/urandom as randomness), then there is simply no way for anyone to send $99 to try to get at that randomness. Either they are not in the list of ten, in which case they have no chance no matter what they do, or they are in the list of ten, in which case they don't have any reasonable way to manipulate my randomness so they're stuck with getting the expected-value $10 per day.

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless2.png)

Vitalik correctly notes that there must be a “plausible mechanism” to turn work into blocks. In other words, there must exist a f1 of type { work –> result }. We might call this the “workability” of the protocol – the extent to which it can be “worked”.

However, Vitalik ignores that [I address this here](http://www.truthcoin.info/blog/pow-cheapest/#is-a-work-independent-protocol-possible) by saying that, in a peer to peer network, all f’s that map to result (ie, every f which { ?? –> result } will have an input which is work related. In other words, the f1 in question will always exist. All protocols are “workable”.

Amazingly, Vitalik gives an example which is so bad, it almost proves my point by contradiction. He uses “my [Vitalik’s] laptop’s /dev/urandom” as an example of something which cannot be “worked”. His example cannot be worked, **because and only because it is not P2P** – it is a trusted 3rd party source of randomness.

(In practice it is not even true that his scenario is “unworkable”, as a prospective “worker” could try to bribe Vitalik, or could try to hire people to track down his laptop’s physical location and then take it from him at gunpoint).

> MC => MR does NOT imply total cost approaches total revenue. For example, suppose that there is an algorithm which pseudorandomly selects 1000 validators out of some very large set (each validator getting a reward of $1), you have 10% of the stake so on average you get 100, and at a cost of $1 you can force the randomness to reset (and you can repeat this an unlimited number of times). Due to the central limit theorem, the standard deviation of your reward is $10, and based on other known results in math the expected maximum of N random samples is slightly under M + S * sqrt(2 * log(N)) where M is the mean and S is the standard deviation. Hence the reward for making additional trials (ie. increasing N) drops off sharply, eg. with 0 re-trials your expected reward is $100, with one re-trial it's $105.5, with two it's $108.5, with three it's $110.3, with four it's $111.6, with five it's $112.6 and with six it's $113.5. Hence, after five retrials it stops being worth it. As a result, an economically motivated attacker with ten percent of stake will inefficiently spend $5 to get an additional revenue of $13, though the total revenue is $113. If the exploitable mechanisms only expose small opportunities, the economic loss will be small; it is decidedly NOT the case that a single drop of exploitability brings the entire flood of PoW-level economic waste rushing back in. This point will also be very relevant in our below discussion on capital lockup costs. Proof of stake can be secured with much lower total rewards than proof of work. What about capital lockup costs?

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless3.png)

Here, Vitalik gives an example where a blockreward can be “worked” in two ways. The second (“forcing a reset”) is irrelevant, but this is the one which he carefully elaborates. But the first “capital lockup costs” is relevant, and it is de-emphasized.

My simple equation does not require that the “workers” attack the system. If the total reward is $1000, then the total waste will be $1000, and it will *all* take the form of capital lockup costs. This would still be true (ie, I would still be right), if it were *impossible* to reset the randomness.

For Vitalik has neglected the “very large set”. It will indeed be very large, and it will be very very wasteful. Capital which is attempting to be staked must, necessarily be “locked up” to at least a minor extent. And if this is not the case in the protocol, it is the case in practice – money that is waiting to be staked cannot be turned toward other purposes. The fact that these “bonds” might be very short-term, will only make them more convenient which will only make the “very large set” even larger – and more wasteful. Instead of two medium numbers multiplied together, we will have a small number multiplied by a large number (but the product will be the same).

If these funds are not officially regarded as “staked” (ie, locked for a full year), we might call them “prestaked” for a day, or an hour. Instead of buying PoW lottery tickets, they will buy prestake PoS lottery tickets in order to win the privilege of becoming a validator.

There are other problems, but they distract from the overall message of MC=MR. Instead, just imagine the total reward is $1000, and that the randomness can not be messed with. In such a case, individuals will tend to invest (“stake”, or “prestake”) a marginal dollar, until the MC=MR, as I suggest. Imagine it were any other way, for example that MC<MR? This would imply that the first person to invest $1 in staking (in joining the “very large set”) would get an expected return of more than $1. So, this will obviously draw more capital in.

Vitalik’s example assumed that Waste = Attack. But this is not necessarily the case; if Attacks = 0 then Waste will just equal regular Work.

> lower total rewards

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless4.png)

We’ll get back to this “security” claim later.

### The Waste-Equivalence Argument, Restated

> Locking up X ether in a deposit is not free; it entails a sacrifice of optionality for the ether holder. Right now, if I have 1000 ether, I can do whatever I want with it; if I lock it up in a deposit, then it's stuck there for months, and I do not have, for example, the insurance utility of the money being there to pay for sudden unexpected expenses. I also lose some freedom to change my token allocations away from ether within that timeframe; I could simulate selling ether by shorting an amount equivalent to the deposit on an exchange, but this itself carries costs including exchange fees and paying interest. Some might argue: isn't this capital lockup inefficiency really just a highly indirect way of achieving the exact same level of economic inefficiency as exists in proof of work? The answer is no, for both reasons (2) and (3) above.

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless5.png)

Let me restate my argument by comparing and contrasting PoW and PoS.

In PoW, you do the following: borrow $W1 money at rate r, buy a bunch of equipment and electrical power, earn BTC, and then liquidate everything and repay what you can, which is $W2 (which is very little, possibly zero). You have come up short, spending a total of $A = (W1*R)-W2 , but meanwhile you have earned $A worth of BTC.

(note: R = (1+r), the loan factor)

In PoS, you do the following: you borrow $S1 money at rate r, “stake it” (ie lock it away for a year, or a day or whatever), earn ETH, get the staked funds back, and repay the loan, which is $S1. But because interest rates were not zero, you still come up short. You invested a total of $B = (S1*R)-S1 , but earned $B worth of ETH.

```
In PoW, you paid cost_w = (W1*R)-W2 .
In PoS, you paid cost_s = S1*r .
In PoW you received benefit_w = $A worth of BTC.
In PoS you received benefit_s = $B worth of ETH.
```

This is all quite basic, and possibly undisputed.

The point I have made since Nov 2014, is that the second half of each sentence drives the first (ie “earned $B worth of ETH” determines how much total money is deployed in “borrow $S1 money”). And therefore the social waste per block will equal the block’s value.

If the benefit of mining, or of stake-ing, is higher then the cost, more people will do it. In practice there is no way to prevent people from staking (where this is defined as: joining the “some very large set” above). At least, there is no P2P way, because all are equal peers, and so no one has the privilege of denying someone entry.

So, if a blockchain currently emits X = $A worth of value in each block, then this blockchain gains nothing by switching to proof of stake. For a given X = $A, all four quantities would be the same: cost_w = cost_s = benefit_w = benefit_s . They are all equal to $X (call it: the “critical $X”).

I really have no idea if Vitalik disputes any of the above facts (which are all that I require to prove my “equally wasteful” thesis).

### Waste is Different From Security

Now, we return to the point that we passed over earlier.

Below, Vitalik argues that the *security*, ie what an attacker would have to pay, is different under PoW and PoS. Specifically, he summarizes it (correctly) as “[the above] serves to show…that PoS gets more bang for its buck in terms of security”.

> Let us start with (3) first. Consider a model where proof of stake deposits are infinite-term, ASICs last forever, ASIC technology is fixed (ie. no Moore's law) and electricity costs are zero. Let's say the equilibrium interest rate is 5% per annum. In a proof of work blockchain, I can take $1000, convert it into a miner, and the miner will pay me $50 in rewards per year forever. In a proof of stake blockchain, I would buy $1000 of coins, deposit them (ie. losing them forever), and get $50 in rewards per year forever. So far, the situation looks completely symmetrical (technically, even here, in the proof of stake case my destruction of coins isn't fully socially destructive as it makes others' coins worth more, but we can leave that aside for the moment). The cost of a "Maginot-line" 51% attack (ie. buying up more hardware than the rest of the network) increases by $1000 in both cases. > >Now, let's perform the following changes to our model in turn: > > Moore's law exists, ASICs depreciate by 50% every 2.772 years (that's a continuously-compounded 25% per annum; picked to make the numbers simpler). If I want to retain the same "pay once, get money forever" behavior, I can do so: I would put $1000 into a fund, where $167 would go into an ASIC and the remaining $833 would go into investments at 5% interest; the $41.67 dividends per year would be just enough to keep renewing the ASIC hardware (assuming technological development is fully continuous, once again to make the math simpler). Rewards would go down to $8.33 per year; hence, 83.3% of miners will drop out until the system comes back into equilibrium with me earning $50 per year, and so the Maginot-line cost of an attack on PoW given the same rewards drops by a factor of 6. > Electricity plus maintenance makes up 1/3 of mining costs. We estimate the 1/3 from recent mining statistics: one of Bitfury's new data centers consumes 0.06 joules per gigahash, or 60 J/TH or 0.000017 kWh/TH, and if we assume the entire Bitcoin network has similar efficiencies we get 27.9 kWh per second given 1.67 million TH/s total Bitcoin hashpower. Electricity in China costs $0.11 per kWh, so that's about $3 per second, or $260,000 per day. Bitcoin block rewards plus fees are $600 per BTC * 13 BTC per block * 144 blocks per day = $1.12m per day. Thus electricity itself would make up 23% of costs, and we can back-of-the-envelope estimate maintenance at 10% to give a clean 1/3 ongoing costs, 2/3 fixed costs split. This means that out of your $1000 fund, only $111 would go into the ASIC, $55 would go into paying ongoing costs, and $833 would go into hardware investments; hence the Maginot-line cost of attack is 9x lower than in our original setting. > Deposits are temporary, not permanent. Sure, if I voluntarily keep staking forever, then this changes nothing. However, I regain some of the optionality that I had before; I could quit within a medium timeframe (say, 4 months) at any time. This means that I would be willing to put more than $1000 of ether in for the $50 per year gain; perhaps in equilibrium it would be something like $3000. Hence, the cost of the Maginot line attack on PoS increases by a factor of three, and so on net PoS gives 27x more security than PoW for the same cost. > The above included a large amount of simplified modeling, however it serves to show how multiple factors stack up heavily in favor of PoS in such a way that PoS gets more bang for its buck in terms of security. The meta-argument for why this perhaps suspiciously multifactorial argument leans so heavily in favor of PoS is simple: in PoW, we are working directly with the laws of physics. In PoS, we are able to design the protocol in such a way that it has the precise properties that we want - in short, we can optimize the laws of physics in our favor. The "hidden trapdoor" that gives us (3) is the change in the security model, specifically the introduction of weak subjectivity.

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless6.png)

In *may* be the case that PoS gets more bang for its buck, which is to say that PoS gets more “security” per blockreward value (ie, per “critical X”, or per “wasted” dollar), than would PoW.

(This is exactly the argument that Jae Kwon of Tendermint retreated to, after admitting that PoS was indeed just as wasteful as PoW.)

In my 2015 article, [I emphasize](http://www.truthcoin.info/blog/pow-cheapest/#example-1-tendermintcasper) that PoS is allowed to have different (probably worse) security assumptions than PoW:

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless7.png)

I highly doubt that PoS is more secure. Perhaps it is, but I still wonder what would happen in my original scenario:

1. Attacker …purchases “used” private keys
2. …executes a large long-range NaS attack (making a trillion fake histories, that all look very very similar to each other) [cost: ~free],
3. …threatens to imprison/kill anyone who tries to point out which history is real [cost: mafia connections, law enforcement, or a couple million $$]).

I think it is hard for Vitalik to both [a] constantly tell us which PoS chain we should be on, and [b] constantly evade capture by the mob / world governments / private investigators.

And, last I heard, there were all kinds of scalability / uptime problems with PoS, which again I am going to just ignore. (And these are just the known/theoretical problems – remember how much we have learned about PoW’s little quirks [block withholding, selfish mining, relay/broadcast strategy, ASICBoost, etc] in just a few years of using it in practice).

For now lets just say that PoS does indeed get more bang for its buck – this is *irrelevant* to my argument about waste. Even if PoS is more secure than PoW, it is still just as wasteful as PoW. The “buck” of PoS is the same as the “buck” of PoW, whatever their respective “bangs”.

What Vitalik is trying to say (I assume) is that, **since the security is lower**, we can then, safely, decrease the critical X.

However, this notion, **that one can control the critical X** is a fallacy that I (in 2015) purposefully [delayed handling](http://www.truthcoin.info/blog/pow-cheapest/#agenda)…

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless8.png)

…until [the end of the piece](http://www.truthcoin.info/blog/pow-cheapest/#the-coinbase-rot-paradox-less-is-more).

Since Vitalik already ignored it once, I’m not sure what good it will do to repeat it, but here goes!

### The Coinbase-Rot Paradox (Reprise)

> Trying to reduce waste only re-increases the waste, and vice-versa.

#### How PoS Might Cash In on the Additional PoS Security

Ethereum might want to take advantage of the supposed PoS security advantage, by decreasing its Critical X, and thereby being less “wasteful” than Bitcoin. But how might it do this? It must decrease the value of its blockreward!

```
Blockreward = C "coins released" * M "market price per coin".
```

Ethereum can’t magically alter the market price (and if they could, they would hardly want to send it downward (!), as would be required in this case), so their only option is to try to decrease factor C, the quantity of Ethers released per block.

#### The Problem with That Strategy

First of all, I wonder if the PoS supporters know that Vitalik is essentially saying “we need to work on PoS so that we can achieve our goal of making sure that, relative today, a higher percentage of Ethers are mined in the future!”. Somehow I doubt it.

But there’s actually an even bigger problem. As I stated in my piece nearly *two years ago*, **moving C down will tend to move M up**, because:

1. Logically, the blockchain must start with 0 coins issued, and end with 100% of coins issued. Thus the blockchain-designer (ie Vitalik) can only control the speed of issuance – he may choose a big candle with a slow fuse, or else he may choose a short candle with a quick fuse.
2. Slowing the issuance speed, will cause today’s quantity of CryptoCoin issued per block to decrease. Hastening the issuance will necessarily require that more CryptoCoin be issued per block today.
3. The units of money are fractional (as Vitalik ought to know), which is why inflation is a tax, and why switching from dollars to cents (or to millicents) would not directly affect anyone’s net worth.
4. Thus, someone who buys into a slow candle will “own more money longer”. Someone who buys into a fast candle will own more money shorter. As a result, the market value of fast candle coins will be less than that of slow candle coins.

Item #2 is the “coinbase” part, and #4 the “rot” part of what I called the “Coinbase-Rot Paradox”.

And the paradox is likely to be quite strong.

#### Allow Me to Elaborate

Consider that society, in a given year, demands X amount of briefcases, and Y amount of refrigerators, and Z amount of money. If Ether were the only money in existence (ie, if no one used USD, gold, etc as money anymore), then public demand for it would total some amount (let’s call it “Sigma”, and let us measure it in purchasing power [as in $PPP]). So, the public wants Sigma$ worth of Ether to exist in the year 2017. In a world with fast Eth, the Eth price is Sigma$ / q_fast , but in a world with slow Eth, the Eth price is Sigma$ / q_slow .

q_slow is, paradoxically, growing at a faster rate, than q_fast!

```
q_fast :    4, 4, 2, 2, 1, 1, .5, .5 ;  [8 years, 15 total]
q_medium : 1.875, 1.875, ... , 1.875 ;  [8 years, 15 total]
q_slow :   .5, .5, 1, 1, 2, 2, 4, 4  ;  [8 years, 15 total]
```

Money supply growth rate in period 3:

```
g(q_fast, 3):    25%  (ie, 2/8)
g(q_medium, 3):  50%  (ie, 1.875/(1.875*2))
g(q_slow, 3):   100%
```

The math probably comes out to be a *complete* wash (in other words, that the Critical X cannot be altered *at all*), but perhaps not – I haven’t checked. I’m really not interested in this question, so perhaps you, the reader can put some thought into it. Perhaps there is an optimally slow issuance schedule.

Whatever the case may be, Vitalik/Kwon’s argument that “PoS is more secure” ends up translating only to a claim that “Bitcoin is *too* vulnerable to 51% attacks”. Even if every single one of their claims is correct (not likely), then the entire PoS project only amounts to a blockchain which is harder to 51% attack, but **otherwise equally wasteful of resources**. (Given that Bitcoin has been 51% attacked zero times, this would seem to be a dubious investment of resources.)

Let me repeat: the security level has *nothing* to do with my claim that PoW and PoS are equally wasteful. If Vitalik derives some rule for an optimally slow issuance schedule, then **someone could just plug that schedule into a PoW chain, and that PoW chain would have the same (lower) economic waste** (at an allegedly lower security level). Which is *my* point. Switching from PoW to PoS doesn’t matter. Both PoW and PoS will waste exactly the same amount: their Critical X.

So lowering the Critical X means that the protocol exhibits lower waste under PoS *and a lower waste under PoW*.

Because they’re THE SAME THING!!

### Other

Vitalik continues, so I suppose I will as well:

> Now, we can talk about the marginal/total distinction. In the case of capital lockup costs, this is very important. For example, consider a case where you have $100,000 of ether. You probably intend to hold a large portion of it for a long time; hence, locking up even $50,000 of the ether should be nearly free. Locking up $80,000 would be slightly more inconvenient, but $20,000 of breathing room still gives you a large space to maneuver. Locking up $90,000 is more problematic, $99,000 is very problematic, and locking up all $100,000 is absurd, as it means you would not even have a single bit of ether left to pay basic transaction fees. Hence, your marginal costs increase quickly. We can show the difference between this state of affairs and the state of affairs in proof of work as follows:

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless9.png)

In the above paragraph, Vitalik draws a marginal/total distinction…but it is (seemingly) on the wrong variable.

I am saying that, **to generate a block**, users will pour forth effort ($PPP) totaling that of the block’s sale value (in $PPP). If MC is below MR, more people will take advantage of this opportunity to earn free money. If MC is above MR, some people will cease this activity (as it is deleting their money). In equilibrium the MC=MR, as taught to all ECON 101 students.

Vitalik is saying that, **in pouring forth the effort**, users will care relatively less and less about each dollar locked up. Locking up the first 1% of their net worth (ie just 1%) will not “hurt” as much as locking up the last 1% (ie, all 100% of it).

In other words, I am saying that “the auctioneer is selling $100 worth of gold, and people will keep bidding on it until the price reaches $100”. And Vitalik is saying “well, you are so rich that you can easily spare some of these $20 bills you have lying around”.

There is no contradiction whatsoever between the points. Vitalik is simply looking at a different variable.

In fact, when he says:

> Hence, the total cost of proof of stake is potentially much lower than the marginal cost of depositing 1 more ETH into the system multiplied by the amount of ether currently deposited.

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless10.png)

If this were true, what it would actually mean is that *a higher quantity* of Ether would be locked up. So it would be *more* wasteful!

For example, imagine that annual Ethereum tx fees + block subsidy, for the whole year, total only $10,000,000. But also imagine that many Eth-users do not care to use their parked Ether *at all* in the next year. **All** of the indifferent Ether would be staked – call it 2 billion USD, at today’s prices. A 2 billion dollar investment can [guarantee](https://www.treasury.gov/resource-center/data-chart-center/interest-rates/Pages/TextView.aspx?data=yield) one at least 24 million dollars or so, but the PoS project is only bringing in 10 million. An additional 14 million has been wasted.

( Users could buy a forward contract to repurchase their ETH next year (at today’s prices), sell it all today, buy Treasury Bonds, earn 24 million, and execute the forward contract to repurchase their ETH. They would be exactly where they were today, but they would have 14 additional million USD. )

> Note that this component of the argument unfortunately does not fully translate into reduction of the "safe level of issuance". It does help us because it shows that we can get substantial proof of stake participation even if we keep issuance very low; however, it also means that a large portion of the gains will simply be borne by validators as economic surplus.

![](/assets/images/2017/m7/proof-of-stake-is-still-pointless11.png)

As stated above, I object to the possibility of “keeping issuance low” (which is the Coinbase-Rot paradox). And I disagree that there will be economic surplus. I think Vitalik is overestimating the size of these “gains” – they would be tiny breadcrumbs spread over a vast population of stakers. And staking *would* be annoying, and so per capital (or per staked $) there would likely be very low surplus.

As I pointed out in the original article, claiming that “it is very easy to stake” is analogous to claiming that “it is very easy to hash”. But **greater efficiency of mining equipment merely results in correspondingly greater hashing**. To see this, imagine two worlds in which the block reward is worth $100: inefficient and efficient. In the inefficient world, hashes cost $1/hash, but in the efficient world they cost $0.00001/hash. In both worlds, miners will spend $100 total – in the first, on 100 hashes; in the second, on 1,000,000 hashes.

### Summary

We have three major differences, as I see them:

1. Vitalik believes that “prestaked” funds do not count as “locked up”, even though funds cannot be used for two purposes at once.
2. Vitalik does not endorse the Coinbase-Rot paradox, for unknown reasons.
3. Vitalik continues to believe that staking is not a big deal because it is easy and convenient to do. I agree, but Vitalik does not reply to my argument that –if staking is indeed very easy and convenient– it will result in tremendously high rates of staking, resulting in great waste (and tiny rewards per staker).

We agree that PoS and PoW can have different security levels and different security models. Vitalik thinks he can trade off some of this security, in return for reducing waste, but he has not explained how he plans to do this to my satisfaction (ie, the C-R paradox). It is also unclear to me if this is even desirable (perhaps security is generally more important than ‘waste’).

I suppose that Vitalik’s strongest pro-PoS argument, would be to take the first objection and try to argue that ‘there is no investment which is comparable to pre-staking’, therefore, society does not have to forgo anything as it watches users compete with each other over where/how to temporarily lock their checking accounts. Vitalik could try to argue that he had created something new and valuable (the ultra-short duration investment) at exactly the same time that he had “wasted” it. This is similar to [Bram Cohen’s PoSPaT](https://www.youtube.com/watch?v=aYG0NxoG7yw&list=PLxiUDysqkJ9x6VsYjjphSA79pEHiMwdI_&index=16) which would make unused hard drive space valuable and then immediately consume (“waste”) this value.

However, this is difficult, as short-duration investments (eg, 4 week treasury bond, savings account for 1 month, commercial paper) already exist. And even if they did not exist today, ultra-short duration investments *could* be invented. Similarly, Bram’s examples would “re-become” wasteful if something like [Sia](http://www.truthcoin.info/blog/sia.tech) or (old-style) Wuala ever got off the ground.

### Conclusion

I go through the [PoS FAQ](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ) (where my arguments are mentioned) and reply, line by line.

I still do not believe that PoS represents a significant improvement over PoW. A world of PoS is still one of greater scarcity of capital, and a world of PoW is still one of greater scarcity of silicon/electricity. The dollar value (or gold value) of each of the two types of waste will tend to be exactly equal.

PoS is theoretically very similar to PoW. But in practice, we have more experience with PoW. A practical person would re-use what already works. However, PoS *very suspiciously* requires a team of highly skilled researchers to constantly be looking in on it. I continue to believe that this PoS research is itself a ‘waste’ of money and time, as it can’t really accomplish anything (and, in practice, doesn’t).

Add Disqus comments.

comments powered by

Disqus

***

{% include signup.md %}
