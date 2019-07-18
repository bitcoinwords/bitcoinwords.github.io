---
title: "Bitcoin: Past and Future"
permalink: "/https://medium.com/adaptivecapital/bitcoin-past-and-future-45d92b3180f1" 

author: adamtacheandmuradmahmudov

tags:
  - Adam Taché
  - Murad Mahmudov
  - CY18 Q2

excerpt: Posted May 30, 2018 by Adam Tache and Murad Mahmudov, this article will analyze these perspectives by discussing trade-offs, philosophical divides within the community, and expected behaviors of the proposed systems.

defaults:
  - scope:
      type: posts
---

# [Bitcoin: Past and Future](https://medium.com/adaptivecapital/bitcoin-past-and-future-45d92b3180f1)
### By [Murad Mahmudov](https://twitter.com/muststopmurad) and [Adam Tache](https://twitter.com/adam_tache)
### Posted May 30, 2018

# Foreword

This is a follow-up to [The Many Faces of Bitcoin](https://hackernoon.com/the-many-faces-of-bitcoin-1c298570d191?source=post_page---------------------------), which discussed four schools of thought of Bitcoin. This article will analyze these perspectives by discussing trade-offs, philosophical divides within the community, and expected behaviors of the proposed systems.

## Index

* Bitcoin as Money
* Roles of Full Nodes & Miners in Bitcoin & Bitcoin Cash
* Addressing "Satoshi's Original Vision"
* Role of SPV
* Segregated Witness
* Bitcoin Maximalism
* Upper-Layer Systems and Alt-Coins

***

# Bitcoin As Money

Bitcoin presents us with an opportunity to reinvent gold, or even rethink money for the digital future. A number of economists have suggested that it may be more appropriate to evaluate items based on their degree of _moneyness._ According to this thinking, it isn't that something either is or is not money; on the contrary, many items can play a monetary role and some items can play this role more effectively than others. In a number of ways, bitcoins have a high degree of moneyness. They are more portable, durable, divisible, and scarce than both gold and government fiat currency.

As of today, bitcoins can best be described as digital commodities with monetary properties. According to the Bitcoin Maximalist [interpretation](https://twitter.com/NickSzabo4/status/954225789129469952?source=post_page---------------------------) of monetary history, it is likely that a new, scarce form of money would evolve roughly along the following lines:

1. Collectible
2. + Store of Value
3. + Medium of Exchange
4. + Unit of Account.

Proponents of bitcoins as digital cash believe that utility should initially take precedence over store of value, and prioritize attaining the medium of exchange role before store of value by making payments as cheap as possible.

Those who believe bitcoin will become the future global monetary standard ascribe current volatility to the fact that bitcoin is undergoing the process of monetization, and that a global cognitive shift is slowly occurring. In their view, despite great volatility, the long-term parabolic ascent of the price is a testament to more and more people believing in a future world where Bitcoin is widely used.

Crypto-[Austrians](https://mises.org/what-austrian-economics?source=post_page---------------------------)who consider themselves[Rothbardians](https://www.mises.org/profile/murray-n-rothbard?source=post_page---------------------------), such as author[Saifedean Ammous](https://twitter.com/saifedean?source=post_page---------------------------), believe that bitcoin's disinflationary nature and cap on supply makes it the most sound money ever invented. They believe that bitcoin, with its fixed monetary supply, is the only fair form of money, as well as one which allows for the most efficient capital allocation by individuals and most efficient price signalling by the market as a whole.

Many individuals in this group are against the idea of fractional-reserve banking and consider it to be fraudulent. They believe that a fractional-reserve banking system is unlikely to emerge atop bitcoin, as bitcoins lack the physical centralization of gold, which forced settlements and clearance to necessarily pass through centralized choke-points, allowing governments to have complete control over the money supply, transmission, and the monetary regime at large. The governments had so much control that they were able to get rid of the gold-standard (which was organically chosen by the market over centuries) and introduce their own fiat standards, not backed by any commodity.

These individuals believe that fractional-reserve systems are simply unsustainable in the long run without lenders of last resort, which do not inherently exist in Bitcoin, and that people would be unwilling to accept bitcoin-substitutes in the market.

Those in the "[Free Banking](https://www.alt-m.org/2015/07/18/hayek-and-free-banking/?source=post_page---------------------------)" wing of the Austrian school, such as [George Selgin](https://www.hillsdale.edu/wp-content/uploads/2016/02/FMF-2014-Bitcoin-Problems-and-Prospects.pdf?source=post_page---------------------------) and [Lawrence White](https://soundcloud.com/cryptovoices/show-40-lawrence-white-money-banking-bitcoin?source=post_page---------------------------), believe that bitcoin's strictly fixed-supply and lack of lenders of last resort do not technically prevent a competitive system of fractional-reserve banks and entities arising atop bitcoin, or in an economy where bitcoin is the defacto monetary standard.

It is clear that there is a chance that bitcoin can, at the very least, emerge as a mildly volatile digital commodity, a store of value akin to digital gold. However, doubts remain whether it will transcend the raw store of value role and achieve low enough volatility to become a global medium of exchange and a unit of account.

Some believe that, due to its strictly inelastic supply, bitcoin is unlikely to be stable in its purchasing power anytime soon, if ever, and that people prefer for their day-to-day currency to be stable in purchasing power. These people have expressed excitement about the emergence of cryptocurrencies with more flexible and self-regulating monetary policies built in. For example, [stablecoins](http://juliankohtx.com/stablecoins-and-the-story-of-money/?source=post_page---------------------------) aim to peg their market value against another form of value, such as the USD or a basket of goods, using an algorithmic central bank.

Others[believe](https://medium.com/@rextar4444/a-neo-gold-standard-bitcoins-optimal-use-case-62d7fbb2f76f?source=post_page---------------------------)that, despite bitcoin's strictly inelastic supply, bitcoin is a perfect solution to[John Nash](https://en.wikipedia.org/wiki/John_Forbes_Nash_Jr.?source=post_page---------------------------)'s[Ideal Money](http://personal.psu.edu/gjb6/nash/money.pdf?source=post_page---------------------------)proposal that he worked on for over fifty years. Nash, a Nobel Laureate in Economics,[proposed(http://web.math.princeton.edu/jfnj/texts_and_graphics/Main.Content/IDEAL_MONEY.../Campus_for_Finance_of_2010/?source=post_page---------------------------)that central banks could inflation-target their currencies against an apolitical index to achieve international relational stability of all state currencies. In response to increasing demand for bitcoin, some believe banks will value target their currencies against bitcoin as a basis for the standardization of the value of money.

## Deflationary Death Spiral

Mainstream, Keynesian, and Monetarist economists have expressed concerns with Bitcoin's fixed-supply. They fear the possibility of harsh deflationary pressures if bitcoin becomes the predominant currency through the process known as [hyperbitcoinization](https://nakamotoinstitute.org/mempool/hyperbitcoinization/?source=post_page---------------------------).

Their fear is that the inability to expand the money supply would result in bitcoin's purchasing power growing by 2–3% per annum, roughly in line with the growth rates of global economic output. Some have expressed concerns that deflationary economics might reduce aggregate demand in the present and the near-term, result in excessive savings and hoarding of money, and produce less consumption, investment and entrepreneurial risk-taking by individuals.

Austrian economists believe that the fears associated with a deflationary form of money are [overblown](https://mises.org/library/deflationary-spiral-bogey?source=post_page---------------------------) and that the 'deflationary spiral' is a myth. Austrian's counter the Keynesian and Monetarists concerns that the delay in spending doesn't last in perpetuity by reminding them that this spending is merely delayed into the future. People will now have a lower time-preference and that instead of buying "useless" things with their "hot potato" decaying money, they will turn their attention to long-term productivity.

They also believe that business profit margins will not be hurt because not only would product prices, but also business costs, deflate at the same rate, leaving the profit margins unchanged. Austrians believe that deflation is absolutely normal, and absent central control on the money supply, both capitalism and technology are naturally deflationary phenomenons. This can be seen in the less-regulated electronics industry, where increased storage/memory/compute capacities are becoming cheaper every year.

According to Austrians, it is the _central bank inflationary fiat printing_ that exacerbates recessions and business cycles, as the perpetually-decaying money embeds the citizenry constant anxiety and stress, resulting in not well though-out investments and expenditures, collectively referred to as 'malinvestment'. These malinvestments are typically inefficient allocations of capital, which are unlikely to result in personal gains, societal gains, productivity, or capital stock.

# Roles of Full Nodes & Miners in Bitcoin & Bitcoin Cash

## The Scaling Debate

The debate over how to scale Bitcoin is very polarizing, and is about scaling throughput, also known as transactions per second (TPS). The main contention is how much it should cost to run a [full node](https://bitcoin.org/en/full-node?source=post_page---------------------------), and what the role of full nodes and miners should be in the the system.

In July 2010, Satoshi Nakamoto, the creator of Bitcoin, [supposedly](https://www.reddit.com/r/Bitcoin/comments/3giend/citation_needed_satoshis_reason_for_blocksize/ctygzmi/?source=post_page---------------------------) added a 1 MB maximum block size limit as an anti-DoS (Denial of Service) prevention mechanism. This 1 MB block size limit stood in place, and until transaction volume increased heavily in 2017, the blocks were never close to full capacity. When this limit was introduced, 1 MB was hundreds of times the size of an average block.

In August 2017, an update called Segregated Witness (SegWit for short, see dedicated section below) was activated, which increased the amount of data that could be stored in a block to above 1 MB. Taking many by surprise, at around the same time, on August 1, a fork of Bitcoin (BTC) named Bitcoin Cash (BCH) spawned from users dissatisfied with the BTC developers' scaling roadmap and emphasis on bitcoins as digital gold. The developers of this fork quickly implemented 32 MB blocks and are planning to increase the limit much further, which would allow for more on-chain transactions per block and cheaper fees but make it more expensive to run a full node.

Factors that influence the cost of running a full node include required bandwidth, the size of the UTXO set (see [this](https://www.safaribooksonline.com/library/view/mastering-bitcoin/9781491902639/ch05.html?source=post_page---------------------------) primer on Bitcoin transactions if you're not familiar with the [UTXO](http://transaction/%20Outputs%20and%20Inputs?source=post_page---------------------------) concept), and required CPU, RAM, and disk space, which are all impacted by the block size.

Those who favor small blocks view them as essential to maintain decentralization of the system by allowing any user to afford validation using a full node, and to develop a [fee market](https://medium.com/@jimmysong/the-fee-market-explained-76b294947b42?source=post_page---------------------------) in order to guarantee miner compensation as the block reward decreases.

The proponents of Bitcoin Cash, "big blockers," view a block size limit as an artificial limit maintained through a centralized planning mechanism in the form of consensus rules. Many prefer miners selecting the size of blocks they are willing to create based on market conditions. There are other blockchain projects where this is the case, such as Ethereum where miners can [vote](https://www.etherchain.org/tools/gasLimitVoting?source=post_page---------------------------) to adjust the gas limit, which is analogous to the block size in Bitcoin, a certain factor each block.

**_The perspective of "small blockers" (Bitcoin project)_**

> Full nodes relay transactions and blocks and do full verification of the data they relay to other members of the (full node) network, enforcing consensus rules and serving as watchful eyes against potentially malicious miners.
Bitcoin's value arose from the system eliminating trust in third-parties, having resilience to state-level attacks, and its censorship-resistant nature. All users having the ability to run a full node is essential to maintain these characteristics.
As the cost of running a full node increases, a smaller percentage of users can afford validation and enforce consensus rules, and a greater percentage of users are forced into using Bitcoin in a trusted manner, relying on others to be honest, rather than the robustness of the system as a whole.
Massive blocks will eventually result in full nodes residing only in data centers, which increases centralization by putting consensus in the hands of a limited number of entities, puts Bitcoin at a greater risk of getting shut down, and degrades privacy by requiring users to connect to other nodes.
SPV (Simple Payment Verification) clients, which are lightweight clients that can prove a transaction is included in a block without downloading the entire blockchain, are incapable of trustless and complete validation.

At this time, even low-end computing devices such as a [Raspberry Pi](https://www.renewable-energy-now.org/2017/07/raspberry-pi-bitcoin-full-node-english/?source=post_page---------------------------) can serve as a functioning full node. Many desire a future where even smartphones can serve as full nodes.

In order for a full node to perform validation, it must propagate the entire UTXO set that it derived by processing the entire chain. The UTXO set can shrink by users and companies consolidating outputs, but it has been [shown](http://statoshi.info/dashboard/db/unspent-transaction-output-set?source=post_page---------------------------)to steadily increase over time and can grow infinitely in size.

By primarily using the blockchain as a settlement layer for off-chain transactions and optimizing space efficiency through technological improvements, the UTXO set is managed much more efficiently, block propagation latency and initial blockchain syncing times are reduced, and the amount of bandwidth, CPU power, RAM, and disk space required to run a full node are minimized.

Off-chain payment-channels (like the [Lightning Network](https://lightning.network/lightning-network-summary.pdf?source=post_page---------------------------)) are being developed, which will be able to settle thousands or millions of transactions in a single transaction on the Bitcoin blockchain.

Although miners are the only entities that can produce new candidate blocks, economic full node operators signal and provide the incentive for miners to create valid blocks by rejecting invalid ones. If a miner were to produce an invalid block, such as one with differing consensus rules than those defined by the rest of the network (e.g. tampering with issuance rate of new bitcoins or altering the maximum number of bitcoins), full nodes would automatically ignore it even if a majority of the hash power accepted the block as valid.

The ability for full nodes to reject invalid blocks and trustlessly verify transactions leads to the saying "Don't Trust, Verify" — and this is why full nodes are deemed the network that miners are being paid to serve.

![](/assets/images/cy18/cy18q2m5/am-1.png){: .align-center}

This is not to say that miners don't have any control at all. Both full node operators and miners power aspects of the system, despite having differing roles. Miners can choose what transactions they include in blocks (profit-maximizing miners will likely include ones with higher fees) and create new blocks, whereas merchants and other full node operators (including mining pool node operators) determine validity of blocks and transactions, enforcing consensus rules.

A User Activated Soft Fork (UASF) [event](http://www.uasf.co/?source=post_page---------------------------) in 2017 demonstrated that users operating full nodes were able to push miners to activate SegWit despite only a minority of miners initially signaling that they were in favor of the update.

<figure>
  <a href="https://twitter.com/Xentagz/status/1000625196057886720"><img src="http://cryptowords.github.io/assets/images/cy18.cy18q2m5/am-2.png"></a>
  <figcaption><a href="https://twitter.com/Xentagz/status/1000625196057886720" title="The perspective of big blockers (Bitcoin Cash project)">The perspective of "big blockers" (Bitcoin Cash project)</a>.</figcaption>
</figure>

Bitcoin Cash proponents look to scale toward unlimited block size and do not believe in the importance of full nodes being cheap to run for all. They claim the best version of Bitcoin was outlined by Satoshi Nakamoto in his original whitepaper, blog posts, and emails. They believe Satoshi only considered miners to be the network and that consensus should be handled purely through hash power.

Some big blockers believe that users simply transacting never need to run full nodes, but some recommend [incrementally](https://web.archive.org/web/20150213020502/https://blog.bitcoinfoundation.org/a-scalability-roadmap/?source=post_page---------------------------) increasing the block size in accordance to [Nielsen's Law](https://www.nngroup.com/articles/law-of-bandwidth/?source=post_page---------------------------) of bandwidth to allow users with "reasonable" computers and internet connections to continue to run full nodes.

> Miners are held accountable through profit-maximization and game theoretic market incentives. Miners will never collude as they are in direct competition with one another to find new blocks and get bitcoins as a reward.
The security model of SPV is good enough for end-users, and full nodes are powerless, passive observers to the mining network. Full nodes are only needed by firms such as payment processors to provide services such as 0-confirmation transactions and serving merkle-branch proofs to SPV clients.
There is nothing sacred about non-monetary Bitcoin consensus rules, which should be allowed to [emerge](https://www.bitcoinunlimited.info/emergent-consensus?source=post_page---------------------------) through a market process.

![](/assets/images/cy18/cy18q2m5/am-3.png){: .align-center}

From [Mark Wilcox](http://markwilcox.com/articles/03/?source=post_page---------------------------):

> "The whole point of the Proof of Work game is that nodes cannot be trusted. The only thing we can trust is the difficulty of solving the problem, and the economic interests of everyone involved. This means that, quite crucially, 'everyone is responsible' is different from 'everyone must do everything'. We collectively need to protect the network. But the whole point of rewarding nodes that contribute hashpower is to free everyone else of the burden of having to worry about attacks on monetary policy or denial of service."

BCH proponents equate decentralization to competition and the network topology of miners instead of full node cost. They rejected SegWit, and Bitcoin Cash was their response. They encourage on-chain applications, such as the social network [Memo](https://memo.cash/?source=post_page---------------------------), which small blockers would likely view as spam and encourage to be developed on upper-layer systems instead.

# Addressing "Satoshi's Original Vision"

**_The perspective of "small blockers" (Bitcoin project)_**

BTC proponents believe that appealing to Satoshi's words is a logical fallacy of appealing to authority, and that Satoshi should no longer matter.

> "If you see the Buddha or a Buddha, kill him."

They generally refer to BCH proponents as whitepaper "religious fundamentalists" who are unable to accept that Bitcoin has organically evolved since its inception. They view BTC as a far superior and more decentralized system than BCH due to the ability for full nodes to serve as a p2p network governance mechanism([**not** a democracy](https://medium.com/@beautyon_/democracy-has-nothing-to-do-with-the-way-bitcoin-works-it-is-a-political-system-where-a-group-of-efb37a627415?source=post_page---------------------------)).

Many view BCH as a [fraudulent](https://hackernoon.com/thats-not-bitcoin-that-s-bcash-f730f0d0a837?source=post_page---------------------------) project guided by leaders attempting to take over the Bitcoin brand and establish a centralized, miner-controlled system that requires trust in third-parties.

BTC proponents also [mention](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2013-April/002417.html?source=post_page---------------------------) that Satoshi laid the groundwork for the Lightning Network through a high-frequency trading payment channel design.

Satoshi's last words about block size were written in December 2010 during a [discussion](https://bitcointalk.org/index.php?topic=1790.msg28917&source=post_page---------------------------#msg28917) about BitDNS, a proposal to use Bitcoin for domain name issuance which led to the creation of a merged-mined blockchain called [Namecoin](https://www.namecoin.org/?source=post_page---------------------------).

> "BitDNS users might be completely liberal about adding any large data features since relatively few domain registrars are needed, while Bitcoin users might get increasingly tyrannical about limiting the size of the chain so it's easy for lots of users and small devices."

Here, Satoshi alluded to the scaling debate and suggested limiting the size of the blockchain might gain consensus.

Bitcoin Cash did not receive social consensus to be called Bitcoin based on the User Activated Soft Fork, market cap, and hash rate. Instead, Bitcoin Cash hard forked to create a new network, whereas Segregated Witness was an update to the original Bitcoin network in which old software still functions.

**_The perspective of "big blockers" (Bitcoin Cash project)_**

BCH proponents pronounce that "Bitcoin Cash is Bitcoin" as they believe Bitcoin was designed to scale on-chain without 'non-mining full nodes' limiting the throughput of the system. They note that Satoshi referred to miners as 'nodes' in his writings.

From Satoshi Nakamoto:

> "Only people trying to create new coins would need to run network nodes. At first, most users would run network nodes, but as the network grows beyond a certain point, it would be left more and more to specialists with server farms of specialized hardware."
"The current system where every user is a network node is not the intended configuration for large scale. That would be like every Usenet user runs their own NNTP server. The design supports letting users just be users. The more burden it is to run a node, the fewer nodes there will be. Those few nodes will be big server farms."

BCH proponents feel small blockers co-opted the Bitcoin project to create a settlement network with high on-chain fees when blocks are full. Some believe Core developers succeeded at changing people's understanding of Proof-of-Work (PoW) game theory, as they [interpret](https://www.reddit.com/r/btc/comments/5zawlw/satoshi_whitepapers_longest_chain_is_bitcoin_rule/dewpjza/?source=post_page---------------------------) Satoshi's descriptions of PoW as mining being the only consensus mechanism.

***

BTC proponents strongly[object](https://www.reddit.com/r/Bitcoin/comments/5j6758/myth_nakamoto_consensus_decides_the_rules_for/dbe7kbb/?source=post_page---------------------------)to the contention that miners ever controlled consensus rules. They note that even in the[original](https://github.com/trottier/original-bitcoin?source=post_page---------------------------)node software, the longest PoW chain rule only applied to resolving disputes between multiple chains using the same consensus rules, and nodes had the option to generate coins or not.

# Role of SPV

In contrast to full nodes, the type of software for lightweight Bitcoin clients is SPV (Simple Payment Verification). SPV clients allow a user to connect to one or more nodes (i.e. from a smartphone), determine the latest block with longest PoW chain, and request [block headers](https://bitcoin.org/en/developer-reference?source=post_page---------------------------#block-headers) (80 bytes each) from the node(s).

As described in section 8 of the whitepaper, a user can obtain the merkle branch which confirms their transaction is inside a block with a valid block header and proof of work. Further confirmations (new blocks on top of the other block) demonstrate further work was done.

SPV clients cannot validate blocks or consensus rules themselves, so they must trust the validation of the node(s) they are connected to.

A theoretical way to increase SPV security, among others, was proposed by Satoshi in the whitepaper. It would allow nodes to alert SPV clients when invalid blocks are detected. Fraud proofs could prove the existence of these invalid blocks with minimal resources required. Although fraud proofs are not implemented today, SegWit enables them to be integrated into Bitcoin with a [soft-fork](https://en.bitcoin.it/wiki/Softfork?source=post_page---------------------------), which is a change that is backwards compatible with old clients and tightens or adds new rules.

# Segregated Witness

A 2017 soft-fork to BTC called Segregated Witness, or SegWit for short, was activated as the result of a multiple year scaling debate. It was primarily a bug fix to an issue involving the malleability of transactions, but also adds more space for transactions and enables easier future updates and extensions through soft forks.

## What is malleability?

Before SegWit, there were malleable (changeable) parts of transactions. For example, a node relaying a transaction or a miner including it in a block could add extra bytes to the transaction's [signature](https://bitcoin.org/en/developer-guide?source=post_page---------------------------#term-signature). This changes the ID, which is a cryptographic hash of the entire transaction, including the signature.

Although there is malleability in other computer software, in the case of Bitcoin, changing the transaction ID after the transaction propagated to the network prevented wallet software to track transactions by ID, users from performing certain types of transactions, and developers from creating certain types of smart contracts.

For example, a valid transaction can spend an unconfirmed output (not yet included in a block) as an input to another transaction in the same block. If the transaction ID of the unconfirmed output was malleated, the first transaction would be confirmed as it's still valid, but the second transaction would be invalid because the transaction data would include aninvalid _Previous tx_ attribute.

Miners, full nodes, and users can choose to use SegWit or not, since it was a soft fork. As of May 2018, transactions with SegWit inputs make up approximately [35%](https://transactionfee.info/charts/payments/segwit?source=post_page---------------------------) of transactions, and SegWit nodes are at approximately [99%](https://luke.dashjr.org/programs/bitcoin/files/charts/segwit.html?source=post_page---------------------------) distribution.

The rest of this section is fairly technical, so feel free to skim or skip to the "Bitcoin Maximalism" section if you are a beginner.

Witness data refers to signatures and unlocking scripts. With SegWit, miners "segregate the witness" by placing the witness data in a separate merkle tree (the data structure inside a block that holds transactions) called the witness merkle tree, which mirrors the transaction tree. The witness root hash is stored in the coinbase transaction, which is the transaction that miners use to pay themselves newly minted bitcoins. Therefore, signatures for SegWit transactions are still included in blocks, since the coinbase transaction affects the merkle root hash that is stored in the block header of a block.

If miners choose to not update to SegWit, then they can't mine blocks with SegWit inputs, as to them these are non-standard transactions. They can still receive SegWit transactions with the witness structure stripped.

**The SegWit update**(for more detail see [SegWit benefits](https://bitcoincore.org/en/2016/01/26/segwit-benefits/?source=post_page---------------------------)) **:**

* Phases out block size in favor of block weight. Currently, blocks can have at most 4 million weight units (WU). A byte in the original block structure weighs 4 WU, whereas a byte in the witness structure only weighs 1 WU. For more, see "[Understanding Segwit Block Size](https://medium.com/@jimmysong/understanding-segwit-block-size-fd901b87c9d4?source=post_page---------------------------)."
* Reduces the UTXO size for SegWit transactions by the size of witnesses, which is around 60–75% of the data. The discount on weight units for the witness structure was introduced to incentivize more responsible growth of the UTXO set by lowering fees.
* Increases the amount of data that can be stored in blocks as the percentage of SegWit transactions increases. The largest block we have [seen](https://www.smartbit.com.au/block/0000000000000000001bbb529c64ddf55edec8f4ebc0a0ccf1d3bb21c278bfa7?source=post_page---------------------------) is 2.1MB.
* Allows payment channels, such as the Lightning Network, to take advantage of the malleability fix.
* Fixes quadratic scaling of Sighash operations.
* Enables the checksummed [Bech32](https://www.youtube.com/watch?v=NqiN9VFE4CU&source=post_page---------------------------) address format.
* Introduces Script versioning to allow for easier soft-forks in the future for features such as SPV Fraud Proofs, [Schnorr signatures and Signature aggregation](https://bitcointechtalk.com/scaling-bitcoin-schnorr-signatures-abe3b5c275d1?source=post_page---------------------------) and [MAST](https://bitcointechtalk.com/what-is-a-bitcoin-merklized-abstract-syntax-tree-mast-33fdf2da5e2f?source=post_page---------------------------) which compress data and further aid on-chain scaling, and [Confidential Transactions](https://www.elementsproject.org/elements/confidential-transactions/investigation.html?source=post_page---------------------------).
* Makes covert [ASICBoost](https://blog.bitmex.com/an-overview-of-the-covert-asicboost-allegation-2/?source=post_page---------------------------) ineffective (though [some](http://www.truthcoin.info/blog/asicboost-worthless/?source=post_page---------------------------) dispute the relevance of ASICBoost in the first place).

**The following are arguments against SegWit:**

* [Some](http://thebitcoin.foundation/?source=post_page---------------------------) users prefer that Bitcoin developers change Satoshi's codebase as little as possible.
* SegWit and the Lightning Network do not solve the scaling debate because users will always have disagreements over how much it should cost to run a full node.
* SegWit technically used a mandatory extension block making it an "[Evil Fork](http://www.truthcoin.info/blog/forks-and-splits/?source=post_page---------------------------)" or "[Forced Fork](https://petertodd.org/2016/forced-soft-forks?source=post_page---------------------------#radical-changes)."
* Pushing the new Bech32 address format onto users invalidates the network effect that was built upon the original address format over the last nine years.
* It is technically possible for miners to censor SegWit transactions in an [anti-UASF](http://www.truthcoin.info/blog/uasf-contradiction/?source=post_page---------------------------) movement by not including any transactions involving SegWit inputs.
* Jihan Wu, the CEO of Bitmain which is the largest mining ASIC manufacturer, [called](https://twitter.com/JihanWu/status/868896110760181760?source=post_page---------------------------) SegWit transactions "unfairly cheap" due to the discount on witness data.

# Bitcoin Maximalism

There are different flavors of Bitcoin Maximalists, but they all believe that Bitcoin is the best and most secure blockchain which has the strongest network effect, most desirable monetary policy, and a highly-capable scripting language built which allows for future development.

Bitcoiners generally believe the idea of a 'token economy' reveals a deep misunderstanding of monetary systems as a whole and view [tokens as snake oil](https://nakamotoinstitute.org/mempool/appcoins-are-snake-oil/?source=post_page---------------------------). They strongly reject a future world of 10,000 currencies, seeing it as no different to barter — the very problem that money is supposed to eliminate. They believe that value accrues to the money held, not necessarily the one transacted with, and the long tail of 'tokens' will suffer from extremely high velocity, rendering them with little to no value accrual and serving as unnecessary friction even if abstracted away from the end user.

# Upper-Layer Systems and Alt-Coins

Many Bitcoiners view [alt-coins](https://nakamotoinstitute.org/mempool/the-problem-with-altcoins/?source=post_page---------------------------) as testing grounds for features that may eventually be integrated into Bitcoin if desirable by users.

It is theoretically possible to copy [almost any](http://www.drivechain.info/faq/index.html?source=post_page---------------------------) blockchain, even a giant block [one](http://www.truthcoin.info/blog/gigachain/?source=post_page---------------------------), and put it on a Bitcoin sidechain. Paul Sztorc's [Drivechain](http://www.drivechain.info/?source=post_page---------------------------) project, which is currently under development, would allow these blockchains to inherent Bitcoin's mining security, although it requires a soft-fork and is awaiting more extensive peer review.

There are three main categories of changes that would (likely) never be integrated into Bitcoin's base layer.

* Alternative **consensus mechanisms** to replace Nakamoto Consensus, such as Proof-of-Stake [(Tendermint](https://tendermint.readthedocs.io/en/master/introduction.html?source=post_page---------------------------#what-is-tendermint), Ethereum's [Casper,](https://arxiv.org/pdf/1710.09437.pdf?source=post_page---------------------------) DFINITY's [Threshold Relay](https://dfinity.org/pdf-viewer/pdfs/viewer?file=..%2Flibrary%2Fthreshold-relay-blockchain-stanford.pdf&source=post_page---------------------------)), Chia's [Proof-of-Space](https://eprint.iacr.org/2017/893.pdf?source=post_page---------------------------), EOS' [Delegated Proof-of-Stake](http://bytemaster.github.io/bitshares/2015/01/04/Delegated-Proof-of-Stake-vs-Proof-of-Work/?source=post_page---------------------------), Algorand's [Weighted Proof-of-Stake](https://eprint.iacr.org/2018/377.pdf?source=post_page---------------------------), or Ripple and Stellar's [Federated Byzantine Agreement](https://www.stellar.org/blog/stellar-consensus-protocol-proof-code/?source=post_page---------------------------).
* Alternative data structures to replace the **blockchain**, such as Coda's [succinct blockchain](https://codaprotocol.com/static/coda-whitepaper-05-10-2018-0.pdf?source=post_page---------------------------), DAGlabs and HashGraph's [DAG](https://www.daglabs.com/?source=post_page---------------------------), or Nano's [block-lattice](https://nano.org/en/whitepaper?source=post_page---------------------------).
* Alternative **governance mechanisms** to replace full node p2p network governance, such as [Decred](https://voting.decred.org/?source=post_page---------------------------) or [Tezos](https://tezos.com/?source=post_page---------------------------)' on-chain governance, DFINITY's [Blockchain Nervous System](https://medium.com/dfinity/the-dfinity-blockchain-nervous-system-a5dd1783288e?source=post_page---------------------------) AI governance, or Bitcoin Unlimited's [miners voting](https://www.bitcoinunlimited.info/solutions/miners?source=post_page---------------------------).

Bitcoiners generally take [issue](https://download.wpsoftware.net/bitcoin/pos.pdf?source=post_page---------------------------) with Proof-of-Stake (PoS) where validators propose and vote on blocks instead of solving energy-intensive cryptographic puzzles. They believe Bitcoin software should be handled with the [same respect as nuclear reactor software](https://medium.com/@hugonguyen/proof-of-stake-the-wrong-engineering-mindset-15e641ab65a2?source=post_page---------------------------), and discount PoS due to its "subjective" nature, which means participation in the network requires subjective information like social information. This contrasts to PoW objectivity where nodes necessarily arrive at the current state by observing the heaviest PoW chain.

Many view PoS as a digital version of the fiat-money system, with PoS validation being anti-competitive in comparison to mining and lacking any ties to real-world value (energy).

Meanwhile, PoS advocates have "[learned to love" weak subjectivity](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/?source=post_page---------------------------) and aim to simulate the security of PoW through threats of economic penalties for validators (slashing dishonest actors by taking away deposits) instead of burning physical energy. They deem PoW as energy wasteful, and think it's possible to design a PoS protocol that is more secure, decentralized, offers faster block times, and is more flexible than PoW, which is "limited" by physics.

In distributed systems terms, Nakamoto Consensus favors liveness (availability) over safety (consistency) and achieves probabilistic finality of transactions that increases with the number of new blocks.

Currently, with Casper's PoS, for example, economic finality is to be achieved once validators fully commit to a block and comes at the cost of some availability. Because finality requires some upper-bound synchrony [asumption](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-3-70fefb1182fc?source=post_page---------------------------), extraordinary events could theoretically partition a significant portion of the network or shut down the entire network for a greater amount of time than this upper-bound validator response time.

This could cause either some partitions to lack the majority of votes needed to come to consensus or the lack of ability for the network to choose a canonical chain when the partition or shut down ends. This could end with liveness or safety faults requiring human action, whereas with PoW, network partitions create temporary forks, which are necessarily resolved through the heaviest chain once the partition is resolved.

There is overwhelming consensus that there should be no experimentation and as little changes made as possible to the base BTC layer, and that payment channels and sidechains should not weaken the security of the base layer. Some users are enthusiastic about the potential of upper-layer systems to bootstrap further utility on Bitcoin.

The main philosophy is to have a hyper-decentralized, hyper-secure base layer that is used to bootstrap security for slightly more insecure protocols on top layers.

**Lightning Network**

Proponents of the Lightning Network consider it to be the most feasible solution to the current Bitcoin scalability problem, allowing people to transact nearly without limits using peer-to-peer payment channels and smart contracts, while using the _main_ Bitcoin chain for occasional settlement purposes.

Despite only being conceptualized three years ago, and only being in beta for several months, the Lightning Network is already seeing a wave of innovations, such as [Dual-Funded Channels](https://github.com/lightningnetwork/lightning-rfc/pull/184?source=post_page---------------------------), [Submarine Swaps](https://submarineswaps.org/?source=post_page---------------------------), Channel Splicing and Factories, Watchtowers, [Eltoo](https://blockstream.com/2018/04/30/eltoo-next-lightning.html?source=post_page---------------------------), Atomic Swaps, and more all covered [here](https://bitcoinmagazine.com/articles/future-bitcoin-what-lightning-could-look/?source=post_page---------------------------).

One common concern about second-layer solutions is that they will negatively impact miners revenue by taking more transactions off-chain. Initial [research](https://arxiv.org/pdf/1712.10222.pdf?source=post_page---------------------------), [presented](https://scalingbitcoin.org/stanford2017/Day2/HowToChargeLightning_ScalingBitcoin.pdf?source=post_page---------------------------) at Scaling Bitcoin 2017, estimated that miner revenue could increase after 20 million users were using the Lightning Network, although decrease under that threshold.

It is important to note that Lightning Network is an extremely new, unproven and immature system. However, many developers believe that it will greatly improve the scalability of Bitcoin and enable cheap micro-transactions, paving a way for Bitcoin to potentially be used as an effective medium of exchange and true global currency.

At the very least, Lightning Network occupies a niche, which will be valuable in itself. And at the most, we haven't even scratched the surface of the upside, potential, and capabilities enabled by the Lightning Network, such as third-layer projects.

***

# Conclusion

Bitcoin is the original, longest-lasting cryptocurrency with the highest levels of hashpower, network effects, liquidity, market capitalization, and arguably the highest amount of "HODLers of last resort." This article attempted to outline the so-called 'small blocker' and 'big blocker' positions on the most notable changes, milestones and debates throughout Bitcoin's past and its near-term future.

The open-source, global and decentralized nature of these digital money-forms makes the governance of these systems complex and even minor changes contentious and controversial. Almost 10 years into its history, Bitcoin and other cryptocurrencies as an asset class are beginning to challenge monetary metals as the defacto store of value assets of the future, as well as challenge existing global payment rails and mechanisms. We believe that the future is bright for Bitcoin and its spiritual brethren.
