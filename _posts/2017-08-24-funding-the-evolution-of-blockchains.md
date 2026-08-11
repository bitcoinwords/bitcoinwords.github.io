---
title: "Funding the Evolution of Blockchains"
permalink: "/funding-the-evolution-of-blockchains"

author: fredehrsam

tags:
  - Fred Ehrsam
  - 2017 Q3
  - Economics
  - Money
  - Technology

excerpt: Funding the Evolution of Blockchains. Posted August 24, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Funding the Evolution of Blockchains](https://medium.com/@FEhrsam/funding-the-evolution-of-blockchains-87d160988481)
### By Fred Ehrsam
### Posted August 24, 2017

Blockchains are digital organisms. As organisms evolve though changes in their DNA, blockchain protocols evolve through changes in their code. And like biological organisms, the most adaptive blockchains will be the ones that survive and thrive.

So what makes for a strong evolutionary process in a blockchain? Forking is an important mechanism that is becoming more common. Forks can speed evolution by allowing many different approaches to be tried in parallel. However, I feel there is another which is barely talked about: **the economic incentives to contribute to a blockchain’s core protocols. These incentives are lacking in almost every major blockchain today and are an opportunity to supercharge their development.**

**The lack of incentives to work on core protocols is reflected in the large number of people working on Etheruem tokens vs. the small number working on Ethereum itself.** Launching a new token has made many millionaires in the last 8 months, whether on paper or liquid. Meanwhile, if you contribute to the core Ethereum codebase at best you 1) own a bunch of ETH personally and the price of them goes up a bit or 2) need to join the Ethereum Foundation and get paid some amount that wouldn’t match the economics of a successful token launch. As a result, **Ethereum is starting to suffer from a tragedy of the commons problem: while lots of people own ETH and would benefit from Ethereum improving, the economic reward for any single individual improving it is low.**

