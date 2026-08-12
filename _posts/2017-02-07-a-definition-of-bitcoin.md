---
title: "A definition of “Bitcoin”"
permalink: "/a-definition-of-bitcoin"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2017 Q1
  - Mining
  - Inflation
  - Technology

excerpt: A definition of “Bitcoin”. Posted February 7, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [A definition of “Bitcoin”](http://gavinandresen.ninja/a-definition-of-bitcoin)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted February 7, 2017

Engineers are great at [not seeing the forest for the trees](http://www.urbandictionary.com/define.php?term=can%27t%20see%20the%20forest%20for%20the%20trees). They get stuck on details and lose track of the bigger picture.

I’ve seen it most often (and have been guilty myself) when they’re optimizing something to make it faster. They’ll start out OK– “it is taking eleven seconds to agitate the snarks, and seven seconds of that is just precomputing the eigenwidgets!”

So they’ll take a day and make precomputing the eigenwidgets ten times faster.

And then realize with just a little tweaking and a really nifty algorithm and two hundred more lines of code they can make it **one hundred** times faster!

So they spend a few days making snark agitation take 0.63 seconds faster (4.07 seconds instead of 4.7 seconds), instead of moving on to the next performance bottleneck. They can become focused on one little thing (Performance of this routine! or Security! or Decentralization! or Compatibility!) and ignore everything else.

I’d like to propose this big-picture technical definition of “Bitcoin”:

> “Bitcoin” is the ledger of not-previously-spent, validly signed transactions contained in the chain of blocks that begins with the genesis block (hash 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f), follows the 21-million coin creation schedule, and has the most cumulative double-SHA256-proof-of-work.<sup>[1](http://gavinandresen.ninja/a-definition-of-bitcoin#fn1)</sup>

If we can agree that is what we mean when we say “Bitcoin” then I think a lot of needless argument about “the trees” might be avoided.

Is there a nifty new type of transaction that is accepted by majority hashrate? Yes, still Bitcoin. Different arrangement of the merkle tree in the block header? Yes, still Bitcoin. Fix the off-by-one error in the difficulty retarget code? Yes, still Bitcoin.

Is there a minority hashrate branch of the chain? Not Bitcoin. Change the proof-of-work? Not Bitcoin. Majority hashrate decides 1% inflation a year is a Good Idea? Not Bitcoin.

Is there a better technical definition of what should or shouldn’t be considered “Bitcoin” ?

***

1. Apologies if I’m accidentally stealing this from somebody, it seems like the obvious definition given [Satoshi’s original whitepaper](https://bitcoin.com/bitcoin.pdf) and implementation. [↩](http://gavinandresen.ninja/a-definition-of-bitcoin#fnref1)

***

{% include signup.md %}
