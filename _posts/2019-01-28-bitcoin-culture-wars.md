---
title: "Bitcoin Culture Wars: What Doesn’t Kill You Only Makes you Stronger"
permalink: "/bitcoin-culture-wars" 

author: brandonquittem

tags:
  - Brandon Quittem
  - CY19 Q1
  - Governance
  - Politics
  - Culture
  - Forking
  - Forks

excerpt: Brandon Quittem shares details on Bitcoin's governance model. Posted January 28, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin Culture Wars: What Doesn’t Kill You Only Makes you Stronger](https://medium.com/@BrandonQuittem/bitcoin-culture-wars-what-doesnt-kill-you-only-makes-you-stronger-b0db7e5515e1)
### By [Brandon Quittem](https://twitter.com/Bquittem)
### Posted January 28, 2019

![](/assets/images/cy19q1/cy19q1m1/bq-1.png)
*Source: [NPR](https://www.npr.org/sections/thesalt/2014/10/27/357903336/gladiator-gatorade-ancient-athletes-also-had-a-recovery-drink)*


There seems to be considerable confusion around Bitcoin’s governance model. In this article, I’m attempting to shine a light on Bitcoin’s informal governance which is often called a “culture war.”

We’ll explore “in-fighting” in the Bitcoin community, lessons learned from failed forks, and highlight a few rarely discussed benefits of Bitcoin’s informal governance including minimizing the attack surface, refining the core message, and lowering the user acquisition cost.

## Bitcoin is Social Consensus Automated by a Protocol
One way to describe Bitcoin is a group of people who loosely organize around a shared system. Users coalesce around the rules of the game which are then automated by code in the Bitcoin protocol. Generally agreed upon rules of the system include fixed monetary policy (21m supply cap), censorship-resistant transactions, and ease of verification.

![](/assets/images/cy19q1/cy19q1m1/bq-2.png)
*Source: Hasu’s [Unpacking Bitcoin’s Social Contract](https://medium.com/s/story/bitcoins-social-contract-1f8b05ee24a9)*

## Disagreements in Bitcoin are “Culture Wars”
Bitcoiners rarely agree on every aspect of the shared system. In fact, it’s common for mutually exclusive ideologies to emerge such as “fast cheap payments on the base layer” vs “decentralization of node operators.”

What happens when mutually exclusive visions collide? Culture wars.

There is no formalized process, such as voting, to change the Bitcoin protocol. However, that doesn’t mean it devolves into chaos, although it might appear that way. Below I’ll explain the general process for changing Bitcoin from a high level. If you want to go in-depth I highly suggest [Pierre Rochard’s Medium post](https://medium.com/@pierre_rochard/bitcoin-governance-37e86299470f) on the topic.

Typically, conflicts are first debated online in places like Twitter, forums, and mailing lists. Users share their perspectives and if the rough consensus is achieved, this signals to developers that it’s worth considering. If sufficiently motivated, someone might create a proposal called a Bitcoin Improvement Proposal (BIP). These BIPs then receive further scrutiny and testing from the community. Ultimately these proposals may or may not be implemented. This process essentially ratifies social consensus into the protocol.

However, when public discourse doesn’t converge on consensus, the intolerant minority is free to test their ideas in the market by creating a “fork.” In other words, anyone can copy and paste the Bitcoin code and launch their own competing token.

Theoretically, the ability to fork prevents excessive bickering and allows the market to decide the value of the new token signaling whether or not the proposed changes were “accepted.” In other words, the original community can choose which side to support and the market price determines the winner.

The ability to fork the Bitcoin code is also useful for securing the network against certain [threat models](https://jwweatherman.com/#/bitcoinThreatModel) however that is a topic of another day.

One perceived weakness to Bitcoin’s informal governance is that it’s very hard to get social consensus on every issue which leads to conservatism. Theoretically, this could make Bitcoin too slow to adopt technological advancements leading to a competing coin gaining dominance in the market.

The perceived weaknesses of informal governance have lead to alternative governance models being proposed. Examples include on-chain voting and “fork resistant” protocols such as Decred.

However, the success of money is ultimately determined by network effects, and Bitcoin is clearly leading that race.

Interestingly, some Bitcoiners believe the base protocol should be calcified soon which theoretically minimizes catastrophic risk, pushes experimentation to the edge, and instills confidence in the base layer as a impartial judge.

## Forks in the Road
When inevitable disagreements cannot be solved through social discourse, the intolerant minority, if sufficiently motivated, can fork Bitcoin. Bitcoin full node operators choose which “version of Bitcoin” they support by running node software that enforces the protocol rules they support.

The most obvious example is the BCH community who wanted to prioritize the payment network aspect of Bitcoin on the base layer at the expense of decentralized node operators.

Instead of rehashing the scaling debate, I will attempt to dispel forking FUD, summarize lessons learned from failed forks, and explain three surprising benefits to these “culture wars.”

**FUD #1: “Forking is a Form of Inflation”**

One of Bitcoin’s biggest achievements is creating a provably scarce digital asset. However, if you fork the Bitcoin code doesn’t that dilute the supply? On the surface, this appears true, if I personally fork Bitcoin and launch my own version (brandon coin) now there are twice as many “Bitcoins.”

However, just because I created a fork of Bitcoin doesn’t mean it has any value. In fact, I would venture to guess the hypothetical “brandon coin” would be worth absolutely nothing. There is no confidence in my token, no developers, no exchange listings. Why would anyone want it?

Obviously “brandon coin” will fail miserably because I simply copied the technical aspect of Bitcoin without mobilizing the social consensus. So does forking Bitcoin dilute the supply? The answer is no.

**FUD #2: “Forking Confuses and Erodes Investor Confidence”**

In a recent [Forbes article](https://www.forbes.com/sites/francescoppola/2018/12/30/bitcoin-maximalists-impossible-dream/#512602ed543b), Frances Coppola claims Bitcoin’s history of forking means Bitcoin is not stable.

> “So Bitcoin does at least have a tribal identity or twenty. But it’s not exactly stable, is it?”

I get where she is coming from. If you dive into the front lines of the Bitcoin culture war on twitter, it appears the community is fractured beyond repair. You could easily point to the BCH community further dividing into ABC and SV in late 2018. When does it end?

However, the highly publicized disagreements account for a small fraction of community. The reality is the vast majority of the Bitcoin community agrees upon the important things and has converged around “Bitcoin core.” This convergence is commonly referred to a Schelling point.

Not to mention, the global population pays no attention to the “toxic debates” happening in places like crypto twitter, reddit, or online forums. Additionally, this type of rigorous debate is extremely healthy for the Bitcoin (more on that below).

One obvious question remains: what happens to the Bitcoiners who pursued “failed forks?” Will they “bend the knee” and come back to the BTC community, or will they double down on their “defeats?” The ball is your court, Roger.

**Lessons learned from forking Bitcoin:**

*   Forking Bitcoin is not a form of inflation
*   No matter how vocal minority chain supports are, they only represent a small percentage of the overall community
*   The market doesn’t value forks (BCH, BCH SV, Bitcoin gold/private/diamond)
*   If two chains use the same PoW mining algorithm, the minority chain is vulnerable to 51% attack (see: Verge, ETC, etc)

Based on 100% of Bitcoin forks being failures in the market, it’s reasonable to assume fewer culture wars will end up with a competitive fork. However, greed is a powerful force and as long as “forkers make money” they’ll continue to exist. At the very least can we put the scaling debate to rest?

Even if forking isn’t used anymore, there will continue to be culture wars in Bitcoin. The next obvious skirmish will be: fungibility vs a verifiable supply. In other words, should Bitcoin prioritize privacy/fungibility on the base chain over the ability to verify total supply? This debate will rage on as the Bitcoin community is split.

If history continues Bitcoin will pursue a path of conservatism. Personally, I would prefer to keep the supply verifiable while achieving enough fungibility through layer two technologies like lightning network and services like coin join.

## Benefits of Bitcoin’s Ongoing Culture Wars
Let’s explore three positive outcomes from Bitcoin’s ongoing culture wars.

**#1 Failed cultural divergences minimize attack surface**

The Bitcoin community has a reputation for being outspoken and approaching new ideas with a rigor not found in other cryptocurrency communities. Sometimes this is viewed as “toxic” by outsiders. However, when communities don’t embrace candid discussion, they risk becoming frail and vulnerable.

This aggressive in-fighting allows Bitcoin to market test new ideas internally where the stakes are low. Internal debates are like “cultural skirmishes” where bad ideas are exposed before being implemented into the protocol. This minimizes Bitcoin’s attack surface.

Most Bitcoiners agree that changes to the protocol should be approached with extreme caution. This is the polar opposite of the popular Silicon Valley mantra “move fast and break things.”

**#2 In-fighting refines the core message**

Cultural skirmishes in Bitcoin allow the community to shed bad ideas and refine the core message. For example, on-chain scaling was attempted by the Bitcoin Cash community which now most people agree was a failure.

In the future, when someone proposes “on-chain scaling,” we can point to the lessons learned from the failed BCH fork. This leads Bitcoiners to converge on the most compelling narratives. Although to be fair, most of the important Bitcoin debates were already hashed out by early Bitcoiners. [Yassine Elmandjra](https://twitter.com/yassineARK) organized a few of the [most popular debates](https://twitter.com/yassineARK/status/1047978606297792513).

In a sense, these narratives are the internal community discussing the best way to represent Bitcoin externally.

This cultural war over the prevailing narrative is not exclusive to the Bitcoin community, however. The entire crypto community is fighting over how to brand this whole phenomenon. Is the prevailing narrative “blockchain everything” or “better money?”

The outside world has a limited bandwidth to receive messages. The message that wins the internal culture war gets the most airtime in front of potential new cryptocurrency converts.

**#3 Ultimately, converging on the messaging lowers user acquisition cost.**

Most people need to hear about Bitcoin three or four times before deciding whether they want to acquire any. There are many reasons why this might be the case. Part of this time delayed action stems from the Lindy Effect. Essentially, “oh wow that Bitcoin thing is still around, maybe I should get some.”

Another potential reason why people take so long to make a decision: inconsistent and conflicting messaging. Depending on when you hear about Bitcoin, the prevailing narrative might have been one of any number of things, including: anonymous digital currency to buy drugs online, fast cheap payments, or digital gold. This brand confusion only makes understanding Bitcoin more complicated.

By refining the core messaging, theoretically, we could reduce the required number of touch points required before potential users make a decision. In other words, Bitcoin culture wars lower the user acquisition cost, effectively making the network more valuable.

## Whatever Doesn’t Kill Bitcoin only Makes it Stronger.
Bitcoin evolves as an expression of the market participants. These “culture wars” may appear toxic however they’re inevitable and a net positive.

Culture wars minimize Bitcoin’s attack surface and help refine the core message. This ultimately enables lower user acquisition costs making Bitcoin more valuable.

Each time Bitcoin survives a cultural skirmish, it’s better prepared for future battles with increasingly more at stake.

-Brandon

* * *

1.  Say hello on [Twitter](https://twitter.com/bquittem) where I post more thoughts like this :)
2.  Here’s another article you might like:
![[](/assets/images/cy19q1/cy19q1m1/bq-2.png)](https://medium.com/@BrandonQuittem/bitcoin-is-a-decentralized-organism-mycelium-part-1-3-6ec58cdcfaa6)

***

{% include signup.md %}
