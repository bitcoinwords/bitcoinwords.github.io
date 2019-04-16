---
title: "Bitcoin Data Science (Pt. 2): The Geology of Lost Coins"
permalink: "/bitcoin-data-science-the-geology-of-lost-coins-part-2" 

tags:
  - Dhruv Bansal
  - CY18 Q2

excerpt: By Dhruv Bansal, Posted May 29, 2018
  
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

# Bitcoin Data Science (Pt. 2): The Geology of Lost Coins
### By [Dhruv Bansal](https://blog.unchained-capital.com/@shrubvandal)
### Posted May 29, 2018

**This is part 2 of a series**

* [Bitcoin Data Science (Pt. 1): HODL Waves](https://cryptowords.github.io/bitcoin-data-science-hodl-waves-part-1)
* [Bitcoin Data Science (Pt. 2): The Geology of Lost Coins](https://cryptowords.github.io/bitcoin-data-science-the-geology-of-lost-coins-part-2)
* [Bitcoin Data Science (Pt. 3): Dust & Thermodynamics](https://cryptowords.github.io/bitcoin-data-science-dust-and-thermodynamics-part-3)

***

There are [many stories](http://www.wired.co.uk/article/bitcoin-lost-newport-landfill) of people losing BTC in large amounts - especially in the early days - when BTC wasn't worth much, and was easily forgotten on an old hard-drive, USB memory stick, even a scrap of paper.

Is it possible to quantify how much BTC is really lost? Blockchains track their internal data forever, and as we showed in [Part 1 of this series](https://blog.unchained-capital.com/bitcoin-data-science-pt-1-hodl-waves-7f3501d53f63), one can visualize Bitcoin's UTXO age distribution to illuminate historical trends in ownership:

![UTXO distribution plot](/assets/images/cy18/cy18q2m5/dhruv-1.png){: .align-center}*The colored bands show the relative fraction of Bitcoin in existence that was last transacted within the time window indicated in the legend. The bottom, warmer colors (reds, oranges) represent Bitcoin transacted very recently, while the top, cooler colors (greens, blues) represent Bitcoin that hasn't transacted in a long time. Bitcoin's money supply grew from 50 BTC to ~ 17M BTC over this time period, so the chart has been normalized by the BTC in existence at each date (left y-axis). The black line shows the USD/BTC price (logarithmically, right y-axis). Chart lovingly made by [Nelson Morrow](https://github.com/nelsontodd) based on [prior work](https://www.reddit.com/r/Bitcoin/comments/2n205b/an_area_chart_showing_the_distribution_of/) by [@jratcliff](https://twitter.com/jratcliff) [[Direct Link](https://plot.ly/~unchained/37)]*

After seeing the UTXO age distribution above, many readers of [Part 1](https://blog.unchained-capital.com/bitcoin-data-science-pt-1-hodl-waves-7f3501d53f63) commented, "a large fraction of the oldest coins are probably lost." This is a reasonable intuition. There were many reasons for BTC holders to transact in 2017 & 2018: a price rally and a pullback, the rise of ICOs, the BTC/BCH fork, new segregated witness addresses, etc. Coins which remain unspent for >5 years have a high likelihood to be lost forever. Can we make this intuition more precise?

Despite the richness of blockchain data, it's extremely difficult to measure how much cryptocurrency is truly lost, as lost coins leave no trace in the blockchain. Lost BTC sits idly in the UTXOs of its last transaction, aging quietly as time passes. The problem is that _so much_ BTC which is **not lost** looks exactly the same on the blockchain.

Still, the UTXO age distribution does provide insight into how to think about lost BTC. The cooler-colored, older age bands can be thought of as [**low-pass filters**](https://en.wikipedia.org/wiki/Low-pass_filter) which only allow the oldest coins to pass into them. As a result, they experience slower, less volatile changes than the hotter colored, younger age bands.

UTXO age bands are like geological strata: evidence of coins held some time ago, buried beneath layers of more recent transactions. Distinguishing lost coins from those dearly held requires unearthing subtle data from the oldest layers, from the deepest records of the blockchain.

> The study of lost bitcoin is geology masquerading as data science.

We believe bitcoin loss occurred over two distinct "cryptogeologic" eras:

1. **Systemic loss**: a large cohort of BTC which was mined together and lost together in the earliest days of Bitcoin by Satoshi and the other first miners. (Bitcoin's _carboniferous period._)
2. **Incremental loss**: BTC lost by individual users gradually over different periods of time.

We'll show that the era of systemic loss has ended, and demonstrate that we are now in the era of incremental loss. Finally, we'll estimate bounds on how much bitcoin is lost. Let's turn to the data.

## Early Systemic Loss

What was happening in Bitcoin in its earliest days in 2009? Answer: Almost nothing.

Satoshi published the [original whitepaper](https://bitcoin.org/bitcoin.pdf) in October, 2008 after working on the concept and the code for the prior couple of years. Satoshi mined the genesis block on January 3rd, 2009, and promptly released the first version of the `bitcoind` software (v. 0.1) on January 9th.

Very few people took Satoshi or Bitcoin seriously in those early days. [Gwern Branwen](https://medium.com/@gwern0)'s excellent article [Bitcoin-is-Worse-is-Better](https://www.gwern.net/Bitcoin-is-Worse-is-Better) describes some of the initial negative reaction from "professional" cryptographers.

In the first days of Bitcoin, poor Satoshi was mostly mining alone, occasionally joined by other crazy people such as [Hal Finney](https://en.wikipedia.org/wiki/Hal_Finney_%28computer_scientist%29). The result was extremely low hashpower, as the chart below shows. Satoshi and the first miners were unable to exceed the minimum hashrate required to trigger an upward difficulty adjustment till the first days of 2010. The average time between blocks didn't hit the target of 10 minutes until a month later, in February, 2010.

![hashrate chart](/assets/images/cy18/cy18q2m5/dhruv-2.png){: .align-center}*Chart depicting hashrate and the average time between blocks over 2009 and the first quarter of 2010. It's likely that only Satoshi and a few other small groups were mining Bitcoin during the entirety of 2009. Chart originally appeared in [an article](https://eklitzke.org/how-many-bitcoins-did-satoshi-nakamoto-mine) by [Evan Klitzke](https://medium.com/@eklitzke).*

Despite the apparent stagnation above, there were still many, many blocks mined in 2009, and over 5M BTC was produced in this period by Satoshi and the first miners through 2011. That's more than 23% of the all BTC that will ever exist. Where did it go?

![average utxo balance by age](/assets/images/cy18/cy18q2m5/dhruv-3.png){: .align-center}*This chart groups the current UTXO set by age and then plots the average BTC balance per UTXO at each age group. The cohort of UTXOs older than 7 years (approx. 1.9M BTC), all mined before 2011, is clearly visible as a "shelf" on the right side of the plot, with the average balance sitting at 50 BTC, the coinbase reward in that era.. [[Direct Link](https://plot.ly/~unchained/207)]*


The above plot shows that the oldest 1.9M BTC of UTXOs in existence are a distinct population. They are the cohort of coins mined by Satoshi and the first miners during those early years of Bitcoin. They form a "shelf" at 50 BTC in the chart because the block reward at that time was 50 BTC (and fees were negligible): they are coinbase outputs that were never spent. (Note that the rapid falloff of this shelf between 6.5–7 years ago occurred in 2011. We'll come back to this date below.)

### Bitcoin's Carboniferous Period

The [carboniferous period](https://en.wikipedia.org/wiki/Carboniferous) occurred about 300M years ago and corresponds to the age in which Earth was covered in trees, but nothing existed which could eat trees. As a result, layers of dead trees accumulated, unable to decay.

![an old forrest](/assets/images/cy18/cy18q2m5/dhruv-4.png){: .align-center}*A late 19th century etching of what a forest would look like during the carboniferous period (300–360 Mya). [From [Wikipedia](https://en.wikipedia.org/wiki/Carboniferous)]*

**2009–2011 was Bitcoin's carboniferous period**: huge amounts of coins were mined but unused, accumulating in the blockchain, eventually becoming lost, unuseable, and buried.

It's ironic that, eons later, the trees which accumulated in the carboniferous period became coal, the chief energy source used for most Bitcoin mining today :)

## Transition to Incremental Loss

Something dramatic happened to Bitcoin in 2011. The cohort of oldest UTXOs noted above diminished rapidly. 5 years later, in 2016, the rate at which BTC was entering the >5 years age band correspondingly diminished. This manifests as an inflection point or "kink" in the >5 years age band of the UTXO age distribution in 2016. One can see the echo of dramatic changes in Bitcoin, 5 years prior, in 2011.
This chart shows the net rate-of-change of the amount of BTC >5 years old over time (trailing 90-day average). Between 2014–2016 (highlighted in blue) we see the effect of Bitcoin's "carboniferous period", which occurred 5 years earlier, from 2009–2011, when many coins were being lost. This period ends abruptly in 2016, corresponding to a dramatic change in Bitcoin 5 years prior in 2011. The time-axis of the chart starts in 2014 because this is the first year in which BTC could enter the >5 years age band (the genesis block having been mined in 2009). [[Direct Link](https://plot.ly/~unchained/205)]

![net rate of BTC entering > 5y age band](/assets/images/cy18/cy18q2m5/dhruv-5.png){: .align-center}*The above plot summarizes this transition. Between 2014–2016 (highlighted in blue) the rate at which BTC was entering the >5 years age band was extremely high. This corresponds to coins which last transacted during Bitcoin's carboniferous period of 2009–2011, when Satoshi and the first miners mined, then subsequently lost, many coins.*

A dramatic decrease in the rate of BTC entering the >5 years age band occurs in 2016, corresponding to the end of Bitcoin's carboniferous period in 2011. The real, geological carboniferous period ended when bacteria evolved which could digest wood, preventing dead trees from piling up for eternity. What caused Bitcoin's carboniferous era to end?

### Curiosity to Commodity

In June, 2011, Bitcoin experienced its first major rally. Over a couple of short months, Bitcoin's price went from less than $1 to a peak of $33. This created significant wealth for many early miners — at least those who hadn't lost their keys.

Before the sudden price increase to $33, Bitcoin miners may have been lax with the security or safe-keeping of the BTC they were earning. The tragic tales of lost hard drives containing untold digital wealth largely occurred around this time. Afterwards, anyone mining BTC would have taken note: 1) BTC was valuable, and 2) it could quickly grow in value by orders of magnitude again.

These lessons fostered a radically different attitude towards mining and safeguarding bitcoin. At <$1/BTC, daily mining revenues would be only a few thousand dollars per day, amounting to perhaps ~ $1M per year — a market barely large enough to support a single small business. At $33/BTC, however, daily mining revenues reached almost $250k, creating a yearly revenue stream of >$80M. Bitcoin went from being a curiosity to a commodity, and Bitcoin mining transitioned from a hobby to an industry.

### Echoes of the Great HODL?

A remarkable feature of the above chart is the upswing in the rate of BTC entering the >5 years age band in the last couple of months. This upswing represents BTC which last transacted in the middle of 2013, 5 years ago.

In [Part 1](https://blog.unchained-capital.com/bitcoin-data-science-pt-1-hodl-waves-7f3501d53f63) of this series we identified the HODL wave pattern of changes in the UTXO age distribution. This recent upswing in the rate of BTC entering the >5 years age band is the arrival of the leading edge of the Great HODL wave started in 2013/2014, when Bitcoin rallied to $1k/BTC.

We know that the Great HODL wave was disrupted by the 2017 rally to $19k/BTC, so it's unlikely that all the 1.5M BTC in UTXOs which entered the 3–5 age band in 2016 would have survived to enter the >5y age band in 2018; many would have been transacted with during the rally, the fork, SegWit, &c.

So, in distinction to Bitcoin's carboniferous period, we predict this recent upswing to be much smaller and abate more quickly. We estimate <500k BTC should enter the >5 years age band over the next 18 months.

## So how much Bitcoin is lost?

It's impossible to know. But, based on the analysis above, we can make an informed guess at some bounds. This will be easier with an absolute version of the UTXO age distribution:

![Bitcoin UTXO age distribution](/assets/images/cy18/cy18q2m5/dhruv-6.png){: .align-center}*An absolute version of the UTXO age distribution chart which has not been normalized by the available BTC supply. The two prior halvings are clearly visible as kinks in the overall rate of production (as discussed in the text, hashpower was unstable in 2009, causing a departure from linearity). Due to the vast difference in the BTC supply between 2009 and 2018, the earlier HODL waves are harder to see though the Great HODL of 2013/2014 is still quite clear. [[Direct Link](https://plot.ly/~unchained/185/bitcoin-utxo-age-distribution/)]*

A conservative lower bound for the amount of lost BTC is the cohort of coins mined in 2009–2011 by Satoshi and the first miners that remain unspent to this day: 1.9M BTC. This is about 2/3 of the BTC in the current >5 years age band. There are certainly many more Bitcoins which were lost in the intervening years since 2011, but can this amount be quantified?

During the 2017 rally, the 3–5 years age band shrinks significantly, **but the >5 years age band barely changes**. This strongly suggests that many coins in the 3–5 years age band are still controlled by someone, but that most coins in the >5 years age band are lost. At some age between 3–5 years, we should expect the former pattern to crossover to the latter pattern. This also suggests a less conservative lower bound of 3M lost BTC — the size of the >5 years age band.
A version of the UTXO age distribution "zoomed into" the 3–5 years age band, split into 3-month intervals, covering the rally of 2017. [[Direct Link](https://plot.ly/~unchained/219)]

![UTXO age distribution](/assets/images/cy18/cy18q2m5/dhruv-7.png){: .align-center}*This "zoomed-in" version of the UTXO age distribution shows finer-grained detail on the 3–5 years age band, splitting it into several 3-month age bands. A HODL wave is evident as a cohort of coins makes its way through the finer-grained age bands in 3 month periods.*

The earlier age bands (36 — 39 months) are significantly slimmer today than they were in a year ago, indicating that most of those coins are controlled by someone who was able to transact with them during the rally of 2017. The older age bands (57 — 60 months) show almost no change during the rally of 2017, just like the >5 years age band.

We estimate the boundary between these behaviors occurs between 45 to 51 months. If we make the rough assumption that most coins older than this are lost, it suggests that an upper bound of 3.8M BTC are inaccessible. Our final estimate from looking at the UTXO age distribution is that between 3–3.8M BTC are lost.

### A More Precise Estimate

It's difficult to be precise when using just UTXO ages to estimate how much BTC is lost. A better approach would label and track individual UTXOs with external metadata, which would distinguish the context of different transactions: miners, exchanges, etc. This approach takes after archaeology more than geology.

Happily, our friends at [Chainalysis](https://www.chainalysis.com/) have already made such an analysis. In an excellent [Forbes article](http://fortune.com/2017/11/25/lost-bitcoins/) published last year, they use such an approach and make their own estimate: 2.78–3.79M BTC lost. It is encouraging that our simple approach, based on looking at just UTXO ages, accords with Chainalysis' more sophisticated approach.

_Many thanks to_ [_Philip Gradwell_](https://medium.com/@philip_gradwell) _and_ [_Kim Grauer_](https://medium.com/@grauer) _from the_ [_Chainalysis Team_](https://medium.com/@chainalysis) _for helpful discussions. Check out the_ [_Chainalysis Blog_](https://blog.chainalysis.com/) _for more fascinating work from their team._

This post is the second in a series using data science to tell stories about Bitcoin; unearthing the deep geological history of the blockchain, while searching for lost treasure.

You might also enjoy:

* [Part 1](https://blog.unchained-capital.com/bitcoin-data-science-pt-1-hodl-waves-7f3501d53f63): In which we describe market cycles with HODL waves.
* Part 3: In which we analyze UTXO dust in the chain.

[Unchained Capital](https://www.unchained-capital.com) has been performing data science on blockchains for years. Discovering the large amount of Bitcoin UTXOs older than 12 months convinced us to start a [lending business](https://www.unchained-capital.com/how_it_works/) to help cryptocurrency owners get value from their digital assets today while continuing to hold them into the future.

If you are holding BTC (and [soon ETH](https://blog.unchained-capital.com/a-simple-safe-multisig-ethereum-smart-contract-for-hardware-wallets-a107bd90bb52)) and you'd like to borrow against your holdings, please [sign up for an account](https://www.unchained-capital.com/sign_up/) on our website and [apply for a loan](https://www.unchained-capital.com/loans/).

Remember _: Friends don't let friends sell Bitcoin._
