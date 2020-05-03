---
title: "The State of L2 Investments"
permalink: "/the-state-of-l2-investments"

author: mohamedfouda

tags:
  - Mohamed Fouda
  - 2020 Q2
  - L2
  - Sidechains
  - Lightning
  - Liquid
  - RSK
  - Technology
  - Financial
  - FinTech
  - Layer 2

excerpt: Mohamed Fouda takes a look at the current state of Bitcoin scaling technologies. Posted April 17, 2020

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***


# [The State of L2 Investments](https://www.tokendaily.co/blog/the-state-of-l2-investments)
### By [Mohamed Fouda](https://twitter.com/MohamedFFouda)
### Posted April 17, 2020

## Part 1: Progress and Investability of BTC Off-Chain Solutions

Friday, 17th of April 2020 · by [Mohamed Fouda](https://www.tokendaily.co/user/MohamedFFouda)

![](/assets/images/2020/m4/mf1.png)

In 2017, the crypto bull run triggered explosive trading activity which stress-tested both Bitcoin and Ethereum networks. They each suffered congestion, delayed transactions, and higher fees. In response to these conditions, several scalability solutions were proposed or revisited with renewed interest in off-chain and layer-2 implementations. Entrepreneurs, researchers, and investors largely viewed L2 (Layer 2) solutions as having limited downside: they require only minor changes to the consensus layer and avoid centralization of the base-layer protocols. Meanwhile, their upside appeared uncapped. These solutions include Bitcoin's Lightning Network and Ethereum's Raiden, which can be described as true L2 solutions, and sidechains such as RSK for Bitcoin and Plasma Chains for Ethereum.

During 2018 and 2019, there was a healthy amount of activity around L2 development. On the Bitcoin side of things, the Lightning Network (LN) launched on mainnet in March 2018. In Ethereum, several L2 variants including state channels, e.g., SpankChain, and Plasma/Plasma Cash, e.g., Loom Network, also launched. However, as the bear market of 2018–2019 continued, we saw a significant dip in on-chain activity. You didn't need to be particularly clever to figure out why: as speculative activity from these networks died down, there was weaker market demand for a scaling solution. As market conditions started improving in Q3 and Q4 2019 we saw more interest in L2 solutions —  both in anticipation of a new bull run that would likely lead to congestion and for added functionality, like privacy, to base layer protocols.

In this series, we examine the current trends in off-chain networks and assess their investability. We also review off-chain solutions' adoption and utility over the last two years. This is the first part of a two-part series. Part one will focus on the Bitcoin ecosystem, the second will focus on Ethereum's off-chain trends.

![](/assets/images/2020/m4/mf2.png)
*Comparison of the capacity of [Lightning Network](https://bitcoinvisuals.com/ln-capacity), [Liquid Sidchain](https://liquid.net/), and [RSK](https://explorer.rsk.co/)*

## Lightning Network

LN is, by far, the most important and loudly discussed off-chain scalability project. Since the release of the 2015 Lightning [paper](https://lightning.network/lightning-network-paper.pdf), the project has been under intense discussion and debate. Since launch, there's been impressive growth in the network in terms of the number of channels, network capacity, and use cases. However, entrepreneurs and investors are still figuring out which business opportunities make most sense in the LN ecosystem. The explored directions include: building liquidity hubs to collect routing fees, offering integrations and user services on LN, payment rails using LN, and finally investing in LN infrastructure.

### Liquidity Provisioning in LN

Since LN's aim is to create a payment network, especially for micropayments, building a business to do just that was low hanging fruit: offer several LN nodes with hundreds of channels, route payments and earn fees. The initial thought was this service would generate enough revenue to 1) cover the costs of operation and 2) generate _risk-free_ profit.

Opponents of this view were quick to point to technical risks and the inherent capital inefficiency in LN that would require high fees or large transaction volumes to achieve this kind of _risk-free_ profit. After two years in operation, the skeptics have so far been proven right. **_Today, it is not currently possible to build a profitable business just by collecting LN routing fees._**

Theoretically, running nodes and routing payments on LN should be part of a profitable business, akin to running Bitcoin full nodes. That's what teams like [LNBIG](https://lnbig.com/#/our-nodes), operators of the largest liquidity provider in LN, are counting on. LNBIG currently operates 25 public nodes and controls, roughly speaking, around 50% of the overall LN capacity.

According to LNBIG’s anonymous founder’s [interview](https://www.theblockcrypto.com/post/41083/person-behind-40-of-lns-capacity-i-have-no-doubt-in-bitcoin-and-the-lightning-network) with The Block, LNBIG may be losing money on this investment now, but they are betting on long term adoption.

![](/assets/images/2020/m4/mf3.png)
_Annualized ROI for providing liquidity in LN during 2018. Source: [BitMEX Research](https://blog.bitmex.com/the-lightning-network-part-2-routing-fee-economics/)_

For those interested in more rigorous data on the economics of liquidity provisioning in the LN, BitMEX Research published thorough [analysis](https://blog.bitmex.com/the-lightning-network-part-2-routing-fee-economics/) in March 2019 on their own experience with LN fees. A major takeaway from the report is that for the first year of LN, under optimized conditions, e.g. channel fee rate, the annualized investment return was only ~1% from routing fees and _this return does not include the on-chain fees required to open the channels._

### LN User Services

![](/assets/images/2020/m4/mf4.png)

The second type of investment in the LN ecosystem, and probably the most abundant, is the investments in user services. This is a broad category that includes all the services that interact directly with the consumer. We can categorize this sector into 3 major buckets:

*   LN-enabled micropayments
*   Financial services on LN
*   Services that improve UX and integration with LN
    

The first type of LN services that organically appeared on the scene was "micropayment services," largely because this was the entire point of the original LN narrative. Publishing platform [Y'alls](https://yalls.org/) and the mobile-minutes service [Bitrefill](https://www.bitrefill.com/) were the first services available for use on LN.

As LN started to grow, there was an uptick in tools that facilitated access to LN, including Lightning-enabled wallets such as [Zap](https://zap.jackmallers.com/), [Eclair](https://play.google.com/store/apps/details?id=fr.acinq.eclair.wallet.mainnet2&hl=en_CA), and [BLW](https://lightning-wallet.com/). Bitrefill also started to offer services to open channels for users like Thor channels. This allowed the LN ecosystem to mature, leading to the emergence of finance-focused LN user services like merchant services/Bitcoin cashback services (Fold), and LN-based BTC on-boarding (River Financial and the currently defunct Sparkswap), and LN-integrated exchanges ([Bitfinex](https://www.bitfinex.com/posts/440), [LN markets](https://lnmarkets.com/)).

**_LN user services sector is the most-heavily invested vertical within the LN sector for two major reasons_**.

1.  The number of companies being built in LN user services is larger than either of the latter two verticals. Statistically, more investment opportunities mean there's a greater likelihood of those projects getting funded.
2.  It is likely that a winner in this vertical can also capture a market outside of crypto.
    

For instance, Fold's focus on offering BTC-dominated cashback goes beyond the regular crypto community and targets a wider mainstream audience. LN here is use as a better UX tool to deliver the BTC rewards. This market direction allowed Fold to raise $2.5M last September. Similarly, Bitrefill managed to close $2M in VC funding to focus on expanding BTC merchant services using LN. Although there is general excitement for LN-based user services, this doesn't come without challenges. Some companies, e.g., Sparkswap, which successfully raised VC money later found that they may have been too early and, in the land of startups, being too early is the same as being wrong.

### Financial Rails Using Lightning

Though this is a relatively new direction in the LN ecosystem, it is likely to be a major trend in the near future. The goal here is to leverage LN features such as global coverage, instant settlement, and low fees to target users outside of crypto. In other words, these businesses use LN as a payment rail on the backend without the user necessarily knowing they are using BTC or LN. We can analogize this to Cash App or Venmo which use protocols like ACH and Swift under the hood to actually move users' money around.

One of the earliest players in this vertical is Zap. Zap plans to use LN to [settle everyday USD payment](https://medium.com/@JimmyMow/announcing-strike-by-zap-4f578c7c8984)s, such as merchant payments or individual cash transfers. The advantage of using LN as a settlement layer is the instant settlement capability and low fees which could replace traditional payments rails that charge up to 15% of the transaction size. Zap's Strike product, for instance, achieves this goal without necessarily requiring the user or the merchant to use BTC at any time. This also solves major problems that hinder BTC adoption in payment systems, including price volatility and unfriendly tax laws around bitcoin payments.

### LN Infrastructure

In crypto land, financing crypto infrastructure with venture capital, i.e., buying equity in companies developing protocols, is a highly contentious topic. The use cases, however, are clear. With Lightning, this means investing in the teams building and advancing the LN protocol. Three major startups working on this vertical are Lightning Labs, ACINQ, and Blockstream. As the critical pieces of the LN are already built, these companies focus on improving both the user and developer experience using the LN. For example, Lightning Labs developed tools like Loop and Faraday to help node operators smoothly manage their channels. Similarly, ACINQ is developing stripe-like API tools to allow businesses to easily integrate with LN.

When it comes to ROI, things get a little more complicated. _**For several crypto focused VCs, it is not clear if providing LN developer services will be enough to build profitable and sustainable businesses** _. Those who do not think infrastructure projects will be directly profitable are really paying for one of two things:

1.  The opportunity to get early access and insights to then invest in closed-source third parties that integrate LN.
2.  Leveraging their existing bitcoin position by supporting LN, which promises to usher in mass adoption by both users and merchants.
    

In spite of differing viewpoints, skeptics haven't hindered either Lightning Labs or ACINQ from raising healthy series-A funding rounds in the past few months. Lightning Labs raised a $10M round early February, which brings the company's raise total to $12.5M. Similarly, ACINQ closed an $8M series-A round last October.

## Bitcoin SideChains

The initial focus of the LN was to support micropayments without the need for any trusted intermediaries. This focus excluded a number of exciting and desired features such as fast settlement of bigger Bitcoin transactions, confidential transactions, and the programmability of BTC transactions. This created an opportunity for other off-chain scaling solutions, namely sidechains, that could also posed as exciting investment opportunities in the Bitcoin ecosystem.

### Liquid

Blockstream introduced [Liquid](https://blockstream.com/liquid/) in late 2018 to address the confidentiality of BTC transactions. Liquid saw slow growth over 2019, with less than 100 BTC locked in the sidechain. However, since January the sidechain has been receiving constant inflows of several hundred BTC each month, achieving a capacity of more than 1600 BTC in mid-April and surpassing the capacity of the LN.

![](/assets/images/2020/m4/mf5.png)
_Liquid BTC (L-BTC) in circulation. Source [https://liquid.net/](https://liquid.net/)_

Blockstream currently lists 44 entities as members of Liquid, with more popular names only joining recently. So far, Liquid hasn't gained significant traction among Bitcoin users. According to the Liquid [block explorer](https://blockstream.info/liquid/), most of the sidechain blocks are empty or have a few single-digit transactions. Although Liquid's main focus has shifted into tokenized securities, the tokenized assets on Liquid have tiny circulation caps. Tether (USDT) is currently the largest security issued on Liquid with a cap of only $16.5M. Liquid's focus on asset (token) issuance doesn't resonate well with many in the Bitcoin community who see the focus as an attempt to replicate Ethereum's ERC-20 model. _**These low levels of adoption are definitely not what Blockstream's $55M series-A investors have hoped for.**_

### RSK

![](/assets/images/2020/m4/mf6.png)
_A Federation secures the two-way peg between Bitcoin and RSK_

RSK's ultimate vision is to replicate Ethereum on top of Bitcoin. To realize this goal, RSK has implemented a sidechain with a two-way peg to Bitcoin, and uses a fork of Ethereum's smart contracts to implement programmability for the pegged Bitcoin asset, which is called _RSK Smart Bitcoin_ (RBTC). Similar to Liquid, RSK uses a Federation to secure the two-way peg, the RSK Federation members are not publicly known and are only identifiable by public keys. **Similar to Liquid, the sidechain is also struggling to gain any significant adoption**. Despite the fact that RSK has been active since December 2018, it has only attracted ~160 BTC to the side chain. During 2019, the network had an average of only 50 BTC in the sidechain.

_**So far, RSK has been an underperforming investment** _, the company behind the project, RSK Labs, raised $7.3M in VC funding, according to Crunchbase. This does not include 22,000 BTC raised in a private [token sale](https://www.rifos.org/blog/rif-token-sale) conducted by RIF Labs, which was merged with RSK Labs to create IOV Labs. What makes the situation worse is that RSK is now competing for attention with an ever-increasing number of projects that build interoperability between BTC and smart contract blockchains.

### Interoperable BTC sidechains

For a while, many crypto investors believed that eventually every feature such as privacy and programmability would be built as layers on top of Bitcoin. For these reasons, Liquid and RSK sidechains may have sounded as good investments. Recently, this may have changed. For investors looking to add programmability to bitcoin, teams working on building bridges between BTC and Ethereum or other smart contract platforms have proven to be the better option. Just look to [TBTC's](https://medium.com/tokendaily/the-use-cases-of-decentralized-btc-on-ethereum-73f480ee9bff) recent raise. The Keep/TBTC team [announced](https://www.coindesk.com/makers-of-keep-protocol-raise-7-7m-to-bring-trustless-btc-to-defi) a raise of $7.7M to accelerate project growth just a few weeks ago.

TBTC is not alone. In fact, it is safe to say that every emerging smart contract platform is already thinking of how to build a Bitcoin sidechain/bridge to its platform. In the Cosmos ecosystem, the [Nomic Bitcoin Sidechain](https://blog.nomic.io/launch-of-nomic-bitcoin-sidechain-testnet-v0-1-0) is an interesting project to watch. The project implements a Bitcoin sidechain using the Tendermint technology stack which would make Nomic BTC (NBTC) interoperable with other Tendermint assets when the Inter-Blockchain (IBC) protocol comes to life. Similarly, Tezos fans have started their own tzBTC project to mint BTC tokens inside the Tezos blockchain.

**In conclusion**, the past two years have witnessed a lot of experimentation and building in the Bitcoin off-chain scalability domain. Investments in LN, particularly in LN infrastructure and user services, has been growing significantly and is likely to continue growing over the next few years.

On the other hand, sidechains built on Bitcoin have struggled to gain enough traction or to capture developer imagination. The sidechain narrative has largely moved into the direction of interoperability. The logic here is simply "_why rebuild it if I can just bridge to the same functionality but with more robustness and liquidity."_

To be clear, we are in the early days, and much of what we wrote above can and _should_ change over the next year. However, we expect many of the developing trends that we are tracking now will form the backbone of our new financial system.




***

{% include signup.md %}
