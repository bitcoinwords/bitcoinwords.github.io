---
title: "The Bitcoin Risk Spectrum"
permalink: "/the-bitcoin-risk-spectrum" 

tags:
  - Nik Bhatia
  - CY18 Q3

excerpt: Part 3 of Nik Bhatia's 4 part Lightning Network thesis. This post looks at the bitcoin risk spectrum. Posted July 9, 2018.

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

# [The Bitcoin Risk Spectrum](https://medium.com/@timevalueofbtc/the-bitcoin-risk-spectrum-949f6abec290)
### [Nik Bhatia](https://medium.com/@timevalueofbtc)
### Posted July 9, 2018

1. [1/4 The Bitcoin Second Layer](https://medium.com/@timevalueofbtc/the-bitcoin-second-layer-d503949d0a06)
2. [2/4 The Time Value of Bitcoin](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2)
3. **[3/4 The Bitcoin Risk Spectrum](https://medium.com/@timevalueofbtc/the-bitcoin-risk-spectrum-949f6abec290)**
4. [4/4 The Lightning Network Reference Rate](https://cryptowords.github.io/the-lightning-reference-rate)

***

<br>


Bitcoin is already a reserve asset. It is the world's first true example of decentralized digital scarcity, and its elegant, predetermined supply schedule reinvents monetary policy. Its value is recognized by millions of people who own bitcoin as a savings vehicle, speculative investment, or currency hedge. Bitcoin is a reserve asset because millions of people own it as one. Its next step is to transition from a reserve asset to a functioning reserve currency by unlocking the bitcoin capital market. Lightning Network's arrival finally allows us to assign [time value to bitcoin](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2), and we can begin building bitcoin's capital market from first principles.

**Lightning Network**

HTLCs are financial agreements with two important properties that eliminate reliance on trusted third parties. Firstly, the contracts have an embedded call option on the counterparty's bitcoin which dissuades theft. Secondly, the contracts have an expiration, which prevents balances to be held in limbo to perpetuity. These two properties remove counterparty risk but instead introduce payment channel management risk. Routing Lightning payments is the equivalent of a short-term bitcoin lease and allows the router to earn fees; these fees can be used to calculate interest earned on bitcoin staked to Lightning payment channels.

**Traditional Capital Markets**

Traditional capital markets have a risk spectrum: generally speaking, higher variance of returns is positively correlated with a higher expected return. More risk, more reward. It is important to note that risk-free rates are entirely conceptual and theoretical. They are simply a matter of convention to facilitate financial theoretical research and improve communication. Therefore, this article is an attempt to discuss and derive bitcoin-native financial theory, including how bitcoin can be reconciled against other assets. Bitcoin is still trillions of dollars of market capitalization away from becoming a legitimate alternative to other deep capital markets like the ones denominated in US Dollars, Euros, Yen, Pounds, and Yuan. Before we dissect bitcoin's risk spectrum, let's take a look at that of the US Dollar to get a sense of which aspects bitcoin should copy and which it should reinvent.

**US Dollar Risk Spectrum**

Why is the US Dollar the world's reserve currency? There are many reasons including geopolitical and economic prowess, but one of the reasons is the depth of its capital market. There are over $100 trillion in bond and equity securities, allowing owners of US Dollars to easily find a home for them. Its capital market can be viewed as a risk spectrum, with risk on the x-axis and expected return on the y-axis.

![](/assets/images/cy18/cy18q3m7/nb-1.png){: .align-center}
US Dollar Risk Spectrum

The first point (illustrated) on the risk spectrum is US Treasury debt. Financial theory requires a risk-free asset to establish baseline interest rates, and currently that asset is US Treasuries. The obvious flaw of this financial theory is that US Treasuries are not truly risk-free. They have default risk, albeit appropriately characterized by market as the lowest possible default risk that an investor can attain. (Many sovereign bonds now have yields lower than yields in the United States, but those bonds are not denominated in US Dollars. This article is written only comparing bitcoin to the US Dollar).

The second point is corporate bonds. Companies issue fixed obligations at a spread to US Treasuries; for example, this year Walmart issued a 5yr bond at 5yr Treasuries plus 0.60% and General Motors issued a 5yr bond at 5yr Treasuries plus 1.37%. Each of these companies used the 5yr US Treasury as a reference rate. Investors consider the risk premium, or creditworthiness, of each company relative to Treasuries. We can see from this example that bond investors view Walmart as more creditworthy than General Motors because Walmart borrows at a lower spread to Treasuries. This is why reference rates are considered an anchor for debt capital markets, because they more easily allow for relative value comparisons.

Further along the risk spectrum are investments with higher risk profiles, such as publicly traded equities and venture capital funds. Theoretical formulas for the expected return on equities usually include a combination of the risk-free rate and the company's risk premium. Venture capital investors will seek an even higher return because the probability of principal loss is perceived to be higher than that of public equities. Theoretical risk premiums are added to each subsequent point of the risk spectrum, all anchored from the risk-free rate.

**Bitcoin Risk Spectrum**

Bitcoin's capital market should be designed from first principles because its final settlement does not require trusted third parties. Final settlement of the US Dollar has counterparty risk because deposits are considered a liability on banks' balance sheets. Holders of US Dollars would rather face the US government as a counterparty rather than banks, so they prefer to purchase US Treasuries with their deposits. Either way, the final settlement has counterparty risk. Additionally, the US Dollar itself depends on a single nation and has a single entity controlling monetary policy in a discretionary way; bitcoin avoids both of these risks. Let's take a look at Bitcoin's risk spectrum.

![](/assets/images/cy18/cy18q3m7/nb-2.png){: .align-center}
Bitcoin Risk Spectrum

The first point (illustrated) on Bitcoin's risk spectrum is bitcoin held in cold storage. The analogy commonly used for cold storage is a gold bar held in your hand. There is no counterparty risk; the risk is its storage and security, much like if you had possession of physical gold. Skilled storage and security practices make loss less likely, and the advent of robust multisignature solutions further reduces risk. Private key management anchors the bitcoin capital market much like the timeliness and consistency of the US government paying back its debt obligations anchor the US Dollar's capital market. The expected return on cold storage bitcoin is at best zero and is actually negative if you consider that storage costs and on-chain transaction costs are non-zero.

I am proposing that the second point on Bitcoin's risk spectrum should be [LNRR, the Lightning Network Reference Rate](https://medium.com/@timevalueofbtc/the-time-value-of-bitcoin-3807b91f02d2). Routing fees earned on bitcoin staked to Lightning payment channels can be expressed as an interest rate. The rates received on the payment channel or node level can be hashed and cryptographically provable. Node operators can opt-in to publish realized interest rates on their capital. If a consensus can be reached on an interest rate calculation protocol, capital providers can publish interest rates in an open and transparent way. Positive interest rates will attract bank-like entities that believe they can earn positive return using effective payment channel management and security techniques. Some bitcoin previously held in cold storage will seek the income attainable in Lightning Network, the first ever example of an opportunity cost tradeoff in bitcoin that doesn't require additional counterparty risk. Bitcoin staked to Lightning is the most unique income producing asset in all of monetary history: income with zero counterparty risk. The historical implications of this on capital markets are tremendous.

A huge leap in risk exists between the second and third point on Bitcoin's risk spectrum. The first two points, as we have established, have various security and management risks but no counterparty risk whatsoever. Real world lending of bitcoin has genuine counterparty risk, whether using exchange-based lending platforms or other forms of direct lending. In theory, these rates of borrowing should be higher than LNRR, and capital providers could use LNRR to make relative value decisions between bitcoin leasing via Lighting and off-chain bitcoin lending. Any real world lending will not have bitcoin's blockchain as security. Lenders will need strong contracts in jurisdictions with strong rule of law to ensure repayment of capital, just as they do with fiat currencies. Complete loss of principal remains.

**Conclusion**

I am increasingly optimistic that we are close to seeing Lightning Network wallets provide a way to calculate interest earned via routing fees. Lightning development is accelerating and the total bitcoin staked to payment channels is increasing accordingly. The time value calculations that we are on the verge of realizing will underpin the entire bitcoin capital market. It will not happen all of a sudden. Node operators will need to cryptographically prove interest earned over a long enough time horizon to attract larger sums of capital to Lighting Network. Wallet infrastructure and security both still need a lot of improvement, especially as UX leaves the command line and enters the GUI phase. I am eager and excited to hear from the Lightning community on how we can achieve the first step on the path to reserve currency: interest rate and time value calculations.
