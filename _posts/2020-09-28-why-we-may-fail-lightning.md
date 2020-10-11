---
title: "Why we may fail Lightning"
permalink: "/why-we-may-fail-lightning"

author: antoineriard

tags:
  - Antoine Riard
  - 2020 Q3
  - Lightning Network
  - Politics
  - Tribes

excerpt: Antoine Riard explains why Lightning might be doomed or what we can do to push the stack forward. Posted September 28, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Why we may fail Lightning](https://medium.com/@antoine.riard/why-we-may-fail-lightning-ee3692de1a55)
### By [Antoine Riard](https://medium.com/@antoine.riard)
### Posted September 28, 2020

A number of years have passed since I started contributing to Bitcoin protocol development. First on Rust-Lightning, then also on Bitcoin Core. I’ve been lucky to work on these projects full-time for the previous year, and it is a good opportunity to reflect on how Bitcoin is doing thus far.

It is a frenzied and noisy environment, and at times you need to reflect and evaluate your roadmap for future Bitcoin contributions. Otherwise, you will quickly get lost and finish each day without making the desired progress.

Let’s get started by honestly looking into the Lightning infrastructure. Then diving into the exciting fringes of Bitcoin and what the different Bitcoin tribes stand for today. It might help us cast a light on the perpetual challenge of bringing Bitcoin to the masses.

## The State of the Lightning Network

Lightning is considered as the flagship of Bitcoin innovation and for good reason. A few years ago it was just a wild dream on a whiteboard, and now you can interact with thousands of LN users all around the world without caring about bank clearing hours or segregated payment networks.

That said, let’s dig into the true state of its infrastructure.

Lightning is binding to a blockchain-as-a-judge model. Namely, a set of transactions binding a contract between participants. In the case of misbehavior the blockchain serves as a judge. The case will be adjudged using the plaintiff’s cryptographic proofs. This is a completely different model than the first layer one.

On the base layer, coalitions of full-nodes will protect your coins against miners misbehaving, assuming you’re sharing the same consensus rules. On off-chain layers, other peers don’t care about your counterparty misbehaving. The double spend problem within your channel is a private matter.

This model presents a new class of attacks on your Lightning node. Your counterparty may try to [burn in fees](https://lists.linuxfoundation.org/pipermail/lightning-dev/2020-June/002735.html) your channel balance. Or exploit the public nature of the base layer to [block](https://github.com/t-bast/lightning-docs/blob/master/pinning-attacks.md) your channel close attempts. Or leverage [malleability](https://lists.linuxfoundation.org/pipermail/lightning-dev/2020-September/002796.html) to break the contract semantics. Or directly [attack](https://arxiv.org/abs/2006.01418) your full-node associated with your Lightning one.

Further, your fee-estimator also becomes a [critical component](https://github.com/spesmilo/electrum/issues/6027) for the safety of your funds. Holistic network behaviors like [mass channel closing](https://arxiv.org/pdf/2006.08513.pdf) could break your security. It should be also remembered that Lightning keys are [hot](https://medium.com/@devrandom/securing-lightning-nodes-39410747734b), with all the challenges that presents.

Sadly most of the attack vectors laid out above are practical today. A subset of them are inter-dependencies with the base layer and need work at this level to be mitigated.

We should remind that Bitcoin protocols won’t be immune to DAO-like failures by the holy spirit of Satoshi. At this point, onboarding millions of users on the network is most likely to produce one of two outcomes.

Either, the whole network burns in flight due to a number of exploited securities issues, greatly impacting the long term public confidence in the platform’s trustworthiness. Or after the first wave of serious attacks, network operators double down on requiring strong identification before any channel opening, using the existing public key infrastructure. This grandly leads to centralization.

None of these scenarios is appealing. Honestly, we would all be heartbroken if we were to end there after all our hard efforts.

On the privacy side, things looks better on paper. The fact is we have to take a [cross-layer approach](https://arxiv.org/pdf/2007.00764.pdf), and it might not be as good as expected. For now, Lightning transaction format makes onchain channel openings [obvious](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-February/017633.html). Balances are [leaked](https://arxiv.org/pdf/2004.00333.pdf) for routing peers which opens the door to traffic observance. A dearth of [LSPs](https://medium.com/breez-technology/sources-of-centralization-on-lightning-and-why-they-matter-b7aa3352231f) to initially peer with will compromise privacy. [Receiver-confidentiality](https://github.com/lightningnetwork/lightning-rfc/pull/765) is still a work in progress.

Lightning privacy is definitively an area that requires more research before making any strong assertions on the level of privacy provided.

Scalability presents its own concerns. The size of the UTXO set is going to be a [bottleneck](https://tik-old.ee.ethz.ch/file//a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks20(1).pdf) at some point. Cheap access to [onchain resources](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-May/017818.html) isn’t guaranteed in the long-term. The prospect of [malicious congestion and spamming](https://lists.linuxfoundation.org/pipermail/lightning-dev/2020-February/002547.html) hasn’t been addressed yet. Routing tables will likely be too large for mobile clients, hence they will need to [delegate](https://github.com/lightningnetwork/lightning-rfc/pull/654), decreasing their privacy. Removing the [onliness requirement](https://github.com/breez/LightningRod) for payments is still being worked on.

I am very confident that these challenges will be addressed in the long term but in the short term they require considerable technological efforts. Step by step, we will make Lightning a robust, efficient, trustworthy financial platform.

If you want to help us in these tasks and get involved with one of the brightest engineering communities, this is the right time to join!

## The nascent Stack of Bitcoin Contract Protocols

That said, narrowing exclusively Bitcoin innovations to Lightning, you will miss the forest for the trees. Other protocols that are being developed at the margins of Bitcoin are fascinating. As a side-note, let’s define a contract protocol as a wider scope rather than the off-chain one as some of the steps can be played on-chain and thus even in optimistic scenarios.

[Vaults](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-April/017793.html) are the next-step in key management. By combining multisignature with timelocks they make coin custodial solutions far safer while enabling more fine-grained withdrawal operations. Future refinements will serve as building blocks for inheritance schemes or multi-stakeholder management.

[Discreet Log Contract](https://github.com/discreetlogcontracts/dlcspecs/) are leading the way in bringing oracles in Bitcoin. By leveraging elliptic curve linearity they make the betting contract unobservable by the oracle provider, only known by the participants posting collateral. They radically reduce the incentive to maliciously misreport the outcome. A future iteration will be to distribute them directly on Lightning as a new class of packets. One use-case example is to let anyone hedge against their local currency devaluing.

[CoinSwap](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-May/017898.html) is the next iteration in privacy-technology. By building on atomic swaps, they hide the exchange of coins from any blockchain observer. Their usage could become massive if they’re used to context-switch coins between different privacy domains (e.g Lightning channels to cold storage).

[Payment Pools](https://bitcoinmagazine.com/articles/building-on-taproot-payment-pools-could-be-bitcoins-next-layer-two-protocol) are still at the whiteboard phase but are promising in their attempt to combine confidentiality, scalability and cost-effectiveness for future massive usage of off-chain protocols.

What should not be underestimated is how these protocols are generating a measurable feedback loop that is improving the base layer.

Off-chain or contracts protocols, require stronger blockchain assurances including protection from certain network failures, whether they be accidental or malicious. As routing nodes earn fees by keeping their coins locked in channels they lose money when transactions get stuck in mempools, and thus they are incentivized to pay more compelling fees. By breaking a number of deanonymization heuristics these new protocols enhance coin fungibility.

In addition, by providing access to financial services to parts of the world devoid of alternatives, they grow the Bitcoin user base, in an ever more geographically distributed way.

It’s likely that each unit of usage of higher layer protocols will bring non-linear growth of value for the base layer. Layering private contracts on the top of the public constitution will make the latter stronger.

The Bitcoin contract protocols stack is still in its infancy. We still have a number of frontiers to approach by combining applied cryptography, distributed systems, financial engineering, law practice and game-theory.

In the future, this stack of contract protocols will gradually form the backbone of more Bitcoin-powered economies. They need to be matured sensibly with lessons learned from previous iterations.

## The Tribes of the Bitcoin Stack

What might end up hindering our attempts to build a stronger Lightning and Bitcoin isn’t any particular technical difficulty. That is something we will address with creativity, craftiness and sweat as per usual. When we look back at Bitcoin’s short yet intense history perhaps we should be more concerned with the risks presented from community disagreements.

Said differently, the discrepancy between the public excitement for Lightning, and the state of infrastructure, sounds like a cultural misalignment.

If you have been to both a Bitcoin and a Lightning conference it is easy to observe divergent communities. Bitcoin conferences often focus on deep technical talks, prioritizing security and protocol engineering, and are attended by seasoned Internet citizens, hackers of all sorts and civil libertarians. After endless waves of scams, they are naturally skeptical but intellectual debates remain open and honest.

On the other side the Lightning crowds feel different. Younger for sure, more startup minded and with talks focused on user experience and product design. Energy is flowing through the air and you have a thousand dazzling Lapps to play with. You can taste the Silicon-Valley influence, and easily recall that some participants were happily promoting their ICOs a few years ago. It is flashier too, the Lightning crowd does like garish yellow and bright purple!

That’s a rough sketch, I guess a lot of us are belonging to these two tribes, at least I would confess so myself.

Let’s sketch these two tribes further.

### The LWN Tribe

We have the OG tribe, they built the Bitcoin of today. Their determination, craftsmanship, intellectual rigor and uncompromising ethics have built and saved the system from both technical and social attacks over the years.

A good chunk of them are sharing a strong Unix background and that’s the best school of sound software engineering. You can appreciate the kinship between the major Internet protocols (TCP/IP) and the Bitcoin ones. They both strive for simplicity.

It is displaying the strengths of the wider open source movement but we should also explore its weaknesses. Our kernels and compilers consist of millions of code lines, hindering their clear prehension. Our chips are closed and a seemingly permanent security disaster. And we are too few considering the Internet as a house for the curious mind.

That is not to say the hard work of the previous years has been wasted nor that we should give up our harshly conquered spaces of freedom. But we should have a clear understanding of the environment that is changing around us.

Bitcoin fungibility is under attack and it’s going to worsen. Network-level disruptions should be anticipated. Block rewards are going to dwindle and fees will have to pay for a consistent network hash rate. Clumsily written codebases will hinder attempts to pass down hard earned knowledge to younger Bitcoiners. And that is just a few of the challenges ahead.

After you, someone needs to come in turn running the full-node. Lightning and contract protocols are likely our best shots to continue the Bitcoin history in the brightest way.

### The Product Hunt Tribe

Then we have the more startup-like tribe. They are talented at listening to users’ needs, executing and serving those users. They make complexity intelligible by wrapping it inside attractive products. It is they who build the gateway to connect to the outside world which allows liquidity to flow in. All oiled with burn rate, ARR and churn.

But it is even easier to look at the failures of the startup movement. Funding cycles, startup bubbles, chasing extreme growth and living in a constant state of urgency are good ingredients for delivering new digital products. But it is not a healthy environment when your main KPI should be optimizing the financial autonomy of your users.

Admittedly, Bitcoin businesses are unique: the typical startup playbook doesn’t apply here. Automatic updates and trust-minimized financial software don’t merge well. Selling a security product and storing user data is quite an oxymoron. Offering nodes in the cloud whilst promising total financial control to your users is just a lie.

If you require your users to trust you in any way, just say it plainly and bear the responsibility. Otherwise you are deceiving when you use terms like privacy and trust-minimization. Be ready to be scrutinized with the same rigor as when we are verifying our protocols.

It’s a worthy goal to reduce information asymmetries, and we should aim for Bitcoin users to allocate their funds and time with the best knowledge available.

Further, the current digital world has been built with the image of the passive user in mind. In Bitcoin that translates into a user who can’t rely on himself to manage his keys, won’t be able to afford the fees for usage and who is too narrow-minded to care about the behavior of the system.

I dare you to do better. One should not forget that Bitcoin is first and foremost a tool for self-determination. If people fail to understand that, you’re the teacher to blame.

The truth is you have real humans on the other side who strongly desire autonomy. One of the most magical experiences of Bitcoin is hanging out at meetups and observing people from all ages and backgrounds eager to learn.

There is no fatality. If keys are too complex to handle, then we should roll out better designed key management solutions. If onchain or off-chain fees are too high, we should craft better optimized protocols. And if the learning curve is too steep, we should produce better educational content.

Failing to keep Lightning & consorts decentralized might be all-right for base layer stability. But there is a non-zero risk of it backfiring. A decade from now, if a good chunk of the coin supply is allocated in channels operated by centralized services, even distributed base layer operators won’t have much economical weight in the bargain to conserve consensus rules.

We may wake up one morning and see them being broken in our plain-sight just as Bitcoin history warned us.

### Beyond the Tribes, our Living Community

Bitcoin is a unique experience, and if we want to pursue it forward we have to draw bridges between the divergent tribes. We need to learn all we can from each of them. But sincerely we shouldn’t bind to their past failures or accept outdated models.

Due to personal ignorance I’m only highlighting two of the Bitcoin tribes and their universes. A global picture would include a thousand of others like the Chinese mining community or the Venezuelan meshnet community. There is a Babel-like diversity in Bitcoin and that’s a force.

We may spend more time fighting each other on social media on insignificant topics instead of solving common problems around a beer at a conference. And we might live in a more fragmented world, trapped within borders, and without access to those high bandwidth events. It’s a first-class necessity to maintain good communication interfaces between all stakeholders.

We are all citizens of this Bitcoin Commonwealth. At least the secp256k1 curve is the same between BitDevs NYC, Berlin’s Room 77, the Dakar Bitcoin Developers meetup and the Bitcoin emBassy TLV.

## What Bitcoin do you want to see ?

Bitcoin presents a fantastic game theory equation to align the long term interests of all of its players. Understanding and respecting its internal rules are the surest path to maximize wealth creation for everyone.

But if we state the problem clearly, if we onboard millions of users in the same way as the Internet, we are more likely to break Bitcoin than anything else.

There is a fear about Bitcoin’s future that it will not achieve as much as the Internet but honestly what we should fear is not doing better than the Internet.

We aren’t playing a zero-sum game. But we may be worried about some minority of its players, driven by the fear of missing opportunities, tapping into the wider majority’s fear of never scaling to drive them against its own interests. Focusing on a adamant definition of onboarding as the only way forward, breaking the rules, giving up on past principles and thus destroying the long term value of Bitcoin.

Looking forward, we can actively choose to onboard new Bitcoin citizens in our own sustainable terms. In a way which preserves the properties which have made the system successful so far. At our own pace, as we have done so far, servicing the human layer.

A Bitcoin onboarding where you rely on an exhaustive set of resources in your native language to get started. Where you have a great network of local meetups to learn from. Where you have a wide set of easy-to-use tools to protect your digital estate. Where you can positively interact with businesses on your own conditions. Where you’re always advancing forward on your personal quest for greater self-determination.

Choosing this way, we’re all going to be winners. Remind that empowered users will have a stronger economic activity. At term this means more flourishing Bitcoin business and thriving economies.

Zooming out, we should always remind ourselves that Bitcoin has its own temporality. Despite floods and riots, the halving did happen. Obviously we are on the edge of a revolution. But coming from a continent which has experienced a bunch of them, the true story with revolutions is that most of the time they fail.

As social and cultural changes are slow to unravel, it is tempting to lose patience and burn to the ground the foundations that have been laid out in a desperate attempt to fasten the process. For Bitcoin to turn into its full-strength, it will take at least a generation, and we have to be steady with this outgrowth.

Always remember that in days of doubts, we have the choice between comfort and complacency, or freedom and adventure. We can achieve a walled garden or a free jungle.

Which one are you going to build?

## Hacking Forward

Welcome those words with prudence. Don’t take them for granted. Make your own opinion. Then act on your own definition of Bitcoin. As a friendly whisper, you’ve always been free to contribute.

Meanwhile, as talk is cheaper than code, here is my promised personal roadmap. It is mostly continuing what I have been working on thus far:

*   On the Bitcoin Core side, there are a thousand interesting things happening. Personally I will be working on improving transaction relay and fee models for off-chain protocols, [AltNet](https://github.com/bitcoin/bitcoin/pull/18988), to make it easier to deploy alternative transport communications and hopefully addressing some of the off-chain security issues I previously referred to. Contributing to the Bitcoin Core review process with a focus on refactoring and code modularity changes, as the health of the Core codebase is critical in the long term.
*   On the [Rust-Lightning](https://github.com/rust-bitcoin/rust-lightning) side, refining our cutting-edge features. Adding more test coverage and auditing the critical parts. Onboarding our new contributors. Moving towards deployment. On top of it scratching the wider Lightning Development Kit ecosystem with the awesome Square Crypto team.
*   On a more research-oriented side, contributing to the [Discreet Log Contract](https://github.com/discreetlogcontracts/dlcspecs/) specification as the setting up of reliable oracles will be such an exciting breakthrough.

Thanks to the reviewers, thanks to Chaincode Labs for the last 12 months, thanks to John Pfeffer for his confidence and thanks to my fellow Bitcoin hackers, from whom I’m learning so much every day.

Have fun on this crazy Bitcoin ride!

Antoine




***

{% include signup.md %}