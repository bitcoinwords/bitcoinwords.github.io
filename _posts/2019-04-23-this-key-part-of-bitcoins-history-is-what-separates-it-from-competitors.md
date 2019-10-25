---
title: "This Key Part Of Bitcoin's History Is What Separates It From Competitors"
permalink: "/this-key-part-of-bitcoins-history-is-what-separates-it-from-competitors" 

tags:
  - Kyle Torpey
  - CY19 Q2

excerpt: Kyle Torpey reminds us of Bitcoin history and why it's so different from the competition. Posted April 23, 2019.

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

# [This Key Part Of Bitcoin's History Is What Separates It From Competitors](https://www.forbes.com/sites/ktorpey/2019/04/23/this-key-part-of-bitcoins-history-is-what-separates-it-from-competitors/#32c0b303ae5e)
### By [Kyle Torpey](https://www.forbes.com/sites/ktorpey/)
### Posted April 23, 2019


There are thousands of different cryptocurrencies in existence today, but bitcoin is still king. In addition to a community ethos that [prioritizes stability and soundness over implementing experimental new features](https://www.forbes.com/sites/ktorpey/2019/01/24/heres-the-critical-difference-between-bitcoin-and-other-crypto-assets/#11050e902797), there is one particular event in Bitcoin's history that clearly illustrates why it is still viewed as the gold standard of cryptocurrencies.
In 2016, code that was intended to lead to the activation of a Bitcoin improvement known as Segregated Witness (SegWit) was made available via a new release of [Bitcoin Core](https://bitcoincore.org/). At the time, this was mainly viewed as nothing more than a technical upgrade (although there was [some disagreement regarding how the upgrade should be implemented](http://gavinandresen.ninja/segregated-witness-is-cool)) that would bring [a variety of benefits to the network](https://bitcoincore.org/en/2016/01/26/segwit-benefits/), including laying the foundation for layer-two payment protocols like the [Lightning Network](https://www.forbes.com/sites/ktorpey/2017/12/28/will-bitcoins-lightning-network-kill-off-altcoins-focused-on-cheap-transactions/).

However, the activation of this seemingly innocuous technical improvement eventually became highly politicized. This politicization of SegWit was recently discussed during a panel at the [Understanding Bitcoin](https://understandingbtc.com) conference in Malta.

## SegWit Gets Political 

"I would say overall that SegWit itself, even among miners, was not really all that controversial in it of itself so much as some miners also wanted a [hard fork](https://bitcoin.org/en/glossary/hard-fork) block size increase at the same time, which is for a number of reasons much more difficult than a [soft fork](https://bitcoin.org/en/glossary/soft-fork). Hard forks require — there's a lot more things that can go wrong essentially there," explained [James Hilliard](https://twitter.com/james_hilliard), a bitcoin mining software developer and consultant.

It was Hilliard's [Bitcoin Improvement Proposal 91](https://bitcoinmagazine.com/articles/bip91-segwit-activation-kludge-should-keep-bitcoin-whole/) (BIP 91) [that would eventually help prevent a split of the Bitcoin network](https://coinjournal.net/bitcoin-now-likely-get-segwit-august-1st-avoid-chain-split/) caused by differing visions of how the system should scale to accomodate more users. The two main scaling proposals at the time were (1) a [user-activated soft fork](https://en.wikipedia.org/wiki/User_activated_soft_fork) (UASF) of SegWit via [Bitcoin Improvement Proposal 148](https://github.com/bitcoin/bips/blob/master/bip-0148.mediawiki) (BIP 148) or (2) a combination of a soft fork activation of SegWit once 80 percent of the network hashrate had signalled their readiness for the improvement combined with a hard-forking increase to the block size limit.

The second of those two proposals came out of an infamous meeting of bitcoin stakeholders and company representatives during the Consensus 2017 conference. Other individuals and companies eventually announced their support for the proposal by adding their names to the public version of the so-called [New York Agreement](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77).

BIP 148 on the other hand was a proposal from a single pseudonymous developer named [Shaolinfry](https://github.com/shaolinfry).

![](/assets/images/cy19/cy19q2m4/torpey-1.png){: .align-center}*Shaolinfry's proposal to simply activate SegWit won out over a plan from some of the largest companies in the Bitcoin ecosystem.*

Hilliard's solution combined these two proposals on the basis of what they had in common: the activation of SegWit via a soft fork.

"[BIP 91] was designed to activate, assuming enough miners ran it quickly, before the user-activated soft fork date," said Hilliard.
[SatoshiLabs](https://satoshilabs.com/) CEO [Marek "Slush" Palatinus](https://twitter.com/slush), who created the world's first bitcoin mining pool known as Slushpool, agreed with Hilliard's assessment of how SegWit became politicized.

"We were in favor of UASF because we believed that SegWit is actually not controversial and it was just misused for some political gain," said Palatinus.

Bitrefill CCO [John Carvalho](https://twitter.com/bitcoinerrorlog) also agreed and explained that the key mistake developers had made was to use [Bitcoin Improvement Proposal 9](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki) (BIP 9) for SegWit's activation process.

BIP 9 is an activation method for soft fork upgrades that requires 95% of the network hashrate (miners) to signal support for an improvement before it activates. Although this was mainly intended to be a mechanism to ensure that miners were upgraded before a soft fork was activated (non-upgraded miners could end up mining invalid blocks after activation), some miners took this as an opportunity to reframe the process as a vote among miners to decide whether or not SegWit should be allowed to activate on the network.

"It put too much power in the hands of the miners. And so, this caused political tension," said Carvalho.

Due to these issues with BIP 9, some Bitcoin Core contributors have [indicated](https://bitcoinmagazine.com/articles/lombrozo-bitcoin-core-developers-may-never-use-miner-focused-bip-9-signaling-again1/) this activation mechanism may never be used again.

## UASF Defines the Roles of Miners and Node Operators

According to Carvalho, the initial UASF proposal for SegWit was a response to the politicization of the activation process by miners.

"UASF was basically a way for the nodes to express themselves and say, 'Miners, we only want these kinds of [blocks](https://bitcoin.org/en/glossary/block), and if you don't give us these kinds of blocks, your blocks will be rejected,'" explained Carvalho.

In Carvalho's view, this clearly defined the roles of miners and node operators in the Bitcoin network.

"Nodes are demanding blocks from miners and miners are supplying blocks — nothing more . . . If the market decides that it wants certain types of blocks with new rules, added rules, then the miners have to capitulate. And UASF never actually had to activate. They capitulated before because they knew that if they let it actually happen, there would be chaos for themselves," explained Carvalho.

## No2x

While Hilliard's BIP 91 solution allowed everyone to stay on the same page over the short term, those who had signed the New York Agreement were still planning to push forward with a hard fork attempt later in the year. However, the planned hard fork attempt was abandoned after it was made clear via [a futures market on bitcoin exchange Bitfinex](https://twitter.com/kyletorpey/status/928014749060788224) and other data points that the new 2x chain forked from Bitcoin would not have sufficient economic support.

According to Bull Bitcoin CEO [Francis Pouliot](https://twitter.com/francispouliot_), this was the moment in time that made it crystal clear all users, not just miners, are in control of Bitcoin's consensus rules ([see this previous post from that time period on this point](https://www.forbes.com/sites/ktorpey/2017/11/30/2017-was-the-year-when-everyone-finally-learned-bitcoin-isnt-controlled-by-miners/)).

"We now can point to a specific point in time, an actual event (No2x). It's proof. It's proof that the miners don't decide the rules," said Pouliot during the Understanding Bitcoin panel.

"As far as I'm concerned, conceptually, the main difference between Bitcoin and, for example, Ethereum in terms of consensus is No2x," Pouliot continued. "2x would have happened on any other blockchain, and it didn't happen on Bitcoin. And it was a very defining moment for Bitcoin in terms of that aspect of the governance."

In other words, Bitcoin has proven itself sufficiently decentralized in order to resist [perceived corporate takeovers](https://www.forbes.com/sites/ktorpey/2017/10/31/is-bitcoin-facing-a-corporate-takeover-via-the-2x-fork-a-developer-and-a-business-leader-debate/) by the largest wallet software providers, exchanges, and miners in the industry ([see this point for an explanation of this point in further detail](https://www.forbes.com/sites/ktorpey/2017/11/09/failure-segwit2x-shows-bitcoin-digital-gold-not-paypal/)). No other cryptocurrency has faced this sort of test up to this point.

The closest thing to an equal test experienced by an altcoin would likely be the pressure Ethereum users faced to hard fork in reaction to the hacking of The DAO. In the end, the hard fork was implemented and the vast majority of users followed (leaving a minority on the chain now known as Ethereum Classic).

It should be noted that Ethereum's test was relatively early in the development of that particular cryptocurrency network, so it's possible Ethereum has become more resistant to these sorts of social or political pressures. Having said that, it's difficult to judge how much sway important actors in the network, such as the Ethereum creator [Vitalik Buterin](https://twitter.com/vitalikbuterin) and blockchain technology firm [Consensys](https://www.theblockcrypto.com/2019/01/10/the-burden-of-infura/), still have when it comes to hard forks.
