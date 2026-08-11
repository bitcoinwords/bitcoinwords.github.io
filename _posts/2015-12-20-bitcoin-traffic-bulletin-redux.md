---
title: "Bitcoin traffic bulletin (redux)"
permalink: "/bitcoin-traffic-bulletin-redux"

author: davehudson

tags:
  - Dave Hudson
  - 2015 Q4
  - Scaling
  - Criticism

excerpt: Bitcoin traffic bulletin (redux). Posted December 20, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin traffic bulletin (redux)](http://hashingit.com/analysis/44-bitcoin-traffic-bulletin-redux)
### By [Dave Hudson](https://hashingit.com/)
### Posted December 20, 2015

In November 2014 I wrote an article, "[Bitcoin traffic bulletin?](http://hashingit.com/blog/2014-11-11)" that sought to look at what happens if the Bitcoin network started to get congested. Since then there has been considerable debate about the Bitcoin block size and there are now many proposals to increase block capacity.

In the original blog post the network's block capacity was at about 30%. As of early December 2015 the network's block capacity is at least 58%. In practice some blocks are mined smaller than the full 1M bytes that could be used (see "[The myth of the megabyte Bitcoin block](http://hashingit.com/blog/2015-01-18)") and so we may have more block capacity being used:

![](/assets/images/2015/m12/bitcoin-traffic-bulletin-redux1.png)

*Effective block sizes over time*

The simple Monte Carlo simulation from that earlier post models the effects of loading on first transaction confirmations:

![](/assets/images/2015/m12/bitcoin-traffic-bulletin-redux2.png)

*Probabilities for the time to a first block confirmation with the Bitcoin network at various load levels (log scale)*

During 2015 we have seen a few attempts to generate "stress tests" that spam the Bitcoin network with large volumes of transactions. In each instance transaction confirmation times were seen to increase, and arguably fees increases to match. This suggests that the network can adapt reasonably well, but service was certainly affected, not least because transactions with small fees could be almost indefinitely delayed.

***

{% include signup.md %}
