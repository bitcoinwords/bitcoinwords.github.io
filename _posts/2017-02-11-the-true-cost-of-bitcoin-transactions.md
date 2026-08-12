---
title: "The True Cost of Bitcoin Transactions"
permalink: "/the-true-cost-of-bitcoin-transactions"

author: erikvoorhees

tags:
  - Erik Voorhees
  - 2017 Q1
  - Mining
  - Economics
  - Money

excerpt: The True Cost of Bitcoin Transactions. Posted February 11, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The True Cost of Bitcoin Transactions](http://moneyandstate.com/the-true-cost-of-bitcoin-transactions)
### By Erik Voorhees
### Posted February 11, 2017

It seems the Bitcoin community is not correctly tallying the true cost of Bitcoin transactions.

The belief is that Cost = Miner Fee. We’ll show why this is wrong, but the fee is of course part of the cost, so let’s examine it first…

Fees are currently averaging in the range of $0.30 to $1.00 per transaction. Here’s an anecdotal sample as I’m writing this:

> Block #451871 $1,287 in fees / 1347 txs = $0.95 avg fee
>
> Block #451872 $1649 in fees / 2161 txs = $0.76 avg fee
>
> Block #451873 $1,497 in fees / 1450 txs = $1.03 avg fee
>
> Block #451874 $1,209 in fees / 1582 txs = $0.76 avg fee
>
> Block #451875 $1,591 in fees / 2180 txs = $0.73 avg fee

Total: $7,233 fees / 8720 txs = $0.83 avg fee

83 cents per transaction on average…

Is that “too expensive?” That’s a judgement call, and sincere people can disagree about what is “too expensive.” It depends what one uses Bitcoin for.

Some people, indeed, are using Bitcoin to move “normal” amounts of money around (ie – like a “peer-to-peer cash system”). This doesn’t refer to “micro transactions,” which are fractions of a dollar and have been impractical in Bitcoin for years, rather it refers to casual payments of $1-$50 in value, which make up the vast majority of human economic activity broadly, and a great deal of Bitcoin activity, specifically. An $0.83 fee doesn’t matter for a $2,500 payment, but it matters if you’re sending $7 to a friend. Indeed, it will actually preclude a $3 daily wage payment.

Consider that a great way to make Bitcoin centralized is to reduce its utility to only the world’s richest.

And those who imagine such users to be using Bitcoin “wrong” are perhaps not understanding what consequences that sentiment invites: such users, finding less utility in Bitcoin, will be incentivized to go to other platforms or just stick with the status quo: fiat. How tragic that someone would actually prefer fiat, but many will if Bitcoin is too expensive to use as a peer-to-peer cash system.

So on the topic of the explicit miner fee, maybe $0.83 is too high, and maybe not. It depends what a user is trying to accomplish.

But $0.83 isn’t the true cost… and this is a point most observers are missing.

The true cost of a Bitcoin transaction can be better considered as:

> Cost = F + T + Ru

Cost = Fee + Time taken to determine fee + Risk of uncertainty. What do I mean by this?

Those people who are using Bitcoin today pay more than a miner fee, they pay in time and uncertainty (risk). As blocks are full, users often need to change the fee they add to their transaction (before or after they send it). Some wallets do an okay job of this, but most don’t (and before you vilify wallet creators, realize that “smart fee policy” is nowhere near a science yet, and changes all the time). So, in addition to the $0.83 miner fee, the user currently has to also spend Time to determine that it ought to be $0.83 in the first place.

A highly-skilled Bitcoiner can figure out an appropriate fee in a minute, but *Bitcoin cannot be imagined as a platform only for highly-skilled Bitcoiners*. If that is the target market, then the project is doomed. A normal user (meaning most users) struggle with the fee estimation (hell, I’ve been doing Bitcoin for six years and I’m not the most graceful at fee calculation myself).

Many casual (read: normal) users of Bitcoin get horribly confused, and if they even bother trying to figure it out, they may wander over to /r/bitcoin to ask advice.

Look at this comment on Reddit to a user who was confused about transaction delays and fees:

![](/assets/images/2017/m2/the-true-cost-of-bitcoin-transactions1.png)

We should realize how awkward and confusing that is for a normal Bitcoin user (ie – a non-technical person who wants a system that is easy and convenient).

And at least that comment was trying to be helpful. Many users get responses more like this:

![](/assets/images/2017/m2/the-true-cost-of-bitcoin-transactions2.png)

Jesus. Add in the misery of dealing with people like /u/MinersFolly and it’s amazing Bitcoin is gaining users at all.

So back to our equation, the true cost of a transaction is: $0.83 (maybe?) + time to determine $0.83 + Risk of uncertainty.

What do I mean by uncertainty? Well, even if a user figures out a recommended fee, there is no guarantee it will be confirmed in the next block. Using a recommended fee gives zero guarantee of delivery time.

Here’s a depressing real world anecdote: A couple months ago I had some friends over for a Civ 6 LAN party. One guy didn’t have the game, so I offered to buy it on Steam for him (they accept Bitcoin!). I paid the BitPay invoice for the Steam game, and waited. And waited. And waited. 25 minutes later it still hadn’t showed up. Three blocks had already happened. Everyone is sitting around waiting. Ultimately, I just pulled out a credit card and bought the game (paying again) so that we could all play. A year ago, this would not have happened. What went wrong? Was my fee incorrect? (I paid the high fee option in Jaxx wallet). Was the mempool too full? We just wanted to play, so back to the 50 year old credit card technology I went.

There are some in the community who read the above and actually think, “meh, what’s the big deal?” Or perhaps respond, “just wait two years for Lightning!” Cool, tell me that when I’m trying to buy Civ 7.

Back to the present… because of this uncertainty users are facing, one of two consequences happen:

1) the user gets annoyed at the delay, or actually suffers some kind of economic loss, or

