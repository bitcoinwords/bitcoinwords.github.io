---
title: "Hashing assurance contracts"
permalink: "/hashing-assurance-contracts"

author: mikehearn

tags:
  - Mike Hearn
  - 2015 Q2
  - Mining
  - Money
  - Inflation

excerpt: Hashing assurance contracts. Posted May 27, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Hashing assurance contracts](https://medium.com/@octskyward/hashing-7d04a887acc8)
### By Mike Hearn
### Posted May 27, 2015

A proposed model for post-inflation Bitcoin mining

Bitcoin Mining Farm / [Marko Ahtisaari](https://www.flickr.com/photos/moia/14266642578/) [CC-BY 2.0](https://creativecommons.org/licenses/by/2.0/)

One common objection to raising the block size limit is that it’s unclear how miners will be funded when Bitcoin’s money supply formula finally drops to zero. To quote [Thomas Voegtlin of Electrum](https://www.mail-archive.com/bitcoin-development@lists.sourceforge.net/msg07673.html),

> The discussion on block size increase has brought some attention to the
>
> other elephant in the room: Long-term mining incentives ……. proponents of the block size increase are conservative; they are trying to preserve the current regime, which is known to work, instead of letting the network enter uncharted territory.

> My problem is that this seems to lacks a vision ….. So here is my question, to both proponents and opponents of a block size increase:
>
> What steady-state regime do you envision for Bitcoin, and what is is your plan to get there?

Mining is currently funded by the creation of new bitcoins. Satoshi’s inflation formula is an astonishingly long term piece of planning — inflation halves every four years, so there is a very long time before the supply of coins dries up.

Gavin Andresen [points out](http://gavinandresen.ninja/when-the-block-reward-goes-away) that attempting to guess what will happen 20 or 30 years from now is optimistic, at best. And I fully agree. I think we need bigger blocks regardless of whether you agree with this article or not.

Still, it’s nice to have at least some answer to this question, even if the best laid plans tend to get abandoned much faster than is relevant here.

So this article describes my proposed solution: hashing assurance contracts.

#### The problem

Satoshi’s original idea is simple: as inflation dries up, people should start attaching transaction fees to make up the difference.

Unfortunately there’s a compelling argument that this might not work. The block chain is what economists call a [public good](https://en.wikipedia.org/wiki/Public_good). From Wikipedia,

> A
>
> public good
>
> is a
>
> good
>
> that is both
>
> non-excludable
>
> and
>
> non-rivalrous
>
> in that individuals cannot be effectively excluded from use, and where use by one individual does not reduce availability to others.

Put in plain English, the block chain is like a lighthouse. It costs money to build and keep the lighthouse operational, but once built there’s no way to stop ships from seeing the light. Thus there is a question of who pays for it. You cannot charge sailors because there’s no way to create a bright light that is invisible to freeloaders.

It may at first seem that the block chain isn’t like a lighthouse, because miners can refuse to mine a transaction that doesn’t have a high enough fee. But it doesn’t work like that: even if one miner refuses to accept a transaction into the chain, they must still process it if it is included by another.

So miners face the following conundrum. The cost of hashing is unconnected from how many transactions are in a block, so taking a transaction and collecting its fees costs you nearly nothing. You see a transaction that has a fee a bit lower than you’d ideally like, but still not zero. You could keep it around but not put it in a block, as a signal to the market that you want higher fees. But then you’re leaving money on the table. When another miner decides he’s OK with the lower price, you will have to process the transaction anyway, therefore, you might as well just take it.

This leads people to observe that they can attach a lower fee than they were doing, and transactions still work pretty much OK. Sure, they might take a bit longer to confirm, but there are really only two speeds that matter in payments: instant and not instant. If your transaction becomes a little bit more “not instant” and takes 40 minutes instead of 10, in practice that won’t affect the setup of most business payments much. So fee prices might enter some kind of downward spiral. And as mining becomes less profitable, miners will shut down hardware in order to regain their previous margins. Hash rate will fall. Wash, rinse, repeat.

#### Downward spiral. Really?

Well ……. maybe. Nobody knows. The argument above relies on the idea that people won’t pay to get faster confirmations, and miners won’t be able to resist including transactions no matter how little fee they attach.

This seems *plausible*, in that it *could* happen, but we don’t *know* it will work out that way. It may be that actually many people do care about the difference between waiting 1 block or 10, and that miners happily set a high fee threshold and stick to it (effectively constraining supply).

This article is about what happens if the downward spiral situation does play out.

#### How much is too much?

One key problem here is there’s no amount of hashing that’s obviously just right. Is there too much mining going on today? Or too little? How would we even know?

The simplest answer is to measure double spending fraud. If double spending due to malicious miners forking the chain is too high then valuable people will drop out of the Bitcoin economy. In that case we can say there must be too little hashing. Of course, we hit the problem of what “valuable people” means, but let’s shelve that for now.

Currently we’re not seeing malicious miners double spending by forking the chain. So there’s too much effort going into mining. That matches our intuition — it’s hard not to see mining farms like in the picture above and wonder if the tiny Bitcoin economy really justifies it. We didn’t see double spending when mining was at half the current level, or a quarter, or even before that. Currently the Bitcoin community is being effectively taxed about $832,000 *per day* …. just to support mining! If this was being paid with transaction fees each Bitcoin payment would cost about $7.50, which is uncompetitive.

We’re not spending so much on mining because we really need it. It’s because printing money distorts behaviour. If you connect money printing to bank lending then you get too many mortgages and then a housing bubble. If you connect it to arbitrary mathematical puzzles, you get too much effort put into solving them.

If Bitcoin were a centrally planned economy we’d probably tamper with the inflation formula at this point to try and reduce the waste. But that’d just bias the system more heavily towards early adopters. Every choice has a cost — so may as well stick with the devil we know, safe in the knowledge that Satoshi made inflation a temporary problem.

But eventually the ball-and-chain of the inflation formula will disappear, and the choice of how much mining we need will be up to us. Then what?

#### Who cares about blocks, really?

A slippery aspect of the Bitcoin protocol is that whilst it’s the receiver of a transaction that cares about double spending risk, it’s the sender who pays the fee.

Different transactions carry different levels of fraud risk. So different participants want different amounts of mining. In that spectrum there should be *some* kind of level that’s acceptable to the largest number of people, but how to discover what that is?

A simple algorithm is as follows:

1. Do some trading.
2. If you experience no double spending, lower the amount of money you’re contributing towards hashing.
3. Once you start to see significant losses due to double spending, raise it again until the losses are acceptable.

That is probably a bit too simple — it may be better to lose some stuff to fraud than pay more towards mining. But you get the idea.

The sticking point is the “money you’re contributing” bit. Contributing how, exactly? If you don’t contribute your transactions will still clear, so why would you do that? If you do, your competitors will ride for free.

In a nutshell, this is the problem of funding public goods.

#### Assurance contracts

An assurance contract, more often called a crowdfund, is supposed to be a solution to the problem of funding public goods. Recall the lighthouse. We solve it like this:

1. Someone with good reputation decides that a lighthouse would be useful, and becomes an entrepreneur.
2. He/she calculates the cost of building it and asks every passing ship to pledge to the project. The pledge is only claimed if and when enough money is raised.
3. The size of the pledge is chosen by the pledgor, based on how much they want it and how much they think other people might contribute.

If most sailors don’t really care in the end, the project won’t get funded. If they care but think they can get away with letting their competitors fund it, the project may well end up not funded at all. Eventually some of them will break the deadlock.

This is of course the Kickstarter model. And there’s already a way to do it on the block chain using Bitcoin protocol features, using an app I wrote called (guess what?) [Lighthouse](https://www.vinumeris.com/lighthouse).

Can we apply similar technology to the problem of funding mining? I think the answer might be yes. Here’s how it’d work.

#### HACs (hashing assurance contracts)

We start by creating a new, independent peer to peer network. This network links people with an interest in seeing mining happen i.e. merchants, exchanges etc. Anyone can use the network to throw out a contract for N BTC and solicit pledges for it. Once the bitcoins are gathered, they are allocated to miners via pure-fee paying transactions.

Take a merchant that’s in the business of moving gold. They need a lot of mining to be viable: let’s say 1 petahash. They know from experience that with anything less than that, there’s some malicious miner out there that will fork the chain in order to double spend against them. They know that it costs at least 1 BTC per block to incentivise that much mining. So, they go onto the new p2p network and look for a contract for that much. If one exists (or is close enough), they join it by pledging. If none exists, they create one.

The technical details aren’t exciting so I’ll gloss over them here, but suffice it to say the Bitcoin protocol (with some small extensions) can be used to do all this in a trust-free manner. You don’t have to know who you are co-operating with to fund the mining. You’d just run a simple app that prints an address in a local wallet. You’d specify how much mining you need, and how much you’re willing to contribute, and then fill up the apps wallet. It would go off and autonomously spend your money to try to make that happen. When it ran out, it’d send you an email so you could fill it back up again. Contributing to mining would become a cost of business. If enough people did it, the cost could be fairly low.

There might be multiple contracts outstanding simultaneously.

Say our gold merchant needs at least 1 BTC’s worth of mining. But another needs less, they only need 0.5 BTC’s worth. The second merchant doesn’t care which contract completes: either will do. Luckily, the assurance contract protocol allows the second merchant to double pledge the same money: he can take part in any contract higher than his required amount, and whichever contract completes automatically invalidates the pledge to all the others.

A sufficiently smart mining agent might use all sorts of market theories to try and get people the best deal. Out of all the individual agents interacting in a p2p free market soup, some kind of consensus on the “right” amount of mining should appear, based on how much people are willing to pay. Transaction fees are still used, but only a few transactions will carry huge fees. The rest may contain fees close to zero, or no fee at all. Miners would include them anyway either to claim the free fee money and/or because the circulation of those coins is needed for merchants to be able to build the assurance contracts in the first place.

#### Conclusion

People want mining and they want to work together to get it. I think a decentralised P2P assurance contract system would be a neat way to solve this in the distant future, but in case it doesn’t work for some reason other ways would be found.

***

{% include signup.md %}
