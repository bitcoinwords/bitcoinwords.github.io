---
title: "How to bribe miners to re-org?"
permalink: "/how-to-bribe-miners-to-re-org" 

tags:
  - Tamas Blummer
  - CY19 Q2

excerpt: Tamas Blummer shares a scenario of a Bitcoin reorg. Posted May 8, 2019.

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


# [How to bribe miners to re-org?](https://medium.com/@tamas.blummer/how-to-bribe-miners-to-re-org-d48025cb3788)
### By [Tamas Blummer](https://medium.com/@tamas.blummer)
### Posted May 8, 2019

_Organizing a re-org to revert a Bitcoin transaction was recently considered but not attempted Binance. They could have done it, would they had better understanding the technology and POW economics. I describe how to bribe miners so they unite for a re-org._

A bitcoin transaction economically matters only if it is recorded in the chain of blocks with most work.

There are already 111 blocks built on top of the block containing the Binance hacker's [transaction](https://blockstream.info/tx/e8b406091959700dbffcff30a60b190133721e5c39e89bb5fe23c5a554ab05ea) by the time of this writing. It is safe to say now, that Binance lost 7000 Bitcoins.

![](/assets/images/cy19/cy19q2m5/tamas-1.png){: .align-center}Block 575011 contains the hacker's transaction and further blocks were mined as usual on top of it.

Bitcoins lost to the hacker could be re-claimed if miner would build an alternate continuation of the chain that roots before the block that contains the hacker's transaction. That alternate continuation would not contain the hacker's transaction and would have to grow faster than the current one, so at some point it exhibits more work and all Bitcoin clients re-org to it. After the re-org the hacker's transaction would ceases to exist in the memory of the network.

![](/assets/images/cy19/cy19q2m5/tamas-2.png){: .align-center}The earlier versions of blocks 575012 and higher would then cease to exist in the memory of the network.

Re-orgs to an alternate chain with higher work are nothing special for the network, but its regular method of resolving the race between independently working miner. Re-orgs that replace the most recent block are quite frequent.

A re-org is costly for the miner who mined on the side that ceases to exist, since the miner loses the Bitcoins mined in those blocks. This is the main reason why miner are keen to extend the chain and avoid creating alternatives.

[Binance CEO considered](https://twitter.com/binance/status/1125959459782553600) to offer the stolen funds to miner who build an alternate chain of blocks. He can offer those funds in the alternate chain since they would remain in his control there. He [rejected the plan](https://twitter.com/cz_binance/status/1126002001093939200) as he thought it was impractical. It is impractical if considered within the bounds of collusion between his friends and network, but would have been possible if he was prepared, knowledgeable and quick.

### How to bribe the miners

Besides calling friends Binance CEO could have done the following as soon as the breach is noticed:

1. Create a transaction that spends a big chunk of the stolen funds from their last controlled address to a bribe address and publish the transaction on their web site.
2. Publish the private key of the bribe address on their website.

The transaction is worthless in the current reality since the funds are at the Hacker's address, but is perfectly valid in an alternate reality that starts with an alternate block 575012.

A miner who builds an alternate 575012 can include the transaction published on the website and also another transaction that moves the bribe to his own address, since he also knows the private key for the bribe address.

![](/assets/images/cy19/cy19q2m5/tamas-3.png){: .align-center}

It is rational for a miner to mine that alternate reality if the bribe is higher than the amount of Bitcoins he mined since Block 575011 **and** there is a sufficient chance that the alternate reality will attract more work than the current chain.

Note that the miner can significantly increase the chances of the alternate reality taking over by not taking the entire bribe but leaving sufficient amount for the next miner.

![](/assets/images/cy19/cy19q2m5/tamas-4.png){: .align-center}

A sufficiently hight bribe and not too greedy split of it can build a coalition for the alternate reality quickly and more efficiently than calling friends as any miner is invited and could be attracted to join.

Eventually the chain of miner splitting the bribe could overtake the current chain and in the new reality after the re-org Binance would own the rest of the stolen funds and miner who participated in the rescue would have earned much more than usual.

I know that above rescue is technically feasible. It would work if those who can lose funds are prepared to offer a bribe and miner are prepared to act on it and make rational choices. Chances of success still diminish exponentially with time.

Exchanges could commit in advance to use this procedure in the unlikely event of losing funds, so miner are also prepared to act swiftly on the offers.

### Consequences?

Consequences of miners acting on a bribe could be severe as the re-org can disrupt regular transaction processing and diminish trust into the block chains immutability.

Damages would be proportional to the length of the re-org. I think damage would be negligible if the rescue maneuver is executed within hours as a re-org of a few blocks is not an event in the technical sense and would not noticeably delay regular transaction processing.

### Addendum

_After publishing above, I participated in a few public discussions and the most prominent objection against the described procedure was that the hacker could counter the bribe on the original chain. While this is technically correct, it neglects that miner who would take that offer would become complicit and target of lawsuits. Even anonymous miner were vary of taking those coins as they could not be sold in short term to cover their electricity cost, also being associated with coins in high interest could dox them._
