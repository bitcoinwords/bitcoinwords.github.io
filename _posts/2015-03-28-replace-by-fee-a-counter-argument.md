---
title: "Replace by fee"
permalink: "/replace-by-fee-a-counter-argument"

author: mikehearn

tags:
  - Mike Hearn
  - 2015 Q1
  - Technology
  - Fees

excerpt: Replace by fee. Posted March 28, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Replace by fee](https://medium.com/@octskyward/replace-by-fee-43edd9a1dd6d)
### By Mike Hearn
### Posted March 28, 2015

##### A counter argument

Lately I have been asked about the *replace by fee* (RBF) patch by Peter Todd, and the “scorched earth” policy he proposed to go along with it.

I think RBF is a badly thought out idea that won’t work, doesn’t do what it’s claimed to do and would be harmful for Bitcoin if adopted.

In this article I will argue the case against RBF. I am not alone in thinking that this proposal is a bad idea and I hope after reading this you will agree with us:

> Repeating past statements, it is acknowledged that Peter’s scorched
>
> earth replace-by-fee proposal is aptly named, and would be widely
>
> anti-social on the current network
>
> — Jeff Garzik

> Coinbase fully agrees with Mike Hearn. RBF is irrational and harmful to Bitcoin. — Charlie Lee, engineering manager at Coinbase

> Replace-by-fee is a bad idea. — Gavin Andresen

> I agree with Mike & Jeff. Blowing up 0-confirm transactions is vandalism.
>
> — Adam Back (a founder of Blockstream)

In a second article, I discuss [double spending in general and other proposed solutions for making it harder](https://medium.com/@octskyward/double-spending-in-bitcoin-be0f1d1e8008).

#### What is it?

Replace-by-fee-scorched-earth is an attempt to fix perceived problems with unconfirmed transactions and make double spending harder.

Since day one Bitcoin has had a rarely discussed but fundamental rule called the *first seen rule*. The first seen rule says that given two transactions or blocks that build off the same dependency, whichever one the node saw first wins.

This rule is not something that can be enforced via the block chain itself, but it’s still critical for how Bitcoin works. In the case of choosing which block to mine on, it’s what incentivises people to start building on top of the new block when one is found rather than trying to split the chain by finding another block that’s somehow “better”. In the case of transactions, it’s what allows us to buy things in shops and make payments in seconds rather than hours.

The RBF patch replaces this rule with a new one that says given two transactions, whichever one pays the highest fee wins. It doesn’t propose changing the first seen rule for blocks, although as we will see in a moment, the broken logic that drives RBF applies to blocks just as easily as it does transactions, so this inconsistency makes little sense.

The primary effect of adopting RBF would be to make double spending of unconfirmed transactions very easy. Todd wants wallets to have an undo button in them that broadcasts a double spend transaction with a higher fee that returns the money back to the users wallet.

#### Scorched earth

This leads to an obvious problem — being able to send money in seconds rather than waiting for blocks is a highly desirable feature. It’s absolutely essential for buying stuff in shops. A currency that can’t be used to buy a newspaper on the street is not going to be seen as a real currency by the man on that street.

So Todd argues for a second thing: what he calls “scorched earth”. It’s actually an idea proposed by a pseudonymous author who called himself John Dillon, although apparently he did not describe this in any public post.

It relies on a second change called *child pays for parent*. This change was originally proposed years ago (by whom has now been lost in the mists of time), and has been implemented by Luke Dashjr in the Eligius pool. It makes a lot of sense by itself and is hopefully going to be integrated into the next Bitcoin Core release. Child-pays-for-parent means that miners will consider the fees of transaction graphs as a whole rather than just the individual components. Intuitively, it means if there is a transaction with no fee sitting around waiting to be confirmed, then another transaction that spends the first and does have a fee will increase the priority of the free transaction. This makes sense for miners as otherwise there would be stranded money they could take blocked up behind a free transaction, and it makes sense for users and merchants as they can now bump the fee on a transaction that’s taking too long to confirm, by adding a spend-to-self transaction on top.

The idea behind “scorched earth” is that if someone buys something with an unconfirmed transaction, when they walk out of the shop and press undo they double spend the original output to themselves with a higher fee, but the merchant sees this and then adds a spend-to-self transaction on top of their original payment with a slightly higher fee, and then the fraudsters wallet does the same to bump the fee on *his* chain of transactions, and so on and so on until the entire payment has been consumed in fees. The fraudster gets the goods, the payment is now going to a miner instead of the merchant, and the merchant is left with nothing.

#### Game theory and rationality

John Dillon argued that by making the initial transaction pay much more money than the actual price of the thing they’re buying (with the merchant sending the difference back to the buyer in a second transaction), an attempt to double spend will result in the buyer losing more money than the product was actually worth and so double spending in this way becomes irrational. Thus unconfirmed transactions would become safe.

Note: this means people will get money stuck in their wallet that’s difficult to spend, because buying something would require committing more money to the transaction than the item actually costs. That would be a severe usability problem, but I’ll ignore it for the purposes of this article.

Additionally, RBF advocates argue that adoption of RBF-SE is inevitable because any rational miner wishes to maximise his income from fees, and as nothing in the Bitcoin protocol enforces the first seen rule it will be abandoned in order to maximise short term profit.

These arguments sound good because they seem to only rely on game theory, a careful arrangement of incentives and some small technical tweaks to the protocol. Also they come with large helpings of cleverness — guaranteed to appeal to Bitcoiners.

**The problem is both arguments rely on extremely dodgy definitions of rationality**. If rationality is misdefined then arguments based on game theory can result in garbage conclusions.

The first argument sounds good until you remember that the merchant still lost their product to the fraudster, and the miner gained more than the price of the goods in question. This situation is stable right until the moment miners and fraudsters realise they can team up and split the earnings. That is easy to implement: miners running the patch set just have to add another patch that picks the output which was double spent and then sends some of the double spent value to it (say a quarter). Now the fraudster got the stolen goods *and* half their money back, so they effectively only paid half price and can now fence the goods for a bit more than that to yield a reliable stream of profit.

In other words, replace-by-fee-scorched-earth collapses completely with only a tiny extra step.

But it gets worse! Even if this collaboration doesn’t happen, the merchant has still lost the goods that were effectively stolen from them. This means any rich company can simply double spend a small competitor into oblivion by repeatedly stealing goods from them. This is much more powerful than market dumping because it works even if the competitor has better products that would otherwise resist below-cost pricing.

In practice, of course, neither outcome would hurt merchants much at all for a stunningly obvious reason: faced with this type of payment fraud they would just abandon Bitcoin and go back to banking. Credit cards might well have chargebacks, but [they are ordinary trade disputes and merchants win the case about 40% of the time](http://www.thecitywire.com/node/32380#.VQwe6hDF9q4). It’s easy to forget this in the middle of entertaining but abstract arguments about game theory. Our competition is not some academic ideal, it’s consensus-by-mainframe. If we’re worse than that Bitcoin won’t get adopted.

There’s one final problem. The code Peter Todd is pushing **does not implement this system** and thus using it would not result in the outcome he suggests, even if we ignore the gaping holes in the underlying reasoning. Specifically he hasn’t implemented the wallet side of the protocol anywhere, not even in obscure wallets, and so in reality nobody would notice the second double spend and start the scorched earth mechanism. They would just lose the entire amount and it’d cost the fraudster one satoshi.

In the end, all this code *actually* does is make fraud easier. That helps nobody.

#### The inevitability of failure

RBF advocates tend to argue that replace by fee is inevitable even if it leads to lots of double spending, because a rational miner will always want to take the transactions with the highest fees and nothing in the block chain algorithm stops them from doing so.

This argument also relies on a ridiculous definition of rational.

Whilst rational economic actors do attempt to maximise their profit, the argument ignores that this takes place in the context of varying time windows. In effect it argues that it’s “rational” to take a tiny increase in profit today even if that destroys your business and all the potential long term profits you could obtain tomorrow and the day after. This definition is absurd and no actual business works that way.

In reality businesses attempt to maximise profit over some kind of time period, which is almost always longer than the time it’d take merchants to abandon Bitcoin and go back to credit cards (probably on the order of weeks or days). If we saw massive double spending then large numbers of merchants would find the hassle of accepting Bitcoin to be much greater than the benefits, would stop accepting it, and the resulting loss of confidence would kill the BTC price. That in turn would cripple miner profits and send many of them underwater on their investments.

Only in a world where most miners have literally nothing to lose and have absolute confidence that BTC will be worthless tomorrow would it make sense for them to collectively wreck their businesses like that. Yet the argument for replace-by-fee states that this outcome is inevitable! That’s not showing much confidence in the future of Bitcoin!

Of course, from time to time there *will* be a miner who has much shorter time horizons than the others. Perhaps they suddenly have an unexpected need for cash, or perhaps they receive notice mining is being banned in their country, or perhaps a bad insider without any stake in the business decides to scam some merchants and run with the money. Bitcoin is designed to tolerate a minority of dishonest miners and a small amount of payment fraud against unconfirmed transactions is tolerable by merchants. What cannot work is a global change to the rules that makes every miner behave this way by default.

#### RBF for blocks

One problem with the definition of replace-by-fee is that whilst Peter’s patch only implements the logic for unconfirmed transactions, if miners are expected to ignore the rule for new broadcasts it stands to reason they would ignore it for confirmed transactions as well.

Put simply, if a miner sees a broadcast double spend of a confirmed transaction that would result in fees higher than the expected cost of forking the chain, miners implementing the RBF policy completely would then start work on forking the chain from that point. And as they would all do it simultaneously, this would then incentivise broadcasts of yet more double spends against already confirmed transactions that have only tiny fee increases — but as miners are working on a rewrite of the timeline anyway, it costs them nothing to go back and include other double spends as well.

So RBF taken to its logical conclusion not only results in unconfirmed transactions becoming useless, but confirmed transactions too!

This is why the abstract to Satoshi’s paper states:

> As long as a majority of CPU power is controlled by nodes that are not cooperating to attack the network, they’ll generate the longest chain and outpace attackers.

Both a plain reading of Satoshi’s paper and common sense will tell you that going back in time and double spending is an attack on the network.

Quoting Satoshi again:

> In this paper, we propose a solution to the double-spending problem using a peer-to-peer distributed timestamp server to generate
>
> computational proof of the chronological order of transactions
>
> . The system is secure as long as honest nodes collectively control more CPU power than any cooperating group of attacker nodes.

Making miners ignore the “chronological order of transactions” by default converts them all into dishonest attackers, which would break the system completely.

#### Is Bitcoin really protected by honesty?

Although Satoshi’s paper used the term honest where these days we would say rational, sometimes people have trouble with the idea that Bitcoin is reliant on lots of people sticking to the rules rather than pure mathematics.

I suspect the belief that Bitcoin is protected by pure maths has its roots in the word cryptocurrency, which is a false friend. After all, everyone knows that nobody can crack an encrypted message no matter how many people agree it should be done. So it stands to reason that *crypto*currency would give the same hardness to money that *crypto*graphy gives to messages. But nothing in Bitcoin is encrypted. All it does is produce a couple of documents — the ledger and an audit log showing how the ledger got into that state. The interpretation of those documents is and always will be up to people, who can ignore them entirely or selectively whenever they want to.

So: money is not a mathematical construct. It’s a social construct. The fact that Bitcoin uses some fairly basic maths to coordinate social decisions over the internet doesn’t change that.

#### Is RBF happening already?

Occasionally someone claims that RBF is already in use by miners and so this policy is already here and we might as well just deal with it. In fact there’s a guy named Tom Harding who monitors the Bitcoin network for double spends. He has observed attempts at exploiting RBF and discovered that for transactions spaced 10 seconds apart it only works about 1% of the time. This is higher than the ideal of zero, but with a 10 second gap some of that can be explained just through slow propagation and anyway, wallets can watch out for a propagating double spend and tell the merchant to abort the transaction. So in practice it’s easy to avoid losses due to this type of attack. 10 seconds is still a lot better than 10 minutes.

### Conclusion

* The current replace by fee patch is incomplete, as it doesn’t implement the protocol in any wallets. So it doesn’t provide the outcome the author claims it does.
* Even if it had more implementations, the underlying logic requires a tortured form of game theory that doesn’t match the real world. It fails as soon as miners and payment fraudsters start collaborating.
* Even if it worked in the way it claims to work, it would allow big companies to crush smaller competitors very easily, just by double spending against them.
* It requires people to have more money than in their wallet than they can actually spend in shops. Good luck explaining this to the ordinary people we want to adopt Bitcoin.
* Making unconfirmed transactions useless would break Bitcoin, cause merchant abandonment, crush the price and push many miners underwater on their investments. It’d be highly irrational for miners to get on board with this.
* The RBF policy directly contradicts the definition of Bitcoin given in the white paper. It would logically apply to blocks as well as unconfirmed transactions given high enough fees and low enough inflation rewards. Bitcoin cannot operate at all with such a policy.
* Given all of the above, RBF is not implemented widely and attempts to exploit it virtually always fail. **RBF is in no way inevitable and miners that adopt it are just shooting themselves in the foot.**

***

{% include signup.md %}
