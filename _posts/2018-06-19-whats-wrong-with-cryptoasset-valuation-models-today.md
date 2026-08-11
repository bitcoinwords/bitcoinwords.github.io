---
title: "What’s Wrong with Cryptoasset Valuation Models Today?"
permalink: "/whats-wrong-with-cryptoasset-valuation-models-today"

author: qiaowang

tags:
  - Qiao Wang
  - 2018 Q2
  - Economics
  - Money
  - Value

excerpt: What’s Wrong with Cryptoasset Valuation Models Today?. Posted June 19, 2018.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [What’s Wrong with Cryptoasset Valuation Models Today?](https://medium.com/@QwQiao/whats-wrong-with-cryptoasset-valuation-models-today-7d1c4b4ba109)
### By Qiao Wang
### Posted June 19, 2018

Valuation modeling has fascinated cryptoasset enthusiasts in recent years. While it’s a great thing that people are thinking about this kind of stuff, I have seen some obvious pitfalls, which I will discuss in this post.

The goal of this post is to encourage people to be critical of the valuation-related books, papers, and blog posts they read, and to be careful with turning these valuation models into trading and investment decisions.

**1 — Lack of Empirical Analysis**

Lots of people give trading advice based on models lacking rigorous empirical evidence. Be wary, because no matter how intuitive these models appear to be, empirically they may not give you an edge. And even if they do give you an edge, respect the market and understand that the edge is usually very small.

**Case study**: As far as I know I was the first person to publish a [empirical analysis of Network Value to Transaction (NVT](https://medium.com/@QwQiao/nvt-and-overconfidence-bias-48bae245afc3)). Yet people have used NVT to make market calls long before. This is extremely dangerous. Charts that show that a model has successfully predicted last three bubbles are **not** rigorous empirical analyses.

**2 — Input Data**

Many research papers don’t make enough effort to describe the input data. How are the fields defined? Where does the data come from? When reading these papers, one should be skeptical of the conclusion, because “garbage in, garbage out”. As a matter of fact, my own blog post on NVT suffers from this problem.

**Case study**: [Are Bitcoin Bubbles Predictable? Combining a Generalized Metcalfe’s Law and the LPPLS Model](https://arxiv.org/pdf/1803.05663.pdf) is a study that shows that network value can be predicted with “active addresses”. However, the paper does not define what “active addresses” is. It merely states that it is collected from bitinfocharts.com. What if the way bitinfocharts.com defines “active addresses” changes over time? This is not to say that the paper has no merit, but that one should always get to the bottom of the data source before forming an opinion.

**3 — Misunderstanding of Model Assumptions**

It’s intellectually tempting to apply a well-known formula to a new context. For instance, I have seen people applying Black-Scholes option pricing formula to VC investing. However, one should fully understand the assumptions behind these formulas before applying them to new situations. How many people know that Black-Scholes assumes that the price movement of the underlying stock follows a geometric Brownian motion? How many people understand the mathematics behind the geometric Brownian motion?

**Case study**: [An Institutional Investor’s Take on Cryptoassets](https://s3.eu-west-2.amazonaws.com/john-pfeffer/An+Investor%27s+Take+on+Cryptoassets+v6.pdf) and the [Understanding Token Velocity](https://multicoin.capital/2017/12/08/understanding-token-velocity/) draw conclusions from the popular formula MV=PQ without clear understanding of why the formula holds in the first place. MV = PQ is merely a tautology: quantity of money transacted equals monetary value of sales, and that’s true by definition.

In “An Institutional Investor’s Take on Cryptoassets”, PQ is assumed to describe an economy where ether is used as computing resources, and MV describes a much larger economy where ether is used to as general money. MV = PQ clearly breaks down when the two sides do not describe the same economy.

“Understanding Token Velocity” first defines Velocity (V) as a function of Average Network Value (which is akin to M) and Total Transaction Volume (which is akin to PQ), and then for some reason argues that M is dependent on V. There are two obvious logical fallacies with this:

* Confusion between cause and effect: When one starts with a definition of V, one is essentially assuming that V is the dependent variable. One cannot then say M is the dependent variable.
* False assumption of independence: When one draws the conclusion that M is an inverse function of V, one is assuming that V and PQ are independent. How is this even theoretically justified?

**4 — Overfitting: Model Complexity**

In data science there is an important concept called [Bias-Variance Tradeoff](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff). The gist of it is that complex models tend to be overfitted, i.e., they perform well in past datasets but poorly in future datasets. This is not to say fancy models are **always** less performant, but one should be extremely cautious. It takes years of data science experience to appreciate the statement “complexity is a form of laziness”.

**Case Study**: [Rethinking Metcalfe’s Law Applications to Cryptoasset Valuation](https://medium.com/cryptolab/network-value-to-metcalfe-nvm-ratio-fd59ca3add76) uses six variables to describe the relationship between two time series. [Valuing Cryptoassets from the Ground Up](https://medium.com/@sall/valuing-cryptoassets-from-the-ground-up-441ad5a9ff03) uses a high-dimensional (e.g., exponents and roots) formula to predict network value. From years of experience as a quant I have high conviction that fancy models like this aren’t profitable in live trading.

![](/assets/images/2018/m6/whats-wrong-with-cryptoasset-valuation-models-today1.png)

**5 — Overfitting: Data Mining**

Another type of overfitting involves models which are built from pure data mining and lack theoretical foundation. You probably have heard of the term [spurious correlation](https://en.wikipedia.org/wiki/Spurious_relationship); it’s essentially the same idea. Conversely, models that perform well tend be those that are based on fundamental understanding of the problem that is being modeled. The best [regularization](https://en.wikipedia.org/wiki/Regularization_%28mathematics%29) method is [domain knowledge](https://en.wikipedia.org/wiki/Domain_knowledge).

![](/assets/images/2018/m6/whats-wrong-with-cryptoasset-valuation-models-today2.png)

**Case study**: One such example is models that predict “[BTC will go to X because mining cost is Y](https://cointelegraph.com/news/mining-will-propel-bitcoin-price-to-36k-in-2019-says-latest-fundstrat-research)”. Needless to say this is spurious correlation. Mining is a function of price, not the other way around.

**Final Thoughts**

When it comes to valuation it’s important to determine at what time horizon we are actually valuing. It’s entirely possible that an asset is at the same time overvalued on the horizon of minutes, undervalued on the horizon of days, and overvalued on the horizon of years.

That said, my feeling is that crafting models to valuing cryptoassets on the horizon of weeks/months is not the most productive approach in this market. Quantitative models work only if patterns persist, but because crypto moves at 10000 mph, regime shifts occur far too often for patterns to persist.

***

{% include signup.md %}
