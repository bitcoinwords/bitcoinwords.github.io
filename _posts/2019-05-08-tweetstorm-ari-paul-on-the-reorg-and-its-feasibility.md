---
title: "Tweetstorm: Ari Paul on the reorg and it's feasibility"
permalink: "/tweetstorm-ari-paul-on-the-reorg-and-its-feasibility" 

tags:
  - Ari Paul
  - CY19 Q2

excerpt: Ari Paul lays out the feasibility of a Bitcoin chain reorg. Posted May 8, 2019.

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

{% include donation.md %}

# [Tweetstorm: Ari Paul on the reorg and it's feasibility](https://twitter.com/AriDavidPaul/status/1126095599449845761)
### By [Ari Paul](https://twitter.com/AriDavidPaul)
### Posted May 7, 2019

* There's a bit of superficial discussion happening (mostly dismissal) of CZ of binance's exploration of reorganizing the blockchain to reverse binance's recent hack. Here's why such a rollback is plausible in a future case (whether we want it to be plausible or not.)
* 2/first, I'm not commenting at all on what I want to happen or what's good for bitcoin. I'm going to argue reorgs in these scenarios may be a natural result of the game theory for bitcoin that Satoshi created.
* 3/this hack was relatively small, but consider Bitfinex's previous hack of 117k+ BTC, which was 30+ days of block rewards. If Bitfinex could create a smart contract to programmatically incentivize miners to re-org 3 days of the blockchain, the simple economic incentives work.
* 4/ then the question is coordination. A reorganization requires 50%+ of hashpower, but doesn't require conscious coordination. If no one miner had more than 1% hashpower, and all were truly anonymous, might raw incentives serve to coordinate a reorganization?
* 5/ I'm not aware of how you could structure such incentives entirely within the bitcoin network itself. The logic of the smart contract would, I think, have to refer to whether a re-org has occurred. The incentives might have to be provided on another layer or network.
* 6/ but I'm probably missing some simple clever in-network incentive structures. Regardless, there's a pie of BTC value that could be programmatically cut to incentivize the reorg for any and every miner, considering only mining economics.
* 7/ if the exchange is incentivized to attempt this, and all rational miners are incentivized to take the deal, why wouldn't the re-org happen? Only one answer I believe - we have to hope the miners act uneconomically in the short-term due to altruism, or non-mining incentives.
* 8/ many miners *are* incentivized by things other than mining math. They have other economic incentives like the value of their ASICs or BTC on balance sheet. It would come down to miner incentives in the reorg payoff vs devaluation of their ASICS or BTC.
* 9/ for any one small miner, they could sell their BTC at market, so more decentralization is actually *worse* in this regard since it makes miner BTC holdings more liquid (smaller relative to market liquidity.) same might apply for secondary ASIC market.
* 10/ in a world where miners don't have to own their ASICS and don't generally hold a bunch of BTC, there would be really clear economic incentives for the re-org to happen. But what about the real world where miners do own ASICs?
* 11/ here it might be a prisoner's dilemma, I'm not clear on the right game theory model. Collectively miners might be hurt by the re-org devaluing their hardware, but every individual miner is incentivized to re-org. Re-org is binary though, different from typical prisoner's.
* 12/if the exchange could think of a way to reward every miner that supports the re-org more than those who oppose it, that might be enough to cause the reorg by turning this into a classic prisoner's dilemma.
* 13/is this a bad thing for Bitcoin? Maybe. One way to think about all of this is just as a cypherpunk free market rising organically from Satoshi's competitive mining game theory solution for BFT. It's just economic actors playing the game.
* 14/what result might this have? For average users, probably none. Average transactions would almost certainly be included in the re-organized chain. So this would probably only be relevant to giant, "fast" transactions separated from the legal system. exchange withdrawals.
* 15/does our twitter conversation on this topic matter or is this just shouting into the wind and it's all up to miner incentives? Twitter actually matters a little here, since we're effectively increasing the cost of the reorg to miners.
* 16/by strengthening the social consensus around immutability, we imply a large devaluation in BTC price should such a reorg occur, which incentivizes miners who own ASICS or BTC not to reorg in marginal cases.
* 17/as part of that social consensus building, I expect the self-appointed social media bitcoin priests to attack this thread. It's kind of their job to vigorously support the immutability social consensus. Have at it you self-appointed social consensus guardians 😀
* 18/a final thought inspired by the brilliant Adam Back (but disagreeing with him.). Past data is useless here. Incentivizing a reorg is a hard coordination problem that fairly simple new tech may solve.![](/assets/images/cy19/cy19q2m5/ari-1.png){: .align-center}
* 19/another final thought again inspired by Adam. Most of the logic in this thread could be changed if node operators ran software that didn't blindly follow the longest chain. Such software may be provided eventually, some Core devs have worked on it.
