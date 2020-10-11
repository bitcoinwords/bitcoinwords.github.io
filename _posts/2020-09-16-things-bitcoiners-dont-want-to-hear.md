---
title: "Things Bitcoiners Don’t Want To Hear"
permalink: "/things-bitcoiners-dont-want-to-hear"

author: shinobi

tags:
  - Shinobi
  - 2020 Q3
  - Thermodynamics
  - Network Effect

excerpt: Shinobi discusses the hard reality of thermodynamics. Posted September 16, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Things Bitcoiners Don’t Want To Hear](https://medium.com/block-digest-mempool/things-bitcoiners-dont-want-to-hear-33823c2e984)
### By [Shinobi](https://twitter.com/brian_trollz)
### Posted September 16, 2020

![Image for post](/assets/images/2020/m9/s2.png)

Bitcoin is suffering from an autoimmune disease right now. People have historically referred to active members in this ecosystem as “Bitcoin’s white blood cells.” They are now attacking Bitcoin itself, and no I am not referring to “plebs” calling out “influencers” for doing dumb shit. I am talking about the inability to confront shortcomings with layers of the system. The inability to confront substantial threats or attack surfaces that are not being worked on in terms of creating solutions and defenses.

People act like Bitcoin is invincible, preordained. It is not. And this is not to say Bitcoin will “fail” in the sense that it will die, even I think that is very unlikely. But it can lose its scalability. It can lose its characteristic of open access. It can lose its censorship resistance. Bitcoin as a system can survive while losing and gaining new characteristics. The progression of the blockchain, with the thermodynamic and probabilistic guarantee of current state, does not in and of itself guarantee these qualities that we value continue.

As long as that central quality of scarcity continues, it can absolutely lose/gain other characteristics and still maintain value through market demand. I’m going to run through two distinct areas in which this is happening at wide scale, one holding the potential for massive internal disruption and disagreement in the same way that things like Bcash played out, and the other massive potential for government corrosion of censorship resistance.

![Image for post](/assets/images/2020/m9/s1.png)
*Ouch*

## Short Circuit With Lightning

Lightning is almost certainly not going to scale for micropayments in the long term. Lightning fees are not disconnected from the fee market for blockspace, they are derivative of them. The reason micropayments work natively on Lightning right now is because fees for blockspace are so low right now; when fees for blockspace go up that will drag fees up for Lightning payments as well. It is not economically rational to be routing payments for profit on Lightning if the eventually necessary on chain operations immediately eat up everything you have earned off chain. Fees on Lightning will increase to compensate for this. And that is just the first issue with micropayments on Lightning.

Another issue is the value of payments. Every Lightning payment, regardless of the value being routed (and remember, part of the fees on Lightning are % based, so higher value = higher revenue for routing), costs the same amount of data. It costs the same amount of CPU operations, of electricity expended, however you want to conceptualize it. Pushed extremely to the margins with the ability to profitably perform ‘x’ computational operations in a time period, won’t you always prefer higher value transactions to maximize revenue?

And yet another issue, are [the problems with too many unresolved HTLCs live in one channel at a time](https://arxiv.org/abs/2006.08513) opening nodes up to attacks unless they limit the amount of unresolved HTLCs they will engage in at one time. This is a further introduction of scarcity in terms of opportunity cost with income. Why would I route your 1/10th of a penny microtransaction which might get me a 1/10th of a penny when I can route this other guy’s 10$ payment and earn 15 cents?

These kinds of false expectations are ultimately at the root of what lead to the big block divide and the split off by Bcash. A long period played out of completely unreasonable expectations being set, and when the time finally came that they were shattered a large swath of people would or could not accept that. Now I don’t think similar expectations being shattered now is going to lead to some doomsday fork or fracture (though it could), but micropayments are very important. They are in general a mechanism to shift the internet away from KYCed tagged and tracked access to services and infrastructure online. But imagine if as micropayments start to embed themselves into applications, they do so in a naive and short sighted way. They assume that Lightning will be a suitable micropayments layer natively. That is potentially a large amount of broken infrastructure when reality kicks in. How does that play out in the war of network effects? Adapt to reality vs. force reality to adapt.

We have things like LNURL Auth. That can create anonymous “micropayment credits” that can be topped up in cost effective chunks. We have alternatives like chaumian ecash tokens (which can be similarly bought in chunks to “top up”) to improve the privacy of micropayments to individual services. These would be actually independent from the on chain fee market, unlike native Lightning, and could in the long term scale to facilitate micropayments. There are even ways you can make chaumian tokens (assuming you trust the issuer to enforce this of course) atomic with native Lightning payments.

Bitcoin is in a race. There are all kinds of entities in the world that would like to stomp out censorship resistant microtransactions that create a foundation to keep an open internet alive. Ignoring long term realities because they make things more complex is wasting time and handing them a win.

## It’s Thermodynamics Stupid

Mining is industrial consumption of energy or people playing hobbyist in their own home. When was the last time (at least in most of the West) you heard of a major industrial consumer of electricity that wasn’t a registered company? Didn’t have legal identities on contracts with electricity producers? With grid operators? We are in an era of Bitcoin where exchanges and market places are being bent over backwards to comply with all the fun legacy regulation and legislation that Bitcoin itself is “natively immune” to. Why wouldn’t that type of application of regulations eventually domino out to miners as well? Doesn’t that threaten Bitcoin’s “native immunity” to regulation?

Miners process transactions, they are what actually facilitates transfer of control of UTXOs. They are the ones who decide which UTXO operations to process or not. Miners’ freedom to do whatever people will pay the highest for is your freedom to transact with censorship resistance. They are two sides of the same coin. Regulation is coming for the entire stack.

Centralized pools are how coordination dominantly occurs between individual hashrate operators. They don’t just help coordinate though, they actually take custody of individual operators money and pay them out for their contributions to the pool. They custody money. They. Custody. Money. A regulatable act. There’s the in to go after them; the prize is the dominant coordination mechanism for hashrate. The part of the process that decides which UTXOs operations to process or not process. The hashers facilitate that process, and pools custody their money. Therefore…pools must KYC their hashers in jurisdictions where regulations apply™.

(Aside: Solo mining just means the only way you’re mining is with a massive single operation which is going to stand out like a sore thumb)

This necessitates decentralizing the operations of the pool. Both of them. It requires a decentralized solution to individual miners coordinating and each doing their own transaction selection, and it also requires a trustless way for individual miners to be paid out on chain when someone in the decentralized “pool” actually finds a block. [P2Pool did this with their sharechain](https://en.bitcoin.it/wiki/P2Pool), but it has massive scalability issues. Every individual miner has their own output for each “share block” directly in the Coinbase transaction. The only real way to alleviate this issue is off chain protocols to accomplish the same trust guarantees without explicitly including an on chain UTXO for each hasher. Otherwise the effect of massive Coinbase TXes both has externalities to the non-mining fee market by taking up scarce blockspace, and a cost is incurred by individual miners having to manage small individual outputs that may approach dust levels.

Even solving these issues does not deal with the root of the problem in this layer of the stack: energy consumption. I call back to the first paragraph relating to this issue. Where do you see industrial level power consumption without KYC? Without knowing whose door to knock on? Who is legally accountable? This comes down to energy at the root. The life force. The meme magic that is rooted in thermodynamics and not you intellectually masturbating in your head. Anyone who knows what they are talking about knows the vast majority of competitive mining equipment is 240 volt. Welcome to the realm of, on a personal level, making the choice between mining and your clothes dryer. Welcome to getting around making that choice between mining and laundry requiring explicit conversations with the utility company. Paperwork. Red tape. Signals. Red flags. The only way to really get around this type of default “registry” governments can look for is at home off the grid energy production. Residentially. With all kinds of restrictions (legal and practical) that a warehouse with industrial lines doesn’t run into. And the minute you consume the available non-suspicious quota of power by giving up your washer and dryer, you can’t scale your mining operation beyond that without undetected off grid power generation.

You can’t escape the fingerprints of thermodynamics. This space is shifting “legit” and corporate. It’s meming about bucking the regulators, the governments, but really on a micro level starting to kiss their asses and cater to it. Anyone reading this know the logistics of an illegal cannabis grow op? The power concerns? The infrared foot print? Disguising that? Recognizing when authorities are looking for such fingerprints? To the few who do, can you imagine the extra complications on top of that baseline that Bitcoin mining entails? The noise? The exponentially larger energy draw at scale? The extra heat? This is really in a worst case scenario an outright illegal market like growing drugs that requires in depth and serious scientific research to scale and operate that infrastructure undetected…how do you attract mindshare here exactly? How is this not career and reputational suicide in the mainstream?

Solve the coordination problem, solve the trustless payout for hashes problem, solve all of that: you still have the thermodynamic problem. That last problem at the foundation is a doozy. How do you source electricity at scale without standing out in paperwork, on licenses, in redtape that flows through government? How do you obscure the noise foot print of a large mining operation? The thermal foot print to helicopters buzzing around overhead with infrared cameras? In a worst case scenario, a large enough percentage of miners need to be able to operate like this in order to make it unprofitable for “legitimate” miners to outright orphan blocks with “verboten transactions” in them. Otherwise kiss censorship resistance goodbye folks. It’s thermodynamics.

***

{% include signup.md %}