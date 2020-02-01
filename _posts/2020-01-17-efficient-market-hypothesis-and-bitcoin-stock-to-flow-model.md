---
title: "Efficient Market Hypothesis and Bitcoin Stock-to-Flow Model"
permalink: "/efficient-market-hypothesis-and-bitcoin-stock-to-flow-model" 

author: planb

tags:
  - PlanB
  - 2020 Q1
  - EMH
  - Stock to Flow
  - Indicator
  - Financial Analysis
  - Finance
  - Pricing
  - S2F
  - Money
  - Value

excerpt: PlanB explains that Stock to Flow is priced in and supported by the EMH. Posted January 17, 2020

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Efficient Market Hypothesis and Bitcoin Stock-to-Flow Model](https://medium.com/@100trillionUSD/efficient-market-hypothesis-and-bitcoin-stock-to-flow-model-db17f40e6107)
### By [PlanB](https://twitter.com/100trillionUSD)
### Posted January 17, 2020

![](/assets/images/2020/m1/pb1.png)
*Would you pick up that bitcoin or follow EMH?*

_Signature: HwdQggZNa6LBEI8XB+yrDWKNQGALYiFT0X745UoGXAuHefm0bXG70cYYPAHNe1tX/K3/z75J0aQjkl4zXZHL7Eo= Message: Efficient Market Hypothesis and Bitcoin Stock-to-Flow Model Address: 1PRoNLcWHzM8DuKpGE4YM9hb1PjSEnWRpn_

## Introduction

[Bitcoin Stock-to-Flow (S2F) model](https://medium.com/@100trillionUSD/modeling-bitcoins-value-with-scarcity-91fa0fc03e25) was published in March 2019 [\[1\]](https://medium.com/@100trillionUSD/modeling-bitcoins-value-with-scarcity-91fa0fc03e25). The model has been well received by bitcoiners and investors. Many analysts have verified the cointegrated S2F model and confirmed bitcoin price forecasts \[2\]\[3\]\[4\].

The S2F model also received critique. The best steel man argument against the model comes from the Efficient Market Hypothesis (EMH). The argument states that the model is based on publicly available information (S2F, bitcoin's supply trajectory) and therefore the analysis and conclusion must be already priced in.

In this article I share my point of view on S2F model and EMH. I analyze arbitrage opportunities, risk & return model and derivatives markets.

## Stock to Flow Model

S2F model was published as a bitcoin valuation model, inspired by Nick Szabo’s concept of unforgeable scarcity and Saifedean Ammous’ analysis of S2F \[1\]\[5\]\[6\]. S2F is a measure of scarcity. The power law relation between S2F and bitcoin price over time captures the underlying regularity of bitcoin’s complex dynamic system of network effects as described by Trace Mayer \[7\].

S2F model is a power law function fitted on Oct 2009 —Feb 2019 _monthly_ data: BTC price =0.4*S2F ^3 (where S2F=1/inflation rate). A later model on 2009–2019 _yearly_ data has higher forecasts: BTC price =0.18*S2F ^3.3

![](/assets/images/2020/m1/pb2.png)

Nick Phraudsta was the first to verify (or better “not falsify”) the S2F model, and he added cointegration analysis, indicating that the correlation is likely not spurious \[2\]. Marcel Burger verified both S2F model and cointegration, with several addition statistical tests\[3\]. Manuel Andersch was the first institutional investor (BayernLB) to verify S2F model and cointegration \[4\].

## Efficient Market Hypothesis

EMH is a well known theory in financial economics. EMH is based on ideas of Friedrich Hayek (1974 Nobel prize) and others. According to Hayek markets are information processing systems, delivering the best possible price discovery \[8\].

EMH is formally described by Eugene Fama (2013 Nobel prize) and comes in three flavors \[9\]:

1.  Weak EMH: historical price data is already priced in and cannot be used to make profits. Technical Analysis (TA) and Time Series Analysis (TSA) do not work.
2.  Semi-strong EMH: public news from media outlets like MSNBC, Bloomberg, WSJ and research companies is already priced in and cannot be used to make profits. Fundamental Analysis (FA) does not work.
3.  Strong EMH: even inside information can not be used to make a profit, because _all_ information is already priced in.

Most investors and economists agree that modern financial markets are reasonably efficient (i.e. they accept weak and semi-strong EMH), however they reject strong EMH.

Following EMH, S2F model should be priced in, because it is based on publicly available data (S2F).

## Risk & Return

To be honest, I have never used EMH directly in my 20+ years experience as an institutional investor managing a multi-billion Euro balance sheet. In practice we _assume_ EMH, and _use_ a risk & return model.

### Assuming EMH

Some people argue that bitcoin markets are not efficient, but I do not agree. In the old days you could buy bitcoin at one exchange in USD and sell it shortly afterwards at another exchange in EUR or JPY and convert it back to USD at a profit, arbitrage was possible. Those days are gone, as the table below shows (13 Jan 2020, 20:00 GMT prices):

_BTCUSD = 8100 BTCEUR = 7300 BTCUSD/BTCEUR = 8100/7300 = 1.11 EURUSD = 1.11_

_BTCJPY = 885.000 BTCJPY/BTCUSD = 885.000/8100 = 109 USDJPY = 109_

Perhaps there is still some money to be made with big computers, fast communication lines and high-frequency trading (HFT) algorithms, but there are no easy arbitrage opportunities.

We can safely assume that the $150B bitcoin market with $10B daily transactions is reasonably efficient.

### Risk & Return Model

Assuming EMH does not mean that you can not make money. You just have to take risk. EMH and non arbitrage lead us to risk & return models.

Harry Markowitz (1990 Nobel prize) introduced an early risk & return model with his famous Portfolio Theory (PT)\[10\]. William Sharpe (1990 Nobel prize) published his well known Capital Asset Pricing Model (CAPM)\[11\]. According to Markowitz and Sharpe all returns can be explained by risk.

This is a simplified risk & return model (without correlation or exotic math):

![](/assets/images/2020/m1/pb3.png)

Bond, Gold, Stocks: 1955–2019 data. Bitcoin: 2009–2019 data.

It is crucially important to understand this chart, so let's dive into it.

The x-axis of this chart is risk (maximum annual loss) and the y-axis is return (average annual return).

The chart shows three classic assets: bonds, gold and stocks. Bonds have the lowest risk 8% and the lowest return 6%. Gold has higher risk 33% and higher return 7.5%. Stocks have the highest risk 40% and the highest return 8%.

Key insight is that returns can be explained by risk alone, consistent with EMH. If you encounter an asset above the line, a first reaction could be that it is a great investment opportunity. A better reaction (from an EMH and non arbitrage point of view) would be that it is too good to be true. We are probably missing risks (or have miscalculated risk) and should try to bring the asset back on the line. Quantifying risk (volatility) is difficult, and indeed the expertise of quants of financial institutions. If an investor calculates that risks are lower than the market prices in, and if he exactly knows why the asset is above the line, then and only then should he decide to invest.

Bitcoin is literally "off the chart": 200% return, 80% risk. Because I can not plot it on the chart, I resized it to a 1% bitcoin plus 99% cash investment. This bitcoin investment is far above the line: 8% return, 1% risk (note that you can't lose more than 1%, even if bitcoin drops 99%, because you only invest 1%). So my first reaction is: the market sees risks that are not in the data. Here is a list of some possible risks:

*   Risk that bitcoin dies
*   Risk of governments making bitcoin illegal and prosecuting developers
*   Risk of fatal software bugs
*   Risk of exchange hacks
*   Risk of 51% attacks by centralized miners
*   Risk of miner death spiral after halving
*   Risk of hard forks

From an EMH and risk & return perspective, all these risks should be in the price data. But these risks are not in the data. According to EMH and the risk & return formula in the chart, 1% risk should give 5.5% + 6.2% * 1% = 5.6% return. And the data shows that 1% bitcoin + 99% cash had 8% return last 11 years.

It seems that these risks have been overestimated by the market, and that bitcoin really was a great investment opportunity, in line with S2F model.

### Derivatives markets

Let's look at what derivatives markets are telling us about the future.

Option markets show no spike at or after next halving:

![](/assets/images/2020/m1/pb4.png)

Source: [https://twitter.com/skewdotcom](https://twitter.com/skewdotcom)

Same story for futures market: slightly higher prices in the future, but no spike at or after the halving, indicating nothing special will happen at the halving:

![](/assets/images/2020/m1/pb5.png)

Source: [https://www.theice.com/products/72035464/Bakkt-Bitcoin-USD-Monthly-Futures/data?marketId=6137544](https://www.theice.com/products/72035464/Bakkt-Bitcoin-USD-Monthly-Futures/data?marketId=6137544)

This is interesting because S2F model forecasts much higher prices after the halving. How should we interpret this?

I think the simple answer is that the market currently overestimates future risk, like it overestimated risk the last 11 years. The efficient bitcoin market not only discounts the fundamental value of scarcity (S2F model), but also all these risks:

![](/assets/images/2020/m1/pb6.png)

*   42% of investors see bitcoin futures as the biggest risk (whales and governments manipulating the price of bitcoin with 'paper bitcoin', spoofing and wash trades).
*   16% still fears miner capitulation after the halving.
*   15% fear selling pressure from scams.
*   I know from discussions with institutional investors that their biggest fear is government making bitcoin illegal.
*   Another risk frequently mentioned by institutional investors is "the next bitcoin", a new (government/central bank backed) coin replacing bitcoin.

Note that without all these risks bitcoin’s value would be much higher, possibly in line with S2F model.

As time progresses, some of these risks will not materialize and disappear from the list. Take miner capitulation for example. I do not think miner capitulation is a big risk, but 15% of investors thinks it is. If hashrate does not decrease after the next halving, the risk of miner capitulation disappears and bitcoin price will rise because the risk is gone.

## Conclusion

Bitcoin S2F model was introduced in March 2019 and verified by many others.

EMH implies that S2F and the model forecasts should be already priced in by the market, because S2F model uses publicly available S2F data.

Current bitcoin markets are indeed reasonably efficient because easy arbitrage opportunities are not possible.

Historical risk & return data of bonds, gold, stocks and bitcoin, shows that bitcoin markets overestimated risk. Bitcoin return was not in line with risk, but very much in line with S2F model. Bitcoin options and futures markets do not expect rising prices at or after next halving. It is possible that markets still overestimate future risks.

My conclusion is that bitcoin markets are indeed reasonably efficient and price in S2F model, but also overestimate risk. Therefore, I prefer using S2F model over a classic risk & return model to forecast future bitcoin price.

So I assume EMH _and_ I would definitely pick up that bitcoin!

## References

\[1\] [PlanB@100trillionUSD](https://twitter.com/100trillionUSD), [_Modeling Bitcoin’s Value with Scarcity_](https://medium.com/@100trillionUSD/modeling-bitcoins-value-with-scarcity-91fa0fc03e25), Mar 2019

\[2\] [Nick@phraudsta](https://twitter.com/phraudsta), [_Falsifying Stock-to-Flow As a Model of Bitcoin Value_](https://medium.com/swlh/falsifying-stock-to-flow-as-a-model-of-bitcoin-value-b2d9e61f68af), Aug 2019

\[3\] [Burger@BurgerCryptoAM](https://twitter.com/BurgerCryptoAM), [_Reviewing “Modelling Bitcoin’s Value with Scarcity”_](https://medium.com/burgercrypto-com/reviewing-modelling-bitcoins-value-with-scarcity-part-ii-the-hunt-for-cointegration-66a8dcedd7ef), Sep 2019

\[4\] Mannuel Andersch (BayernLB), [_Is Bitcoin outshining gold?_](https://www.bayernlb.com/internet/media/ir/downloads_1/bayernlb_research/megatrend_publikationen/megatrend_bitcoins2f_20190930_EN.pdf), Sep 2019

\[5\] Nick Szabo, [_Bit Gold_](https://unenumerated.blogspot.com/2005/12/bit-gold.html), 2008

\[6\] Saifedean Ammous, [_The Bitcoin Standard: The Decentralized Alternative to Central Banking_](https://www.amazon.com/gp/product/1119473861/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1119473861&linkCode=as2&tag=saifedean-20&linkId=553d55d8f25cbfc8923c63ea38d2c1d4), 2018

\[7\] Trace Mayer, [_The Seven Network Effects of Bitcoin_](https://nakamotoinstitute.org/mempool/the-seven-network-effects-of-bitcoin/), 2015

\[8\] Friedrich Hayek, [_The Use of Knowledge in Society_](https://www.kysq.org/docs/Hayek_45.pdf),1945

\[9\] Eugene Fama, [_Efficient Capital Markets: A Review of Theory and Empirical Work_](http://www.bu.edu/econ/files/2011/01/Fama1.pdf), 1970

\[10\] Harry Markowitz,[_Portfolio Selection_,](http://onlinelibrary.wiley.com/doi/10.1111/j.1540-6261.1952.tb01525.x/full) 1952

\[11\] William Sharpe, [_Capital Asset Prices: A Theory of Market Equilibrium under Conditions of Risk_](http://efinance.org.cn/cn/fm/capital%20asset%20prices%20a%20theory%20of%20market%20equilibrium%20under%20conditions%20of%20risk.pdf), 1964

***

{% include signup.md %}