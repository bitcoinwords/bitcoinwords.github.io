---
title: "The Lightning REference Rate"
permalink: "/the-lightning-reference-rate" 

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---

# The Lightning Network Reference Rate
### [Nik Bhatia](https://medium.com/@timevalueofbtc)
### Posted March 11, 2019

_The Lightning Network Reference Rate, Part 4 of 4_

![code](/assets/images/cy19q1/cy19q1m3/nik-1.png){: .align-center}

**Abstract**

I present a three part proposal for Lightning Network node operators. The first and most crucial part of the proposal is a node-level calculation standard for the accrual of satoshis. The Node Accrual Rate (NAR) is offered as a formula to calculate the profitability of an individual Lightning node, expressed as an annualized interest rate.

The second part of the proposal is to convince Lightning node operators to disclose their NARs to each other. Transparency and financial disclosure are core tenants of capital markets, and the disclosure of NARs could correspondingly push bitcoin forward on its path to becoming a more robust asset class.

The third and final part of the proposal is to advocate a framework in which NARs across the network can be aggregated, averaged, and reported as one rate called the Lightning Network Reference Rate (LNRR). LNRR can pave the way for a world of relative value calculations and be instrumental in the pricing of off-chain bitcoin lending.

This is not a proposal for any changes to Lightning Network itself, nor a call for all nodes to share fee accrual data. Nodes will elect for themselves whether or not to share data, and most will likely choose not to do so. The formula is merely a suggestion for developers trying to capture the economics of payment routing.

**The Time Value Layer**

The Lightning Network sets up a framework from which we can calculate the time value of bitcoin. Interest rate calculations must have three known inputs: principal, income, and time. In Lightning terms, a node opens channels with other nodes and broadcasts the channel opening, essentially locking up principal for a predetermined amount of time. Assuming incoming channels are also opened to the node, the node is now positioned to route payments and charge fees for doing so. These routing fees can be considered income. The ending calculation can be expressed in many ways, but through time node participants will elect standards around which to coalesce. This proposal is a starting place for the discussion around these standards. If multiple standards emerge, I would view this as a positive development because competing calculation standards would foster deeper study of Lightning Network routing economics.

Lightning Network is also an optionality layer. Optionality is relevant to Lightning because it serves to offset one of the primary risks undertaken by Lightning node operators: malicious counterparty risk. Nodes carry the risk of their channel counterparts broadcasting a previous channel state, but this risk is theoretically negated by embedded call options which become executable upon malicious activity. The settlement optionality simultaneously serves as a security enforcement mechanism and a velocity accelerant.

**Proposal #1: Node Accrual Rate**

I propose the idea of a Node Accrual Rate (NAR) for individual Lightning nodes that desire a standardized method for calculating their realized interest rates. Nodes should be able to automatically calculate their rate of return on capital allocated to facilitate Lightning Network payment routing. Rates can be calculated by querying observable data available in their lnd, c-lightning, or Eclair clients. The following is a proposal for one way to calculate the rate using a generic formula for compounding interest and adapting for block time. The node data can be sliced and diced dozens of logical ways, and I look forward to many counterproposals that are sure to include innovative ways to capture return data.

_NAR = [(p+f)/p]^(52,560/n)-1_

Let _n_ = the measurement period, expressed in number of blocks, suggested minimum value of 100

Let _p_ = node's average balance held in channels over the measurement period, expressed in satoshis

Let _f_ = total routing fees earned by the node over the measurement period, expressed in satoshis

_52,560_is the approximate number of blocks per year to normalize NAR as an annualized rate

_n_:

The suggested 100 block minimum measurement period is arbitrary but matches the minimum block time before mining rewards become spendable. Said another way, your Lightning node should be active a certain number of blocks in order to reasonably measure an annualized rate of return. I believe this minimum can be increased to cover at least one full difficulty adjustment period of 2,016 blocks once routing activity becomes more commonplace. A longer minimum measurement period would make for higher quality and less noisy data.

_p_:

The average balance of a node throughout time can be measured a multitude of ways. Striking channel balances upon each new block confirmation and then averaging these amounts over the measurement period could be a clean and impartial way to determine _p_.

_f_:

Lightning Network node operators are already sharing _f_ with each other. I've seen numerous " _day_fee_sum"_screenshots on Twitter with positive integers next to them. Accelerated adoption of the Lightning Network over the past few months brought time value to bitcoin in a trustless way, and nodes are earning sats as a result. Node operators already sharing _f_ with each other will soon be calculating and sharing their NARs as well.

**Proposal #2: Disclosure of NARs**

Lightning node operators currently volunteer information about collecting routing fees, managing payment channels, and other emergent routing techniques. In a similar way, I anticipate and strongly encourage nodes to volunteer their NARs. Sharing NAR data is an easy way to display profitability to other capital market participants. The exchange of profitability information is a foundational tenant of capital markets; the widespread exchange of NAR data between nodes would accordingly bring long term health to bitcoin's capital market. Node operators are already disclosing the small amount of sats they've earned by routing payments through the Lightning Network, leading me to believe that such NAR exchanges will be commonplace for nodes motivated by profit or by transparency. Some nodes will look to attract capital in order to leverage their newfound skill set, even though most nodes will not be motivated to share data. Some nodes will be dishonest about their NAR, and the market will have to identify fraudulent disclosures just as forensic accountants dissect every disclosure from publicly traded corporations.

