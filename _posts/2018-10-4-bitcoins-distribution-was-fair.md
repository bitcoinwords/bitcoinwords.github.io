---
title: "Bitcoin's Distribution was Fair"
permalink: "/bitcoins-distribution-was-fair" 

author: danheld

tags:
  - Dan Held
  - CY18 Q4

excerpt: Dan Held's take on Bitcoin's distribution, posted October 4, 2018

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

# [Bitcoin's Distribution was Fair](https://blog.picks.co/bitcoins-distribution-was-fair-e2ef7bbbc892)
### By [Dan Held](https://blog.picks.co/@danhedl)
### Posted Oct 4, 2018

## Foreword

As Bitcoin rises in popularity, and continues to challenge mainstream thought, there will be concerns around certain [parameters](https://medium.com/@danhedl/pow-is-efficient-aa3d442754d3) of its existence. One of those is that the distribution of Bitcoin wasn't "fair," particularly in the earlier stages of network development. I'll dive into the timeline surrounding Bitcoin's launch, and provide a thorough debunking of unfair early distribution claims.

TL;DR — Satoshi set out to design the fairest system possible.

To enjoy this article in its fullest, I recommend playing this song then continue reading. If you like this music, please follow my [playlist](https://open.spotify.com/user/txdan2010/playlist/3X0JDW2W59uQ6Yx2J2X3XW?si=YpoSB0bLSSuaUoUhh7AClA) on Spotify.

## Distribution

Premining is the mining or creation of a number of crypto coins before the cryptocurrency is launched to the public. Premining sometimes has a negative connotation due to the ability of private developers to privately mine and allocate a number coins to themselves before releasing the open source code of the currency to the public. This could lead to a feeling of lack of transparency in the digital currency offered to the public.

Satoshi didn't premine. Satoshi gave everyone a two month heads up before mining the Genesis block, reaching out to the only other people who would possibly be interested in experimenting with a sovereign digital currency at the time, the cypherpunks (via public e-mail list). The whitepaper was published on October 31, 2008, then Bitcoin 0.1 software was released on January 9, 2009.

The Genesis Block alone was minted earlier January 3, 2009. It was unlike all other blocks (no previous block to reference) and required custom code to mine it. Satoshi included a message in the Genesis Block as a "proof of no premine."

> "The Times 03/Jan/2009 Chancellor on brink of second bailout for banks"-[Genesis Block](https://en.bitcoin.it/wiki/Genesis_block)

Timestamps for subsequent blocks indicate that Nakamoto did not try to mine all the early blocks solely for himself. Before Satoshi's invention, the concept of pre-mining didn't exist. To be this prescient demonstrated incredible maturity.

The code to mine bitcoin was available on the day Satoshi began mining (other than the special purpose Genesis Block). It even had a 1-click miner in there so it was incredibly easy. Once the code was released, several individuals started mining — we know for a fact that Hal Finney was mining one day after the initial launch. Satoshi definitely wasn't mining alone in the early days, granted the number participating was slim.

![](/assets/images/cy18/cy18q4m10/dan-1.png){: .align-center}

For the first year of Bitcoin's existence, Satoshi and other miners couldn't muster enough hashrate to mine more than 144 blocks/day and trigger an upwards difficulty adjustment. Satoshi mined because the network required a miner, he turned them off when there was a stable network that didn't need his mining power. He [reduced](http://organofcorti.blogspot.com/2014/08/167-satoshis-hashrate.html) his % of the hashrate in a slow and steady manner. The Satoshi fingerprinted mining carefully balanced the hashrate of the cluster, with the goal of historically viewable well-meaning intentions. Satoshi initially followed a plan of reducing the hashrate by 1.7 Mhps every five months, but a month after the second such drop abandoned this method in favour of a continuously decreasing hashrate.

![](/assets/images/cy18/cy18q4m10/dan-2.png){: .align-center}*[http://organofcorti.blogspot.com/2014/08/167-satoshis-hashrate.html](http://organofcorti.blogspot.com/2014/08/167-satoshis-hashrate.html)*

How much did Satoshi mine? Other than a few coins (some still [circulating](https://bitcointalk.org/index.php?topic=548508.0)), it's not empirically knowable how many he owned, but we can assign a high probability that he was the miner who minted close to ~ 700,000. BitMEX reviewed the original [estimate](https://bitslog.wordpress.com/2013/04/17/the-well-deserved-fortune-of-satoshi-nakamoto/) made by Sergio Demian Lerner where he discovered that Satoshi's miner had a "fingerprint" (the increase in the ExtraNonce value in the block can potentially be used to link different blocks to the same miner). BitMEX built on his analysis and [concluded](https://blog.bitmex.com/satoshis-1-million-bitcoin/) that although the evidence is far less robust than many assume, there is reasonable evidence that a single dominant miner in 2009 could have generated around 700,000 bitcoin.

> "Although there is strong evidence of a dominant miner in 2009, we think the evidence is far less robust than many have assumed. Although a [picture is worth a thousand words](https://bitcointalk.org/index.php?topic=178629.0;all), sometimes pictures can be a little misleading. Even if one is convinced, the evidence only supports the claim that the dominant miner may have generated significantly less than a million bitcoin in our view. Perhaps 600,000 to 700,000 bitcoin is a better estimate." — BitMEX

![](/assets/images/cy18/cy18q4m10/dan-3.png){: .align-center}*Bitcoin blocks mined in 2009 — Allocation to the dominant miner — ExtraNonce value (y-axis) vs block height (axis)*

Bitcoin's market cap was ~ $0 for nearly a year and a half. Miners were wasting money on hardware and electricity to mine, with no guarantee that the Bitcoins they received would ever have value. In fact, "faucets" were set up to freely distribute Bitcoins in order to "seed" adoption (ex the 10k btc faucet set up by [Gavin](https://www.reddit.com/r/btc/comments/6vsk7u/gavins_original_bitcoin_faucet_used_to_give_away/) and other Bitcoiners who donated funds). The first recorded exchange of Bitcoin for "real world" value occurred on May 22, 2010, now known as Bitcoin Pizza Day, where Laszlo Hanyecz [agreed](https://en.bitcoin.it/wiki/Laszlo_Hanyecz) to pay 10,000 Bitcoins for two delivered Papa John's pizzas. He went on to do this trade 2 more times, maximizing the dispersion of his Bitcoins.

> "It might make sense just to get some in case it catches on. If enough people think the same way, that becomes a self fulfilling prophecy." —[Satoshi Nakamoto](http://www.metzdowd.com/pipermail/cryptography/2009-January/015014.html)

The early pioneers were the ones crazy enough to take the financial, temporal and social risks to participate in the Bitcoin project, keeping it alive and acting as arbiters of the system in its early days. Nearly all lost or sold all of their Bitcoins as evidenced by this analysis done by [Dhruv Bansal](https://medium.com/@shrubvandal)

![](/assets/images/cy18/cy18q4m10/dan-4.png){: .align-center}

With each of those boom/bust cycles we've seen Bitcoin redistributed from old hodlers to new hodlers via selling, decreasing the Gini Coefficient. In 2017 [alone](https://blog.unchained-capital.com/bitcoin-data-science-pt-1-hodl-waves-7f3501d53f63), we saw 15% of all BTC move out of old hodler hands.

The theoretical total number of bitcoins, slightly less than 21 million, should not be confused with the total spendable supply. The total spendable supply is always lower than the theoretical total supply, and is subject to accidental loss, willful destruction, and technical peculiarities.

> "Ten years ago cryptographers and HCI experts created the ultimate experiment to see how well human beings could hold onto long-lived secret keys. We structured the experiment so participants would lose hundreds or thousands of dollars if they failed. The results of that experiment have not been pretty." — Some Cryptographer on Twitter

There are [many stories](http://www.wired.co.uk/article/bitcoin-lost-newport-landfill) of people losing BTC in large amounts — especially in the early days — when BTC wasn't worth much and was easily forgotten on an old hard-drive, USB memory stick, even a scrap of paper. Coins which remain unspent for >5 years have a high likelihood to be lost forever. Despite the richness of blockchain data, it's extremely difficult to measure how much cryptocurrency is truly lost, as lost coins leave no trace in the blockchain. The problem is that so much BTC which is not lost looks exactly the same on the blockchain.

> "The study of lost bitcoin is geology masquerading as data science." —[Dhruv Bansal](https://blog.unchained-capital.com/@shrubvandal?source=post_header_lockup)

Unchained Capital did a great [analysis](https://blog.unchained-capital.com/bitcoin-data-science-pt-2-the-geology-of-lost-coins-79e5a0dc6d1) of lost coins, and found that bitcoin loss occurred over two distinct "cryptogeologic" eras: Systemic (earlier miners, and Incremental loss: (coins lost by individual users gradually over time). Their estimate: 2.78–3.79M BTC lost which aligns with another more [sophisticated](http://fortune.com/2017/11/25/lost-bitcoins/) analysis done by Chainalysis.

> "Lost coins only make everyone else's coins worth slightly more. Think of it as a donation to everyone." —[Satoshi Nakamoto](https://bitcointalk.org/index.php?topic=198.msg1647#msg1647)

From private key management mistakes, to scams and exchange hacks, to resisting selling temptation, early HODLers SURVIVED. In compensation for that risk, they absolutely deserve the value appreciation.

Some argue Bitcoin's distribution is analogous to a Ponzi scheme, but it's nothing like one. The definition of a [Ponzi Scheme](https://www.investopedia.com/terms/p/ponzischeme.asp): "a fraudulent investing scam promising high rates of return with little risk to investors. The Ponzi scheme generates returns for older investors by acquiring new investors." It isn't one for the following reasons:

Transparency

Absolutely nothing about Bitcoin is a secret. It's open source, anyone can review the code, anyone can contribute to the code, anyone can run the software voluntarily and participate in the network, and anyone can use the network without permission. The entire history of all Bitcoin transactions is visible to anyone in the world too. It's the total opposite of a fraudulent investing scam, which is shrouded in vague promises of high returns with capital inflows and outflows that are kept in a secret ledger.

Returns

The Bitcoin whitepaper never mentions an investment or promising high returns. In a Ponzi scheme, the value for early investors rely solely on new entrants coming in with fresh capital, and their earnings/dividends come directly from this capital. With Bitcoin, the opposite is true. Most early Bitcoiners lost or sold their Bitcoin. Bitcoiners are human, they make human mistakes and have human needs (buying a house).

> "Bitcoins have no dividend or potential future dividend, therefore not like a stock. More like a collectible or commodity." —[Satoshi Nakamoto](https://bitcointalk.org/index.php?topic=845.msg11403#msg11403)

Usage

The market's determination of what one Bitcoin is worth has nothing to do with greater fools getting in the system, but an after effect of its true value proposition, one that it already had even when it was worth nothing.

## Conclusion

Satoshi was a person like any other, not some infallible being. This was the fairest distribution he could have come up with given what he was building/timing/audience. It's intellectually dishonest to compare Satoshi's early mining of Bitcoin at a loss, with premining of an ICO with a positive market value (or expected positive market value).

> "Bitcoin benefited from an extremely rare set of circumstances. Because it launched in a world where digital cash had no established value, they circulated freely. That can't be recaptured today since everyone expects coins to have value. Not only was it fair, but it was historically unique in its fairness. The immaculate conception."[Nic Carter](https://medium.com/@nic__carter)

Satoshi wanted to signal to everyone that Bitcoin wasn't a scam. The conservative deescalation of his mining contributions, his departure from the community, never spending any of his coins, nor using his influence for any purpose, shows that he wanted the world to make up their own mind about his project and judge it on its own terms.

Unlike every other founder in history, Satoshi never cashed out.
