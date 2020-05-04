---
title: "Bitcoin Stock-to-Flow Cross Asset Model"
permalink: "/bitcoin-stock-to-flow-cross-asset-model"

author: planb

tags:
  - PlanB
  - CY20 Q2
  - S2F
  - Valuation
  - Gold
  - Financial

excerpt: PlanB's part 3 of his series on Bitcoin valuation. Posted April 27, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin Stock-to-Flow Cross Asset Model](https://medium.com/@100trillionUSD/bitcoin-stock-to-flow-cross-asset-model-50d260feed12)
### By [PlanB](https://twitter.com/100trillionUSD)
### Posted April 27, 2020

<br>

>_"The important thing in science is not so much to obtain new facts as to discover new ways of thinking about it" - William Lawrence Bragg_

## Introduction

Bitcoin (BTC) Stock-to-Flow (S2F) model was [published in March 2019](https://medium.com/@100trillionUSD/modeling-bitcoins-value-with-scarcity-91fa0fc03e25) [1].

The original BTC S2F model is a formula based on monthly S2F and price data. Since the data points are indexed in time order, it is a time series model. This model has activated quantitative analysts around the world. Many have verified the non-spurious relationship between S2F and BTC price [2][3][4].

![](/assets/images/2020/m4/p1.png)
*Current S2F model*

If you are not familiar with the S2F model, I highly recommend reading the original article because it explains background and terminology.

In this article I solidify the basis of the current S2F model by removing time and adding other assets (silver and gold) to the model. I call this new model the BTC S2F cross asset (S2FX) model. S2FX model enables valuation of different assets like silver, gold and BTC with one formula.

First, I will describe the concept of phase transitions, because it introduces a new way of thinking about BTC and S2F. It explains why S2FX model is important.

Second, I will describe S2FX model, how it works and what the results mean.

## Phase Transitions

Phase transitions are an important perspective in understanding S2FX model. During phase transitions, things get totally different properties. Transitions are often discontinuous. Three examples of phase transitions are:

1.  Water
2.  US Dollar
3.  BTC

**Water** The classic example of phase transitions is water. Water exists in four different phases (states): solid, liquid, gas, ionized. It is all water, but water has totally different properties in each phase.

![](/assets/images/2020/m4/p2.png)

**US Dollar** Phase transitions are also present in finance. For example the US Dollar has transitioned from gold coin (One dollar = 371.25 grains of pure silver = 24 grains of gold), to paper backed by gold (“In gold coin payable to the bearer on demand”), to paper backed by nothing (“This note is legal tender for all debts, public and private”). Although we keep calling it Dollar, the Dollar has totally different properties in these three phases.

![](/assets/images/2020/m4/p3.png)

**BTC** Same is true for BTC. Nic Carter and Hasu show in their 2018 study how BTC narratives changed over time [5].

![](/assets/images/2020/m4/p4.png)
*[_How major Bitcoin narratives changed over time_](https://medium.com/@nic__carter/visions-of-bitcoin-4b7b7cbcd24c)*

These BTC narratives seem very continuous in the chart. However, if we combine the narratives with financial milestones (and later S2F and price data), they look very much like phases with more abrupt transitions:

1.  “Proof of concept” -> after Bitcoin white paper [6]
2.  “Payments” -> after USD parity (1BTC = $1)
3.  “E-Gold” -> after 1st halving, almost gold parity (1BTC = 1 ounce of gold)
4.  “Financial asset” -> after 2nd halving ($1B transactions per day milestone, legal clarity in Japan and Australia, futures markets at CME and Bakkt)

These three examples of phase transitions in water, US Dollar and BTC offer a new perspective on BTC and S2F. It is important to not only think in term of continuous time series but also in phases with abrupt transitions. In developing S2FX model, I see BTC in each phase as a new asset, with totally different properties. A logical next step is identifying and quantifying BTC phase transitions.

## BTC S2F Cross Asset (S2FX) Model

The chart below shows the monthly BTC S2F and price data points used in the original S2F model. One can visually identify four clusters.

![](/assets/images/2020/m4/p5.png)

These four clusters could indeed indicate phase transitions.

Quantifying these clusters can be done by minimizing distance between monthly BTC data and clusters. I use a genetic algorithm (minimizing absolute distance) to quantify four clusters. Future research could focus on different clustering algorithms (e.g. k-means algorithm).

![](/assets/images/2020/m4/p6.png)

Each of the four identified BTC clusters has a very different S2F-market value combination that seems to be consistent with halvings and changing BTC narratives.

1.  BTC “Proof of concept” (S2F 1.3 and market value $1M)
2.  BTC “Payments” (S2F 3.3 and market value $58M)
3.  BTC “E-Gold” (S2F 10.2 and market value $5.6B)
4.  BTC “Financial asset” (S2F 25.1 and market value $114B)

Like water and US Dollar these four BTC clusters represent four different assets, each with different narrative and characteristics. BTC "Proof of concept" with S2F 1.3 and only $1M market value is a totally different asset than BTC "Financial asset" with S2F 25 and $114B market value.

With the phase transition perspective of BTC clusters as different assets, I can now add other assets like silver and gold to the model. This makes it a real cross asset model. For silver and gold I use stock and flow numbers from recent analysis by Jan Nieuwenhuijs [7] and ultimo December 2019 prices from TradingView.

5. Silver S2F 33.3 and market value $561B
6. Gold S2F 58.3 and market value $10,088B

![](/assets/images/2020/m4/p7.png)

The chart shows the four quantified BTC clusters (plus the original BTC monthly data for context), silver and gold. They form a perfect straight line.

I use regression analysis to make the S2FX model. Note that a big difference with the original S2F model is that I use silver and gold S2F and market value data in the regression analysis. S2FX model shows a significant relationship between S2F and market value of these six assets (low p-Values F-test and low p-Values coefficients) with a perfect fit (99.7% R2).

![](/assets/images/2020/m4/p8.png)

The S2FX model formula can be used to estimate the market value of the next BTC phase/cluster (BTC S2F will be 56 in 2020–2024):

Market value = exp(12.7598) * 56 ^ 4.1167 = $5.5T.

This translates into a BTC price (given 19M BTC in 2020–2024) of $288K.

BTC price forecast is significantly higher than $55K in the original study. Please be aware that the S2FX model is a first step that has not yet been replicated and reviewed by others.

Note 1: Although six observations is low, nevertheless I value the results of the S2FX model relevant. Future research could focus on adding more assets to the analysis. However, most assets have low S2F values (≤1) and are therefore not interesting. On the contrary, diamonds have a high S2F but have a very complex valuation (rough/cut, carats, different colors and brightness etc).

Note 2: S2FX model allows for interpolation, instead of extrapolation in the original S2F model. The original S2F model makes a forecast that falls outside the data range used in making the model. The new S2FX model makes a forecast that falls within the data range used in deriving the formula.

![](/assets/images/2020/m4/p9.png)

Example of interpolation (left) and extrapolation (right) — data in blue, black line is model, red dot is forecast

## Conclusion


In this article I solidify the basis of the current S2F model by removing time and adding other assets (silver and gold) to the model. I call this new model the BTC S2F cross asset (S2FX) model. S2FX model enables valuation of different assets like silver, gold and BTC with one formula.

I have explained the concept of phase transitions. Phase transitions introduce a new way of thinking about BTC and S2F. It led me to the S2FX model.

S2FX model formula has a perfect fit to the data (99.7% R2).

S2FX model estimates a market value of the next BTC phase/cluster (BTC S2F will be 56 in 2020–2024) of $5.5T. This translates into a BTC price (given 19M BTC in 2020–2024) of $288K.

Solidifying known facts from the original S2F study, the S2FX model offers a new way of thinking about BTC transitioning into the fifth phase.

**Follow **[**PlanB@100trillionUSD**](https://twitter.com/100trillionUSD)

## References


[1] [PlanB@100trillionUSD](https://twitter.com/100trillionUSD), [_Modeling Bitcoin’s Value with Scarcity_](https://medium.com/@100trillionUSD/modeling-bitcoins-value-with-scarcity-91fa0fc03e25), Mar 2019

[2] [Nick Emblow](https://twitter.com/btconometrics), [_Falsifying Stock-to-Flow As a Model of Bitcoin Value_](https://medium.com/swlh/falsifying-stock-to-flow-as-a-model-of-bitcoin-value-b2d9e61f68af), Aug 2019

[3] [Marcel Burger](https://twitter.com/BurgerCryptoAM), [_Reviewing “Modelling Bitcoin’s Value with Scarcity”_](https://medium.com/burgercrypto-com/reviewing-modelling-bitcoins-value-with-scarcity-part-ii-the-hunt-for-cointegration-66a8dcedd7ef), Sep 2019

[4] [Mannuel Andersch](https://twitter.com/moneymanolis), [_Is Bitcoin outshining gold?_](https://www.bayernlb.com/internet/media/ir/downloads_1/bayernlb_research/megatrend_publikationen/megatrend_bitcoins2f_20190930_EN.pdf), Sep 2019

[5] [Nic Carter](https://twitter.com/nic__carter), [Hasu@Hasufl](https://twitter.com/hasufl), [_Visions of Bitcoin — How major Bitcoin narratives changed over time_](https://medium.com/@nic__carter/visions-of-bitcoin-4b7b7cbcd24c), Jul 2018

[6] [https://bitcoin.org/bitcoin.pdf](https://bitcoin.org/bitcoin.pdf) — Satoshi Nakamoto, 2008

[7] [Jan Nieuwenhuijs](https://twitter.com/JanGold_), [_How Much Silver Is Above Ground?_](https://www.voimagold.com/insight/how-much-silver-is-above-ground), Dec 2019


***

{% include signup.md %}
