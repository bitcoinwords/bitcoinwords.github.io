---
title: "Platform currencies may soon be obsolete"
permalink: "/platform-currencies-may-soon-be-obsolete"

author: aleksandrbulkin

tags:
  - Aleksandr Bulkin
  - 2017 Q3
  - Mining
  - Economics
  - Money

excerpt: Platform currencies may soon be obsolete. Posted July 11, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Platform currencies may soon be obsolete](https://blog.coinfund.io/platform-currencies-may-soon-be-obsolete-78d9b263d902)
### By Aleksandr Bulkin
### Posted July 11, 2017

![](/assets/images/2017/m7/platform-currencies-may-soon-be-obsolete1.jpg)

Here is my claim. Within 5 years the biggest cryptocurrency by market cap will not be Ethereum or any other platform currency. Instead, it will be an application token.

Yes, I said it. Ether (both real and “classic”) may be entirely obsolete and so will [Atoms](https://cosmos.network/plan), [Tezzies](https://www.tezos.com/faq), and all others whose use is to pay for transaction capacity in a single blockchain network.

Let me explain.

The current investment thesis for platform currencies is usually based on the following claims:

1. That network effects cause a single currency or just a few currencies to accrue most of the value in the space.
2. That a single currency will serve as a dominant tool for injecting value into ICOs (this is Ether’s primary role today).
3. That a single blockchain can and will host most of the dApps that generate value in the space.

All of these claims may be false in the long term.

1. It is a mistake to think that network effects matter for cryptocurrencies. Cryptoexchange technology (both centralized and decentralized) is maturing every day, while at the same time multi-currency wallet technology becomes increasingly more accessible. As frictions to holding and exchanging multiple cryptotokens decrease any payment system and any financial flow whatsoever can easily extend to all existing cryptocurrencies. At that point it will matter not whether you use Ether, Bitcoin or any other token — all will work equally well.
2. Ether became a dominant currency for token sales because it allows for their execution via smart contracts when project founders are distributing new ERC20 tokens. This is a significant selling point, but we do notice that many token sales today accept bitcoin and some accept other currencies as well. Blockchain interoperability technology via oracles both centralized and decentralized is maturing as fast as exchanges. Eventually a smart contract will be able to seamlessly issue tokens on one blockchain in response to events observed on others.

This shows that it is not at all necessary for a platform currency to become a large store of economic value. The next point provides a reason for why it is likely that the space will move away from this model altogether. The reason is that hosting all dApps on a single blockchain (and consequently relying on a single platform currency) is, actually, a very bad thing.

Consider two events: the [DAO hack](http://www.coindesk.com/understanding-dao-hack-journalists/) and the recent [Status](https://status.im/) crowdsale. The first caused Ether price to drop by two thirds while the latter caused the Ethereum network to virtually [stop processing transactions](https://www.reddit.com/r/ethereum/comments/6flqu0/preventing_icos_status_from_ddosing_the_netowrk/) for an extended period time. These are both examples of inter-application contagion. The first one is economic: when one application suffers a collapse all other applications suffer from a perception spill-over of that collapse. The other is technical: when one application causes the transaction volume on the network to spike all other applications suffer from slowdowns and transaction bottlenecks.

Inter-application contagion is the reason why dApps that require reliability of both throughput and economic value may start choosing to host themselves on a separate blockchain altogether. And what could be easier? It is not that hard to clone the Ethereum blockchain with a different root block, crowdfund by selling the premined currency *of that blockchain instance,*and operate completely independently from others without worries of contagion.

Of course this can’t happen today. The reason is very simple: proof-of-work consensus requires miner cycles to secure the blockchain. Absent miner interest an Ethereum clone can’t operate. Miners look for the most profitable work per GPU cycle, and an upstart Ethereum clone isn’t going to look good to them. But not so when proof-of-stake consensus ([Casper](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ) or [BFT](https://cosmos.network/whitepaper)) becomes operational. When this happens a single node can validate as many blockchains as it has disk space for. Crowdsale participants can setup validator nodes and off we go.

The outcome is clear: platforms will be irrelevant and easily cloned. Application currencies will be tied to their own blockchain instances and will dominate the space.

Obviously, the picture I am describing here is years away. There still are a few pieces of technology that need to be perfected before we will see it play out. For the near term Ether and Bitcoin may remain both a store of economic value, de-facto index assets, and currencies intimately tied to the cryptoinvestment process. But I predict a cryptocurrency future less “maximalist” and more diverse than the conventional wisdom thinks.

*Thanks to Greg Meredith of*[*RChain*](https://medium.com/@rchain_coop)*for inspiring some of these thoughts.*

[*CoinFund*](http://coinfund.io)*is a blockchain technology research company, advisory team, and private cryptoasset-focused investment vehicle. We work with companies in the blockchain space and beyond to understand how blockchain-based economics can be used for financial applications such as crowdfunding, and more. If you’re a blockchain project or are interested in exploring blockchain technologies for your product, please*[*get in touch with us*](mailto:info@coinfund.io)*or join us in the*[*CoinFund Slack*](http://slack.coinfund.io)*.*

***

{% include signup.md %}
