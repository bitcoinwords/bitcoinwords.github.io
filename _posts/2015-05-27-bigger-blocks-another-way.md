---
title: "Bigger blocks another way?"
permalink: "/bigger-blocks-another-way"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2015 Q2
  - Mining
  - Economics
  - Security

excerpt: Bigger blocks another way?. Posted May 27, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bigger blocks another way?](http://gavinandresen.ninja/bigger-blocks-another-way)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted May 27, 2015

Get ten engineers on a mailing list, ask them to solve a big problem, and you’ll probably end up with eleven different solutions.

Even if people agree that the one megabyte block size limit should be raised (and almost everybody does agree that it should be raised at some point), agreeing **how** is difficult.

I’m not going to try to list all of the proposals for how to increase the size; there are too many of them, and I’d just manage to miss somebody’s favorite (and end up with a wall-of-text blog post that nobody would read). But I will write about one popular family of ideas, and will explain the reasoning behind the twenty-megabyte proposal.

### Dynamic limits

One very popular idea is to implement a dynamic limit, based on historical block sizes.

The details vary: how often should the maximum size be adjusted? Every block? Every difficulty adjustment? How much of an increase should be allowed? 50% bigger? Double?

If the block size limit is just a denial-of-service prevention measure (preventing a big, evil miner from producing an 11 gigabyte block that the rest of the network is forced to validate), then any of these proposals will work. Engineers could [bike-shed](http://en.wiktionary.org/wiki/bikeshedding) the parameter choice to death, but I like the idea of a simple dynamic limit on the maximum allowed size.

There are more complicated proposals for a dynamic block size limit that (for example) involve proof-of-stake voting or linking the maximum block size to the mining reward and/or the amount of fees in a block. I like them less than a simple solution, because consensus-critical code must be absolutely correct, and every additional line of code is another opportunity for a chain-splitting bug to slip through code review and testing.

### So why a fixed 20MB ?

Some of the core committers don’t like the idea of giving miners the ability to collude (either intentionally or as a response to economic incentives) to increase the block size without limit.

For example, [Gregory Maxwell wrote](http://sourceforge.net/p/bitcoin/mailman/message/34090559/):

> Do people (other than Mike Hearn; I guess) think a future where everyone depends on a small number of “Google scale” node operations for the system is actually okay? (I think not, and if so we’re never going to agree–but it can be helpful to understand when a disagreement is ideological).

Greg really should have said “other than Mike Hearn [and Satoshi](http://www.metzdowd.com/pipermail/cryptography/2008-November/014815.html)”:

> Long before the network gets anywhere near as large as that, it would be safe for users to use Simplified Payment Verification (section 8) to check for double spending, which only requires having the chain of block headers, or about 12KB per day. Only people trying to create new coins would need to run network nodes. At first, most users would run network nodes, but as the network grows beyond a certain point, it would be left more and more to specialists with server farms of specialized hardware.

I struggle with wanting to stay true to Satoshi’s original vision of Bitcoin as a system that scales up to Visa-level transaction volume versus maintaining consensus with the other core committers, who obviously have a different vision for how the system should grow. Twenty megabytes is meant to be a compromise– large enough to support transaction volume for the next couple of years, but small enough to make sure volunteer open source developers can continue to process the entire chain on their home Internet connection or on a modest virtual private server.

If compromise isn’t possible, then a simple dynamic limit intended just to prevent DoS attacks is a very attractive long-term solution.

***

{% include signup.md %}
