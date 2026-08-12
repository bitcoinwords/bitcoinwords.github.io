---
title: "Other definitions of Bitcoin"
permalink: "/other-definitions-of-bitcoin"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2017 Q1
  - Mining
  - Economics
  - Security

excerpt: Other definitions of Bitcoin. Posted February 8, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Other definitions of Bitcoin](http://gavinandresen.ninja/other-definitions-of-bitcoin)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted February 8, 2017

[Yesterday’s post](http://gavinandresen.ninja/a-definition-of-bitcoin) triggered some interesting discussion on reddit and twitter.

I realize now I should have been more specific– when I said “technical definition of Bitcoin” I meant a couple of things:

I am thinking of what Bitcoin is today and in the near future, not what it might eventually evolve into. While it is fun to talk about what Bitcoin will be in 100 years, that wasn’t the point of my blog post. I didn’t mean to imply that any definition of what Bitcoin is today and in the near future would somehow be iron-clad and binding and never change; thinking you can control how a technology evolves is even sillier than thinking you’ll be able to predict beyond a decade or maybe two.

I also want a definition that could be useful in determining which of two competing ledgers a neutral geek would point at and say “that one is Bitcoin as described in the original Bitcoin whitepaper”. It is very possible I’m not seeing the forest for the trees, and I should think of the whole social infrastructure that is Bitcoin and accept the fact that “Bitcoin” is a human-generated concept that cannot be pinned down. But I think [that’s stupid](https://en.wikipedia.org/wiki/Criticism_of_postmodernism), and even imperfect definitions can help to bring clarity.

I found two suggestions for modifying the definition interesting. First, instead of talking about double-SHA256-proof-of-work, just say “chain with most energy expended on proof of work.” I *do* think that if SHA256 was ever horribly broken the proof-of-work could change and the result should still be called “Bitcoin”.

That other is to declare that “Bitcoin” is the ledger starting with the genesis block that has the biggest market cap (exchange rate times number of coins) instead of most proof-of-work. That probably matches people’s intuitive notion better than proof-of-work, and if there was some fast, secure way to determine which branch of the ledger has the larger market cap it would even be a useful technical/engineering definition.

In practice, the chain with the biggest market cap will be the chain with the most proof-of-work. I can imagine [extremely unlikely scenarios involving economically irrational miners trying to destroy Bitcoin](http://gavintech.blogspot.com/2012/05/neutralizing-51-attack.html) where that isn’t true, but Bitcoin’s two-week difficulty adjustment period makes it [expensive for a minority of hashpower to maintain a split in the blockchain](http://gavinandresen.ninja/minority-branches).

***

{% include signup.md %}
