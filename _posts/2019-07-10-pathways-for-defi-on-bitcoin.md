---
title: "Pathways for DeFi on Bitcoin"
permalink: "/pathways-for-defi-on-bitcoin" 

author: mohamedfouda

tags:
  - Mohamed Fouda
  - CY19 Q3

excerpt: Mohamed Fouda explains ways that Bitcoin is being onramped to DeFi. Posted July 10, 2019.

defaults:
  - scope:
      type: posts
---

# [Pathways for DeFi on Bitcoin](https://medium.com/tokendaily/pathways-for-defi-on-bitcoin-a68563c4c95)
### By [Mohamed Fouda](https://twitter.com/MohamedFFouda)
### Posted July 10, 2019

![](/assets/images/cy19/cy19q3m7/mf-1.png){: .align-center}

Decentralized Finance (read **DeFi)**has been a popular narrative for many crypto investors and enthusiasts. DeFi builds upon the promise that several critical financial services are cheaper and more efficient when the role of intermediaries is downsized or eliminated altogether. Theoretically, it also makes online financial services more inclusive since it transcends artificial barriers like different geographic boundaries or jurisdictions.

**_DeFi products and protocols are made possible by allowing us to code the rules (and consequences) of our financial interactions into permissionless blockchains._** Consequently, it comes as no surprise that almost all current DeFi projects have been developed on Ethereum to leverage its smart contract functionality.

