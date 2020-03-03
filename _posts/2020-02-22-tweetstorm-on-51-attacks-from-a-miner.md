---
title: "Tweetstorm: On 51 percent Attacks from a Miner"
permalink: "/tweetstorm-on-51-attacks-from-a-miner"

author: stevebarbour

tags:
  - Steve Barbour
  - CY20 Q1
  - Tweetstorm
  - 51% Attacks
  - Attack
  - Incentives
  - Cooperation


excerpt: Steve Barbour explains a basic funamental on mining and a 51% attack. Posted February 22, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Tweetstorm: On 51% Attacks from a Miner](https://twitter.com/SGBarbour/status/1231344795991175168)
### By [Steve Barbour](https://twitter.com/SGBarbour)
### Posted February 22, 2020

Bitcoin's security properties are amazing. For example, one really great aspect of proof-of-work consensus is that if a 51% attacker decides to orphan blocks from honest miners then the difficulty will adjust downward up to 50%.

This results in a decrease in the cost for honest miners to find blocks, so the honest hashpower that was priced out before is now incentivized to come online, increasing the difficulty for the attacker to maintain 50%+ of total hashpower.

And as soon as the dishonest attacker yields to honest miners the difficulty increases up to 2x, increasing the cost to attack and driving expensive hashpower offline again.

In parallel, if the dishonest attacker also chooses not to include certain transactions in his blocks then fees increase as a result and honest miners who accept the transaction in their block are paid more than the attacker, driving up honest hashpower.

Further, since 50%+ of hashpower gives the majority miner 100% of rewards, then any extra capital spent on maintaining their hashpower beyond 50% is wasted.

And then, of course, there are many incentives for an attacker to play nice rather than censor other miners or merchants. Bitcoin really is beautifully engineered system.

***

{% include signup.md %}
