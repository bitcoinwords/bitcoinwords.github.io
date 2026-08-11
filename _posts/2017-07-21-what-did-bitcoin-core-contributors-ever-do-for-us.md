---
title: "What did Bitcoin Core contributors ever do for us?"
permalink: "/what-did-bitcoin-core-contributors-ever-do-for-us"

author: johnnewbery

tags:
  - John Newbery
  - 2017 Q3
  - Technology
  - Security
  - Governance

excerpt: What did Bitcoin Core contributors ever do for us?. Posted July 21, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [What did Bitcoin Core contributors ever do for us?](https://medium.com/@jfnewbery/what-did-bitcoin-core-contributors-ever-do-for-us-39fc2fedb5ef)
### By John Newbery
### Posted July 21, 2017

This afternoon, I tweeted a response to the strange suggestion that we **fire core**. I’ve ignored the fact that Bitcoin Core isn’t a person or an organization (in the traditional sense), and that everyone is perfectly free to run their own re-implementation of Bitcoin, but instead focused on a few of the things you’d need to do if you were serious about rejecting the work of the Bitcoin Core contributors.

I’ve included a mix of enhancements that have been around for one or more releases, stuff that’s going in to 0.15 right now, and longer-term development or research work. People who don’t actively follow the [bitcoin core github repository](https://github.com/bitcoin/bitcoin/) probably aren’t aware of the wide range of work that the contributors are doing. Hopefully this gives some insight into that world.

Disclaimer: I contribute to Bitcoin Core.

So here goes, what have Bitcoin Core developers ever done for us?

[libsecp256k1](https://github.com/bitcoin-core/secp256k1) is a heavily optimized library for doing elliptic curve math over Bitcoin’s secp256k1 curve. Elliptic curve math is used for creating signatures to spend transactions, and for validating signatures in transactions that you receive from the network. In addition to being several times faster than OpenSSL, libsecp256k1 has much better protection against timing, derandomization and side-channel attacks. Bottom line: transaction signing/validation is faster *and* more secure.

libsecp256k1 was mostly written by Pieter Wuille, Andrew Poelstra, Peter Dettman and Greg Maxwell, and [started being used](https://github.com/bitcoin/bitcoin/pull/6954) by Bitcoin Core in v0.12. Pieter, Andrew, Peter and Greg continue to maintain and make improvements to libsecp256k1.

Pruning allows a full node to discard old blockchain data, while still fully validating all the consensus rules. It means that users can run a Bitcoin Core node on diskspace-constrained hardware and enjoy the **exact same** security of running a full node. The blockchain is now over 125GB, but a pruning node can be fully synced to the network with just 2–3GB of disk storage.

[Automatic pruning functionality](https://github.com/bitcoin/bitcoin/pull/5863) was added in Bitcoin Core V0.11. The code was mostly written by Suhas Daftuar, Alex Morcos, Adam Weiss and Brad Andrews. Pruning was further improved in V0.14 to [allow pruning to be run manually by the user](https://github.com/bitcoin/bitcoin/pull/7871). Principal contributors were Brad Andrews and Russ Yanofsky.

Multiwallet is a long-requested and wanted feature that has finally been merged in v0.15 🎉. This allows users to have completely segregated wallets, for use-cases such as separating business and personal accounts or having wallets for different purposes running concurrently. We don’t yet have separate authentication for different users, but future versions may allow multiple users to safely access different wallets on the same Bitcoin node.

Luke Dashjr contributed [multiwallet](https://github.com/bitcoin/bitcoin/pull/8694) in V0.15. The [RPC interface](https://github.com/bitcoin/bitcoin/pull/10849) was provided by Jonas Schnelli.

Having a fast, efficient networking layer is essential for quick block/transaction propagation and the overall health of the network. The faster that blocks are able to propagate through the network, the lower the block orphan rate, and the more secure the network is.

Cory Fields has been doing continued work to refactor the networking code for several releases, with a [major and significant improvement](https://github.com/bitcoin/bitcoin/pull/9441) delivered in V0.14. V0.15 and future releases will continue to see improvements in cleaning up and isolating the network code from the server code.

One of the most exciting [benefits of segregated witness](https://bitcoin.org/en/release/v0.13.1#segregated-witness-soft-fork) is that it gives us the ability to upgrade the scripting language. There are several exciting script upgrades under investigation, but the one that will probably get most attention in upcoming releases is Schnorr signature support. Schnorr signatures are an alternative signature scheme to the currently used ECDSA which allow multiple signatures to be added together or ‘aggregated’. This is a win for scalability (since if multiple signature are added together, the aggregated signatures takes up only as much space as one of input signatures), validation cost (since only one signature needs to be validated instead of many) and privacy (since an aggregated signature doesn’t reveal whether the input was a single signature or many signatures).

Greg Maxwell, Pieter Wuille and Andrew Poesltra have been [investigating Schnorr signature aggregation](https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/), particularly working to make sure that the aggregation scheme is safe from the *signature cancellation* problem.

Currently, Bitcoin Core exists as a single process, with shared memory access between the network code, consensus code, wallet code and user interface code. Ideally we’d like to separate the wallet into a separate process, so if the networking function was hacked or compromised, your wallet function and private keys would be safer.

Russ Yanofsky has been [doing the groundwork for process separation](https://github.com/bitcoin/bitcoin/pull/10102) during V0.15. Look out for further progress in this area in V0.16 and V0.17.

Every transaction submitted to the Bitcoin network attaches a user-chosen fee, which goes to the miner who confirms that transaction in a block. Set the fee too low and your transaction won’t get confirmed in a block. Set it too high and you’ve donated money to the miner unnecessarily. Between those two extremes is a continuum of where to set your fee — a high fee will probably get you confirmed in the next block, a slightly lower fee might see your transaction confirmed in the next 3 or 4 blocks, and even lower than that and your transaction could take a few hours to get confirmed. Choosing the correct fee for your transaction is a hard problem, requiring knowledge of the current state of the network and some smarts to predict what will happen depending on where you set the fee.

Alex Morcos has [spent a lot of time thinking about and analyzing fee strategies](https://gist.github.com/morcos/d3637f015bc4e607e1fd10d8351e9f41) and [significantly improved the fee logic](https://github.com/bitcoin/bitcoin/pull/10199) in V0.15.

Bitcoin Core runs multiple threads so different tasks can be run in parallel on a multi-core computer. However, a lot of the functions grab a ‘global lock’ before doing their work, and other threads need to wait for that global lock to be released before they can do continue with their work. Result: Bitcoin Core is not as able to do as much work in parallel as we’d like. If we can reduce the places where that global lock is grabbed and held, then Bitcoin Core would be able to things like run wallet tasks, validate blocks and serve blocks and transactions to peers simultaneously .

This is **very** delicate work and requires a deep understanding of Bitcoin Core’s multi-threading model. Get it wrong and you could easily cause crashes or memory corruption. Matt Corallo has done [a lot](https://github.com/bitcoin/bitcoin/pull/9725) of [the](https://github.com/bitcoin/bitcoin/pull/9605) [plumbing](https://github.com/bitcoin/bitcoin/pull/10178) [work](https://github.com/bitcoin/bitcoin/pull/10179) for this in V0.15. We should see some major payoff for that work in V0.16.

Several companies now offer hardware wallets, which allow you to keep your private keys and signing code on a dedicated security device. That’s a much, much more secure model than having you private keys on a network-connected computer, which could potentially get hacked. Sadly there’s no standardized interface for hardware wallets, so each vendor provides their own software wallet to use with their hardware wallet. It’d be great if Bitcoin Core could support hardware wallets so users could benefit from running fully hardware-separated signing code behind the most secure Bitcoin full node.

HWW support is probably at least a couple of releases away, but Jonas Schnelli and Nicolas Dorier have already been doing some [early](https://github.com/bitcoin/bitcoin/pull/9728) [work](https://github.com/bitcoin/bitcoin/pull/9662) to make sure that Bitcoin Core is ready for HWW support. Hopefully we’ll see some more progress on this in V0.16 or V0.17.

Of course, none of these code changes would be of any use at all if we didn’t have repository maintainers to do the work of signing and merging all the commits, making sure translations are ready, preparing release notes, and doing all the other things that turn a bunch of code changes into a software product that normal people can run. Wladimir van der Laan is lead maintainer and has been tirelessly doing that work for many releases. Everyone in the Bitcoin community owes him a huge debt of gratitude.

I’ve tried to give shout-outs to the main contributors behind each of these features. Open-source software is a collaborative activity and there are far more who have contributed code, review, testing time, documentation and much more to these and other initiatives. If I’ve made any egregious omissions, please accept my apologies and message me on twitter so I can set the record straight!

***

{% include signup.md %}
