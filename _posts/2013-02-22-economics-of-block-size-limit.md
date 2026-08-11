---
title: "Economics of block size limit"
permalink: "/economics-of-block-size-limit"

author: olegandreev

tags:
  - Oleg Andreev
  - 2013 Q1
  - Economics
  - Block Size
  - Scaling

excerpt: Economics of block size limit. Posted February 22, 2013.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Economics of block size limit](https://blog.oleganza.com/post/43677417318/economics-of-block-size-limit)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted February 22, 2013

Bitcoin blockchain has a built-in limit of 1 MB per block of transactions. Bigger blocks are rejected by other nodes as invalid. This means that at 10 minutes per block and with average transaction size of 400 bytes, Bitcoin network registers about 40 transactions per second.

The limit was set in place initially to make sure that the network is not spammed with huge blocks with useless transactions when people were just starting playing with Bitcoin and mining blocks was possible on personal computers. Huge blocks could lead to excessive use of bandwidth which could lead to higher percentage of orphaned blocks due to higher synchronization delays. There was no empirical proof for this limit, it was mostly an intuitive safety mechanism, “good enough” in the short run. Satoshi, the initial developer, suggested that the limit is temporary and should be raised or removed once the network becomes more powerful and could sustain larger amount of transactions.

It is important to keep in mind, that the limit was almost never exercised. So even if there was no hard limit, the blockchain would not grow faster. It was just a precaution. (Assuming, the soft limit of 250 Kb which is not enforced, would still be there.)

Today the number of transactions is steadily growing and may hit the block limit within a year or two. So people start discussing whether the block size limit should be raised, eliminated or if there should be scheme to adjust it dynamically. To change the limit, a consensus will be required. More than 50% of nodes running the full chain must agree to a new rule to switch to it.

What are the factors at play?

Some people fear that if block size will become unlimited, miners will include a lot of spammy transactions, eat everybody’s bandwidth, fees will get lower (thus undermining sustainability of the blockchain in the future) and some miners with poorer connection will be forced out of the market which is supposedly unfair to them.

In reality though, Bitcoin as any other free market, has nothing to do with fairness, but everything to do with mutual satisfaction of self-interests. Miners are motivated by increasing their revenue short term as long as ensuring their investment and raising value of BTC in the long term.

Is there any natural limit on the block size? Sure there is: it is network bandwidth and the costs of storage and transaction verification. The more transactions you need to verify and transmit, the higher your operating costs and (most importantly) the higher the risk of orphaning a block. If the block is too big to be distributed and verified by other peers, the risk of somebody else creating a shorter block in parallel gets higher. If the shorter block gets validated by majority faster than the longer one, the latter will become orphaned. Orphaned blocks mean immediate loss of time and money for miner, and since transactions are rescheduled and delayed, frequently orphaned blocks undermine market value of miner’s savings.

Miners already can choose any block size within the limit and many use the default soft limit of 250 Kb. If it was profitable for some of them to create bigger blocks, they would do that already. Since they do not, it shows that there are market forces at play and hard limit does not matter yet. Even if it was 100 Mb, the blocks would still be compact.

As the base reward is still comparatively big (25 BTC till 2017), miners are even more likely to keep the blocks as small as it does not hurt the market price. Transaction fees contribute 1.12% of the revenue, while bigger blocks with more transactions increase risk of losing 25 BTC. As time goes by, more transactions would compete with 25 BTC reward, increasing average transaction fees. Increasing fees will motivate miners to allow slightly larger blocks (until the risk of losing reward is balanced by the amount of fees). Halving days would only increase motivation to include more transactions. And as blocks and fees get larger, miners would take care of ensuring better connectivity to keep risk of losing blocks low.

It is true that the miner cares about propagating the block as fast as possible to reach the 50%+ of other miners. Some people think the bigger block sizes will favor miners with better connectivity and poor miners somewhere in Botswana will be out of luck. This is shortsighted speculation. A miner with slower connection can always create smaller blocks than other miners to compensate for the connection problems. If it is not profitable for him, it’s not a problem of other users. If I want to mine from a middle of Siberian forest, no one has any obligation to respect my decision. It is entirely possible that in the future 90% of mining will happen in Iceland where the electricity is cheap. There could be great connection between miners, blocks could be bigger and allow a lot of transactions to be put in with lower fees. The rest of the world could download the whole chain without worrying about its delays and sizes. If you want to verify it yourself, just pay for the bandwidth and storage. There is no real threat that by being closer to each other, miners will form a cartel (they can do that today already). Even if they do, arbitrarily raised transaction fees would lower the market value of their own savings, and also any member of cartel can undercut everyone by dropping his fee requirements and earning much more than the rest of them.

What about poor geeks on slow connections with old clunky hard drives that protect our freedom by chatting on Bitcoin forums and sharing 0.0001% of a mining pool? They would need to adjust. Just like CPU miners were losing to GPU miners, and both of them — to ASICs, they would need to adjust to a bigger blockchain. This does not hurt anybody’s freedom except their own. Millions of regular customers would never bother downloading blockchain. They would either trust others, or use escrow payment systems anyway. And those people will provide real value on the market and will make sure that they have their connections faster, drives harder and operations as cheap as possible. Being a lonely chatty geek in Botswana does not bring any value to anybody.

If the miners hit the block limit, it would only mean one thing: there is a desire to process more transactions, but historical untested agreement does not allow it. Then miners and other full nodes will either raise the limit (the smaller the increment, the bigger support it will have), or transaction fees will go up as people compete for the space in blocks. As transaction fees go up, not only miners, but also regular users and service companies using the full blockchain would desire increment of the limit. So it will be even easier to achieve a consensus about raising the limit.

My prediction is that the block size limit will probably never be abolished, but will be constantly pushed up by a factor of two as amount of transactions approaches the limit. Maybe after a couple of updates, people would decide that it’s safe to abolish the limit completely if it is cheaper to account for it, than to have uncertainty of a hard fork.

***

{% include signup.md %}
