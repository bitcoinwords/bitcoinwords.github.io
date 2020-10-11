---
title: "Tweet Thread on the Lightning Network User Experience"
permalink: "/tweet-thread-on-lightning-network"

author: giacomozucco

tags:
  - Giacomo Zucco
  - 2020 Q3
  - Tweet Thread
  - Lightning Network
  - Progress
  - Technical
  - Adoption
  - Economics
  - UX

excerpt: Giacomo lays out perception and reality of Lightning Network adoption. Posted September 15, 2020

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Tweet Thread on the Lightning Network User Experience](https://twitter.com/giacomozucco/status/1305828218067456000)
### By [Giacomo Zucco](https://twitter.com/giacomozucco)
### Posted September 15, 2020


1/
Many people complain that "managing Lightning Network liquidity is still very hard" when they talk of Bitcoin & LN as a possible online payment solution. After using it to send & receive most <$50 payments for almost 1 year, I strongly disagree, especially within the context.

2/
When we compare LNP with other, existing online payment systems, we compare it with Credit Cards, Debit Cards & newer Fintech Systems like PayPal. Debit Cards are especially used (especially for frequent, small payments, where the "refill" mechanism provides more security).

3/
How does a Debit Card work? There's a consequential distinction to be made here: the way Debit Cards work for people using them to *pay* over the internet (most of us, most of the time) is different from the way they work for people using them to *receive* (online merchants).

4/
In order to spend, you have to periodically fill up a bigger amount using a slower & possibly more expensive (especially wrt fixed costs) transaction (bank wire, typically). When the refill is complete, you can finally send small & frequent transactions, almost seamlessly.

5/
You can keep paying until the bigger amount, the one you filled up before, is over. Then you will have to fill up again (slower process, typically with fixed costs inconvenient for very small amounts), & so on. It may not be perfect, but it's the typical UX for this use-case.

6/
Now, receiving online payments via Debit Card is an entirely different story. There's a lot of regulatory friction: legal paperwork, KYC/AML compliance (which literally excludes the majority of people on this planet), fixed & dynamic fees, chargebacks. Truly terrible UX.

7/
How does LNP compare, UX-wise? I would argue it provides a strictly better UX in both cases (that is, assuming a merchant does accept it in the 1st place, which is still very uncommon, thus degrading the *overall* utility of this payment method for now). Let's see both cases.

8/
In order to spend, you have to periodically fill up a bigger amount using a slower & possibly more expensive (especially wrt fixed costs: the blockspace fees on-chain) transaction. When the refill is complete, you can finally send small & frequent transactions, quite easily.

9/
Unlike Debit Card spending, which is often actually free, LNP is not free: you have to pay for liquidity & "distance" from your payee in the graph. But fixed costs are still negligible &, of course, you have some advantages compensating: possible anonymity being the main 1.

10/
There's another important advantage: unlike w/ Debit Cards, where you *always* have to refill after your spending balance is empty, w/ LNP you may actually manage to rebalance it w/o getting back onchain: either receiving (see below) or routing other people's transactions!

11/
Granted: managing inbound liquidity in order to receive is not trivial (more on this below), & routing other people's transaction effectively, either for profit or to get some spending balance back is quite complex. But this is not even an option at all w/ our benchmark!!!

12/
Now, receiving. First you have to get some inbound liquidity: while not easy, it's orders of magnitude easier than getting a KYC/AML identity. Then you have to maintain it, which I'd argue it's not that more complex than the paperwork required for the Debit Card benchmark.

12/
Now, receiving. First you have to get some inbound liquidity: while not easy, it's orders of magnitude easier than getting a KYC/AML identity. Then you have to maintain it, which I'd argue it's not that more complex than the paperwork required for the Debit Card benchmark.

13/
So, in conclusion: basically identical to the "standard" online-payment UX for payers (thus also familiar, easy to learn/explain); very different but not necessarily harder to the "standard" online-payment UX for payees (the difference is technical complexity vs legal 1).

14/
If people find LNP UX confusing/complex, it's probably because they are comparing it w/ some inexistent "magical free lunch" that some Bitcoin advocates made up, where you somehow have all the advantages of on-chain BP, but not the drawbacks (cost, time, chain-privacy, etc.).

15/
If instead of this fake red herring you compare LNP with *actual* widespread alternatives in online payments, ie Debit Cards, I don't see any "liquidity management" complexity for payers, & I see why such complexity may compensate for lack of legal friction for payees.

16/
Of course, you may argue that the assumption that opening a well-connected channel with outbound liquidity is trivial, depends on the fact that there are huge "famous" LN nodes, which in itself carries some centralization risk. Fair. Still nothing compared to the benchmark.

17/
You may also argue that routing becomes very difficult when you have to pay very large amounts, even if you "filled up" your spending balance enough. But bigger amounts are exactly the use case where fixed blockspace fees become negligible, making on-chain BP more convenient.

18/
If anything we can agree that switching between on-chain BP & off-chain LNP could be made even smoother, hiding stuff from the user (ie: if LN routing fails the wallet tries to open a direct channel with the receiving node, if that fails it falls back on a normal BP address).

19/
Having said this, during an ongoing monetization process it's more rational to spend shitty fiat if you still have it & you can (NgU!). So people will probably not spend much with LNP. They will stack sats & limit spending to black/grey markets or privacy-sensitive purchases.

20/20
Eh, I forgot to add: The end.



***

{% include signup.md %}

