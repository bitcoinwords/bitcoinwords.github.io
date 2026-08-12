---
title: "Why increasing the max block size is urgent"
permalink: "/why-increasing-the-max-block-size-is-urgent"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2015 Q2
  - Mining
  - Scaling

excerpt: Why increasing the max block size is urgent. Posted May 4, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Why increasing the max block size is urgent](http://gavinandresen.ninja/why-increasing-the-max-block-size-is-urgent)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted May 4, 2015

Perhaps the most common objection I hear to raising the maximum block size from one megabyte is that “blocks aren’t full yet, so we don’t have to do anything (yet).”

It is true that we’re not yet at the hard-coded one megabyte block size limit; on average, blocks are 30-40% full today.

There is a [very good blog post by David Hudson at hashingit.com](http://hashingit.com/analysis/34-bitcoin-traffic-bulletin) analyzing what will happen on the network as we approach 100% full blocks. Please visit that link for full details, but basically he points out there is a mismatch between when transactions are created and when blocks are found– and that mismatch means very bad things start to happen on the network as the one megabyte limit is reached.

Transactions are created steadily over time, as people spend their bitcoin. There are daily and weekly cycles in transaction volume, but over any ten-minute period the number of transactions will be roughly equal to the number of transactions in the previous or next ten minute period.

Blocks, however, are created via a random Poisson process. Sometimes a lot of blocks are found in an hour, sometimes all the miners will be unlucky and very few (or none!) will be found in a hour.

The mismatch between the steady submission of transactions to the network and the random Poisson distribution of found blocks means we will never have blocks that are 100% full all of the time. Sometimes miners will find a lot of blocks in a row, clearing out the queue of waiting transactions.

Conversely, very bad things can happen when miners happen to be unlucky. The queue of transactions waiting to be confirmed will grow, using more and more memory inside every full node. Full nodes could (and probably will in a future release of Bitcoin Core) start to drop transactions from the queue, which will make transaction confirmation less reliable.

If the wallet re-broadcasts transactions if they are not confirmed after a few blocks (the Bitcoin Core wallet does), then bandwidth usage spikes as every wallet on the network rebroadcasts its unconfirmed transactions.

If the number of transactions waiting gets large enough, the end result will be an over-saturated network, busy doing nothing productive. I don’t think that is likely– it is more likely people just stop using Bitcoin because transaction confirmation becomes increasingly unreliable.

***

{% include signup.md %}
