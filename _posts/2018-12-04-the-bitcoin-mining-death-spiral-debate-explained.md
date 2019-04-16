---
title: "The "Bitcoin mining death spiral" debate explained"
permalink: "/the-bitcoin-mining-death-spiral-debate-explained" 

tags:
  - Arjun Balaji
  - CY18 Q2

excerpt: By Arjun Balaji, Posted December 4, 2018
  
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


# The "Bitcoin mining death spiral" debate explained
### By [Arjun Balaji](https://www.theblockcrypto.com/author/arjun_tb/)
### Posted December 4, 2018


## Quick Take

* Bitcoin is not going into a miner-induced death spiral
* In an extremely unlikely scenario if hash rate dropped a lot, miners can be kept running by increasing fees
* If that wasn't enough, as a last resort, there could be an emergency fork to manually lower difficulty

Bitcoin is not going into a "mining death spiral."

Now that we've gotten that out of the way... rather than fear-mongering, _The Block_ is committed to clarifying comments and concerns posed by [crypto-fund managers](https://twitter.com/AriDavidPaul/status/1069685155202326528) and enthusiasts alike with level-headed technical clarity.

The case that Bitcoin is going into a miner-induced death spiral is intuitively compelling: Bitcoin prices drop materially, eventually marginally profitable miners shut off, ad infinitum, until all the miners are gone and no one mines Bitcoin (cue: Bitcoin is dead, redux).The argument is crutched on a few core assumptions often relied on by critics: $BTC would have to trade sub-$1000, with hash rate dramatically dropping off before the [difficulty adjustment](https://en.bitcoin.it/wiki/Difficulty), the variable representing the difficulty of mining a new Bitcoin block. Miners, who are strictly rational short-term, would then choose to shut off all their miners or mine alternative cryptocurrencies rather than take losses mining Bitcoin unprofitably.

For context, Bitcoin's difficulty adjustment doesn't happen every two weeks. The difficulty of mining a Bitcoin block is naturally adjusted by the system every 2016 blocks, which probabilistically averages to two week intervals.

This tends to follow the hash rate, as seen [below](https://www.theblockcrypto.com/tiny/bitcoins-mining-difficulty-saw-the-largest-drop-in-the-asic-era/):

![Bitcoin difficulty v hashrate](/assets/images/cy18/cy18q4m12/arjun-1.png){: .align-center}

The biggest issue with the mining death spiral case is that we've seen this before. The narrative was [first entertained](https://bitcointalk.org/index.php?topic=46498.0;all) on Bitcointalk forums as early as 2011. More recently, there was a resurgence in the ASIC era with the last cycle of Bitcoin mania. As now Messari CTO [Dan McArdle](https://twitter.com/robustus) noted in a [January 28th, 2015 tweet](https://twitter.com/robustus/status/560586576687013888): "What happened to everyone arguing that price-drop -> miners leaving -> systemic incentive fail spiral? Did it not happen after all? #duh"

Of course, while industrialized mining has changed the landscape materially, the fundamental game theory Bitcoin relies on have not. Bitcoin analyst [Nic Carter](https://twitter.com/nic__carter) elegantly explains the possibilities:

![Bitcoin's death spiral](/assets/images/cy18/cy18q4m12/arjun-2.png){: .align-center}

Before the proposed death spiral, Bitcoin could have an emergency fork to a manually adjusted lower difficulty (to speed up the process to the next natural adjustment). Of course, this is very undesirable and should be considered a last-resort.

The third possibility and likely possibility isn't covered on Nic's original chart out of simplicity: when hash rate drops off precipitously in between difficulty adjustments, higher fees can serve as a market-funded incentive to force miners to stay on.

Prior to proclaiming Bitcoin's demise due to the death spiral, it's important to understand a few common misconceptions about miners and their relationship with the difficulty adjustment:

* **The "break-even cost of mining" is much lower for many miners than is often quoted by analysts** (who focus on the average miner). Many of the most profitable miners have a "cost per Bitcoin" (opex + capex) that asymptotically approaches 0. This is the combined result of heavily-subsidized electricity (often free or even negative-cost) and extremely low cost of ASICs for the largest miners, who are often vertically integrated or receive favorable deals from hardware manufacturers.
* Similar to producers in other markets (e.g., traditional commodities), **miners have a set of constraints that may _rationally force them to mine at a loss_** — this is a situation accounted for by miners. These constraints include long-term power purchase agreements, hardware purchase agreements, facility leases, and other financial arrangements. With these constraints and strategically-planned cash reserves, miners can mine at a loss for an extended period.
* Contrary to mining other commodities, where mining at a loss results in sustained price suppression (due to increased supply in the market), **rational miners _want_ to mine Bitcoin to accelerate the time to the next difficulty adjustment** (which more accurately reflects the "real" difficulty of mining). The miners that endure a crypto "bear market" are at a massive competitive advantage, as we saw [with](https://www.coindesk.com/bitcoin-mining-manufacturer-hashfast-enters-chapter-11-bankruptcy) [miner](https://www.coindesk.com/bitcoin-mining-firm-cointerra-files-chapter-7-bankruptcy) [consolidation](https://www.coindesk.com/coinlabs-alydian-bankruptcy-debt-3-6m) in the last market cycle.

The nuances of Bitcoin's game theory — the fee market, miner incentives, etc. — are often mis-understood and mis-represented with appeals to narrative, rather than historicism and pragmatic analysis.

Be better than the narrative.
_Disclosure: Arjun Balaji is an analyst, engineer, and technical advisor to The Block. He founded Shomei Capital and holds bitcoin._
