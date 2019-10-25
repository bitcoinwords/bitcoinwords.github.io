---
title: "BTC Long/Short MVRV difference indicates an end of the bear cycle"
permalink: "/btc-long-short-mvrv-difference-indicates-an-end-of-the-bear-cycle" 

tags:
  - Valentin
  - CY19 Q2

excerpt: Valentin expands on the MVRV ratio and adds insight to the data that indicates an end to the bear market. Posted May 7, 2019.

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

# [BTC Long/Short MVRV difference indicates an end of the bear cycle](https://app.santiment.net/insights/read/btc-long%2Fshort-mvrv-difference-indicates-an-end-of-the-bear-cycle-377)
### By [valentin](https://twitter.com/valentinmihov)
### Posted May 7, 2019


The BTC Long/Short MVRV difference is almost at 0% at the moment, which historically has proven to indicate an end of a bear cycle. 

What does that mean and what exactly is the BTC Long/Short MVRV difference?

![](/assets/images/cy19/cy19q2m5/valentin-1.png){: .align-center}
The MVRV Long/Short difference for the last 8 years. Green is BTC price on log scale. 

May be you are familiar with the MVRV ratio, which was first developed by Murad Mahmudov and David Puell at the end of 2018: [https://blog.goodaudience.com/bitcoin-market-value-to-realized-value-mvrv-ratio-3ebc914dbaee](https://blog.goodaudience.com/bitcoin-market-value-to-realized-value-mvrv-ratio-3ebc914dbaee)

The idea is to measure how much each BTC holder paid for his coins and compare it to the current price of BTC. If the ratio is above 1.0, then on average all BTC holders will get profit if they sell their coins now. If it is below 1.0, on average everyone will realize a loss if they sell. The bigger the ratio, the more sell pressure there will be on the BTC price.

At Santiment we extended this metric to a "Time-bound MVRV", which is the same as MVRV, but takes into account only coins that moved in the last X days. For example we have 365day MVRV and 60day MVRV. These ratios will measure the average profit/loss of all coins that moved within the last 365 days and 60 days respectively. When we computed these 2 metrics we observed something very interesting: during a bull market the 356day MVRV is bigger than 60day MVRV and during a bear market it is the opposite. The explanation could be that the short term traders are usually profiting when the market goes down and sideways, while during a bull run the long term holders are the ones that will have the final call - ultimately when the long term holders start to sell, that will be the end of the bull run. Another nice thing about the time-bound MVRV is that it automatically filters out lost coins.

![](/assets/images/cy19/cy19q2m5/valentin-2.png){: .align-center}
365day (purple) vs 60day (yellow) MVRV. Lines on the inflection points. Red is bear cycle. Green is bull cycle.

Having all the above in mind we developed a single indicator that we call MVRV Long/Short MVRV difference, which captures this phenomena. The indicator will bottom at the bottom of the bear market and will top at the top of the bull run. As you can see from the first image above, when the indicator crosses 0, the price of BTC grows steadily. The tricky point is to identify the top of the ratio.

We are still researching this indicator and so far we've been able to beat a buy'n hold strategy using it as it gives us a good indication when we should sell. If you want to get access to this metric go to [https://santiment.net/dashboards/](https://santiment.net/dashboards/) and requests access.
