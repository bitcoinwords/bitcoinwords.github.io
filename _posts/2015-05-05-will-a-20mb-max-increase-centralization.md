---
title: "Will a 20MB max increase centralization?"
permalink: "/will-a-20mb-max-increase-centralization"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2015 Q2
  - Politics
  - Scaling

excerpt: Will a 20MB max increase centralization?. Posted May 5, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Will a 20MB max increase centralization?](http://gavinandresen.ninja/does-more-transactions-necessarily-mean-more-centralized)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted May 5, 2015

Continuing with objections to raising the maximum block size:

> More transactions means more bandwidth and CPU and storage cost, and more cost means increased centralization because fewer people will be able to afford that cost.

I can’t argue with the first part of that statement– more transactions **will** mean more validation cost. But how much? Is it significant enough to worry about?

I’ll use ChunkHost’s [current pricing](https://www.chunkhost.com/) to do some back-of-the-envelope calculations. I’m not affiliated with ChunkHost– I’m using them for this example because they accept Bitcoin and I’ve been a happy customer of theirs for a while now (I spun up some ‘chunks’ to run some 20 megabyte block tests earlier this year).

CPU and storage are cheap these days; one moderately fast CPU can easily keep up with 20 megabytes worth of transactions every ten minutes.

Twenty megabytes downloaded plus twenty megabytes uploaded every ten minutes is about 170 gigabytes bandwidth usage per month – well within the 4 terabytes/month limit of even the least expensive ChunkHost plan.

Disk space shouldn’t be an issue very soon– now that blockchain pruning has been implemented, you don’t have to dedicate 30+ gigabytes to store the entire blockchain.

So it looks to me like the actual out-of-pocket cost of running a full node in a datacenter won’t change with a 20 megabyte maximum block size; it will be on the order of $5 or $10 per month.

I chose 20MB as a reasonable block size to target because 170 gigabytes per month comfortably fits into the typical 250-300 gigabytes per month data cap– so you can run a full node from home on a “pretty good” broadband plan.

***

So if running a full node costs so little why are we seeing the number of full nodes on the network declining, even with one megabyte blocks? Won’t bigger blocks accelerate that decline?

And why are companies outsourcing the running of nodes and using API services like those offered by BitPay or Coinbase or Chain? Again, won’t bigger blocks accelerate that trend?

I think the answer to both of those questions is “no” – or, at least, “not significantly.” I agree with [Jameson Lopp’s conclusion](https://medium.com/@lopp/the-state-of-the-bitcoin-network-2b6911fd9e32) on the cause of the decline in full nodes– that it is “a direct result of the rise of web based wallets and SPV (Simplified Payment Verification) wallet clients, which are easier to use than heavyweight wallets that must maintain a local copy of the blockchain.” Give the typical user three experiences: a SPV wallet, a full node processing one megabyte blocks, and a full node processing twenty megabyte blocks, and they will choose SPV every time.

Hosting and bandwidth costs of $10 per month are trivial even to a cash-starved startup. Finding and hiring good people is expensive, and that is what is driving companies to outsource blockchain maintenance. A larger maximum block size won’t change that equation.

***

{% include signup.md %}
