---
title: "Chasing fake volume: a crypto-plague"
permalink: "/chasing-fake-volume-a-crypto-plague"

author: sylvainartplayribes

tags:
  - Sylvain 'ArtPlay' Ribes
  - 2018 Q1
  - Money
  - Inflation
  - Politics

excerpt: "Chasing fake volume: a crypto-plague. Posted March 10, 2018."

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Chasing fake volume: a crypto-plague](https://medium.com/@sylvainartplayribes/chasing-fake-volume-a-crypto-plague-ea1a3c1e0b5e)
### By Sylvain 'ArtPlay' Ribes
### Posted March 10, 2018

*In this piece I will expose why I believe more than $3 billion of all cryptoassets’ volume is fabricated, and how OKex, #1 exchange rated by volume, is the main offender with up to 93% of its volume being nonexistent. I’ll endeavour to prove it by analyzing publicly available data.*

When I set out to datamine for this piece, I had no idea I would end up talking about fake volume.

I initially meant to gather data about cryptoassets liquidity, that could be a complement to volume. I thought it would prove an interesting indicator when assessing the value of an asset.

I decided my metric of choice would be to collect orderbooks from all major exchanges, and to measure how badly market selling $50k USD worth of each cryptocurrency would crash the price. Throughout this article, I will refer to this number as “slippage” (see the annex for a proper definition). I would later refine my slippage metric by selling more or less on each exchange depending on the volume they processed, and changing the sold amount with regards to the currency market cap.

I expected that slippage should generally be a decreasing function of volume, but that some differences might show from one currency to another. After all, if you have a gargantuan volume on a given pair, there has to be a very high competition between market makers to satisfy the avid buyers and sellers. And that kind of competition is bound to densify orderbooks and reduce spreads.

Right?

Well… it turned out this was the obvious tendency, yes. But where I had expected mild differences between currencies, I found ridiculously massive discrepancies between *exchanges*. Not the kind that can be easily hand-waved away (“*oh well, their users must behave differently*”), but the kind that can only be explained by some figures being overstated as much as 95%.

Leading the pack is OKex, currently ranked #1 exchange by volume with $1.7b total volume on both [CoinMarketCap](https://coinmarketcap.com/)and [LiveCoinWatch](https://www.livecoinwatch.com/)websites.

#### **OKex is a ghost town**

A bit of wash trading and artificial volume inflation is to be expected in a thoroughly unregulated market. What I did not expect was the magnitude of the fraud. Consider the following chart:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague1.png)

*Slippage = f(Volume), OKex, Kraken, Bitfinex, GDAX*

It’s a representation of the average slippage and volume of all pairs among a selection of a score of cryptocurrencies with a daily volume over $100k over four major exchanges: OKex, Kraken, Bitfinex and GDAX, over the course of 24 hours.

Orange, dark blue and light blue dots are respectively GDax, Bitfinex and Kraken.

Red dots are OKex.

You may for example read that the orange dot at the bottom right represents a GDAX pair, with a volume close to $200m, and a slippage of less than 0.1%

The chart is striking. It shows how, although all first three exchanges seem to behave rather similarly, OKex pairs all have a massively higher slippage with regards to their volume. Like I explained before, this can only mean that most of the volume OKex claims is completely fabricated.

Besides, for legibility’s sake, I elected to remove from the dataset all slippage data over 4%. Reintroducing the ignored data paints an even more absurd picture of OKex traffic, and requires a logarithmic scale:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague2.png)

*Slippage = f(Volume), OKex, Kraken, Bitfinex, GDAX — log scale*

Many pairs, albeit boasting up to $5 million volumes, would cost you more than 10% in slippage, should you want to liquidate a mere $50k in assets. Those pairs included, at the time of the data parsing (06/03/18): NEO/BTC, IOTA/USD, QTUM/USD. Hardly illiquid or low-profile assets.

Although those numbers alone prove to me without the shadow of a doubt that a suffocating majority of OKex volume is fake, I had not witnessed first-hand how they implemented it. I thus logged into their platform and had a look at some pairs trading history. And indeed, they fake their volume in a laughingly obvious and artificial way:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague3.png)

*Volume = $1b * sin ( epoch )*

Compare this perfectly neat and absurdly consistent sinusoidal volume with what happens on an actual exchange:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague4.png)

*Poloniex is generally quite liquid across all pairs, in spite of diminished volumes since August 2017*

Spikes, dips, snowball effect on higher volatility. Not a chart out of a high school oscilloscope.

