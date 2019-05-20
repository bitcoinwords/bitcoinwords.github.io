---
title: "The Time Value of Bitcoin"
permalink: "/the-time-value-of-bitcoin" 

tags:
  - Nik Bhatia
  - CY18 Q2

excerpt: Part 2 of a 4 part series, Nik Bhatia's thesis on the Lightning Network. In this post he explains the time-value of bitcoin. Posted June 8, 2019.

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

# [The Time Value of Bitcoin](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2)
### By [Nik Bhatia](https://medium.com/@timevalueofbtc)
### Posted June 8, 2018

1. [1/4 The Bitcoin Second Layer](https://cryptowords.github.io/the-bitcoin-second-layer)
2. **[2/4 The Time Value of Bitcoin](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2)**
3. [3/4 The Bitcoin Risk Spectrum](https://medium.com/@timevalueofbtc/the-bitcoin-risk-spectrum-949f6abec290)
4. [4/4 The Lightning Network Reference Rate](https://cryptowords.github.io/the-lightning-reference-rate)

***

<br>

![](/assets/images/cy18/cy18q2m6/nb-1.png){: .align-center}

**tl;dr**

The HTLCs in Lightning Network give bitcoin a path to become a global reserve currency.

**Abstract**

Lightning Network provides a framework to measure the time-value of bitcoin, a precursor for a capital market and reserve currency status. Observable variables in Hashed Time Locked Contracts can be used to calculate the interest rate received on bitcoin held in payment channels, allowing investors to measure their opportunity cost of capital. Lightning Network wallet software should include ways to calculate interest and prove the rate received in a trust-minimized way. A reference rate should be developed akin to US Dollar LIBOR, using consensus to dictate how the rate is calculated. This reference rate can anchor off-chain bitcoin lending into the global economy, leading to bitcoin-denominated banks, credit ratings, debt capital markets, and eventually an entire financial system: a path toward status as a global reserve currency.

**Calculation Method**

Three observable variables are needed to calculate an interest rate: principal, cash flows, and time. In Lightning Network, the principal is the amount of bitcoin in a payment channel; cash flows are routing fees; time is the block-time in which the fee collection is measured. Wallet implementations should experiment with different interest rate calculation methods with the eventual goal of a consensus method. The US Dollar has Treasuries, Fed Funds, LIBOR, OIS, and SOFR all acting as reference rates within the capital market for lending, borrowing, and swapping cash flows. Bitcoin needs to establish a reference rate of its own, referred to in this writing as LNRR (Lightning Network Reference Rate).

There are many possible ways to calculate LNRR. Principal may be measured once per block or using an average over time. Fees may be measured for individual HTLCs, individual payment channels, or Lightning Network nodes with multiple channels. Block-time may be measured by the locktime of HLTCs or measured one block at a time. Compounding conventions may be discrete or continuous. On-chain fees paid to open and close channels may be included or excluded in the calculation. We need to experiment with calculation methods because bitcoin is an entirely new asset class and shouldn't adhere to financial conventions of the past, even though traditional fixed income markets set the bar extremely high for financial sophistication.

**Time-value of bitcoin**

Fees, time-value, and security risk premiums are discussed in the _The Bitcoin Lightning Network: Scalable Off-Chain Instant Payments_ by Joseph Poon and Thaddeus Dryja:

_The_ **_time-value of fees_** _pays for consuming time (e.g. 3 days) and is conceptually equivalent to a gold lease rate without custodial risk; it is the time-value for using up the access to money for a very short duration._

_Historically, one of the largest component of fees and interest in the financial system are from various forms of counterparty risk — in Bitcoin it is possible that the largest component in fees will be derived from_ **_security risk premiums_** _._

Fees in Lightning Network can be attributed to two components, time-value and security risk premium. Fees compensate the leasing of bitcoin which translates into **time-value**. Positive interest rates should attract capital and competition. But Lightning Network node operators investing capital are not doing so purely risk-free. They are taking on a variety of risks, most notably the risk of using hot wallets to stake liquidity to the network. Therefore, interest rates will vary between nodes due to different security practices, captured here by the catch-all variable **security risk premium**.

_r = time-value + security risk premium_

**Lightning Banks**

Lightning Network will birth Lightning banks. Their first function will be to provide liquidity to Lightning Network by funding payment channels. They will try to position themselves as central routing hubs, capturing as many fees as possible. Competition will be open and fierce. Those with the greatest ability to efficiently manage payment channels and actively optimize routing positioning will profit.

**Reference Rate**

LIBOR was originally intended as an inter-dealer interest rate, however market conditions and manipulation scandals have significantly changed its role. Despite its evolution, LIBOR's model could serve as an example for LNRR to follow. The calculation method for LIBOR is essentially a panel: banks are asked to submit rates and these rates are aggregated to form a reference rate published once a day. Lightning banks can publish their interest rates to each other in order to foster a dealer community similar to the LIBOR panel banks. Any node that can publish an interest rate can potentially contribute to LNRR, and ideally all interest rates that are published would be cryptographically provable by all participants to assure complete transparency.

Once Lightning banks establish LNRR, they can reference this rate and charge a spread for loans that are not secured by the Bitcoin blockchain. They can use the reference rate to attract deposits which would also not be secured by the blockchain. While off-chain, trusted, bitcoin denominated capital market activity does not benefit from Bitcoin's immutability, it is essential for the establishment of bitcoin as a currency capable of global economic activity. Economic activity requires a tradeoff between time preferences which can only be achieved when savers are allowed to lend capital.

**Conclusion**

LNRR is not some magic solution. This paper is a suggestion to the Lightning developer community to start experimenting with the translation of HTLCs to a financial framework. We cannot go from Trace Mayer's sixth network effect of financialization to the seventh network effect of reserve currency status without the correct financial tools. Bitcoin has already emerged as a new asset class and is now acting as a reserve asset for millions around the world. Transitioning from reserve asset to reserve currency will present a challenging path. Ideas like LNRR should be discussed and explored so that we can continue to push bitcoin forward as the world's best abstraction of money.

Follow me at https://twitter.com/timevalueofbtc

**Sources**

Bitcoin: A Peer-to-Peer Electronic Cash System by Satoshi Nakamoto

[https://bitcoin.org/bitcoin.pdf](https://bitcoin.org/bitcoin.pdf)

The Bitcoin Lightning Network: Scalable Off-Chain Instant Payments by Joseph Poon and Thaddeus Dryja

[https://lightning.network/lightning-network-paper.pdf](https://lightning.network/lightning-network-paper.pdf)

Mastering Bitcoin 2nd Edition — Programming the Open Blockchain by Andreas M. Antonopoulos

[https://github.com/bitcoinbook/bitcoinbook](https://github.com/bitcoinbook/bitcoinbook)

CRYPSA event with Trace Mayer

[http://www.bitcoin.kn/2015/06/crypsa-event-with-trace-mayer/](http://www.bitcoin.kn/2015/06/crypsa-event-with-trace-mayer/)
