---
title: "How Not To Critique Bitcoin"
permalink: "/how-to-not-critique-bitcoin" 

author: connerbrown

tags:
  - Conner Brown
  - 2020 Q1
  - Building
  - Response
  - Move Slow
  - Slow
  - Network Effects
  - Game Theory
  - Technology
  - Economics
  - Ethos

excerpt: Conner Brown defends moving slow. Posted January 28, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [How Not To Critique Bitcoin](https://medium.com/@Conner_/how-not-to-critique-bitcoin-d5d04e99edc1)
## A quick defense of moving slow and not breaking things.
### By [Conner Brown](https://twitter.com/_ConnerBrown_)
### Posted January 28, 2020

![](/assets/images/2020/m1/cb4.png)

After publishing my latest article, I received some pushback about Bitcoin’s flexibility. This viewpoint is best expressed by [Paddy’s tweetstorm here](https://twitter.com/paddypisa/status/1217844970352205824) and parts of [Daniel Goldman’s article here](https://blog.theabacus.io/how-not-to-critique-ethereum-11b542b08206). This is a quick response, but it needs to be said.

## More opcodes more problems.

Their view holds that Bitcoin’s simple and conservative baselayer is a major hinderance to developing smart contracts on layer two. It is an understandable view. There are many cool features in the pipeline for Bitcoin, and many of them are already written, but we still don’t have them! However, patience is a virtue. It may be tempting to add as many features as quickly as possible, but when dealing with an **entirely new global monetary system**, its important to be extremely cautious — this may be our only shot at changing the world! Recall that we’ve had a [potential inflation bug from something as simple as a routine optimization](https://bitcoincore.org/en/2018/09/20/notice/). If Bitcoin fails, the dream of digital sound money may be dead for decades.

Returning to the contracts analogy, it might seem great to have a judge that can make decisions in a variety of fields, but only so long as they have sufficient expertise. After all, a judge is no good if their decisions can’t be relied upon. Therefore, it’s better to use their judgement for a few critical decisions they will get right with high confidence. Bitcoin’s slow and methodical development approach is necessary for building the rock solid foundation required for something so important.

The recent push for [BIP 119](https://github.com/bitcoin/bips/blob/master/bip-0119.mediawiki), OP\_CHECKTEMPLATEVERIFY (fka OP\_SECURETHEBAG), is a great example of this thinking. Covenants in Bitcoin were once an enabled feature, but core developers disabled them as a precaution to prevent potential fungibility issues. Jeremy Rubin’s BIP 119 proposal thus only enables a few limited forms of covenants which bring clear benefits (channel factories, vaults, easier coinjoin, congestion control, etc.) with limited downside risk.

To be clear, it would have been easier to just enable covenants in the first place and avoid this BIP altogether, but this is an important example of Bitcoin’s design philosophy: **First, Do No Harm**.

Bitcoin developers realize the protocol is tied to the financial wellbeing of millions and each change to the protocol could cause incredible unforeseen damage. Thus, Bitcoiners opt to only add features once their safety is reasonably certain. This measured approach takes time, and BIP 119 for example still has a ways to go before being implemented, but is ultimately worth it to ensure the integrity of the system.

In fact, adding features can actually slow you down. Ethereum claimed to be Bitcoin 2.0 with plenty of extra functionality, yet their complexity is causing them to stall. Bitcoin’s simple base layer allowed for the construction of lightning channels; Ethereum’s attempt at something similar, Plasma, has been a complete flop, and even plasma still required a trusted validator set! If bitcoin’s base layer is so burdensome, why can’t competitors build these “simple” lightning contracts on their chain?

I understand the temptation to enable as many functions as quickly as possible, I’m excited about Bitcoin too! But slow and steady wins the race, and I think the team which limits downside risk as much as possible will ultimately be victorious in the long run.

## Build on concrete, not quicksand.

Bitcoin’s certainty extends far beyond its scripting language. Those building smart contracts for the future must also think about the broader design decisions of the protocol as well. When I wrote that Bitcoin is simple and certain, I was also referring to the architecture of the protocol more broadly.

The Bitcoin Community has opted for a set monetary policy, a hard blocksize limit set by full nodes, and a strong defense of its consensus mechanism, proof-of-work. These are community norms that are strictly enforced by consensus and which have been defended from attacks in the past.

Bitcoin’s principles and architecture give certainty for companies building for the long term. In comparison, other smart contracting platforms have none of these properties. Even Ethereum, the closest competitor to Bitcoin, has a block size limit (gas limit) that [continues to fluctuate at the whims of miners](https://twitter.com/etherchain_org/status/1172784483231252482?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1173254283057221632&ref_url=https%3A%2F%2Fen.ethereumworldnews.com%2Feth-miners-ethereum-gas-limit%2F), the community continually promising to remove PoW for PoS (disincentivizing long term mining operations), and have no set monetary policy.

This swirling uncertainty on key parameters is a deterrent to building businesses on additional layers. Businesses rely on certainty that their contracts will be settled properly. This is empirically proven. Which protocol has the most companies building on layer two, despite seemingly infinite ICO grant money for other chains? Bitcoin. Entrepreneurs want certainty, not free funds.

I want to finish by highlighting the context of this discussion. Bitcoin is not a food delivery app, it is money. Money does not lend itself to moving fast and breaking things. Above all else, people want their money to be safe. This priority on safety is **essential for bootstrapping a store of value**. For something to be valuable, other’s have to decide to store their precious time and energy in it. Value accumulation requires hodlers — people with strong conviction that their money is safe.

This is one of the key reasons for Bitcoin’s market dominance. For many (including myself), only Bitcoin’s extremely cautious development approach allows users to feel comfortable storing any meaningful amount of wealth in it. This cannot be forgotten, no matter how shiny a new functionality may be.

***

{% include signup.md %}