2) the user can’t use Bitcoin for this tx at all because it is time sensitive and user can’t risk the uncertainty.

And be careful not to discount the utility loss to a Bitcoin user, who was getting excited about making a Bitcoin transaction (the future of money!), only to discover his tx is stuck in the mempool for 33 hours. We’re lucky if that user ever gives Bitcoin another chance.

Fee + Time + Risk of uncertainty (F+T+Ru). Since T and Ru are not measureable, it seems most engineers in the industry have been completely oblivious to them. The costs are more apparent to an economist, and are very apparent to anyone in business with actual users (there’s a reason why nearly every Bitcoin business with more than ten thousand users is very eager to see both SegWit and a hardfork blocksize increase… but that’s another topic).

> As blocks approach capacity:
>
> 1) Miner fees get more expensive
>
> 2) Time/effort to determine fees rises
>
> 3) The reliability of transactions falls toward zero (risk of hours-long delay for first confirmation, even with “good fees”)

Many people have only been considering #1, above.

Those who look at a recent tx fee of $0.30 and obnoxiously proclaim, “transactions are cheap, you can’t expect the system to be free!” are really missing the point and are harming the prospects of this project. The miner fee is only part of the cost that users are dealing with, and if peoples’ time and sanity are worth anything, it is the lesser part.

And let’s end this silly false dichotomy of Bitcoin as a “payment system” vs a “settlement system.” Such distinction is a relic of fiat banking networks and has no place with blockchain-based assets. The reality is this: every payment on a blockchain network is a settlement, and the cheaper these transactions, the more widespread uses the platform will find, meaning greater utility, a broader and more decentralized user-base, higher market capitalization, more liquidity, and therefore more hashpower dedicated to it, and more security derived therefrom.

If Bitcoin transactions are too expensive (considering F+T+Ru), people will use other platforms instead for some or all of their economic activity, period. [As I tweeted yesterday](https://twitter.com/ErikVoorhees/status/830197808573587457), I’ve found myself now holding a modest balance of Ethereum merely for the purpose of small (not micro) payments to friends. It’s just cheaper and more reliable. And I’m doing that with more allegiance to Bitcoin than almost anyone on Earth, how dedicated will a normal person be to a platform that isn’t helpful to them?

The response of some has been, “so what, good riddance.” Such people are being arrogant, naïve, and suffering from a disease common in the business world: not listening to or respecting customers. Such people are free to have that sentiment, of course, just as they are free to end up on a lonely platform.

Now, obviously a blockchain cannot (and should not) handle all the world’s transactions on-chain, but that doesn’t mean we shouldn’t do all we can to acquire as much transaction marketshare as safely possible. This is a platform about network effects, after all. Just because it’s true that Bitcoin’s blockchain can’t handle Visa-level scale on-chain, doesn’t mean we should be comfortable and complacent about a 5 tx/sec threshold today, especially during Bitcoin’s formative years, while the world is still watching and waiting to see if it catches on as the money protocol of the future (those who think Bitcoin’s dominance is “inevitable” are, again, suffering arrogance).

**Conclusion**

The community needs to take [at- or near-capacity blocks seriously](http://imgur.com/a/RzAQM), and yet many have dismissed the issue, saying silly things like “well when fees rise it’s just the free market at work.” Sure it is, and when users leave Bitcoin, or never bother a second transaction because their first was obnoxious and unreliable, their preference of alternatives will also “just be the free market at work.” The goal should be to do everything practical to make Bitcoin cheaper and more efficient, because if we don’t, it leaves a huge opportunity for Bitcoin’s successor. Bitcoin is free-market money. It competes, and it must be competitive.

As the true cost of Bitcoin transactions rises, utility at the margin falls, and the platform’s fundamental value as a tool for human economic interaction declines alongside. Reduce the number of use-cases for which Bitcoin makes sense, and the quantity and quality of people willing to hold a portion of Bitcoin declines.

As will the price, as will the promise.

![](/assets/images/2017/m2/the-true-cost-of-bitcoin-transactions3.jpg)

  [Erik Voorhees](http://moneyandstate.com/the-true-cost-of-bitcoin-transactions#) http://www.ShapeShift.io Erik Voorhees, CEO of leading digital asset exchange ShapeShift.io, is among the top-recognized serial Bitcoin advocates and entrepreneurs, understanding Bitcoin as one of the most important inventions ever created by humanity. Erik's former project, the groundbreaking gaming phenomenon SatoshiDICE, was, at its peak, responsible for more than half of all Bitcoin transactions on Earth and popularized the concept of "provable fairness." Having been a featured guest on Bloomberg, Fox Business, CNBC, BBC Radio, The Peter Schiff Show, and numerous Bitcoin and industry conferences, Erik humbly suggests that there is no such thing as a “free market” when the institution of money itself is centrally planned and controlled. This blog is about the human struggle for the separation of money and state, and about Bitcoin as the instrument by which it will happen.

You can start editing here.

***

{% include signup.md %}
