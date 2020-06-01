---
title: "Why Bitcoin might not survive a Bitcoin Standard"
permalink: "/why-bitcoin-might-not-survive-a-bitcoin-standard"

author: hasu

tags:
  - Hasu
  - 2020 Q2
  - Economics
  - Banking
  - Bitcoin Standard
  - Transactions
  - Central Banks
  - Threat
  - Custodial Banking
  - Sovereignty

excerpt: Hasu examines weighs outcomes in a Bitcoin standard world. Posted May 25, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Why Bitcoin might not survive a Bitcoin Standard](https://insights.deribit.com/market-research/why-bitcoin-might-not-survive-a-bitcoin-standard/)
### By [Hasu](https://twitter.com/hasufl) on [Deribit Insights](https://insights.deribit.com/market-research/why-bitcoin-might-not-survive-a-bitcoin-standard/)
### Posted May 25, 2020

![](/assets/images/2020/m5/h1.png)

Bitcoin allows users to store and transfer value without trusting any third party. However, these assurances are constrained to 4400 transactions per block (more, if you count one-to-many payments). All else equal, Bitcoin’s capacity is constrained by the block size. The current block size limit exists for technical and incentive-compatibility reasons that are unlikely to go away soon.

Some people posit you can scale Bitcoin by increasing the blocksize. While that would allow more transactions, the assurances of these transactions would be worse. Consequently, Bitcoin protects its properties by excluding usage beyond the safe capacity limit. Over time, the safe capacity limit can be expanded, for example via additional layers like Lightning.

I’d like to challenge this orthodoxy by saying <strong>Bitcoin’s ability to exclude users is smaller than commonly assumed</strong>. While Bitcoin can control the number of users inside the network, it has no control over the number of users accessing the network through custodial banks. The growth of this banking layer is outside of the protocol’s control and could grow into a systemic risk for Bitcoin.

Users adopt custodial banks because they offer lower transaction cost over a variety of dimensions. These can include stronger network effect, faster payment clearing, legal recourse, lower transaction fees, or access to financial services like exchange or money markets.

A popular vision today is that the future “Bitcoin stack” will consist of different layers that represent unique points on a trust/cost graph. If higher layers break down, users can retreat to lower layers.

In this article, I will show <strong>how a custodial banking layer creates systemic risk for Bitcoin.</strong> Then,<strong> what drives the growth of the custodial banking layer</strong>, and finally, <strong>how a negative outcome for Bitcoin could be prevented</strong>.

## How a custodial banking layer creates systemic risk for Bitcoin

Imagine a future where 200 million people use Bitcoin, most of them via the custodial banking layer. These banks use the base chain as an interbank settlement network. Users trade in Bitcoin IOUs representing bitcoin deposits.

The long-term stability of this arrangement is a matter of who has leverage over whom. If users can leave at any time and go to a competitor (including the trustless layers of the system), the custodial banking system is kept in check. But if users are locked in, then the power resides with the banks (and thereby governments). <strong>Whether users are locked in or not depends on the exit cost from the system</strong>.

### Manual exit cost

When governments can come in and cancel the redeemability for bitcoin, this may be seen as jacking the exit cost from the system to infinity. Governments may find it difficult to control the network layer itself, but in this example they don’t need to at all. They <strong>already control the banks</strong>.

This is what happened <a href="https://en.wikipedia.org/wiki/Executive_Order_6102" target="_blank" rel="noopener noreferrer">in 1933</a> to the gold of US citizens and <a href="https://en.wikipedia.org/wiki/Nixon_shock" target="_blank" rel="noopener noreferrer">in 1971</a> to the gold of other nation-states held within the domestic US.

If redeemability is canceled, Bitcoin completes the transition back to fiat money based on Dalio’s chart of the long-term debt cycle.

![](/assets/images/2020/m5/h2.png)
*Source: <a href="https://www.linkedin.com/pulse/money-credit-debt-ray-dalio" target="_blank" rel="noopener noreferrer">Linkedin</a>*

Notably, this is not a scenario where users could “UASF” or respond in any other way at the protocol level since the rules of the Bitcoin standard still abide by the rules of the Bitcoin protocol. Users allowed it to become a political problem that now requires a political solution.

### Organic exit cost

In practice, governments may not even have to cancel redeemability for bitcoin, because the exit cost can grow very large organically.

Take a bank run scenario where all 200 million people, or at least a significant part of them, wanted to leave the banking system and move down the stack to a more trustless layer. Some of them can successfully make the transition, but they would be the winners of an auction that jacks transaction fees to the thousands to tens of thousands of dollars. The rest would be left behind on the higher layer.

If a higher layer grows too large relative to the capacity of the lower layer, people <strong>lose the optionality of moving back down the stack</strong>. As users find themselves permanently locked into the higher layer, governments can safely implement a variety of taxes or rule changes in the system.

## What drives the growth of the custodial banking layer

People use higher layers because they offer them more favorable points on the trust/cost spectrum. Remember that “cost” includes many things, not just transaction fees. It also includes network effect, settlement time, reversibility, privacy, etc.

I’m afraid there exists <strong>a feedback loop that makes custodial layers more attractive the larger they become, driving further users to them</strong>.

This can be first shown with an example from the gold standard. Every user of gold competes with other users in the market place. If they can settle debts sooner rather than later, suppliers are more willing to do business with them. If banking can give them lower fees, they can forward this price saving to their trading partners. The result is a feedback loop where users migrate to the cheapest solution over time.

The benefits of using a bank ledger are local and immediate, whereas the downsides are global and often happen with decades of delay.

The same feedback loop exists in Bitcoin, but arguably in an even stronger way. If the custodial banking layer becomes very successful, imagine that all these settlement transactions drive up the transaction fees on the base layer. Suddenly, <strong>more and more people become priced out of using trustless layers at all</strong>. The custodians can afford to pay more for the base layer space because their transactions represent the bundled interest of thousands of users off-chain.

![](/assets/images/2020/m5/h3.png)

As a result, formerly noncustodial users can find themselves facing the option to use custodial options or stop using Bitcoin altogether. This also holds, for an only slightly lesser degree, for the Lightning Network, where you can’t safely route payments <a href="https://twitter.com/Truthcoin/status/1234535778719539208?s=20" target="_blank" rel="noopener noreferrer">smaller than 3.5x the on-chain fee limit</a>.

Interestingly, the feedback loop can still hold if transaction fees are very low. The reason is, again, that fees represent merely one aspect of the overall transaction costs. If the security budget of the main chain is very low, settlement times could become very excessive. This further increases the relative advantage of custodial off-chain solutions like banks.

## How a negative outcome for Bitcoin could be prevented

I see two ways to minimize the systemic risk from a custodial banking layer.

First, the community can <strong>discourage users from adopting IOUs on a large scale</strong>. This involves constructing a narrative where new users can still get financial exposure to Bitcoin, but not use it in a way where banks have a leg up on the trustless layers.

![](/assets/images/2020/m5/h4.png)

Arguably, this has already happened in the last couple of years and shows how well the Bitcoin community instinctively understands that Bitcoin’s assurances degrade for everyone if too many people use it in the wrong way.

Second, we need to continue to <strong>innovate and expand Bitcoin’s trustless capacity to more users</strong>. Specifically, we need to pioneer ways for multiple users to share a single UTXO, so they can also bundle their interest and survive in the on-chain marketplace for blockspace with custodial banks.

There is an implicit assumption in Bitcoin that users will pay more to use the base layer or its trustless extensions like the Lightning network. In practice, Bitcoin doesn’t just compete with fiat money or even other cryptocurrencies, but also with custodial Bitcoin banks.

I would still firmly count myself as a “small-blocker”, but the analysis raises some doubt whether keeping validation costs low is as effective as commonly assumed. You can have a low validation cost but become forced into custodial layers by high transaction fees, very long settlement times, or other cost factors.

Many in Bitcoin believe there is a big risk in moving too fast, but hardly any risk in moving too slow. This would be true if Bitcoin could grow at its own pace, but it can’t. We <strong>must make sure that enough demand from the market can be met with trustless capacity, or risk that the custodial banking system will forever encumber the base layer</strong>.



***

{% include signup.md %}