Advertising profitability, even if unaudited, will attract capital looking for return. Example: a Lightning node with sufficient capital and well positioned inbound and outbound payment channels earns a NAR (annualized return) of 0.25%. Funded with 10 million sats (0.1 bitcoin/~$400), the node earns about 957 sats (~$0.04) in one difficulty adjustment period (2,016 blocks/~2 weeks). The implications of being able to earn sats without relinquishing control of private keys is truly a monumental arrival for bitcoin in capital market terms, no matter how tiny the amount of interest may seem.

The node operator can choose to leverage its profitability by advertising a historical rate of return. The node from the example promises depositors a rate of return of 0.15% because a 0.25% return on routing would ensure a positive profit margin. The investor takes counterparty risk because the node could instantaneously exit scam with the depositor's money or simply fail to deliver on its promise to pay a rate of 0.15% on invested capital. The node, however, is instead motivated by creating a strong reputation as a counterparty and repays all depositors the promised rate to establish creditworthiness and increase the potential for additional deposits. The routing income accrues to the node in a trustless way, but the depository relationships occur entirely off-chain in trusted counterparty situations. The bitcoin era Lightning Network bank, without barrier to entry, available to anybody with the appropriate hardware and software, has arrived. Many will route, profit, succeed, raise deposits, fail, mislead, overpromise, and default, all essential components to a healthy and functioning capital market.

**Proposal #3: Lightning Network Reference Rate**

Lightning Network transitions bitcoin to a more capital market oriented asset. Hashed Timelock Contracts (HTLCs) combine some of the protocol's most powerful features into a standardized financial agreement with defined optionality and expiry, allowing participants in the Lightning Network confidence to transact bitcoin without the burden of continuously auditing individual clauses. In theory, the HTLCs in Lightning Network provide bitcoin with its own native risk-free asset, which is a theoretical term in traditional finance used to describe the asset bearing the lowest possible risk within an investment universe. The US Treasury's obligations carry this label in US Dollar capital markets, and like bitcoin held in Lightning payment channels, have materially less risk than other counterparties. Bitcoin held in Lightning payment channels should serve as a low-risk alternative to off-chain lending and can be used as a reference transaction by which to measure risk premium.

If Lightning node operators around the world disclosed enough NAR data to establish a statistically significant average, this average rate could serve the purpose of offering the bitcoin capital market an accurate measure of low-risk time value. Example: hundreds of nodes disclose NARs, and a cluster of rates is observed around 0.18%. The rate can be a cluster, average, or median of publicly disclosed NARs taken each block or daily, and the end result would be a reference rate widely disseminated to all Lightning Network participants. The Lightning Network Reference Rate (LNRR) can be a very powerful signal that bitcoin has a native time value, a rate that risky off-chain lending should theoretically exceed. If LNRR is equal to 0.18%, an exchange offering 6% on deposits is actually offering a rate of LNRR+5.82%. LNRR represents the time value of the transaction and 5.82% represents its risk premium.

Investors can lend money to the US Treasury at 2.5%, or they can lend to investment grade (IG) corporations at Treasuries plus 1% or junk grade (HY) corporations at Treasuries plus 4%. Investors don't look at the IG and HY companies as investment opportunities yielding 3.5% and 6.5%; they strip away the Treasury component (time value of the US Dollar) to determine relative value between credit spreads. The Lightning Network Reference Rate can and should serve a similar function in bitcoin capital markets. Exchanges wouldn't be offering deposit rates at 6% or 8.5% but instead at LNRR+5.82% or LNRR+8.32%.

**Reserve Currencies**

Reserve currencies need deep and liquid capital markets. Investments denominated in bitcoin exist only on a small scale, largely because bitcoin is still mostly a commodity and costs resources to store and use as opposed to other assets that accrue positive time value. Lightning Network officially switches the equation for bitcoin but is still a nascent technology. For bitcoin to continue its journey toward becoming a world reserve currency, theoretical financial frameworks such as time value, risk premium, and optionality have to evolve but without relying too heavily on legacy ideas and ideals. The primary reason for this proposal is to offer an opportunity for bitcoin to capture relevant characteristics from traditional capital markets and transform them into native and emergent bitcoin financial theory.

**Further Reading**

This is the fourth and final article in the series titled The Lightning Network Reference Rate. Please check out Part 1, "[The Bitcoin Second Layer](https://medium.com/@timevalueofbtc/the-bitcoin-second-layer-d503949d0a06)," Part 2, "[The Time Value of Bitcoin](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2)," and Part 3, "[The Bitcoin Risk Spectrum](https://medium.com/@timevalueofbtc/the-bitcoin-risk-spectrum-949f6abec290)."

Follow me on Twitter at [https://twitter.com/timevalueofbtc](https://twitter.com/timevalueofbtc)
