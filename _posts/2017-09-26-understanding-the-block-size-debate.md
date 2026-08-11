---
title: "Understanding the Block Size Debate"
permalink: "/understanding-the-block-size-debate"

author: jordanclifford

tags:
  - Jordan Clifford
  - 2017 Q3
  - Mining
  - Scaling
  - History

excerpt: Understanding the Block Size Debate. Posted September 26, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Understanding the Block Size Debate](https://medium.com/@jcliff/understanding-the-block-size-debate-351bdbaaa38)
### By Jordan Clifford
### Posted September 26, 2017

### The crux of the issue

##### Background

No issue in the history of cryptocurrencies has been debated as passionately, as often, or as forcefully as the bitcoin block size. To an outsider, it must be quite comical to witness folks debating a consensus parameter within the bitcoin network — no joke — as if it were a matter of life or death. To insiders, the stakes are high, tribal lines are drawn, and crossing them risks your reputation among your peers.

The block size limit entered the world innocuously enough. A maximum block size limit of 1MB was added by Satoshi Nakamoto without any fanfare, or even any explanation, in July of 2010. Satoshi’s intent remains a debated topic, yet the parameter’s effect is clear — it limits the size of a block, the size of the batch of updates to the global ledger.

Recall that the Bitcoin network batches transactions into blocks that are released to the network approximately every ten minutes. To participate in the bitcoin network without a trusted third party, *all* *of this blockchain data* must be downloaded and verified in more or less real time. The more data that needs to be downloaded and verified to keep pace with the network, the larger the system requirements (bandwidth, cpu, storage) will necessarily be.

The Bitcoin max block size limits the rate at which information is etched into the blockchain. Essentially, it acts to throttle the entire system. This limits the number of “on-chain” transactions that can be processed. The parameter’s value is of great consequence as it dictates the transactional throughput of the base layer. It also dictates the system requirements for participating in Bitcoin without needing to trust another party.

##### Let the debate begin

Chronicling the debate in its entirety is outside the scope of this post. There are too many characters, complexities and interactions to capture them all, but a few defining moments stand out.

The earliest moments of the debate can be seen in [this seminal post from Jeff Garzik](https://bitcointalk.org/index.php?topic=1347.0) in 2010. Jeff is one of the earliest contributors to Bitcoin, first committing to the project in March of 2011. Jeff thought Bitcoin supporting more than 3–10 tps (transactions per second) would win Bitcoin favor in the court of public opinion. He offered a simple patch to scale up the network to Visa levels. Theymos, moderator of [bitcointalk.org](http://bitcointalk.org) and [/r/Bitcoin](https://www.reddit.com/r/bitcoin), correctly pointed out this is a consensus parameter change, and deployment would need to be coordinated across the network. The patch was rejected.

The thread went dormant after Satoshi suggested that the change could be later phased in when needed. Satoshi left the community before executing on his strategy. Gavin Andresen took over in 2010 after Satoshi disappeared. He stewarded the project until 2014 when he stepped back to focus on the longer term vision for Bitcoin.

Discussion and debate of the block size would linger as background noise until Gavin posted a [series](http://gavinandresen.ninja/time-to-roll-out-bigger-blocks) [of](http://gavinandresen.ninja/why-increasing-the-max-block-size-is-urgent) [blog](http://gavinandresen.ninja/it-must-be-done-but-is-not-a-panacea) [posts](http://gavinandresen.ninja/block-size-and-miner-fees-again) [in](http://gavinandresen.ninja/does-more-transactions-necessarily-mean-more-centralized) [May](http://gavinandresen.ninja/big-blocks-and-tor) [of](http://gavinandresen.ninja/utxo-uhoh) [2015](http://gavinandresen.ninja/are-bigger-blocks-better-for-bigger-miners). The [debate stage was now set](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-May/007869.html), but without Satoshi, the Bitcoin community at large would struggle for years to converge on a path forward.

##### All in favor

> The existing Visa credit card network processes about 15 million Internet purchases per day worldwide. Bitcoin can already scale much larger than that with existing hardware for a fraction of the cost. It never really hits a scale ceiling. If you’re interested, I can go over the ways it would cope with extreme size.

> — Satoshi Nakamoto, April 2009

Proponents of increasing the block size primarily argue one reason to raise the block size: capacity. If bitcoin is going to become a useful global currency, then it must have enough transactional capacity to service its users’ needs. Not just the users of today or yesterday, mind you, but the users of the future as well.

Big blockers contend that larger blocks allows room for more users and makes Bitcoin more useful as money and more competitive as a payment solution. They believe that Bitcoin is ultimately a product that must compete in the market for adoption. A congested network with slow confirmation times and high fees pushes users elsewhere — an outcome that should be avoided.

Furthermore, many believe capacity should not be subject to an enforced production quota at all. Rather, Bitcoin miners should be allowed to produce additional capacity until [supply meets demand](https://scalingbitcoin.org/papers/transaction-fee-market-exists-without-block-size-limit.pdf). A planned quota introduces economic inefficiency by preventing mutually consensual activity.

Additionally, many big blockers posit that [larger blocks would not adversely impact decentralization](https://news.bitcoin.com/bigger-blocks-means-decentralization-bitcoin/). With a larger block size, the network would accommodate more users with cheaper fees — enticing more parties to join. While larger blocks may raise the barrier to entry for participation, big blockers argue it would actually diffuse control over more parties.

##### All opposed

> The decentralized Bitcoin blockchain is globally shared broadcast medium — probably the most insanely inefficient mode of communication ever devised by man.

> — Gregory Maxwell, September 2016

Opponents to a block size argue that increasing the block size limit is unimaginative, offers only temporary relief, and damages decentralization by increasing costs of participation. Increasing the block size may set dangerous precedent for future increases. Additionally, introducing a social/technical process for a hard fork risks that very same process becoming a future attack vector within Bitcoin.

Small blockers argue that effort should instead be spent optimizing use of the block space we already have. They favor scaling solutions that [push transactions off chain](https://lightning.network/), and have no problem being patient while they are developed.

Small blockers believe Bitcoin’s main value proposition is its censorship-resistant nature and ability to minimize needed trust. They contend that these properties can only come from a Bitcoin that cannot be controlled. To evade control [read: attacks] from government regulators, mining cartels, and other adversaries, the system should strive to remain maximally decentralized, avoiding single points of failure or control.

In order to preserve decentralization, system requirements to participate should be kept low. To understand this, consider an extreme example: very big blocks (1GB+) would require data center level resources to validate the blockchain. This would preclude all but the wealthiest individuals from participating.

A low barrier to entry preserves the ability for individuals and small parties to participate fully in the network, without needing trusted third parties. Small blocks also increase network nimbleness by reducing the time it takes to bring new nodes online. This allows seamless network reconfigurations in the event of an attack.

##### Who’s in charge anyway?

With so many stakeholders with very different priorities, the scaling debate has failed to converge. The Bitcoin network must stay in consensus with itself, so without different factions able to agree on a path forward, the status quo prevails. As a meta problem, creating a process to increase the block size remains controversial. Any process, action and/or inaction results in winners, losers, and possibly dangerous precedent.

The small blockers prefer not to change the block size limit, believing that it is too risky. They instead argue for a proposal called Segregated Witness (SegWit), a backwards compatible change that allows for [additional capacity](https://bitcoincore.org/en/2016/01/26/segwit-benefits/#block-capacitysize-increase), opens the door to future [scaling improvements](https://bitcoincore.org/en/2016/01/26/segwit-benefits/#script-versioning), and also changes the fee calculus to help [combat bloat](https://bitcoincore.org/en/2016/01/26/segwit-benefits/#reducing-utxo-growth).

Big blockers worry that activating SegWit, especially without being paired with a simple block size increase, puts a nail in the coffin in the idea of Bitcoin ever acting as a scaled payment network. Miners like Jihan Wu refused for months to activate SegWit without a block size increase.

##### Compromise?

Compromise efforts have given us signed agreements attempting to bust the stalemate, notably the [Hong Kong agreement](https://medium.com/@bitcoinroundtable/bitcoin-roundtable-consensus-266d475a61ff) in Feb 2016 (SegWit + 2MB), and more recently the [New York Agreement (NYA)](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77) in May 2017 (essentially identical to the Hong Kong agreement). However, these proposals to modify the block size limit have run in to staunch resistance.

The NYA — an active proposal set to activate SegWit followed by a doubling of the block size within 6 months — does not satisfy everyone. Big blockers and small blockers alike groan that the agreement may ruin Bitcoin. Small blockers believe a hard fork block size increase is not needed, and a closed door meeting deciding Bitcoin’s fate is a deal breaker, while big blockers argue that the agreement vindicates the small block philosophy, offering only temporary relief without enough future capacity growth.

##### What’s next?

Differences in priorities and visions have already led to a permanent split in the community. On August 1st, 2017, a minority contingent of miners and exchanges, upset with the the prioritization of SegWit and lack movement on the block size, launched [Bitcoin Cash](https://medium.com/@linda.xie/a-beginners-guide-to-bitcoin-cash-34b003f357c8).

In November of this year, it looks likely that we have the ingredients for another split. Jeff Garzik’s [btc1 project](https://github.com/btc1/bitcoin/) aims to become the new Bitcoin [reference client](https://en.wikipedia.org/wiki/Reference_implementation) upon activating a 2MB hard fork, completing the NYA agreement. The NYA currently boasts signaling from [90+% of the hash rate](https://coin.dance/blocks#proposals) and support from some of the most prominent Bitcoin companies [Coinbase, BitPay, Bitmain, etc.]. Core developers remain [vehemently opposed to the agreement](https://en.bitcoin.it/wiki/Segwit_support#Developers).

Ultimately, Bitcoin is an anarchic system. There is no official governance structure to it, which can be a feature or a bug, depending on your point of view. Disputes are settled via code that users choose to run and the tokens they choose to value. Exchanges and miners are two important [Schelling points](https://en.wikipedia.org/wiki/Focal_point_%28game_theory%29) for coordination on which software version to run. The Bitcoin Core developers also have sway over many users. However, it’s ultimately up to the market [read: millions of users] to decide what Bitcoin is.

***

{% include signup.md %}
