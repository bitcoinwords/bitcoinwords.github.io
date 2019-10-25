---
title: "Full Reserve Banking with Bitcoin"
permalink: "/full-reserve-banking-with-bitcoin" 

tags:
  - Tamas Blummer
  - CY19 Q2

excerpt: Tamas Blummer makes the case for full reserve banking with Bitcoin as the reserve asset. Posted June 28, 2019.

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      read_time: true
      comments: false
      share: true
      related: false
---

{% include donation.md %}

# [Full Reserve Banking with Bitcoin](https://medium.com/@tamas.blummer/full-reserve-banking-with-bitcoin-462b21ae9479)
### By [Tamas Blummer](https://twitter.com/TamasBlummer)
### Posted June 28, 2019

_Unchecked inflation of money supply through fractional reserve is creating a mess in the world we live in. Bitcoin could overcome this mess implementing this proposal!_

### Fractional Reserve Banking
The fiat currencies we use nowadays come into existence by someone borrowing them. To illustrate the mechanics let’s consider the case of Bob who buys a house with a mortgage loan. This implies the following series of events:

1. Bob signs a mortgage contract with Alice the banker.
2. Alice ensures that she has the right to sell the real-estate in case Bob would fail to follow terms of the contract. How she achieves this depends on jurisdiction, not relevant here.
3. Alice credits the account of the seller of the real-estate with the selling price, that is also the notional amount of the mortgage.
4. Bob regularly pays installments that cover interest and partial redemption of the mortgage until the notional amount is fully paid back through the redemptions.
5. If all goes well till end then Alice forgoes the right secured on the property, if not she uses the right to recover her loss.

This is all fine, but there is a disturbing detail in step 3. where does Alice have the money from that she debits to the seller? In our current banking system Alice simple creates it. Yes, this is completely legal until Alice does not violate a long list of checks mandated by banking regulators, mostly aimed to ensure that the amount of money Alice creates does not exceed a high multiple of her own capital and deposits under her control. This is called fractional reserve banking. The money created this way will be gradually destroyed again through Bob’s redemption or if he fails by the forced sell price.

If you think this is crazy, then consider that even the money Alice has is created the same way. Alice actually borrows that money from the central bank whereby she provides some collateral. The collateral may well be a so called ABS that re-packaged Bob’s mortgage agreement with many others.

There is no hard limit on the amount of money such system can create. The soft limits are regulated ratios and the bank’s capability to get people signing further loans that they can also honor, so the bank can afford to pay interest to the central bank. The later is not a hurdle nowadays as some central banks lend at 0% interest.

Wait, it gets even more crazy. Credits that fail, reduce the value of bank’s collateral and thereby would force them to reduce their own borrowing from the central bank which would curtail their ability to create credit which would slow down the economy and therefore cause even more credits to fail. To avoid that central banks got more creative recently and begun to buy assets that represent troubled credits at prices no one else would pay, thereby pumping or at least maintaining their value. They even invented a “Modern Monetary Theory” to justify all this.

It is evident that such a system is bound to create an ever increasing amount of debt and the measures that central banks do to underpin it only delay the inevitable collapse of the scheme at latest at the point where all prices of credit become meaningless. Guess what, we are pretty close to that. A huge fraction of government debt is trading at prices that makes them yield negative returns. That is the sum of interest and redemption does not cover the selling price.

All above was an introduction, so you understand why we need an alternate way of doing lending, so a Bitcoin economy does not end up in the same trap.

### Full Reserve Banking
Full Reserve Banking is where banks are no longer allowed to extend loans in excess of their own capital. Before gold receipts were introduced, this was the way banking worked.

Not only historians have interest in full reserve banking, but is seen by many people including some economists as an alternative to fractional reserve banking that we should stop for previous reasons. The most prominent move into this direction was a recent popular vote in Switzerland to mandate full reserve banking to all Swiss banks, that achieved 24% support of voters.

![](/assets/images/cy19/cy19q2m6/tb-2.png){: .align-center}

### Bitcoin credits
Bitcoin as is is digital cash. It does not mandate any form of banking it might be used in. Although there is a fixed supply of Bitcoins nothing yet enforces a limit on credit denominated in Bitcoins. This could lead to the very same problems in a Bitcoin economy, we currently see elsewhere.

We have seen repeatedly that e.g. Bitcoin exchanges operated a fractional reserve scheme, some collapsed as customer demanded their deposit and some are still getting away with it.

One way to keep check on Bitcoin businesses is requiring proof of reserves, that is like a public audit cryptographically proving that the Business had at a certain time point access to a number of Bitcoins.

Proof of Reserves is not much better than traditional audits as it does not give a guarantee of ongoing ordinary business, just shows a picture that could have been painted temporarily for the time point of the audit.

### Credit Covenants
The best solution would be if every Bitcoin credit would carry its own proof that it is covered by reserves all the time.

It turns out that this is technically possible with implementation of the proposal [I posted today to the Bitcoin developer mailing list](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-June/017059.html). There you have the technical details, for which I give a higher level description here.

On the technical level Bitcoins exist as unspent transaction outputs UTXOs. Transactions merge and split UTXOs to new UTXOs. One could consider an UTXO a coin of certain amount. An coin can be spent by someone if able to satisfy any of conditions that the coin is programmed to accept.

Giving credit to someone means transferring coins to him and hoping to get them back. Such a deal requires trust, since the borrower could be dishonest or bankrupt by the time the credit should be re-paid.

It was a great option if we could programmatically ensure that the coins will be paid back. We can achieve this by assigning a condition to the coin such that the lender can take it again later. Next we have to ensure that this condition is inherited by any coin that arises from splits or merges of this borrowed coin.

The technical means to do that is to assign a credit covenant to the coin that forces descendant coins to offer the same option to be taken later by the lender.

Do coins encumbered with a credit covenant have a value? They represent exclusive but temporary access to a scarce resource. I intuitively think yes, but the answer will be given by the market. An analogy to support my intuition is land that is not sold but rented for a longer term. If land is scarce then people will pay to take over a previously agreed rent contract.

The idea of covenants was first introduced in [a paper suggesting a solution for Bitcoin Vaults](http://fc16.ifca.ai/bitcoin/papers/MES16.pdf). I generalized the idea to be compatible with the [taproot proposal](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-May/016914.html) and provided examples how it can be used to technically enforce full reserve banking on the mailing list.

I know hope that the community understands the importance of full reserve banking and that we developer work together to complete and deploy this proposal on the network.

*Correction: the first discussion of covenants is probably [this post](https://bitcointalk.org/index.php?topic=278122.0) on bitcointalk.org.*