“*But it’s the day and night cycle in China!*”. I do not believe it speaks highly of OKex engineers that they actually reflected upon ways to make washtrading less conspicuous than a straight constant stream of trades, but all they could come up with was a perfect sine wave.

#### **How bad is it?**

As obvious as it is that most of OKex’s volume is doctored, how do we go about estimating whether it’s 90%, 95%, or 99% fake? I propose the following method:

* Gather a list of trustworthy exchanges that all behave consistently on that regard
* Perform a regression on their combined datasets, so as to be able to predict a trading pair volume from an observed slippage
* Compare OKex claimed volume numbers vs estimated volume numbers as predicted by our model.

To that effect I used data from the following exchanges: Bitfinex, GDAX, Poloniex, Bistamp, Gemini and Kraken. Given the volatility of the dataset at lower volumes, I also decided to change the metric I used: instead of a $50k marketsell, I simulated a $20k one.

Here is what the data from the trusted exchanges looks like, this time showing volume as a function of slippage:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague5.png)

*Volume = 4.4/slippage — 5.5*

#### Notice that due to extremely volatile data, any model becomes absurd when slippage exceeds 0.7%. The one proposed above is the best fit I came up with for slippages below 0.7%. Over this threshold, the only reasonable assumption is that the expected volume is most likely under $1M.

As you can see when plugging-in legible OKex data on the above plot, something is definitely not quite right:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague6.png)

*Pretty though*

Out of 28 pairs on selected currencies with volumes over $100k, only 11 have a slippage under 0.7%. They are as follows:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague7.png)

*OKex data, and estimated % fake volume*

The total proportion of faked volume on these pairs would, according to this model, amount to a staggering 93.6%. The discarded pairs (slippage > 0.7%) would not significantly alter this number one way or the other.

Arguably, the regression I used could not be very accurate on very high volumes, for lack of a robust dataset. It only seems fair, then, to discard the BTC/USD pair. Still the number remains ridiculously high: **about 92.9% off all OKex’s volume is most likely fabricated.**

#### **Huobi, a close runner-up**

Similar to OKex, Huobi shut down following China regulatory crackdown, to better re-open later under the Huobi.pro licence. Following the same methodology, here are the results:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague8.png)

*Huobi data, and estimated % fake volume*

**81.8%** of made-up volume, not quite as shameless as their most direct competitor but still extremely high.

A quick glance at their trading history easily confirms that although the volume appears much, much more organic than OKex’s, there still exists a strong background of constant low-key wash trading:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague9.png)

*Legit volumes *do not* maintain any kind of constant baseline*

#### **The Chinese rip-offs armada**

You may or may not have noticed, but CoinMarketCap has quite recently listed a host of Chinese trading exchanges that all boast rather high trading volumes but somehow, no one has ever heard about. Most of them obviously share the same User Interface and trading engine.

Among them, but definitely not limited to, are names such as: Lbank, Exx, RightBTC, CoinEgg, Zb, BitZ, Bibox, CoinEx…

Those platforms are so blatantly faking their volumes that they do not even deserve running numbers: just go and have a look for yourself. It is an absolute disgrace that CoinMarketCap and LiveCoinWatch should list these scamholes alongside sometimes struggling legit exchanges.

#### **HitBTC and Binance**

For a variety of reasons, I had suspicions about two leaders in the altcoin space, HitBTC and Binance. Here’s how they fare against our set of “respectable” exchanges:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague10.png)

*HitBTC & Binance vs reference*

It’s easy to see that, for a given volume, both exchanges, especially Binance in orange, appear significantly less liquid, and as such, suspicious.

Running the same analysis we did for OKex and Huobi before yields the following results. First for HitBTC:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague11.png)

*HitBTC data, and predicted volume discrepancy*

Those numbers cannot be deemed significant. Although they prove that HitBTC is slightly less liquid than the reference exchanges, such a small difference between claimed and re-estimated volumes can stem from a number of reasons, including mere variance.

Binance results are however more intriguing:

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague12.png)

*Binance data, and predicted volume discrepancy*

A 70% difference with our mathematical prediction is worrying. But it serves to remember that the input of the model is slippage in a given trading pair, which is not entirely endogenous to sheer volume.

