---
title: "Doing nothing is a choice"
permalink: "/doing-nothing-is-a-choice"

author: laurentmt

tags:
  - LaurentMT
  - 2016 Q1
  - Mining
  - Economics
  - Privacy

excerpt: Doing nothing is a choice. Posted March 5, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Doing nothing is a choice](https://medium.com/@laurentmt/doing-nothing-is-a-choice-2c26376358a2)
### By LaurentMT
### Posted March 5, 2016

*“Ask not what bitcoin can do for you, ask what you can do for bitcoin” - J.F. Kennedy (Biography - Apollo Editions)*

Dear Brian,
 
First, I would like to apologize for the length of this letter and my crappy english.

A bit of context. During these last 12 months, I’ve been working on the development of an analytics platform dedicated to the bitcoin blockchain. Long hours spent on charts taught me a few things that I would like to share with you.

One of these things is that bitcoin is still a small economy and therefore it’s still possible that the activity of a single actor/service has a very noticeable impact.

Some occurrences of this phenomenon are related to well-known events like the growth of the number of transactions in 2012 (launch of Satoshi Dice).

![](/assets/images/2016/m3/doing-nothing-is-a-choice1.png)

Some others are less well-known. For instance, there is this step pattern in the growth of the UTXO set which is likely to be caused by a small number of faucets doing weekly payments.

![](/assets/images/2016/m3/doing-nothing-is-a-choice2.png)

At last, some cases remain mysterious (at least to me) but are likely to be the result of the activity of a single/small number of services, like this surprising decrease of address reuse between Q2 and Q4 2013.

![](/assets/images/2016/m3/doing-nothing-is-a-choice3.png)

Ok. Back to the subject. Some times ago, I was playing with a chart displaying the number of transactions VS the average size of transactions (aggregated by months).

![](/assets/images/2016/m3/doing-nothing-is-a-choice4.png)

I couldn’t help but notice that it looks like bitcoin had several distinct phases in its history (note that my “classification” is 100% manual & subjective but you get the idea) and it seems that since July 2015, the network has entered a new phase which is… kinda “weird”. My interpretation is that a part of this new behavior is related to the spam attacks from last summer and to cleaning operations done by mining pools after the attacks. At this point, I have no explanation for observations from October to now.

A few days ago, I was playing with statistics provided by blockchain.info about long chains of transactions and I was really surprised by the growth of long chains during the last 6 months

![](/assets/images/2016/m3/doing-nothing-is-a-choice5.png)

![](/assets/images/2016/m3/doing-nothing-is-a-choice6.png)

Even if we all know that correlation isn’t causation, this time I couldn’t help but wonder if this activity is “natural” or not. Because, you know, the debate is hot in the community and it has already created a few collateral damages (spam attacks, ddos of services,…). For the sake of “neutrality”, I’ve decided not to follow a specific hypothesis but to check in the blockchain if I could find recurrent patterns explaining this activity and these long chains and I’ve found two things.

1/ It seems that there was a lot of peeling chains lately and to be honest, I don’t get what people try to achieve with this pattern. Usually, it is used to obfuscate the trail of a financial flow or to gain more privacy. For instance, it was used by Mark Karpeles in 2011, before and after its proof of solvency transaction.

![](/assets/images/2016/m3/doing-nothing-is-a-choice7.png)

Now, here’s the problem with this explanation. Since 2011, several startups doing blockchain analysis have been funded ($100k - $1M). Moreover development of tools allowing to detect this kind of pattern (at least manually) is a no brainer. Even someone like me can build this kind of tool.
So, my conclusion is that if these transactions are created for obfuscation, the sender should stop and find another method because this one isn’t going to help her. **If they are spam, it may be difficult to prove it but actually it doesn’t matter** (more on this later).

2/ If you look at the chart of long chains, you can observe a very specific fingerprint: growth seems to start in September with a peak in December, a low just after Christmas and a new peak in February. My platform processes a few algorithms allowing to cluster addresses in entities. I’m cautious with these results because the work is still early stage (especially the manual task of tagging addresses) and the results are obviously still incomplete. Anyway, I was surprised to find a pretty good correlation between the activity on some exchanges and the fingerprint observed for long chains.

![](/assets/images/2016/m3/doing-nothing-is-a-choice8.png)

![](/assets/images/2016/m3/doing-nothing-is-a-choice9.png)

Without being a rocket scientist, I guess that the recent price increase plays a role here. It seems quite possible that a part of these long chains are just correlated to this surge of activity and how some services process their transactions. For instance, Huobi seems to follow the rule “1 transaction per withdrawal” with transactions forming long chains. I may be wrong but **I don’t know any reason to suspect a malicious intent in this case**.

As you see, these are just a few checks done in the blockchain while looking for clues and certainly not definitive proofs of anything.

More importantly, these observations lead me to this conclusion:

> “On the blockchain, any sufficiently inefficient process is indistinguishable from a spam attack” — Satoshi’s third law

I’m more and more convinced that we should stop talking (myself included) of spam or malicious activity when we talk about a public blockchain aiming to provide censorship resistance. Instead, we should focus our efforts and discussions on efficient processes & “good practices” VS inefficient processes & “bad practices”. The main reason is that **human intents don’t matter for the bitcoin blockchain and there is no difference between a spam attack and an inefficient process** because consequences are the same for the blockchain.

The point is that many services have grown very quickly and sometimes technical solutions which were fine at small scale (even when not optimized) start to have a very noticeable impact when the service grows (you remember my intro ?). It’s likely that many services (exchanges, online wallets, gambling websites, …) have room for optimizations and that just a few major services implementing a few optimizations would make a visible difference.

For instance, I’m convinced that many exchanges may aggregate some of their operations (like withdrawals) in a single transaction instead of using long chains. Bitcoin allows this. Why not use the feature ?

Your own company, Coinbase, creates [2 transactions per withdrawal](https://twitter.com/LaurentMT/status/703058669173403652). I get the reasons for this choice and there are obvious improvements to be done by others services in terms of refund transactions. But is it really the best that we can achieve ?

Obviously, a proper scaling requires work at protocol level and this is the job of the core devs (whatever the implementation) but fact is that all developers and services can help to greatly improve the efficiency of the network.

**Sadly, this discussion about the role played by the ecosystem NEVER happened in the past 12 months of debate.**

In my humble opinion, these improvements aren’t going to become a reality because people are naturally good or benevolent but because there’s a voluntary and collective effort (a new Blockchain Alliance ?) aiming to fight against this never ending “tragedy of the commons” scenario.

I may be too optimistic but I still think that we (the 2016 bitcoin ecosystem) are better than the “tragedy of the commons” and that we can collectively improve this situation if we really want to.

**There’s only one question that each one of us should answer as a conclusion of this too long debate: “Do you want to ?”**

In the eyes of the rest of the world, we’re the crazies following in the footsteps of a crazy who was thinking that he could reinvent money. Why would we be afraid of things deemed impossible ?

My 2 satoshis.
laurentmt

***

{% include signup.md %}
