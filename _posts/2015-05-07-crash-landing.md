---
title: "Crash landing"
permalink: "/crash-landing"

author: mikehearn

tags:
  - Mike Hearn
  - 2015 Q2
  - Money
  - Technology
  - Scaling

excerpt: Crash landing. Posted May 7, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Crash landing](https://medium.com/@octskyward/crash-landing-f5cc19908e32)
### By Mike Hearn
### Posted May 7, 2015

![](/assets/images/2015/m5/crash-landing1.jpg)

*What not to do*

A common argument for letting Bitcoin blocks fill up is that the outcome won’t be so bad: just a market for fees. Everyone loves markets, right? So who could object to that?

Actually lots of people could object, for the same reason that nobody really welcomes the new market for IPv4 addresses. IP addresses becoming scarce, complicated hacks like carrier NAT and corporations duking it out in the market for capacity is not a win for the internet: it’s a temporary kludge whilst we all migrate to the real solution: IPv6.

But it doesn’t matter — because the assumption underlying all of this is wrong. I don’t believe fees will become high and stable if Bitcoin runs out of capacity. Instead, I believe Bitcoin will crash.

In this article I will examine two scenarios.

The first is what will happen if next year (when I predict blocks will get over-full) we are running substantially the same software as today.

The second is what will happen if we are running some hypothetical upgraded version of Bitcoin Core and wallet apps.

In both cases I assume a 1mb block size limit.

#### Same code as today

What actually happens when Bitcoin Core runs out of capacity?

Transactions flow into the system at a somewhat steady rate. The rate is lower on Sundays. They enter the “memory pool” which is a holding area for transactions before they appear in the block chain. As the name implies, it’s stored in memory only. If a node is restarted the local copy of the pool is cleared, though of course transactions live on in the memory of other nodes.

As we approach 100% full, the first thing that happens is that [confirmation times start to become huge](http://hashingit.com/analysis/34-bitcoin-traffic-bulletin). According to Monte Carlo simulations by Dave Hudson, at 80% full half of all transactions take around 20 minutes to confirm. At 100% full half of all transactions should wait longer than 6 hours.

But actually that’s not what would happen. The reason is that at 100% full, the true rate transactions are occurring at would likely be more than 100%. So a permanent backlog would start to build up.

Bitcoin Core has no code in it to handle a permanent and growing transaction backlog. Transactions just queue up in memory until the node runs out. At that point one of three things can happen:

1. The node might become incredibly slow as it enters swap hell.
2. The node might crash when it tries to allocate memory and fails.
3. The node might be killed by the operating system kernel.

All three cases are bad news. Bitcoin Core does not restart itself automatically. If a node dies or freezes up it requires the owner to notice restart it manually, each and every time.

What’s more, almost all wallets don’t know how large the backlog is. They will let users send money regardless of how big the memory pool has become. So as the backlog grows, nodes will start running out of memory and dying. And it will take time until they get restarted.

You might think that nodes being restarted will help clear the situation because the node will forget about all the transactions and then be back to normal. But this has two problems. One — it makes double spending a lot easier. People want to buy things quickly and that will become suddenly less reliable. Two — wallets still have no clue anything is wrong. They just notice their transactions didn’t confirm yet. And wallets are programmed to keep re-broadcasting transactions that aren’t yet confirmed. So nodes will quickly fill back up again as transactions are re-announced and the backlog gets even longer, once again pushing them over the limit.

I don’t know how fast this situation would play out, but as Core will accept any transaction that’s valid without any limit a node crash is eventually inevitable.

##### What happens then?

Well, users will notice that transactions aren’t confirming. They will have been complaining for a long time before this, but now they’re going to *really*complain. Some of them will experience real inconvenience and may even lose money, because e.g. they arrange an in person trade, move money from their desktop/web wallet to their phone, and by the time they arrive at the trading point their transaction has still not confirmed so their wallet will not let them send the money.

We know this because in the past we’ve hit “soft block size limits”. This is where miners are programmed by default to only make blocks below a certain size that’s less than 1mb. Back in 2013 [this soft limit of 250kb was hit and transactions started to back up](https://bitcointalk.org/index.php?topic=149668.0). Users were complaining, which is why I made the linked post. Some mining pools bumped their soft limits and started making bigger blocks, so things calmed down pretty quick. But if you read that discussion you can see all the same arguments then as now. There is no problem! Just pay more in fees!

##### Why a fee market doesn’t save you

There is much talk of a “fee market”. There are the beginnings of such a market today. The problem is that in the short term this would make the overload situation worse and even create more centralisation.

How so?

* Fees are currently very low. As transaction backlogs build and nodes start to crash, everyone will think “One more penny is no big deal. I can afford that”. Let’s assume for a moment that child-pays-for-parent is implemented. So in an attempt to bump the fees on their first transaction which suddenly don’t seem to be enough, they generate *another* transaction, which makes the overload situation even worse and makes nodes crash out even faster!
* There is no good way to automatically choose a fee. Even if you decide to bump your fee a little bit, because it’s taking hours to confirm transactions you can easily be outcompeted by other transactions that pay even more a short while later. The only way you are able to discover that the fee you paid is insufficient, is when you notice the transaction is not confirming. But you’re expecting transactions to take many hours anyway even if the fee is high enough (see the simulation data above). So after hours and hours you would try adding another fee with another transaction, but the same thing can happen — the “race to the top” is not synchronized and everyone is taking the smallest steps possible because they don’t want to waste money. So you have to keep adding more money and yet …. you don’t get what you feel you are paying for!
* SPV wallets have no way to know what their fee competition looks like without some fairly hefty protocol changes (which require a fork). Currently they can get by with some hard-coded fee levels, which work fine almost all the time. In an overload situation that wouldn’t be true any more and they would have to ask a trusted third party. The whole “small blocks makes things more decentralised” argument ignores this problem: for the many users who are using the most practical type of decentralised wallets today, they would end up with LESS decentralised software than before.

##### But how will miners be sustained without fees?

This comes up a lot.

Neither me nor Gavin believe a fee market will work as a substitute for the inflation subsidy. It just doesn’t seem to work, economically. You can [read Gavin’s thoughts on this](https://blog.bitcoinfoundation.org/blocksize-economics/), and I wrote a post explaining [one possible alternative](https://bitcointalk.org/index.php?topic=157141.0;all).

So what role *do* fees have? Their primary purpose today, and I believe in future as well, is to let people buy their way out of the penny flooding protections Bitcoin has. In an ideal world most transactions would in fact be free. Only wallets that send transactions very rapidly (e.g. exchange wallets) would have to pay fees. Miners would include free transactions ordered by “priority” as they do today (calculated as coin age times value), and they’d do it because circulating bitcoins are valuable bitcoins. Additionally the psychological difference between “Bitcoin has no fees” and “Bitcoin has tiny fees” is significant.

Maybe that won’t happen. We’ll have to see. But this is the reason why I don’t see an artificial overload solving economic problems.

##### How would users react?

Badly.

Many years ago I was walking down a corridor with my new Google mentor, the incredible [Andrew Kirmse](https://en.wikipedia.org/wiki/Andrew_Kirmse). He said I’d be doing capacity planning and cluster buildouts for Google Earth.

I felt a bit nervous about it, so 22 year old me said:

> “I guess if we run out of capacity the worst that could happen is we’d have an outage for a few hours. Or maybe a day.”

Andrew looked at me like I was insane. *“Yeah … but that’d be bad. That’d be in the news”*.

In the news??? Huh! Right! Of course it’d be in the news. Google hardly ever had outages. It had a reputation for competence. If Google Earth went down for hours because it ran out of capacity …. that’d be seen as a sign of incompetence. That would be a story worthy of CNN. Gulp.

How do you think ordinary Bitcoin users would react on hearing of crashing nodes, a swelling transaction backlog, a sudden spike in double spending, skyrocketing fees … and all of it because of an entirely predictable event with an incredibly simple fix?

They would conclude that the Bitcoin developer community was incompetent. That would make the news.

And as Bitcoin holders who aren’t daily users woke up and read these stories, they would conclude that maybe they had miscalculated the future value of Bitcoin …. that maybe Bitcoin wasn’t going to be the currency of tomorrow after all.

Whenever there are sudden swings in price, there are spikes in transaction traffic as people move their coins into exchanges. This can be seen very clearly on the graphs. As large numbers of people suddenly lost faith in Bitcoin and the price started to fall, they would decide that now was the time to get out. And so long dormant coins would start to move ….. or at least try. The transaction backlog would get even worse.

##### The aftermath

Bitcoin would eventually recover. Users who became frustrated at the extreme unreliability would give up and stop trying to spend their coins. Many coins would make it to an exchange wallet and stay there. Node operators would make their nodes auto-restart. SPV wallets would find some trustworthy central authority to get fee data from.

Most importantly, the overload would eventually go away …. because the users would go away. The backlog would clear. Fees would fall to the minimum again.

So life would go on.

Bitcoin would survive.

But it would have lost critical momentum. It would have become the MySpace of digital currencies. The faithful would have lost a lot of faith, and businesses that were trying to bring Bitcoin to the mainstream would “pivot” towards something else. People who were motivated by Making The World A Better Place™ would conclude the ordinary people around them would never use their products, and so they’d leave.

#### With upgraded code

Let’s rerun the scenario with upgraded code. It isn’t much better, but I have to do this, otherwise I know some people will bring it up.

Let’s imagine the following change is made before Crunch Day: Bitcoin Core imposes limits on the mempool size, so it can’t run out of memory any more.

There are other changes theoretically possible, like the chain fork required to let SPV clients calculate fee estimates themselves (this is a lot of work), but I don’t believe there’s any chance that they would happen in time.

OK, so … both blocks and the memory pool become full. Bitcoin is done: it can’t digest any more transactions at the moment.

What happens now? One of the following:

* Wallets attempt to submit a transaction to the network, and get a *reject* p2p protocol message back from the remote peers, telling them that the memory pool is full. The user is shown an error message and the coins do not move. The user is understandably rather upset that his money *seems to be stuck in his wallet and he cannot even sell it for a working currency*.
* Wallets attempt to submit a transaction to the network, but don’t get a reject, or only get rejects from half their peers. I’ll talk about why this can happen in a moment. The nodes that received the transactions attempt to relay it, but not everyone’s mempool is identical, so the transaction won’t propagate everywhere reliably. It might make it to some mining pools but not others. It may or may not make it across the network to the receipient of the funds. If the recipient doesn’t see it, you don’t get to buy your product. If they do see it, but the transaction doesn’t make it to all the miners, your 6 hour 50th percentile confirmation window just got a LOT worse. Transactions could routinely take a day to confirm, or more. The user will be understandably rather upset that the money *seems to be stuck in his wallet and he cannot even sell it for a working currency.*
* The wallet learns that their transaction didn’t make it into the mempool, and decides to try again with a higher fee. They resubmit, and nodes say … OK. I will kick out the lowest fee paying transaction and replace it with yours. However, the original sender of that transaction has gone offline and doesn’t know this has happened. Now their transaction is stuck — it will never confirm. Eventually they may notice and try to bump the fee again, but once more, they have no guarantee they won’t be gazumped a second time, or a third, or a fourth ….. after a few tries, the user will be understandably rather upset that the money *seems to be* *stuck in his wallet and he cannot even sell it for a working currency.*

Why would wallets not receive reject messages? Put simply, it’s that darned developer consensus again. Some Bitcoin Core developers believe that the *reject* message should be something only used for debugging and not something apps can rely upon. So there is no guarantee that a wallet would learn that its transaction didn’t fit. If not, we’re back to the infinite-confirmation-time transaction problem again.

#### Conclusion

I believe there are no situations in which Bitcoin can enter an overload situation and come out with its reputation and user base intact. Both would suffer heavily and as Bitcoin is the founder of the cryptocurrency concept, the idea itself would inevitably suffer some kind of negative repercussions.

For this reason, it’s important that we raise the limit with plenty of time to spare, so business as usual can continue.

***

{% include signup.md %}