So it’s not surprising these massively valuable blockchains don’t have many people working on them. Despite being worth over $30bn and $65bn, there are only 15 meaningful contributors to [Ethereum](https://github.com/ethereum/go-ethereum/graphs/contributors) and [Bitcoin](https://github.com/bitcoin/bitcoin/graphs/contributors) respectively, and the rate of contribution isn’t going up much with their rise in popularity.

![](/assets/images/2017/m8/funding-the-evolution-of-blockchains1.png)

*Commit history of Ethereum’s main implementation*

![](/assets/images/2017/m8/funding-the-evolution-of-blockchains2.png)

*Commit history of Bitcoin’s main implementation*

This is a shame. Improvements to these protocols would create massive amounts of value. For example, let’s say someone or a group of people implemented an Ethereum scaling solution like [sharding](https://github.com/ethereum/wiki/wiki/Sharding-FAQ) or [Plasma](http://plasma.io). Each of **these improvements would likely increase the value of Ethereum by over 10%, creating roughly $3 billion in value at current Ether prices.**

So how do we incent people to work on the [common good](https://en.wikipedia.org/wiki/Common_good) of the core protocols?

**Private funding** was one of the first methods used when [MIT funded](https://gavintech.blogspot.hu/2015/04/joining-mit-media-lab-digital-currency.html) Bitcoin core developers Gavin Andresen, Wladimir van der Laan, and Cory Fields in 2015. Some projects like [Blockstack](https://venturebeat.com/2017/08/16/blockstack-announces-25-million-fund-to-rebuild-the-internet-for-a-blockchain-world/) have funds of private individuals and VCs to invest in projects built on top of the protocol, but this is different because it is not focused on improving the core protocol directly.

Private funding can be a good first step because it is fast, decisive, and lightweight. However, the economics probably don’t work at some point. If a protocol upgrade like sharding in Ethereum could create $3bn in value, private funding is already unable to scale to be able to offer anything close to the value that could be created.

**Public crowdfunding**hasn’t been tried much in the blockchain space or nothing has worked enough to come to mind. A theoretical example of this would be the Ethereum Foundation announcing an open crowdfund for a feature bounty.

Public crowdfunding still suffers from a tragedy of the commons problem. Everyone will want the benefit of the crowdfunded efforts but is incentivized to sit on the sidelines and hope others chip in.

**Inflation funding**is where things get interesting. **It allows economic rewards that are otherwise unthinkable.** Remember, if Ether holders believed an upgrade (ex: sharding) would make the price go up by >10%, they’d be happy to pay close to 10% of their tokens for it. That means **Ethereum could crowdfund a $3bn feature bounty by inflating the number of ETH by 10% and pay the newly created tokens to the creator(s) of the upgrade**. This is somewhat analogous to taxes: everyone in the community chips in to fund common infrastructure (ex: roads) which no one would build alone.

Funding protocol developments through inflation would also allow anyone in the world to contribute more easily. **Not everyone wants to be employed by a foundation or reveal their identity: some of the largest advances in cryptocurrency like**[**Bitcoin**](https://en.bitcoin.it/wiki/Satoshi_Nakamoto)****[**itself**](https://bitcoin.org/bitcoin.pdf)**and**[**Mimblewimble**](https://scalingbitcoin.org/papers/mimblewimble.pdf)**were anonymously airdropped.**

Finally, the funds in token sales set aside for future protocol development will eventually run out, and this feels like a good solution to that eventuality.

An example of how this would work: a developer submits a pull request to Ethereum with a working implementation of sharding. The community discusses and tests it. There is an on-chain vote of Ether holders to 1) determine if the upgrade should be merged and 2) if so, what the size of the bounty should be. The pull request increases the number of ETH outstanding and sends the new tokens to an address the developer includes. This would require a hard fork the first time, but may not in the future. The size of the bounty ends up being fair because Ether holders want to incentivize developers to keep submitting improvements like this in the future.

I find [Tezos interesting because it proposes a version of this concept](https://www.tezos.com/static/papers/position_paper.pdf). Here’s an excerpt from their position paper:

![](/assets/images/2017/m8/funding-the-evolution-of-blockchains3.png)

*“Funding Innovation”, from the Tezos position paper*

Open feature bounties are a powerful way of accelerating change. The self-driving car revolution was kicked off by [The DARPA Grand Challenge](https://en.wikipedia.org/wiki/DARPA_Grand_Challenge_%282005%29) to make an autonomous car traverse 132mi of a desert. **It offered a $2m feature bounty and drew over 40 teams from different universities and companies. Imagine how much competition there would be for multi-hundred million or billion dollar feature bounties.** And the potential size of the bounties will grow as the value of the network grows.

![](/assets/images/2017/m8/funding-the-evolution-of-blockchains4.png)

*A $2m feature bounty created this.*

**A protocol which provides strong incentives for people to improve it is likely to evolve faster than one that does not. So blockchains which fund innovation through token inflation would seem to have a superior evolutionary algorithm.** And over the long run, rate of change is often more important than starting point.

There are some counterarguments. Contributors value things beyond money: the intellectual pursuit, the status and camaraderie it brings within their community, and the mission of a project. But I’d argue proper economic incentives can only add to this list and are also necessary for some people to be able to focus 100% of their time on a project. Also, as [*The Mythical Man Month*](https://en.wikipedia.org/wiki/The_Mythical_Man-Month)**suggests, [more people working on software doesn’t necessarily mean it will go faster or turn out better](https://en.wikipedia.org/wiki/The_Mythical_Man-Month). However, adding more people to software projects usually fails when its components can’t be divided up, and [there are a sufficient number of different scaling paths](https://docs.google.com/spreadsheets/d/1oIaWzybcWLQ22eXTZlLrG7Lhn82EIrRvqi3S5v94l0k/edit#gid=0) at this point where each can be pursued relatively independently. Finally, approving upgrades and bounties requires greater community coordination. Yet, looking at different attempts to upgrade protocols, it seems on-chain voting on upgrades is something that would reduce complexity, not add it.

**So, perhaps the highest leverage thing protocol designers can do is think about how to engineer the evolutionary characteristics of their blockchains — specifically, the economic incentives for anyone to come along and improve them.** The best engineered organisms can outpace others, even if they start smaller or later.

This can be the biggest step function change in the rate of innovation in the blockchain space if implemented well. **By harnessing their decentralized nature they can evolve faster than a centralized organization ever could.**

*Thanks to*[*Dan Romero*](https://twitter.com/dwr)*,*[*Arthur Breitman*](https://twitter.com/ArthurB)*,*[*Brian Armstrong*](https://twitter.com/brian_armstrong)*,*[*Joseph Poon*](https://twitter.com/jcp)*, and*[*Albert Wenger*](https://twitter.com/albertwenger)*for conversations which influenced this post.*

***

{% include signup.md %}
