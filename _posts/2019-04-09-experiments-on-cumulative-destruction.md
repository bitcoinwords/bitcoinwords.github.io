---
title: "Experiments on Cumulative Destruction"
permalink: "/experiments-on-cumulative-destruction" 

tags:
  - David Puell
  - Willy Woo
  - CY19 Q2

excerpt: David Puell and Willy Woo lay out new models for the concept of destruction into price analysis. Posted April 9, 2019.

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

{% include donation.md %}

# [Experiments on Cumulative Destruction](https://medium.com/@kenoshaking/experiments-on-cumulative-destruction-3a126fbd63b3)
## Two Approaches to Bring Bitcoindays Destroyed Into the Price Domain
### By [David Puell](https://twitter.com/kenoshaking) and [Willy Woo](https://twitter.com/woonomic)
### Posted April 9, 2019 

_Disclaimer: Nothing here should be considered investment or trading advice._ 

Okay, so this article is now well overdue given the recent price action. BTC never rests! The last few months have been very productive in terms of discovering new valuation metrics based on on-chain analytics. The recent proposals using [coindays destroyed](https://bitcoin.stackexchange.com/questions/845/what-are-bitcoin-days-destroyed) by [Tamas Blummer](https://medium.com/@tamas.blummer/liveliness-of-bitcoin-174001d016da) and the team at [Adamant Capital](https://medium.com/@adamant_capital/a-primer-on-bitcoin-investor-sentiment-and-changes-in-saving-behavior-a5fb70109d32) have put this essential metric once again on the map. We thought we'd give it a go at coming up with a way to best translate the concept of destruction into a precise price level for market analysis.

### Experiment A: Cumulative Value-Days Destroyed (CVDD) by Willy Woo 

When coins move from one investor to another, the transaction carries both a USD value and also destroys a time value relating to how long the original investor held their coins. CVDD tracks the cumulative sum of this value-time destruction as coins move from old hands into new hands as a ratio to the market age. It is calculated with the following formula: 

![](/assets/images/cy19/cy19q2m4/woo-7.png){: .align-center}

Note that 6 million is used for calibrating the chart. This number is arbitrary and would be different had we used hours or blocks as unit for the age of the market. 

CVDD has hit the historical Bitcoin price bottoms with remarkable accuracy.

![](/assets/images/cy19/cy19q2m4/woo-8.png){: .align-center}*CVDD*

Unlike [delta cap](https://medium.com/@kenoshaking/bitcoin-delta-capitalization-1d51a7b256b4), CVDD tends to consistently climb in value — this becomes useful to frame an increasing lower bound for a market bottom during bear seasons when the market price is falling. 

When used in conjunction with the top price model, CVDD and top price provide upper and lower bands for price action.

![](/assets/images/cy19/cy19q2m4/woo-9.png){: .align-center}*CVDD and top price*

When used in conjunction with Coinmetric's [realized price](https://coinmetrics.io/realized-capitalization/), CVDD can help the visualization of Bitcoin's accumulation bottoms.

![](/assets/images/cy19/cy19q2m4/woo-10.png){: .align-center}*CVDD and realized price*

Both CVDD and realized price have remarkable resemblances in shape, so it is no coincidence that they both use HODL time by the investor in their calculation.
It is important to note that both CVDD and top price are interesting curiosities, and are not guaranteed to work in future cycles.

### Experiment B: Transferred Price and Balanced Price by David Puell
Instead of using a 6-million figure, transferred price uses supply to bring destruction into the price domain:

![](/assets/images/cy19/cy19q2m4/puell-1.png){: .align-center}

Looking at this as a life-to-date moving average of spending behavior (again, old hands selling into new hands), it can be assumed that when subtracted from realized price (the average paid for all coins in the market), a "fair" valuation measure emerges. Balanced price denotes the level at which, during bear markets, a full detox has been achieved — market price matching what was paid minus what was spent.

![](/assets/images/cy19/cy19q2m4/puell-2.png){: .align-center}
![](/assets/images/cy19/cy19q2m4/puell-3.png){: .align-center}*Balanced price*

It goes without saying that this evokes [delta price](https://medium.com/@kenoshaking/bitcoin-delta-capitalization-1d51a7b256b4) in both calculation and visualization. We believe that delta serves as a technical analysis proxy of balanced price. The former seems to be agile enough to catch exact bottoms — the "wicks" — while the latter catches the full accumulation level prior to the bull run, also defining the brief moment when price remains below it as "capitulation." 

More iterations on coindays destroyed to follow. Stay tuned...

**Sources**
  1. [_Woobull.com_](http://charts.woobull.com/) _:_ Charts and early price data archeology.
  2. [_Coinmetrics.io_](https://coinmetrics.io/charts/) _:_ Realized price data.
  3. [_Blochchair.com_](https://blockchair.com/): Coindays destroyed data.
**Authors**
  1. [Willy Woo](https://twitter.com/woonomic), on-chain analytics pioneer @[Woobull.com](https://woobull.com/).
  2. [David Puell](https://twitter.com/kenoshaking), Head of Research @ Adaptive Capital.