Indeed I know from having experienced it first-hand that Binance has a [pretty restrictive policy when it comes to API-trading](http://HitBTC%20data,%20and%20predicted%20volume%20discrepancy). I spent some time debating them how I believed such rules to be utterly stupid, as they would only hinder their exchange growth and liquidity.

Indeed, because of these restrictive trading rules, it is quite likely that many people running market making strategies across several exchanges would be reluctant to implement the same strategies on Binance, as they would constantly get banned without ever knowing the actual limits they should not have crossed.

With fewer professional market makers, it is easy to see how orderbooks become thinner and the hereby introduced model might be completely off. It could however serve well to keep a close eye on Binance claimed volume in the future, although inspecting their volume history does not show any obvious suspicious activity.

#### **Caveat**

While I have virtually no doubt about my claims, the numbers should not be taken at face value. Here are a few reasons why:

* Like I mentioned about Binance, API conditions matter. I could easily see a better API improving liquidity on a given exchange.
* Fees may matter as well. Higher fees mean market makers have less incentive to outbid themselves and reduce spreads.
* I have only gathered one 24h averaged sample and did not bother controlling for variance. I am no academic or stats buff, but it does look like most of the results should be rather robust. Feel free to argue differently.
* Different consumer-bases may behave differently across different exchanges, although from my personal algo-trading experience, that tends to be anecdotal at best.

#### **Why should you care?**

One may argue that “*since it’s not a regulated market it’s not even illegal, why shouldn’t they do what they want?*”, and one would be wrong. **Precisely because the market is not regulated the responsibility behooves the market actors themselves**. Spreading awareness and boycotting exchanges that endorse this practice is the least we can do.

One may argue that “*well they’re not hurting anyone*”, and one would be wrong. First of all, by inflating their volume, they position themselves in a way that could allow them to defraud gullible investors. More importantly, if you’re neither gullible nor a VC investor they can and they do have an impact on some cryptocurrencies valuation. Litecoin and Bitcoin Cash notably, have had as much as 75% of their volume circulating on one or the other of these exchanges. OKex alone consistently accounts for over 30% of either currency’s volume.

![](/assets/images/2018/m3/chasing-fake-volume-a-crypto-plague13.png)

*The state of the Bitcoin Cash Markets, on the day of its latest pump*

By displaying mostly artificial volumes, these currencies look more appealing to traders, as they seem to garner much more attention than they actually do (volume is a good antidote to volatility). Also, consistently completing washtrades in the upper part of a spread bracket may induce people to generally ever-so-slightly overvalue the currency.

The unethical exchanges are also likely to attract more customers than ethical ones that would have more actual volume and liquidity, and could allow users to trade faster and/or pay for less slippage!

Finally, engaging in washtrading, if not strictly speaking illegal, could well be a predictor of future unsavory behavior, and should encourage all users to exercise extra caution.

#### **Conclusion**

By my reckoning, over $3 billion dollars of daily volume is nonexistent. Possibly more. Yet somehow, the practice is, if not encouraged, at least thoroughly ignored by popular data aggregators and most of their users, when all anybody really has to do is have a look to figure out that something is amiss.

Cryptoassets are in a dramatic bear market at the moment, following the bullish frenzy of 2017. It is my belief that growth cannot resume until we have achieved a sound enough trading environment. The ecosystem market cap and awareness have blown way past the point when we could afford to allow such blatant manipulation.

“*Crypto doesn‘t need regulation!*”, we all claim. It is high time we proved it. Because as it stands the state of crypto is arguably a testament to the failure of the free-market.

ArtPlay (Follow me [@ArtPlaie on Twitter](https://twitter.com/ArtPlaie))

— — — — — — — — — -

**Annex**

My definition of slippage is actually somewhat improper. I define slippage as the percentage change between the observed mid-spread price and the lowest price I had to consent to to sell the asset.

For those of you who may want to explore the data I collected, [here it is, raw data is on sheet1](https://drive.google.com/file/d/1m1ZeRfqKzP6DkZifJfG4j1D2CM-gU30z/view?usp=sharing):

I used the [CCXT Python](https://github.com/ccxt/ccxt) library for data mining purposes: [https://github.com/ccxt/ccxt](https://github.com/ccxt/ccxt)

Finally, I have not listed all exchanges that I believe to be doctoring their volumes. Off the top of my head, simply by looking at trade history charts, Tidex, Liqui and Wex are all guilty to some unquantified extent (unquantified, but probably high). Most likely many more. Investigating the OKex future contracts, if possible by any means, could also yield interesting surprises, as they also claim huge volumes on futures.

Popular exchange Bittrex is absolutely clean. As best as I can tell, so should be exchanges such as Cryptopia or Kucoin (with a shade of a doubt on the latter, which I know for sure kickstarted their activity with a ton of very obvious washtrading)

For lack of data, I have not explored most Korean exchanges. Bithumb seemed OK, but I’d have to double check. No idea about Coinnest or Upbit.

***

{% include signup.md %}
