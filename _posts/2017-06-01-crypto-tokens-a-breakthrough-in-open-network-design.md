---
title: "Crypto Tokens: A Breakthrough in Open Network Design"
permalink: "/crypto-tokens-a-breakthrough-in-open-network-design"

author: chrisdixon

tags:
  - Chris Dixon
  - 2017 Q2
  - Economics
  - Money
  - Store of Value

excerpt: Crypto Tokens: A Breakthrough in Open Network Design. Posted June 1, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Crypto Tokens: A Breakthrough in Open Network Design](https://medium.com/@cdixon/crypto-tokens-a-breakthrough-in-open-network-design-e600975be2ef)
### By Chris Dixon
### Posted June 1, 2017

It is a wonderful accident of history that the internet and web were created as open platforms that anyone — users, developers, organizations — could access equally. Among other things, this allowed independent developers to build products that quickly gained widespread adoption. Google started in a Menlo Park garage and Facebook started in a Harvard dorm room. They competed on a level playing field because they were built on decentralized networks governed by open protocols.

Today, tech companies like Facebook, Google, Amazon, and Apple are [stronger](https://medium.com/@cdixon/the-internet-economy-fc43f3eff58a) than ever, whether measured by [market cap](http://www.visualcapitalist.com/chart-largest-companies-market-cap-15-years/), share of top mobile apps, or pretty much any other common measure.

![](/assets/images/2017/m6/crypto-tokens-a-breakthrough-in-open-network-design1.png)

*Big 4 tech companies dominate smartphone apps (source); while their market caps continue to rise (source)*

These companies also control massive proprietary developer platforms. The dominant operating systems — iOS and Android — charge 30% payment fees and exert heavy influence over app distribution. The dominant social networks tightly restrict access, hindering the ability of third-party developers to scale. Startups and independent developers are increasingly competing from a disadvantaged position.

A potential way to reverse this trend are [crypto tokens](http://continuations.com/post/148098927445/crypto-tokens-and-the-coming-age-of-protocol) — a new way to design open networks that arose from the cryptocurrency movement that began with the introduction of Bitcoin in 2008 and accelerated with the introduction of Ethereum in 2014. Tokens are a breakthrough in open network design that enable: 1) the creation of open, decentralized networks that combine the best architectural properties of open and proprietary networks, and 2) new ways to incentivize open network participants, including users, developers, investors, and service providers. By enabling the development of new open networks, tokens could help reverse the centralization of the internet, thereby keeping it accessible, vibrant and fair, and resulting in greater innovation.

#### Crypto tokens: unbundling Bitcoin

Bitcoin was introduced in 2008 with the publication of [Satoshi Nakamoto’s](https://en.wikipedia.org/wiki/Satoshi_Nakamoto) landmark [paper](https://bitcoin.org/bitcoin.pdf) that proposed a novel, decentralized payment system built on an underlying technology now known as a [blockchain](https://en.wikipedia.org/wiki/Blockchain). Most fans of Bitcoin (including [me](http://cdixon.org/2013/12/31/why-im-interested-in-bitcoin/)) mistakenly thought Bitcoin was solely a breakthrough in financial technology. (It was easy to make this mistake: Nakamoto himself called it a “p2p payment system.”)

![](/assets/images/2017/m6/crypto-tokens-a-breakthrough-in-open-network-design2.jpg)

*2009: Satoshi Nakamoto’sforum postannouncing Bitcoin*

In retrospect, Bitcoin was really two innovations: 1) a [store of value](https://en.wikipedia.org/wiki/Store_of_value) for people who wanted an alternative to the existing financial system, and 2) a new way to develop open networks. Tokens unbundle the latter innovation from the former, providing a general method for designing and growing open networks.

Networks — computing networks, developer platforms, marketplaces, social networks, etc — have always been a powerful part of the promise of the internet. Tens of thousands of networks have been incubated by developers and entrepreneurs, yet only a very small percentage of those have survived, and most of those were owned and controlled by private companies. The current state of the art of network development is very crude. It often involves raising money (venture capital is a common source of funding) and then spending it on paid marketing and other channels to overcome the “bootstrap problem” — the problem that networks tend to only become useful when they reach a critical mass of users. In the rare cases where networks succeed, the financial returns tend to accrue to the relatively small number of people who own equity in the network. Tokens offer a better way.

Ethereum, introduced in 2014 and launched in 2015, was the first major non-Bitcoin token network. The lead developer, [Vitalik Buterin](https://a16z.com/2016/08/28/ethereum/), had previously tried to create smart contract languages on top of the Bitcoin blockchain. Eventually he realized that (by design, mostly) Bitcoin was too limited, so a new approach was needed.

![](/assets/images/2017/m6/crypto-tokens-a-breakthrough-in-open-network-design3.png)

*2014: Vitalik Buterin’sforum postannouncing Ethereum*

Ethereum is a network that allows developers to run “smart contracts” — snippets of [code](https://en.wikipedia.org/wiki/Ethereum#Smart_contracts) submitted by developers that are executed by a distributed network of computers. Ethereum has a corresponding token called Ether that can be purchased, either to hold for financial purposes or to use by purchasing computing power (known as “[gas](https://ethereum.stackexchange.com/questions/3/what-is-gas-and-transaction-fee-in-ethereum)”) on the network. Tokens are also given out to “miners” which are the computers on the decentralized network that execute smart contract code (you can think of miners as playing the role of cloud hosting services like [AWS](https://en.wikipedia.org/wiki/Amazon_Web_Services)). Third-party developers can write their own [applications](https://dapps.ethercasts.com/) that live on the network, and can charge Ether to generate revenue.

Ethereum is inspiring a new wave of token networks. (It also provided a simple way for new token networks to launch on top of the Ethereum network, using a standard known as [ERC20](https://github.com/ethereum/EIPs/issues/20)). Developers are building token networks for a wide range of use cases, including distributed [computing](http://filecoin.io/) [platforms](https://golem.network/), [prediction](https://augur.net/) and financial markets, incentivized [content creation networks](https://steem.io/), and [attention and advertising networks](https://basicattentiontoken.org/). Many more networks will be invented and launched in the coming months and years.

Below I walk through the two main benefits of the token model, the first architectural and the second involving incentives.

#### **Tokens enable the management and financing of open services**

Proponents of open systems never had an effective way to manage and fund operating services, leading to a significant architectural disadvantage compared to their proprietary counterparts. This was particularly evident during the last internet mega-battle between open and closed networks: the social wars of the late 2000s. As Alexis Madrigal recently [wrote](https://www.theatlantic.com/technology/archive/2017/05/a-very-brief-history-of-the-last-10-years-in-technology/526767/), back in 2007 it looked like open networks would dominate going forward:

> In 2007, the web people were triumphant. Sure, the dot-com boom had busted, but empires were being built out of the remnant swivel chairs and fiber optic cables and unemployed developers. Web 2.0 was not just a temporal description, but an ethos. The web would be open. A myriad of services would be built, communicating through APIs, to provide the overall internet experience.

But with the launch of the iPhone and the rise of smartphones, proprietary networks quickly won out:

> As that world-historical explosion began, a platform war came with it. The Open Web lost out quickly and decisively. By 2013, Americans spent about as much of their time on their phones
>
> looking at Facebook
>
> as they did the whole rest of the open web.

Why did open social protocols get so decisively defeated by proprietary social networks? The rise of smartphones was only part of the story. Some open protocols — like email and the web — survived the transition to the mobile era. Open protocols relating to social networks were high quality and abundant (e.g. [RSS](https://en.wikipedia.org/wiki/RSS), [FOAF](http://xmlns.com/foaf/spec/), [XFN](https://en.wikipedia.org/wiki/XHTML_Friends_Network), [OpenID](http://openid.net/)). What the open side lacked was a mechanism for encapsulating software, databases, and protocols together into easy-to-use services.

For example, in 2007, Wired magazine ran an [article](https://www.wired.com/2007/08/open-social-net/) in which they tried to create their own social network using open tools:

> For the last couple of weeks, Wired News tried to roll its own Facebook using free web tools and widgets. We came close, but we ultimately failed. We were able to recreate maybe 90 percent of Facebook’s functionality, but not the most important part — a way to link people and declare the nature of the relationship.

Some developers [proposed](http://bradfitz.com/social-graph-problem/) solving this problem by creating a database of social graphs run by a non-profit organization:

> Establish a non-profit and open source software
>
> (with copyrights held by the non-profit) which collects, merges, and redistributes the graphs from all other social network sites into one global aggregated graph. This is then made available to other sites (or users) via both public APIs (for small/casual users) and downloadable data dumps, with an update stream / APIs, to get iterative updates to the graph (for larger users).

These open schemes required widespread coordination among standards bodies, server operators, app developers, and sponsoring organizations to mimic the functionality that proprietary services could provide all by themselves. As a result, proprietary services were able to create better user experiences and iterate much faster. This led to faster growth, which in turn led to greater investment and revenue, which then fed back into product development and further growth. Thus began a flywheel that drove the meteoric rise of proprietary social networks like Facebook and Twitter.

Had the token model for network development existed back in 2007, the playing field would have been much more level. First, tokens provide a way not only to define a protocol, but to fund the operating expenses required to host it as a service. Bitcoin and Ethereum have tens of thousands of servers around the world (“miners”) that run their networks. They cover the hosting costs with built-in mechanisms that automatically distribute token rewards to computers on the network (“mining rewards”).

![](/assets/images/2017/m6/crypto-tokens-a-breakthrough-in-open-network-design4.png)

*There are over 20,000 Ethereum nodes around the world (source)*

Second, tokens provide a model for creating shared computing resources ([including](https://medium.com/@FEhrsam/the-dapp-developer-stack-the-blockchain-industry-barometer-8d55ec1c7d4) databases, compute, and file storage) while keeping the control of those resources decentralized (and without requiring an organization to maintain them). This is the blockchain technology that has been talked about [so much](https://trends.google.com/trends/explore?q=blockchain). Blockchains would have allowed shared social graphs to be stored on a decentralized network. It would have been easy for the Wired author to create an open social network using the tools available today.

#### Tokens align incentives among network participants

Some of the [fiercest battles](http://cdixon.org/2009/09/14/the-inevitable-showdown-between-twitter-and-twitter-apps/) in tech are between [complements](https://en.wikipedia.org/wiki/Complementary_good). There were, for example, hundreds of startups that tried to build businesses on the APIs of social networks only to have the terms change later on, forcing them to pivot or shut down. Microsoft’s battles with complements like Netscape and Intuit are legendary. Battles within ecosystems are so common and drain so much energy that business books are full of frameworks for how one company can squeeze profits from adjacent businesses (e.g. Porter’s [five forces](https://en.wikipedia.org/wiki/Porter%27s_five_forces_analysis) model).

Token networks remove this friction by aligning network participants to work together toward a common goal— the growth of the network and the appreciation of the token. This alignment is one of the main reasons Bitcoin continues to defy [skeptics](https://99bitcoins.com/bitcoinobituaries/) and flourish, even while new token networks like Ethereum have grown along side it.

Moreover, well-designed token networks include an efficient mechanism to incentivize network participants to overcome the bootstrap problem that bedevils traditional network development. For example, [Steemit](https://steemit.com/) is a decentralized Reddit-like token network that makes payments to users who post and upvote articles. When Steemit launched last year, the community was [pleasantly surprised](https://coinreport.net/social-network-steemit-distributes-1-3-million-first-cryptocurrency-payout-users/) when they made their first significant payout to users.

![](/assets/images/2017/m6/crypto-tokens-a-breakthrough-in-open-network-design5.png)

*Tokens help overcome the bootstrap problem by adding financial utility when application utility is low*

This in turn led to the appreciation of Steemit tokens, which increased future payouts, leading to a [virtuous cycle](https://www.usv.com/blog/fat-protocols) where more users led to more investment, and vice versa. Steemit is still a beta project and has since had mixed results, but was an interesting experiment in how to generalize the mutually reinforcing interaction between users and investors that Bitcoin and Ethereum first demonstrated.

A lot of attention has been paid to token pre-sales (so-called “ICOs”), but they are just one of multiple ways in which the token model innovates on network incentives. A well-designed token network carefully manages the distribution of tokens across all five groups of network participants (users, core developers, third-party developers, investors, service providers) to maximize the growth of the network.

One way to think about the token model is to imagine if the internet and web hadn’t been funded by governments and universities, but instead by a company that raised money by selling off domain names. People could buy domain names either to use them or as an investment (collectively, domain names are worth tens of billions of dollars today). Similarly, domain names could have been given out as rewards to service providers who agreed to run hosting services, and to third-party developers who supported the network. This would have provided an alternative way to finance and accelerate the development of the internet while also aligning the incentives of the various network participants.

#### The open network movement

The cryptocurrency movement is the spiritual heir to previous open computing movements, including the open source software movement led most visibly by Linux, and the open information movement led most visibly by Wikipedia.

![](/assets/images/2017/m6/crypto-tokens-a-breakthrough-in-open-network-design6.png)

*1991: Linus Torvalds’ forumpostannouncing Linux; 2001: the first Wikipediapage*

Both of these movements were once niche and [controversial](https://medium.com/@cdixon/it-s-hard-to-believe-today-but-10-years-ago-wikipedia-was-widely-considered-a-doomed-experiment-a7a0dfd27b8b). Today Linux is the dominant worldwide operating system, and Wikipedia is the most popular informational website in the world.

Crypto tokens are currently niche and controversial. If present trends continue, they will soon be seen as a breakthrough in the design and development of open networks, combining the societal benefits of open protocols with the financial and architectural benefits of proprietary networks. They are also an extremely promising development for those hoping to keep the internet accessible to entrepreneurs, developers, and other independent creators.

***

{% include signup.md %}
