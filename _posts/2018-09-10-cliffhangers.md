---
title: "Cliffhangers"
permalink: "/cliffhangers" 

tags:
  - LaurentMT
  - CY18 Q3

excerpt: Part 3 in a 3 part series, LaurentMT looks at the idea of an optimal age of the UTXOs to measure how far the system is running from its optimum. Posted September 10, 2018.

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---

# Cliffhangers
### By [LaurentMT](https://medium.com/@laurentmt)
### Posted September 10, 2018

**This is post 3 of 3 in a series**
* [Gravity](https://cryptowords.github.io/gravity)
* [The Yin and Yang of Bitcoin](https://cryptowords.github.io/the-yin-and-yang-of-bitcoin)
* [Cliffhangers](https://cryptowords.github.io/cliffhangers)

***

_"Be like the cliff against which the waves continually break; but it stands firm and tames the fury of the water around it." — Marcus 'Rocky' Aurelius, Meditations of a Bitcoin miner_

![](/assets/images/cy18/cy18q3m9/lmt-1.png){: .align-center}

In the [previous](https://medium.com/@laurentmt/gravity-10e1a25d2ab2) [parts](https://medium.com/@laurentmt/the-yin-and-yang-of-bitcoin-bf056f3fd58c) of this series, we've started to investigate the efficiency of Bitcoin's PoW. In this third part, we're going to focus on a slightly different question: "Is the system running at its optimum ?".

For this, we'll first underline some points related to the effects of an increasing hashrate and we'll introduce the Satoshi's cliff, a 3D visualization illustrating the diminishing marginal security provided by older blocks. Then, we'll define what could be considered as the theoretical optimum of the system and we'll wonder how far is the system from this optimum. At last, we'll conclude with a few thoughts about the diverging paths followed by Bitcoin and Bitcoin Cash.

### Prologue: Bitcoin Steroïd and Bitcoin Arctic

We've previously discussed the influence of hodling over the efficiency of Bitcoin's PoW by imagining two hypothetical versions of Bitcoin. While caricatural, these two examples were useful for understanding the consequences of different trade offs. Bitcoin Steroïd sacrifices its efficiency for a maximized activity while Bitcoin Arctic sacrifices its activity for a maximized efficiency. Obviously, none of these solutions is very satisfying. Can we do better ?

### Satoshi's Cliff

When I began to study the Bitcoin protocol, I was first amazed by the idea of new PoWs piling on top of old ones and providing an ever increasing security. But as often with Bitcoin, things aren't as simple as they seem. The truth is that with an increasing efficiency and availability of mining hardware, the security provided by old individual PoWs tends to decrease.

This phenomenon can be illustrated with a statistics provided by P.Wuille on [this page](https://bitcoin.sipa.be/). The chart displays the number of days which would be required for recomputing all PoWs since day 1 with 100% of the actual hashrate.

proof-of-work equivalent days (source: bitcoin.sipa.be)

In order to better visualize the evolution of the two phenomena (i.e. the cumulative effect of PoW and the effect of an increasing hashrate on old blocks) we're going to compute a 3D visualization generalizing the chart provided by P.Wuille. This visualization is going to display how many days (z axis) would be required to rewrite the history back to a past block (y axis) with 100% of the expected hashrate used to mine a more recent block (x axis).

I'll call this chart the "Satoshi's Cliff"

Satoshi's Cliff (simplified version, x and y axes are expressed in time periods between 2 adjustments of the difficulty)

Let's choose any value on the x axis and starting from the bottom, let's climb the cliff. As you can see, rewriting more blocks requires more and more time (and is more expensive). But at some point, we reach a plateau. Being older doesn't provide a significant additional security to an UTXO. This highlights why the approach followed by Bitcoin Arctic (i.e. a "naive" maximization of accumulated PoWs) isn't optimal. Once the plateau has been reached, activity is sacrificed for almost no additional security.

### On the edge of the cliff

Based on this observation, we're going to define the "edge of the cliff" as a theoretical optimum for the system. Indeed, beyond a certain point it doesn't seem very wise to sacrifice activity for the diminishing marginal security provided by older PoWs.

It's important to note that **the concept of an** **optimal age doesn't really make sense for an individual UTXO**. Indeed, as the "owner" of an UTXO you don't have a fine-grained control over its age. Either you hodl the UTXO and at some point it will reach the plateau or you spend it and it instantly goes back to the bottom of the cliff.

In my opinion, **this concept of optimal age is primarily useful when we consider the UTXO set as a whole.**It can be considered as a reference point for the distribution of existing bitcoins per age. The more existing bitcoins are concentrated around the optimal age, the closer the system is from its optimum.

Ok. Let's try to determine the evolution of this optimal age. For this, we're going to iterate over all the values on the x axis and plot a 2D chart for each value (a kind of transverse slice of the cliff).

A slice of the cliff

Then, we're going to use a very simple method based on vector arithmetic (see Annex A) in order to approximate the optimal age for the slice. We just have to repeat the same operation for each slice and that gives us the following chart.

Let's note that very different criteria might be used to determine what is the optimum at a given date. Which one is best remains an open question.

### A lemming effect ?

SELLL !

You may remember some observations made about the Hodl Waves which suggest a "lemmings" effect occurring during rallies in the bitcoin's price, with many old UTXOs "jumping" from the cliff. As it was shown earlier, one of the consequences of this phenomenon (coupled with the increasing hashrate) is a temporary degradation of the efficiency of the system. Does it mean that the system is significantly moving away from our theoretical optimum during these events ?

As a first benchmark, we can try to use a few data points provided by the Hodl Waves analysis and plot the distribution of UTXO amounts per age. The selected data points will be the last 4 four top and bottom values identified for the PPR. We'll then plot an interval identifying the position of the optimal age on top of these distributions.

Distribution of existing bitcoins per age (selected data points are the last 4 top and bottom values of the PPR)

We can observe that for most of these data points, a majority of the existing bitcoins (50–70%) are hanging on the cliff (i.e. below the optimum). But an indicator more important than the median is the concentration of existing bitcoins around the optimum. I must admit that I've been a bit surprised here. I was expecting a clear differentiation between the bottoms (07/07/2012, 31/01/2013, etc) and the tops (21/09/2012, 16/11/2013, etc) but it doesn't seem to be the case.

To be honest I don't think that we can infer anything definitive from so few data points. Unfortunately, I lacked time for computing an exhaustive fine-grained comparison and it remains a task to be done. [Yep. It's a really brutal cliffhanger]

### Bitcoin and Bitcoin Cash

As a last thought on this subject, I'll say that it should be interesting to observe how Bitcoin and Bitcoin Cash evolve in the future. As you certainly noticed, the trade offs described for Bitcoin Arctic and Bitcoin Steroïd have some resemblances with the divergent visions followed by the two chains.

Concerning Bitcoin, it should be particularly interesting to observe how the Lightning Network impacts the efficiency of the system. Indeed, the idea of long lived channels (i.e. several months or years) may help to "naturally" aggregate more UTXOs around the optimum (which is currently oscillating between 18 and 24 months).

Concerning Bitcoin Cash, it should be interesting to observe if the effect of an ever increasing number of on-chain payments can be counterbalanced by hodlers and if it's enough to stay close from an optimal use of the security provided by its PoWs.

### Conclusion

In this third part, we've discussed the idea of an optimal age of the UTXOs allowing to measure how far the system is running from its optimum. It's clear that this post has barely scratched the surface of the question. My hope is that this first foray into the subject will encourage more people to investigate it.

_(_ [_Next part_](https://medium.com/@laurentmt/electric-money-e2cd34f78f56) _)_

### Acknowledgements

I wish to thank [@Beetcoin](https://twitter.com/Beetcoin), [Pierre P.](https://twitter.com/piporbtc) and [Stephane](https://twitter.com/StephBres) for theirs precious feedback and their patience :)

A great thank you to [@SamouraiWallet](https://twitter.com/SamouraiWallet) and [TDevD](https://twitter.com/SamouraiDev) for theirs feedback and their support of OXT.

**_Annex A — Approximation of the optimal age of an UTXO_**

We're going to use a method inspired from the [Needle algorithm](https://raghavan.usc.edu//papers/kneedle-simplex11.pdf). For any value on the x axis of the 3d chart, we can define a 2d chart (a slice of the cliff) and compute a vector Vi (see chart below).

We can then iterate over each value of the x axis of this 2d chart and compute the vector Vo. From these two vectors, we can compute the vector Vd and its norm (dot product + vectors addition). We consider the point O maximizing the norm of the vector Vd as our optimum.

An interpretation of this method is that the segment IA is what we would observe if the hashrate was constant. Thus, O is the point maximizing the effect of an increasing hashrate (compared to a constant hashrate) while making a trade off between a maximized security and a maximized activity.
