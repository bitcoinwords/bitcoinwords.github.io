---
title: "Intent, Complexity and the Governance Paradox"
permalink: "/intent-complexity-and-the-governance-paradox"

author: simonmorris

tags:
  - Simon Morris
  - 2019 Q1
  - Privacy
  - Governance
  - Altcoins

excerpt: Intent, Complexity and the Governance Paradox. Posted January 5, 2019.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Intent, Complexity and the Governance Paradox](https://medium.com/@simonhmorris/intent-complexity-and-the-governance-paradox-bittorrent-lessons-for-crypto-3-of-4-1d14ac390f3f)
### By Simon Morris
### Posted January 5, 2019

## Intent, Complexity and the Governance Paradox — Bittorrent Lessons for Crypto (3 of 4)

Following on from my posts about [Why Bittorrent Mattered](https://medium.com/@simonhmorris/why-bittorrent-mattered-bittorrent-lessons-for-crypto-1-of-4-fa3c6fcef488) and [What Decentralization is Good For](https://medium.com/@simonhmorris/if-youre-not-breaking-rules-you-re-doing-it-wrong-bittorrent-lessons-for-crypto-2-of-4-72c68227fe69), I want to discuss three themes related to decentralized ecosystems which were all relevant to Bittorrent and are all relevant to many crypto projects.

![](/assets/images/2019/m1/intent-complexity-and-the-governance-paradox1.jpg)

##### The Problem of Intent

At the end of my post on [what decentralization is good for](https://medium.com/@simonhmorris/if-youre-not-breaking-rules-you-re-doing-it-wrong-bittorrent-lessons-for-crypto-2-of-4-72c68227fe69) I argued the main justification for a decentralized architecture was its resistance to various forms of censorship, or put a different way an ability the break the rules without anyone being able to stop you. There may be useful projects that have nothing to do with rule-breaking, but if the gold in the gold-rush is indeed rule-breaking, then without any rule-breaking it won’t much matter what sort of picks and shovels you are trying to sell.

While it’s tempting to focus on the actual rules being broken, we shouldn’t forget about the person or company breaking the rules. And this introduces the thorny problem of ‘intent’.

The uncomfortable thing about ‘intent’ is that in the final analysis, the legal system has very little patience for defendants who set out to break laws. When looked at holistically, if an ecosystem enables wholesale law-breaking and is built on technology explicitly designed to break those laws — at some point the enforcers are going to come looking for the authors to hold them accountable.

By and large Bittorrent Inc. and Bittorrent’s inventor Bram Cohen were able to skirt around the intent problem as it was clearly never Bram’s intent to engineer a system to broker the type of rule-breaking that occurred. In fact the popularity of Bittorrent was wholly accidental. 
On a parallel path, although Satoshi’s [Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf) was pretty explicit in its intent to break rules, the anonymity of its authorship has prevented the possibility to hold a person or entity accountable for any rules that could have been broken.

The approach of Ethereum is presumably more similar to that of Bittorrent — do nothing to try to adapt it as a better way to break any specific set of rules, and encourage good use cases as publicly as possible.

Contrast this with the start-ups who are on the public record aiming to break rules with their un-censorable system once it is launched. For example a certain well funded project which commendably wants to break the terrible music copyright and royalty rules that make the DJ art-form prohibitively expensive to publish online. But given they are on the record with this objective, its hard now to see enforcement authorities looking kindly on them (or their VC investors) in the event that they succeed.

So does this mean that you should simply not promote what you’re doing? Or do so with a veil of anonymity so no-one can join the dots? Or just get lucky and succeed by accident like Bittorrent did? And what will we discover of the future legal liability of those who flagrantly break rules (even very unpopular ones), or those who have leading roles in a blockchain system that makes it possible?

![](/assets/images/2019/m1/intent-complexity-and-the-governance-paradox2.png)

##### The Cost of Complexity

A second important theme for decentralized systems is a common lack of appreciation for just how complex these systems are and how finely balanced they need to be to operate correctly.

I originally joined Bittorrent in 2007 to work on a decentralized CDN which aimed to do something like “tie together all the unused storage and bandwidth on people’s PCs into a content delivery network which had zero operating costs (for us)”.

In time it proved there were a number of things wrong with this ambition (most of which I won’t touch on here), although perhaps the most important one which we discovered the hard way was the cost of complexity.

It was technically possible to cobble together some sort of CDN from under-utilized PCs, but we were flat wrong that this represented a free resource that could be easily aggregated and sold. On one side consumers had a strong perception that the bandwidth was theirs and not ours to re-sell, so to try to do so was costly in the form of goodwill with consumers. Even more damagingly we discovered that our CDN needed to integrate well with a fast growing and fast evolving tech stack designed to manage and deliver media online. The advantages we offered in terms of cheaper prices for delivering bits were vastly overshadowed by the sort of concessions our prospective customers would have to make in rearchitecting their content management systems. A value proposition of “a bit cheaper but much more complex and much less flexible” was ultimately not very appealing. We thought it was a strictly cheaper solution, but when framed holistically it was anything but.

And this was for a decentralized system that in truth was entirely centrally controlled and managed. For a system that must support independent developers writing software which speaks the same protocol the complexity is still bigger. The truth is that large scale decentralized systems, even when there is only one developer, are fiendishly difficult to get working right, and this ultimately must add into the cost.

Overall its hardly surprising at this point that the timelines for projects seem to keep getting pushed out as engineers are facing down the sheer difficulty of challenges they are faced by — many of which may not actually be solvable no much how much money you throw at them. On one side they must accommodate a fluid future and integrate with the predominant internet technology paradigm of “launch MVP quickly and iterate”, and on the other they must get it absolutely positively right the very first time, because of the third and final theme I’d like to discuss:

![](/assets/images/2019/m1/intent-complexity-and-the-governance-paradox3.png)

##### The Governance Paradox — Each New Decision is Harder than the Last

Governance in this case means the ability to make decisions efficiently and implement them quickly and effectively. Decision-making in a rule-breaking decentralized system is very hard. In fact it’s worse than that — decentralized governance is perhaps something close to an oxymoron. In a decentralized system which can’t be controlled, it is very hard to, errrm, control it. That’s the point. You can’t have it both ways. It turns out, viz. Bittorrent, that you can indeed build and release a system such that when ‘the man’ comes over to compel you to stop whatever it is that you’ve done that annoys him, you can actually say *“no, sorry, it can’t be done”*. But you cannot then turn around and easily make changes and updates to that system. Coordination costs are high and the timeframe to get things done is extremely long. This at least is the experience of BitTorrent Inc. and the Bittorrent ecosystem.

Getting things done in a rule-breaking decentralized system is hard for at least three reasons:

1. **the status quo is a safe place** — there are multiple stakeholders with often conflicting interests — the fact that a stable equilibrium between such groups has been found in the first place is perhaps extraordinary, but it is also something that all groups will tend to cling to.
2. **coordination is hard** and costly especially with many paranoid participants whose **interests are not necessarily obvious** to you — in the world of Bittorrent this meant that changes to different parts of the Bittorrent protocol to introduce obvious win:win optimizations or attack mitigations took many months and sometimes were shelved completely.
3. **major players are exposed**— even if you want to do something that you believe you can do and that will be popular with all stakeholders, you must consider an important additional stakeholder — the enforcer of the rules that have been broken. Considering the enforcer of the rules always has a chilling effect on all stakeholders. For many years BitTorrent Inc constantly audited its own internal thought processes based on second-guessing how various enforcement authorities might react. While the Bittorrent ecosystem was decentralized and extremely hard to censor, BitTorrent Inc — one of the few participants with real potential influence — was highly visible and felt exposed to legal repercussions of any of its actions. For these reasons it was frequently reluctant to even try to actively lead.

These exact same themes are clearly playing out in the world of crypto-currencies. Pre-launch these projects are completely centralized so they are blissfully immune to this issue and are able to make progress at speed. But post-launch, to the extent that projects are truly decentralized (clearly many only pretend to be) they are incredibly hard to govern. The difficulty of deciding what should happen next has caused progress to slow to a crawl and led to contentious stand-offs and projects splintering.

There are a number of crypto-projects which are trying to address the governance issue with various approaches to enabling decision-making that is ‘fair’ and ‘effective’ (for some definition of those terms). But in practice the only way to make any large-scale governance viable is to re-centralize power in a smaller number of deciders with some number of rules around how you can become and remain a decider. This role of ‘decider’ becomes more and more problematic the more successful an ecosystem gets at breaking rules, and the less willing the ‘deciders’ are to be held individually responsible. Established decentralized governance in the form of bodies like ICANN, the IETF and W3C have long been slow, contentious and prone to the undue influence of major participants. But I expect that governance of rule-breaking decentralized systems will present an even greater challenge as a result of the perceived liability even of participation, and certainly of leadership.

I’m always curious to look at crypto projects to see how they handle the problem of intent (do they talk about the rules they are trying to break), how well they understand the cost of complexity that their plans entail, and how they are addressing the governance paradox where every decision is going to be harder than the last.

(My final post in this series is on [who wins in the face of decentralized disruption](https://medium.com/@simonhmorris/decentralized-disruption-who-dares-wins-bittorrent-lessons-for-crypto-4-of-4-f022e8641c1a).)

***

{% include signup.md %}
