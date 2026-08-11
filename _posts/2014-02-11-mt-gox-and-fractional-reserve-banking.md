---
title: "Mt. Gox and fractional reserve banking"
permalink: "/mt-gox-and-fractional-reserve-banking"

author: petersurda

tags:
  - Peter Surda
  - 2014 Q1
  - Economics

excerpt: Mt. Gox and fractional reserve banking. Posted February 11, 2014.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Mt. Gox and fractional reserve banking](http://www.economicsofbitcoin.com/2014/02/mt-gox-and-fractional-reserve-banking.html)
### By [Peter Surda](http://www.economicsofbitcoin.com/)
### Posted February 11, 2014

While Mt. Gox has been long accused of running a fractional reserve system, the accusations increased during the last couple of days due to an escalation of the [transaction malleability aspect of Bitcoin](https://en.bitcoin.it/wiki/Transaction_Malleability), and the inability of Mt. Gox to handle it on the technical, managerial and PR level. Some of the more elaborate accusals have been done by Dave Howden ([first](http://mises.ca/posts/blog/bitcoin-bank-run/), [second](http://mises.ca/posts/blog/bitcoin-bank-run-take-2/)). While I don’t know whether Mt. Gox is or isn’t running fractional reserves, I thought I’d bring up a bit of my research on the theory of anti-FRB arguments. In an earlier version of the draft of my master’s thesis, dating about two years ago (i.e. long before the situation at Mt. Gox started escalating), I had a section analysing the legitimacy of FRB from Austrian perspective. It didn’t make it into the final version because my advisor argued that it is outside of the scope of the topic, so I should consider leaving it out (he was probably right). I think that it might be useful to look at the Mt. Gox situation from this perspective. The next section is quote from the draft (with some minor modifications).

### Redeeming deposits on demand

[de Soto (2009)](http://mises.org/document/2745) argues that a deposit contract requires that the deposited item be redeemable on demand, and because it is impossible to redeem all fractional reserves on demand in all cases, it is illegitimate:

> “Its [deposit contract, ed.] fundamental purpose is the custody or safekeeping of the good and it implies, for the duration of the contract, that the complete availability of the good remain in favor of the depositor, who may request its return at any moment. … The obligation of the depositary is to guard and protect the good with the extreme diligence typical of a good parent, and to **return it immediately to the depositor as soon as he asks for it**.” [emphasis added]

I submit that there are cases where redemption on demand is refused even during a full reserve deposit. Following is a list of some of these cases:

1. it is outside of the opening hours of the bank
2. the bank is undergoing an audit during which access to reserves is suspended
3. the particular branch does not have sufficient reserves[<sup>1</sup>](https://blog.economicsofbitcoin.com/#bot1)
4. there are technical difficulties in accessing the reserves, for example a malfunction in the lock in the safe, or the person with the key is indisposed
5. there is an issue with verifying the authenticity of the withdrawal request[<sup>2</sup>](https://blog.economicsofbitcoin.com/#bot2)
6. the deposits were stolen by a third party and the bank was unable to obtain enough reserves from the insurance/bank owners/other financing source on time

In none of these cases is there a fraudulent behaviour by the bank. The last three cases could be argued to be a consequence of negligence and give a rise to liabilities, however the first three are perfectly legitimate occurrences. Therefore, the impossibility to redeem the deposit on demand is not a sufficient criterion to conclude illegitimacy.

There is also the praxeological issue of differentiating withdrawal on demand and after a fixed period. The act of withdrawal is a type of action, and as such takes some time. It begins with the depositor initiating a contact with the bank, continues through the bank obtaining identification of the depositor or at least the bearer instrument he provides, verifying it, accessing their reserves, recording the withdrawal in their accounting systems and presenting the specie to the withdrawer[<sup>3</sup>](https://blog.economicsofbitcoin.com/#bot3). During this time, the bank can liquidate some of their investments to compensate for the lack of reserves at the time of initiation of the withdrawal request. So from praxeological point of view, it is impossible to differentiate between on demand and not on demand deposits.

### Applying the theory onto Mt. Gox

Based on known facts, Mt. Gox suffered from points 2, 4, 5 and 6. Their automated system for processing withdrawals is broken, they cannot verify if a withdrawal did or didn’t occur, and have a mess in their accounting as a result and are re-auditing their systems. We don’t know for sure if any of the deposited bitcoins have been stolen as a result of this, but previously, the US Department of Homeland Security and the US Secret Service [seized](http://techcrunch.com/2013/08/23/feds-seize-another-2-1-million-from-mt-gox-adding-up-to-5-million/) (i.e. stole) about 5 million USD from Mt. Gox’s bank accounts in the USA.

I’m not going to speculate whether Mt. Gox can fix this mess, but at least theoretically the problems casued by transaction malleability should be possible to audit, and at least there where account holders themselves successfully performed a double spend attack, Mt. Gox knows who they are, and can attempt legal action against them.

### What can we learn from this?

I would like to introduce a saying: “Whatever bad happens with Bitcoin happens to Mt. Gox first”. In other words, Mt. Gox is a lucrative target, because of its history, market share, poor management and PR skills. Attacks thus tend to affect Mt. Gox first. This generates knowledge, and entrepreneurs and users who observe these attacks, their consequences and reactions of Mt. Gox can learn from this, and not repeat the mistakes. Maybe we can argue that Mt. Gox should have spent more on management, auditing, PR or lobbying (to avoid the account seizures), but not all of this can be known in advance, and thus some level of experimenting is necessary. I don’t want to present myself as [Captain Hindsight](http://southpark.wikia.com/wiki/Captain_Hindsight). Nassim Taleb [argues](http://www.amazon.com/Antifragile-Things-That-Gain-Disorder/dp/0812979680) that we should honor failed entrepreneurs for showing us what doesn’t work. Maybe we should do the same thing with Mt. Gox. After they repay everyone their deposits back.

***

Footnotes:
 [**1**](https://blog.economicsofbitcoin.com/#top1)An analogous situation would be an ATM running out of cash.
 [**2**](https://blog.economicsofbitcoin.com/#top2)In a security breach in May 2012, Bitcoinica lost their main trading database and they had to gather the data required for the verification from other
 sources, which was a time consuming process that took many weeks. Recent announcement (June 13th 2012) indicated that the payouts have started, however at the time of writing (June 17th) there were still unprocessed claims. Update for this blog post: Bitcoinica entered liquidation in November 2012 and still hasn’t concluded.
 [**3**](https://blog.economicsofbitcoin.com/#top3)The process described is exactly the same irrespective of whether the withdrawal is done through a clerk, through an ATM or online banking.

***

{% include signup.md %}