![](/assets/images/cy19/cy19q3m7/mf-2.png){: .align-center}
DeFi movement is rapidly [growing](https://defipulse.com/?source=post_page---------------------------)

However, Bitcoin is still the most liquid, familiar, and decentralized cryptocurrency in the world (with dominance exceeding 60% at time of writing). This obviously positions bitcoin as a strong competitor for financial products that can benefit from trustlessness and decentralization. **_However, just because it is obvious does not mean it is easy._**

Bitcoiners want to preserve the _hardness_ of Bitcoin at all costs and are not willing to radically change the monetary policy for any reason, DeFi or not. There is no chance smart contract functionality would be added to the Bitcoin protocol to allow for the implementation of DeFi products, though sidechain solutions like RSK exist.

But, that does not mean Bitcoin DeFi could never happen.

Many individuals and teams are striving to use Bitcoin, _with its current structure_, in financial products ranging from centralized to almost completely decentralized.

**_In this article, I discuss how Bitcoin DeFi can be made possible. The different technological approaches are explained along with the different use cases that they target._**

## But First, What Do We Mean by DeFi?

Decentralized Finance or **DeFi** is an umbrella term for all the financial services that can be performed without a central authority or when the mechanism to control the financial product is decentralized between different entities. DeFi products include decentralized lending, decentralized exchanges, decentralized derivatives or even decentralized issuance of stable coins. Many argue that **_decentralized payments on their own are DeFi products._**I happen to agree with this argument. In this regard, BTC is the cryptocurrency with most merchant adoption. Services like [BTCPay Server](https://btcpayserver.org/?source=post_page---------------------------) even allow merchants to receive BTC directly without a third-party payment processor. Therefore, this article is mainly about how Bitcoin can _expand_ its DeFi footprint beyond decentralized payments.

***

## Overview of Bitcoin Centralized Financial Products

Before diving into the pathways for DeFi on Bitcoin, let's start with some of the "centralized" financial services currently using Bitcoin. These will be prime targets for decentralization once DeFi can be efficiently executed on Bitcoin.

### Bitcoin Lending

One of the most popular financial services built on Bitcoin is lending. We can categorize companies in this area into two buckets. First, are the companies that allow investors to borrow Bitcoin and other cryptocurrencies for trading or market making purposes; the most well-known company in this sector is [Genesis Capital](https://genesiscap.co/?source=post_page---------------------------). Genesis Capital has [reportedly](https://genesiscap.co/q4-insights/?source=post_page---------------------------) processed $1.1B of crypto loans in 2018, ending the year with ~ 75% of these loans in BTC.

The other line of lending businesses are the companies that offer BTC-collateralized loans such as [BlockFi](https://blockfi.com/?source=post_page---------------------------) and [Unchained Capital](https://www.unchained-capital.com/?source=post_page---------------------------). To protect against collateral value volatility, these companies only issue over-collateralized loans with loan-to-value ratios of 20–50%.

### Margin Lending

Margin lending is a special case of collateral-based lending used for leveraged trading. In such scenarios, the borrowed funds are not allowed to leave the lending platform. Instead, if the trade loss is equal or below the collateral value, the margin position is liquidated to return the funds to the lender. Exchanges, such as BitMex, Kraken, Bitfinex, and Poloniex, are the major players in margin trading field. However, most of these products are not available for US customers because of regulatory uncertainty.

### Stablecoins

Stablecoins that can be transferred easily with low fees have specifically been of interest to traders who want to benefit from volatility but keep a stable value when they are not in active positions. [Tether](https://tether.to/?source=post_page---------------------------) (USDT) was one of the earliest stablecoins offered to address this issue. It was completely built on Bitcoin using the [OmniLayer protocol](https://www.omnilayer.org/?source=post_page---------------------------). OmniLayer allows the creation and transfer of assets using Bitcoin transaction's opcode space.

USDT was created as a stablecoin pegged to the dollar with the promise that the USDT tokens are only minted when corresponding USD deposits are credited to the Tether company and burnt when the USDT tokens are redeemed back to USD. Although Tether can be transacted in a decentralized way, it is centralized in the most important aspects: reserves and control. The Tether company holds and controls all the USD reserve for the issued USDT tokens in its bank account which regularly puts them in legal [headwind](https://www.wsj.com/articles/bitfinex-used-tether-reserves-to-mask-missing-850-million-probe-finds-11556227031?source=post_page---------------------------)s.

![](/assets/images/cy19/cy19q3m7/mf-3.png){: .align-center}
USDT usage on Ethereum is stealing activity away from USDT Omni activity. Source: CoinMetrics

Recently, Tether started to reduce its dependence on the Bitcoin network by issuing USDT on other blockchains like Ethereum and EOS, which has been taking activity away from the Bitcoin blockchain.

***

## Decentralized Finance in Bitcoin

![](/assets/images/cy19/cy19q3m7/mf-4.png){: .align-center}
Possible technological approaches to use Bitcoin for DeFi

Now let's look into how DeFi products can be used with Bitcoin and list a few use cases and projects in that area. The possible use cases include decentralized exchanges (DEXs), decentralized lending, decentralized stablecoins, and decentralized derivatives. The technological approaches to implement Bitcoin DeFi include

1. Using Bitcoin current capabilities such as [Hash Time Locked Contracts (HTLCs)](https://en.bitcoin.it/wiki/Hash_Time_Locked_Contracts?source=post_page---------------------------) to facilitate direct cross-chain atomic swaps to build decentralized exchanges with other cryptocurrencies.
2. Federated sidechains to Bitcoin such as Blockstream's [Liquid](https://blockstream.com/liquid/?source=post_page---------------------------). These sidechains use two-way pegs to the Bitcoin blockchain and allow the use of pegged BTC in various financial activities.
3. Using Bitcoin within other protocols such as Ethereum or Cosmos to interact with DeFi products.
4. Using layers on top of Bitcoin like OmniLayer or Lightning Network.

These technologies differ in capabilities and the range of DeFi applications they can support. In addition, most of these technologies are work in progress. In the following, we explore these technologies and the use cases they target.

## Cross-chain Swaps For Decentralized Exchanges

The simple premise of DEXs is to execute trades between Bitcoin and fiat or between Bitcoin and other cryptocurrencies while keeping custody of your coins until the trade is completed. In other words, trading without the need to deposit your valuable bitcoins into a centralized exchange wallet and be subjected to the exchange security risks.

While such trades can be performed using platforms like [LocalBitcoins](https://localbitcoins.com/?source=post_page---------------------------) or [OpenBazaar](https://openbazaar.org/?source=post_page---------------------------), these platforms are only suitable for once-in-a-while slow trading and are not suitable for fast or frequent trading that allows efficient price discovery. For the latter, a centralized order book along with the ability to quickly settle trades is needed. Practically speaking, building a truly decentralized exchange is one of the hardest challenges in DeFi. As long as you have centralized servers keeping or even displaying the order book, you still have centralized components. However, our focus here is mainly around keeping custody of coins until trades are settled. In this domain, we believe a small number of companies are developing the technology needed to achieve that. The ones that we feel at the leading the pack are [Arwen](https://www.arwen.io/?source=post_page---------------------------) and [Summa](https://summa.one/?source=post_page---------------------------).

[**Arwen**](https://arwen.io/?source=post_page---------------------------)uses the concepts of trustless on-chain escrows and cross-chain atomic swaps to allow non-custodial access to centralized exchanges order books. In that sense, it is possible to trade efficiently on a centralized order book while maintaining custody of the asset until the trade is executed. Currently, the product only supports cryptocurrencies that use the same codebase as Bitcoin such as Litecoin and Bitcoin Cash. They are working on implementing cross-chain atomic swaps between Bitcoins and Ethereum and ERC-20 tokens. Arwen can currently be used (in beta) on Kucoin exchange.

[**Summa**](https://summa.one/?source=post_page---------------------------)has invented the [Stateless SPV](https://medium.com/summa-technology/cross-chain-auction-technical-f16710bfe69f?source=post_page---------------------------) technology to allow for trustless financial services for Bitcoin and other blockchains. Stateless SPV allows for validating Bitcoin transactions using an Ethereum smart contract making it possible to perform a wide range of financial transactions using Bitcoin. Using that technology, Summa's team [performed](https://medium.com/summa-technology/summa-auction-bitcoin-technical-7344096498f2?source=post_page---------------------------) an auction using bitcoin bidding for Ethereum-issued tokens. The team is working on generalized cross-chain exchanges between Bitcoin and Ethereum and ERC-20 tokens.

## Bitcoin DeFi Using Federated Sidechains

Bitcoin sidechain is a concept that was proposed by Blockstream in [2014](https://blockstream.com/sidechains.pdf?source=post_page---------------------------) to introduce new features to Bitcoin without changing the protocol base layer. Since then the concept has developed [significantly](https://twitter.com/gakonst/status/1146793685545304064?source=post_page---------------------------). The simple idea of sidechains is to create a separate chain with a small number of validators (called a federation) and use a token in that chain that is a pegged to BTC through a two-way peg. The benefits can include faster transaction confirmation or implementing features that may be controversial such as confidential transaction, tokenization of other assets or smart contracts. The main drawback of sidechains is the need to trust a small federation to operate the sidechain and keep it running. There is also a risk of losing money by using sidechains if, for any reason, sidechain validators decided to abandon the chain. In those situations, pegged assets would get stuck and cannot be redeemed back to BTC.

A notable sidechain working to bring smart contract functionality to Bitcoin is [RSK](https://www.rsk.co/?source=post_page---------------------------). It supports Solidity smart contracts making it easy to migrate Ethereum DeFi protocols to RSK. In addition to RSK, Blockstream has commercially launched its [Liquid](https://blockstream.com/liquid/?source=post_page---------------------------) sidechain product in 2018. However, Blockstream's initial focus is around the tokenization of assets and faster transaction but the concept could be expanded later to support DeFi applications.

## Decentralized Derivatives Using Bitcoin Layers

A third approach to implement Bitcoin DeFi products is to utilize intermediate layers built on top of Bitcoin such as Lightning Network or OnmiLayer. As LN is a relatively new Bitcoin development, building complex DeFi products using LN is a topic of research. The most notable effort there is [Discreet Log Contracts](https://medium.com/@gertjaap/discreet-log-contracts-invisible-smart-contracts-on-the-bitcoin-blockchain-cc8afbdbf0db?source=post_page---------------------------) which are discussed in some detail at the end of this article.

The other option is using OmniLayer. One of the interesting projects in this regard is [Tradelayer](http://tradelayer.org/?source=post_page---------------------------), which is trying to implement decentralized derivative markets on Bitcoin. The project aims to extend the OmniLayer protocol with multisig channels to allow for using Bitcoin, or other tokens issued on Bitcoin, as collateral for peer-to-peer derivative trades. A possible scenario is to have traders pledging capital to multisig addresses and co-sign transactions and trade updates to settle the derivative trade. In this sense, users can take leverage natively and get fast-execution by co-signing trade transactions. Using the same methodology, another possible use case could be the issuance of stable coins using Bitcoin as collateral the same way Ether is used to collateralize DAI issuance on MakerDao.

## Bitcoin DeFi With External Help

### Wrapped BTC on Ethereum

A completely different approach to allow using Bitcoin in DeFi is to leverage other networks like Ethereum or Cosmos. As most DeFi projects now work on Ethereum, it seemed logical to try to find ways to use BTC on Ethereum. The simplest idea is to issue a BTC-backed ERC20 token ([WBTC](https://www.wbtc.network/?source=post_page---------------------------)) that can be traded on any Ethereum DEX or used in various Ethereum DeFi projects. The BTC used to mint WBTC are secured in mutisig wallets maintained by the project custody providers. As of early July 2019, only ~ 540 WBTC were minted is a tiny fraction of the BTC circulating supply.

![](/assets/images/cy19/cy19q3m7/mf-5.png){: .align-center}
Growth of the Wrapped BTC (WBTC) supply over time

While WBTC may facilitate using BTC in DeFi, it suffers a few important drawbacks. The first and most important is counterparty risk. The BTC used to collateralize WBTC is maintained by centralized parties that might be hacked. Secondly, introducing intermediate entities to custody the assets (BTC) to some extent kills the point of the DeFi movement. Finally, to use BTC/WBTC in DeFi, users have to pay fees in ETH, which is something many Bitcoin fans are not willing to do.

### Cosmos Zones

Interoperability blockchain projects, such as Cosmos, opened new opportunities to bring DeFi to assets like Bitcoin. For example, Cosmos protocol defines Peg Zones where assets (issued on Cosmos) can be pegged to other blockchain assets like [Bitcoin](https://github.com/nomic-io/bitcoin-peg?source=post_page---------------------------). In these zones, it is possible to add smart contract functionality to the pegged asset and benefit from faster finality. This approach has garnered the support of some hardcore Bitcoin supporters like [Eric Meltzer](https://twitter.com/wheatpond?source=post_page---------------------------) for one specific reason: in this approach, Bitcoin will remain the native currency to pay fees and use the peg zone. Bitcoiners can stake their pegged bitcoins in the zone to process the zone transactions and claim the zone fees. In that sense, Bitcoin will benefit from the new tech without depending on a different asset. This comes in stark contrast to WBTC, which requires using ETH to pay for fees or interact with DeFi protocols.

![](/assets/images/cy19/cy19q3m7/mf-6.png){: .align-center}

It is worth mentioning that using Cosmos zones for Bitcoin DeFi is still work under development and there is a number of stealth projects that are building it. It is not clear yet how the two-way peg between Bitcoin and Cosmos would work. The implementation of the Cosmos [Inter-Blockchain Communication](https://cosmos.network/docs/spec/ibc/?source=post_page---------------------------) (IBC) is not yet finalized. If the two-way peg requires custodial services, like WBTC, or a few validators to execute the peg, like federated sidechains, the Bitcoin zone on Cosmos will not offer much differentiation to other solutions.

In addition to the projects that are building such systems for Bitcoin, we are seeing a lot of interest in using Cosmos for bringing DeFi to other assets such as [Kava Labs](https://medium.com/kava-labs/defi-coming-to-cosmos-808034b733be?source=post_page---------------------------). If these efforts deemed successful, barriers for Bitcoin use in DeFi would significantly diminish. Success in this regard is to be able to attract sufficient liquidity to the peg zone and to maintain a reasonable level of decentralization by attracting a large enough number of validators.

***

## Research to Expand Bitcoin DeFi Capabilities

### Merkelized Abstract Syntax Trees (MAST)

Bitcoin, in its current form, has a limited form of smart contract capabilities through the [Script](https://en.bitcoin.it/wiki/Script?source=post_page---------------------------) language. Script is not a Turing-complete language meaning it cannot be used to describe general programs. However, it still can be used to implement some smart contract functionality. This is done via Pay to Script Hash (P2SH) and SegWit addresses, in which, a transaction cannot be spent unless some conditions (defined through a Script program) are satisfied. The problem with that approach is that complex transactions with multiple conditions would be excessively large, making them too expensive to use. For those reasons, there is a [proposal](https://github.com/bitcoin/bips/blob/master/bip-0114.mediawiki?source=post_page---------------------------)to implement Merkelized Abstract Syntax Trees ([MAST](https://themoneymongers.com/merkelized-abstract-syntax-tree-mast/?source=post_page---------------------------)) in Bitcoin. MAST is simply an extension to the P2SH capabilities that would make it cheaper and viable to utilize complex conditions to spend Bitcoin transactions.
While the obvious benefit of MAST is improving Bitcoin scalability by saving block space, the less obvious benefit is that it could allow for some Bitcoin DeFi use cases. For example, _if we assume a decentralized price-feed oracle can be implemented_, MAST could allow for decentralized lending or even decentralized stable coin issuance using BTC as collateral.

The following diagram shows a possible decision tree for a decentralized lending scenario using MAST. The various conditions for the loan settlement can be coded into a redemption script and hashed into a MAST address. The MAST address can guarantee fair execution of the loan and that the lender would get the loan collateral if the borrower didn't pay back the loan on time or if the collateral value goes below the loan value plus interest.

![](/assets/images/cy19/cy19q3m7/mf-7.png){: .align-center}

### Discreet Log Contracts

Another research idea that can expand Bitcoin DeFi capabilities is the [Discreet Log Contracts](https://adiabat.github.io/dlc.pdf?source=post_page---------------------------) (DLCs) suggested by [Tadge Dryja](https://twitter.com/tdryja?source=post_page---------------------------) of the MIT Digital Currency Initiative (DCI). A simple explanation of a DLC is that it is a way for two parties to create a Futures Contract which is simply a bet on the future price of an asset. A DLC requires both parties to select an oracle (or a number of oracles) that publicly broadcasts the asset price before they create the contract. At the time of the contract settlement, any of the two parties can use the publicly broadcasted signed messages from the oracle to settle the contract and claim their profits. DLCs utilize [Schnorr signatures](https://en.wikipedia.org/wiki/Schnorr_signature?source=post_page---------------------------) to hide the contract details from the oracle. This guarantees the oracle cannot game the output of the contract. As DLCs use similar technology to that of Lightning Network, it is possible to integrate DLCs with LN channels.

## Conclusion

DeFi protocols have been generating a lot of buzz since early 2018. While Ethereum is recognized as the lead protocol within the DeFi movement, developers and investors have been eyeing the massive potential of Bitcoin in DeFi as the most liquid cryptocurrency. This great interest is pushing many developer teams to figure out the best ways to make it happen. While this would bring even more competition between Bitcoin and Ethereum and probably all new smart contract platforms, such competition is what is needed to encourage progress and deliver the vision of a public decentralized financial system.

I would like to thank [Matt Corallo](https://twitter.com/thebluematt?lang=en&source=post_page---------------------------), [Tony Sheng](https://twitter.com/tonysheng?source=post_page---------------------------) and [Matthew Hammond](https://twitter.com/mchammond?source=post_page---------------------------) for their feedback on this article.
