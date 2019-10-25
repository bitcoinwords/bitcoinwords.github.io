---
title: "Envisioning LSPs in the Lightning Economy"
permalink: "/envisioning-lsps-in-the-lightning-economy" 

author: roysheinfeld

tags:
  - Roy Sheinfeld
  - CY19 Q3
  - Lightning
  - Economy
  - Lightning Service Providers
  - LSP
  - Scaling
  - L2
  - Layer 2

excerpt: Roy Sheinfeld shares a vision of a Lightning enabled future and what Lightning Service Providers might look like. Posted Septemeber 25, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

# [Envisioning LSPs in the Lightning Economy](https://medium.com/breez-technology/envisioning-lsps-in-the-lightning-economy-832b45871992)
### By [Roy Sheinfeld](https://twitter.com/Breez_Tech)
### Posted September 25, 2019

[Our recent post about Lightning Service Providers](https://medium.com/breez-technology/introducing-lightning-service-providers-fe9fb1665d5fhttps://medium.com/breez-technology/introducing-lightning-service-providers-fe9fb1665d5f) has generated plenty of feedback. (Your attention is flattering.) Many people in the Lightning community have responded with something along the lines of:

> “Sure, we get the structural necessity of LSPs in the network, and it’s nice to have a catchy term for these entities, but we don’t understand how LSPs are actually going to work _in practice_. Who are they? What’s their incentive structure? How do they work as businesses?”

Glad you asked. We’ve been thinking about these questions a lot lately, and I’d be happy to share our ideas to help concretize LSPs and the Lightning economy more generally.


![](/assets/images/cy19/cy19m9/rs-1.png)
<cite>Some startups have hammocks and ping-pong tables. We think the old fashioned way. On our chins. (Source: [Wikimedia](https://commons.wikimedia.org/wiki/File:The_Thinker,_Auguste_Rodin.jpg))</cite>

## Quick recap: what’s an LSP again?

[LSPs](https://medium.com/breez-technology/introducing-lightning-service-providers-fe9fb1665d5fhttps://medium.com/breez-technology/introducing-lightning-service-providers-fe9fb1665d5f) provide Lightning users with network services. These services include things like routing, guaranteeing uptime, SLAs, rebalancing channels _with_ _other LSPs_ to keep the network fluid, and — perhaps most importantly — opening funded channels.

To understand why these functions are so vital, let’s think backward from the endpoint of a functioning Lightning economy. Yes, Lightning already works very well for a nascent technology. But to expand from thousands of users to billions, we need to simplify and streamline the onboarding process. It’s not enough to be more convenient and attractive than bitcoin; we have to make Lightning more convenient and attractive than fiat.

For example, fiat users are accustomed to having access to their funds and being able to receive payments immediately. Waiting ten seconds at a card reader when making a purchase on a busy shopping day is considered an inconvenience. Fiat banks have buried routing deep in their backend via [SWIFT](https://fin.plaid.com/articles/what-is-swift/), leaving users in blissful ignorance of its complexity. Fiat and banks have had years, decades, centuries to streamline their UX and move the complexity of the system into the backend.

Lightning has to do the same, and LSPs are the way to do so at scale. Functions like rebalancing, opening funded channels, and guaranteeing uptime are services LSPs have to provide to let users just be users, not network admins.

A few months ago, [I quoted Alfred North Whitehead](https://medium.com/breez-technology/breez-open-beta-lightning-fast-bitcoin-payments-no-compromises-14fabca76396?source=collection_home---2------12-----------------------), who said that “Civilization advances by extending the number of important operations which we can perform without thinking about them.” The Lightning Network advances by extending the number of important operations users can perform without thinking about them. LSPs multiply users’ capabilities while reducing demands on their time and expertise.

If you want a Lightning economy, you need onboarding, and LSPs are how to make it happen.

## Do any LSPs exist yet, and if so, who are they?

Yes, LSPs exist. They’re here. They’re among us. One of them is sharing his ideas with you right now.

![](/assets/images/cy19/cy19m9/rs-2.gif)
<cite>Remember: anybody could be an LSP. Are you listening, or were you paying attention to the LSP in the red dress? (Source: Warner Bros. Studios)</cite>

At the moment, LSPs are those few firms developing Lightning clients, providing services, and running nodes. They just offer different selections of user services.

For example, [Eclair](https://github.com/ACINQ/eclair-mobile) runs a node, opens channels under certain conditions, and provides a wallet app. Bitrefill’s [Thor](https://www.bitrefill.com/thor-lightning-network-channels/?hl=en) opens channels with inbound liquidity for users, which they can access by a third-party wallet app. Their up-market [Thor Turbo](https://www.bitrefill.com/buy/turbo-lightning-channel/?hl=en) service also provides users with some outbound BTC liquidity … for a price. [LNBIG](https://lnbig.com/#/) and [LightningTo.me](https://lightningto.me/) open channels with users’ existing wallets, giving them varying amounts of inbound capacity. [Olympus](https://medium.com/@JimmyMow/announcing-olympus-lightning-enabled-fiat-ramps-by-zap-1f5349a96ee9) and [Sparkswap](https://sparkswap.com/) open channels for users and let them buy bitcoin with fiat, depositing the satoshis directly into the users’ payment channels. (More on these last two below.)

[Breez](https://breez.technology/) opens pre-configured, non-custodial channels, provides a full-service wallet app, gives users incoming liquidity at no extra charge, lets users manage all their bitcoin from a single balance, publishes a highly informative and entertaining blog, and is kind to small children and puppies.

This list is illustrative, not exclusive. There are more, and we’re not trying to make a point by leaving anybody out.

## Incentives for first-generation LSPs

Innovation takes a certain kind of attitude. I mean, we’re all doing okay, so the conventional wisdom would be not to change a running system, right? Innovators need the audacity to look at a running system and to say to themselves, “Nope, this could be better.”

Different people investing their time and energy into starting an LSP might have any number of different motives. Some might see a chance to get rich by riding the growth of the Lightning economy, and others might believe in bitcoin and its potential to change the world for the better, sensing a duty and an opportunity to realize that better world. (Where do we stand? [Here’s a hint.](https://medium.com/breez-technology/why-breez-is-committed-to-bitcoin-b0418f86fec3))

![](/assets/images/cy19/cy19m9/rs-3.png)
<cite>Tradition is the beauty of the green grass beneath our feet. Progress is the result of trying to reach the greener grass on the other side. (Source: [Su — May](https://www.flickr.com/photos/su-may/6888459262))</cite>

Because Lightning is still so new and it’s still changing so fast, nobody has really cracked the formula yet. Nobody knows the best business model for LSPs. Indeed, there might be several viable, scalable business models for different kinds of LSPs servicing different niche markets. We’re just surveying what’s currently possible, concretizing our vision of the coming Lightning economy, and interpolating between the two.

Today’s LSPs are on the cutting edge. We’re the early adopters, the first movers, the cool kids on the Lightning network. Since we’re committed to — and certain of — [the coming Lightning economy](https://medium.com/breez-technology/breez-on-ios-a-big-step-towards-the-lightning-economy-and-a-giant-leap-for-breez-cbcf2db77acb), the time, effort, and coin we’re spending on building the network and our user base now is an investment in our future. The future is our incentive, and progress is our reward.

Speaking of the future…

## The second wave of LSPs

As the Lightning network and the Lightning economy grow, the LSP model will become more attractive. Indeed, for some current market actors, expanding their businesses into Lightning services will be a requirement for survival. A couple of existing business models will feel pressure to become LSPs in the next, say, one to three years. First are the exchanges. Second are existing payment apps, like Square’s [Cash App](https://cash.app/bitcoin) and Venmo.

Think about it: as the Lightning economy grows, bitcoin will gradually suck fiat out of the economy, and exchanging currencies is what exchanges do. Ergo “exchanges.” Existing bitcoin users are already familiar with exchanges, and many incoming fiat users will have to pass through an exchange before joining the Lightning economy. (Unless, of course, their LSP offers [a handy, in-app means](https://medium.com/breez-technology/breez-moonpay-the-easiest-way-to-buy-spend-bitcoin-on-lightning-3c40b3d3815a) to top-up their balances.)

Occupying the conduit between crypto and fiat, the exchanges won’t be able to miss the flow towards Lightning. And not expanding their services to take advantage of that position would be ludicrous.

In fact, as bitcoin expands to become the default medium of exchange with Lightning as its medium, exchanges are going to face a very busy transition period, after which, however, they’re going to need a new business model. In the absence of fiat, there won’t be as much left to exchange. Expanding their offerings to include LSP services would be a natural, rational way to master the transition.

Further, running an exchange is also a capital-intensive undertaking. They need to have bitcoin on hand anyway, but bitcoin doesn’t accrue interest. Now, if the exchanges could put some of that bitcoin into funding users’ channels, they could even make some money on the bitcoin that would otherwise just be sitting around collecting digital dust.

The proof of exchanges’ interest in the LSP model is in the fact that a couple of them _are already doing it_. [Sparkswap](https://sparkswap.com/) and [Olympus](https://medium.com/@JimmyMow/announcing-olympus-lightning-enabled-fiat-ramps-by-zap-1f5349a96ee9) let users purchase bitcoin with USD, so they’re exchanges. But they also open channels for users, like LSPs. Sparkswap opens users’ channels immediately (just like Breez), and Olympus opens the channel when the user buys bitcoin through a Turbo channel. They’re effectively exchanges that offer Lightning services as well.

As for the payment apps, integrating Lightning as the preferred means of transferring everyday quantities of bitcoin is a natural progression from their existing businesses. Cash App _already_ facilitates bitcoin transfers (well, sort of, because it’s custodial, so it’s [not really bitcoin](https://medium.com/breez-technology/bitcoin-is-peer-to-peer-or-it-is-nothing-3ec724c1c0e?source=collection_home---2------6-----------------------), is it?). Lightning is simply a better way to do what they’re already doing.

## The evolving LSP business model

When the exchanges enter the LSP space, we can expect more attention and more entrants to join the party. We’re all used to bandwagons by now, right? But that’s a good thing because it means that more people will start experimenting with more different kinds of LSP models. Some might be very large and serve hundreds of thousands of users; others might be very small and might only service a few dozen friends. The LSP model scales in both directions, up and down, which is great for decentralization.

The Lightning economy needs many people to help cultivate it, and decentralization has always been in bitcoin’s DNA, so this trend is good for all of us and good for bitcoin.

At this stage, growth (read: onboarding) is the name of the game. A number of business models are thinkable for LSPs with sufficient capital. Each has to balance cost with scalability, onboarding with revenue.

![](/assets/images/cy19/cy19m9/rs-4.png)
<cite>If everyone jumps on the same bandwagon, it’s a revolution. (Costumes optional) (Source: [Wikimedia](https://commons.wikimedia.org/wiki/File:Circus-Parade_white-bandwagon_Jul09.jpg))</cite>

## Freemium models

Now, if a firm is entering an existing but very promising space with incumbent, pioneering competitors, it’ll need to catch up with and then surpass that competition. It has to grow faster than the existing providers, just like Spotify, Medium, Dropbox, and Skype have done in their respective markets. They started with good, competitive products, and _gave them away_ — at least their basic functions or in some limited quantity.

The LSP business also lends itself to such freemium models. Since Lightning allows for transaction fees, a “free” service would effectively run on a pay-as-you-go basis, charging users transaction fees that are high enough to cover their costs. Limits on, say, channel capacities would also help contain the LSPs’ costs and provide users with an incentive to upgrade.

Such free user plans would be great for private users who want to experiment with Lightning before committing to a paid plan or for users who require limited capacity and a low-cost service (e.g. students). However, other classes of users, like businesses, will need better service, optimal reliability, more flexible capacity, and they’ll also be willing to pay for it.

In order to serve clients who need enterprise-grade performance, there will also be a market for paid, premium LSPs. Premium services could include higher channel capacities, higher transaction volumes, lower fees, SLA-guaranteed provision quality, and so on in exchange for a flat monthly fee.

## Upselling

We’ve all seen those ads for phones that only cost $1. It’s also the case that you can usually buy bananas in grocery stores in the northern hemisphere for less than the cost of shipping them thousands of kilometers. These providers can lose money on phones and bananas because they make far more on the mobile contracts and laundry detergent they sell to those same customers.

Perhaps counterintuitively, such [loss leaders](https://en.wikipedia.org/wiki/Loss_leader) can be rational and profitable because they attract customers to associated products or services with higher margins.

![](/assets/images/cy19/cy19m9/rs-5.png)
<cite>An in-app marketplace in practice. More revenue streams = faster growth = accelerating progress.</cite>

LSPs could pursue a similar strategy by offering some services for free, like opening and funding channels, as long as users commit to using other services, like exchanging, for a price. If the margin on the profitable services and the user volume are sufficiently large, the LSPs can afford to offer some services for free. Indeed, they might even have an incentive to do so at scale.

Having users’ attention when they’re paying and making transactions is also a valuable commodity in itself. There is no reason why LSPs have to restrict their business models to their own services. They can also sell _products_ and third-party services. More specifically, why not let users purchase directly from an in-app marketplace? Doing so requires another button in the app and perhaps a few B2B partnerships, but LSPs are working on that kind of thing anyway.

Additional revenue streams, like in-app marketplaces, also help to increase customer lifetime value (CLV). That’s an important consideration, since services like opening funded channels increase the customer acquisition cost (CAC) — at least in the very short term. What matters, though, is the overall [CAC:CLV ratio](https://simplicable.com/new/cac-to-clv), so raising the CAC is not a bad thing if doing so raises the CLV even higher.

## LSPs in a maturing Lightning economy

Once the second wave has hit, we can expect “LSP” and “the Lightning economy” to be household terms, even if many people aren’t entirely sure how they work — much like bitcoin now. At that point, the banks will be sweating because the entire economy will be excising the middlemen. So who would be the next entrants into the LSP market? Who would stand to gain from widespread disintermediation?

In a word: everyone. It’s hard to estimate what the banking system costs the world, but a decent first estimate is to add up the value of all the world’s banks. They’ve been able to amass around [$124 trillion in assets](https://notesmatic.com/2017/01/value-chain-analysis-of-the-banking-industry/#targetText=However%2C%20the%20U.S.%20banks%20are,financial%20crisis%20at%2011.83%20percent.), a number that grows somewhere around 10% per year. That’s the size of the pie that stands to be recut. And LSPs are the knives.

![](/assets/images/cy19/cy19m9/rs-6.png)
<cite>Mmmm. Slicing the pie. Is this the first pastry analogy we’ve used? No. Is it possible that I have a thing for sweet, delicious pastries? Maybe. (Source: [skeez](https://pixabay.com/photos/pumpkin-pie-dessert-food-baked-1041330/))</cite>

That pie is big enough for everyone to have a slice, so the LSP market is sure to flourish. The range of small-scale LSPs is likely to expand rapidly, but they won’t be the only ones.

Other things being equal, those companies with the greatest transaction volumes — excluding banks — will be the ones with the greatest incentive to foster the Lightning economy. Those with vast user bases will also have an advantage in entering the LSP market. So which businesses have vast user bases and process vast quantities of transactions? The [FAANG](https://www.investopedia.com/terms/f/fang-stocks-fb-amzn.asp) crew (possibly without Facebook, pending the fate of Libra) come to mind, and they are likely to join the third wave of LSPs.

## Third-wave business models

The image in the crystal ball gets fuzzier the farther forward we look. Business models might be as diverse as the scales of the actors providing LSP services. Small LSPs might rely on personal contacts and low overheads, like a corner barber shop. Medium-sized ones might rely on custom localizations and brand tie-ins, like many current franchise operations. The largest have vast opportunities to onboard their current users while cutting costs and expanding their revenue streams.

To imagine a big tech player entering the LSP business, consider a company like Netflix. In 2018, Netflix had around [140 million subscribers](https://www.statista.com/statistics/250934/quarterly-number-of-netflix-streaming-subscribers-worldwide/), and their gross sales were around [$18 billion](https://www.marketwatch.com/investing/stock/nflx/financials). Imagine the number of transactions involved and the magnitude of transaction fees they had to remit to banks. If Netflix wanted to set up an LSP, they could pay for the R&D out of petty cash, and they could maybe save a few hundred million per year by disintermediating all those payments. Considering what banks currently make, a company like Netflix could soon be generating more revenue from a growing FinTech arm than they do from their traditional video-on-demand business.

In the third wave, scale will remain important, as always. But the key is always to find the right solution for the niche. Some people prefer processed cheese from a factory; others prefer artisanal Chesires ripened strictly in the cold months. We’re eager to see where the Lightning economy goes, and we’re excited to be growing along with it.

![](/assets/images/cy19/cy19m9/rs-7.png)
<cite>Like the sunrise, the fact that the Lightning economy is coming is more important than the exact timing. And they’re both beautiful to watch. (Source: [Rohit Gangwar](https://www.pexels.com/photo/silhouette-of-mountains-during-sunrise-904268/))</cite>

***
