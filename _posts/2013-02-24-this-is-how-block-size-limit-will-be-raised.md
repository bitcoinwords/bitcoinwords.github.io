---
title: "This is how block size limit will be raised"
permalink: "/this-is-how-block-size-limit-will-be-raised"

author: olegandreev

tags:
  - Oleg Andreev
  - 2013 Q1
  - Block Size
  - Scaling
  - Governance

excerpt: This is how block size limit will be raised. Posted February 24, 2013.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [This is how block size limit will be raised](https://blog.oleganza.com/post/43849158813/this-is-how-block-size-limit-will-be-raised)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted February 24, 2013

The last post was filled with different ideas and did not show clearly the single principle behind it. Here I will try to explain it on a simple example.

Imagine you are selling apples. You are selling, like 100 apples per day for $1 each. Suddenly the demand for apples grows. People want to buy more than 100 apples per day. If you haven’t yet increased the supply of apples, people will try to outbid each other. Say, the most prominent apple lovers are willing to pay $1,5 per apple. For you it means an immediate increase in revenue: up to $150 per day instead of $100.

For a minute lets suppose that your apples are special and you have no competition. Will you earn even more if you increase supply of apples? You cannot really know in advance because you never know the “demand curve” (because it does not really exist and demand changes over time). On one hand, your revenue may drop down: more apples mean less competition for them and a lower price. On the other hand, the price may get lower, but the increase of purchases will be greater, so the total revenue would be even bigger. Also, if you reduce supply to 10 apples per day, it does not mean that you will find customers willing to pay $15 or more to make a bigger revenue. Maybe at some point they’ll buy something else or abstain from buying at all.

The important point is that the only way to know the best price and the best amount of supply is to try different amounts and settle at the optimum point. In other words, when demand grows, you should always be able to increase the supply to see if it increases your revenue or not. If it does not, you may lower the supply back to optimal amount.

Back to the block size. Today, miners and customers do not hit the limit of 1 Mb per block. The limit virtually does not exist (blocks are typically under 250 Kb due to optional limit). The limit could be 100 Gb and the blocks would still have the same size we have today. So nobody would take the risk to change the rule because the rule does not affect anyone.

Fast forward a year or two from now: the amount of transactions is growing. If the miners do not find it efficient to send bigger blocks (due to bandwidth latencies causing more orphaned blocks, or storage costs, or time spent on verification or something else), they will not send bigger blocks. So the limit still would not matter. But if they find it efficient to send blocks up to 1 Mb in size, they will “feel” the limit. Block size cannot be arbitrarily increased, so transactions will begin competing for a place in the block. Transaction fees will rise. But we don’t know how much they will rise. At some point, for some people it would be cheaper to use external clearing houses that will offer lower fees and sync with blockchain less frequently. For miners that would mean uncertainty. How much would they earn in fees if the block size can be increased? Will they have bandwidth problems? Will they have bigger or smaller revenue? The only way to know for sure is to try, but you cannot try it unless you increase the limit. So they would naturally be motivated to increase the limit to be allowed to find an optimal block size.

Who else would be motivated to do so? Customers, of course. They would like to pay lower fees for non-mediated transactions instead of relying too much on clearing houses. Even clearing houses would like to have a bigger limit so they pay lower fees. Because clearing house provides additional service of instant confirmation (vs. 10-20 minute confirmation by the blockchain) and there would always be people willing to pay for that service. In addition, clearing houses may provide arbitration and many other extra services. In other words, everyone who creates raw transactions is interested in having lower mining fees.

The only people in disadvantage are nodes that have bandwidth/storage problems. Those who mine on lower bandwidth are having the same economical disadvantage as having slower computer. The fastest miners earn more and that’s what matter for clients. It is absolutely the same as with people who mined on a single GPU and now have to switch to ASIC or drop out. The non-miners would have to compare their costs of delayed validation with the costs of upgrading their network. If they choose slow network and delays, their customer base will be limited: customers who want faster validations will switch to faster competitors. In the end, if the majority of miners and other users sees it economically more profitable to try bigger blocks, they will switch and the minority would have to adjust. But since there is some level of uncertainty here, the limit will never be abolished or raised too much. Most probably, it will be increased by a factor of two, so everyone can easily calculate their costs and risks. And if the 2 Mb block turns out to be too expensive, miners would simply create smaller blocks until we have better networks or faster computers.

And the last point: the hard fork does not imply that everyone should switch some other rules at the same time. Updating software is not that expensive. It is expensive to come to a consensus. And the more stuff you put into a proposal, the harder it will be to get a consensus. However, if people feel need to update two simple lines of code and bump the limit from 1 Mb to 2 Mb, it will be much easier to come to an agreement. And repeat again when necessary.

Summary: no one will change the block size limit until it is reached. And when it is reached, Bitcoin users will switch to a slightly higher limit (e.g. from 1 Mb to 2 MB), so everyone can try and see if it is profitable. If it is not, then miners will simply mine smaller blocks. But if it is profitable, more transactions will go through, until we hit the limit again and repeat. Most probably, the block size limit will never be abolished because of the fear, uncertainty and doubt that people generate in a hard fork discussion.

***

{% include signup.md %}
