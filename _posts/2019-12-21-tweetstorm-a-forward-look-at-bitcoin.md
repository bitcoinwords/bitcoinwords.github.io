---
title: "Tweetstorm: A forward look at Bitcoin"
permalink: "/tweetstorm-a-forward-look-at-bitcoin" 

author: johnnewbery

tags:
  - John Newbery
  - CY19 Q4
  - Technology
  - Roadmap
  - Tweetstorm


excerpt: John Newbery gives a glimpse of what to expect from Bitcoin. Posted December 21, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Tweetstorm: A Decade of Bitcoin Technology](https://twitter.com/jfnewbery/status/1208559196465184768)
### By [John Newbery](https://twitter.com/jfnewbery)
### Posted December 21, 2019

The end of the decade is a good time to look back and marvel at the giant strides that Bitcoin has made since Satoshi gave us the whitepaper in 2008. It's also a natural point to look forward to what the upcoming years might hold in store.

This is where I think Bitcoin is headed over the next few years. Tell me why I'm wrong and what I've missed!

The lightning protocol teams working on c-lightning ([@Blockstream](https://twitter.com/Blockstream)), eclair ([@acinq_co](https://twitter.com/acinq_co)), LND ([@lightning](https://twitter.com/lightning)) and rust lightning will continue to iterate rapidly on the lightning protocol.

All implementations now support basic multi-path payments ([https://bitcoinops.org/en/topics/multipath-payments/ …](https://bitcoinops.org/en/topics/multipath-payments/ "https://bitcoinops.org/en/topics/multipath-payments/")). We'll get better support of that as well as dual-funding, splice-in and splice-out ([https://bitcoinops.org/en/topics/splicing/ …](https://bitcoinops.org/en/topics/splicing/ "https://bitcoinops.org/en/topics/splicing/")).

Taken together, those technologies will make channel and liquidity management much easier. They'll be automated, fade into the background and user experience will improve drastically.

Lightning infrastructure will improve. [@bitfinex](https://twitter.com/bitfinex) recently added lightning deposits and withdrawals. All other exchanges, merchant service providers, custodians and wallets will follow suit or become obsolete.

We'll see more lightning wallets: a mix of non-custodial; self-custodied with outsourced routing; and fully-self-managed wallets. This is a brand new space and there'll be lots of experimentation. Different teams will find different niches to fill.

Already, wallets like [@MuunWallet](https://twitter.com/MuunWallet), [@Breez_Tech](https://twitter.com/Breez_Tech), [@PhoenixWallet](https://twitter.com/PhoenixWallet), [@ln_zap](https://twitter.com/ln_zap) and [@bluewalletio](https://twitter.com/bluewalletio) are experimenting with different models.

Tooling for lightning developers will improve. When we ran the lightning apps residency just over a year ago, the attendees spent a lot of time setting up their lightning dev environments.

Now, with Polar ([https://github.com/jamaljsr/polar](https://github.com/jamaljsr/polar "https://github.com/jamaljsr/polar")) by [@jamaljsr](https://twitter.com/jamaljsr), lightning app developers can set up a test environment with a few clicks. More and better tools will continue to appear.

With better tooling, we'll see faster innovation on the application layer. Teams at [@zebedeeio](https://twitter.com/zebedeeio), [@SatoshisGames](https://twitter.com/SatoshisGames), and others we haven't heard of yet will delight us with new and unexpected lightning experiences.

The schnorr/taproot softfork ([https://bitcoinops.org/en/topics/taproot/ …](https://bitcoinops.org/en/topics/taproot/ "https://bitcoinops.org/en/topics/taproot/")) will be activated in 2020 or 2021. That'll provide a huge improvement in fungibility, privacy, scalability and functionality. For an overview of the benefits, watch the Optech exec briefing here: [https://bitcoinops.org/en/2019-exec-briefing/#the-next-softfork …](https://bitcoinops.org/en/2019-exec-briefing/#the-next-softfork "https://bitcoinops.org/en/2019-exec-briefing/#the-next-softfork").

That'll allow lightning to upgrade from HTLCs to Payment Points. That's a big improvement for privacy and payment decorrelation, and allows 'Stuckless payments' with proofs-of-payment -- another huge boost in LN usablity.

See the [@suredbits](https://twitter.com/suredbits) series of blog posts here [https://suredbits.com/payment-points-part-1/ …](https://suredbits.com/payment-points-part-1/ "https://suredbits.com/payment-points-part-1/") for more details on Payment Points.

Even better, lightning channel opens and closes will look identical to payments to single pubkeys. The same is true for payments to k-of-n pubkey thresholds. That's good for fungibility, privacy and scalability.

In fact, with schnorr/taproot, there's almost no downside to encumbering UTXOs with advanced scripts instead of single pubkey outputs.

Cold storage UTXOs will be k-of-n multisig keytrees, and all hot wallet UTXOs will be stored in channels (with splicing-out used to make on-chain payments). When transactions hit the chain, they'll look like any other single pubkey/signature payment.

Payments into wallets will pay directly into channel open outputs (thanks to [@esneider](https://twitter.com/esneider) for pointing this out to me). There'll be no concept of an on-chain balance and an in-channel balance. Just a single, unified balance that can be used for lightning or on-chain payments.

Wallet teams will collaborate on a PayJoin payment protocol ([https://bitcoinops.org/en/topics/payjoin/ …](https://bitcoinops.org/en/topics/payjoin/ "https://bitcoinops.org/en/topics/payjoin/")). A large number of on-chain transactions will be 2-input-2-ouput transactions, vastly improving fungibility and privacy, and foiling chain analysis.

The inputs to those PayJoin transactions may be channel splice-outs, and the outputs may be channel opens, but there'll be no way to tell from observing the chain.

Eventually we'll have cross-input signature aggregation ([https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/#signature-aggregation …](https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/#signature-aggregation "https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/#signature-aggregation")), which means those PayJoin transactions will only have a single signature, and will be \*cheaper\* than regular change-producing transactions.

Larger coinjoins will be cheaper still. An advanced PayJoin payment protocol could even batch multiple payments to the same merchant/exchange and use only a single signature.

We'll get SIGHASH\_NOINPUT or SIGHASH\_ANYPREVOUT ([https://bitcoinops.org/en/topics/sighash_noinput/ …](https://bitcoinops.org/en/topics/sighash_noinput/ "https://bitcoinops.org/en/topics/sighash_noinput/")), making eltoo ([https://bitcoinops.org/en/topics/eltoo/ …](https://bitcoinops.org/en/topics/eltoo/ "https://bitcoinops.org/en/topics/eltoo/")) possible, and blurring the lines between layer 1 and layer 2 ([https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-September/002136.html …](https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-September/002136.html "https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-September/002136.html")).

That'll make lightning even more usable and allow more advanced layer 2 contracts like channel factories ([https://bitcoinops.org/en/topics/channel-factories/ …](https://bitcoinops.org/en/topics/channel-factories/ "https://bitcoinops.org/en/topics/channel-factories/")).

All these advanced features will require greater wallet interoperability. That's where miniscript ([https://bitcoinops.org/en/topics/miniscript/ …](https://bitcoinops.org/en/topics/miniscript/ "https://bitcoinops.org/en/topics/miniscript/")) comes in.

With miniscript, wallets will eventually be able to enter contracts with each other that don't require pre-templated scripts (as lightning currently does). This wallet interoperability will allow faster innovation in layer 2 contracts.

OP_CTV ([https://bitcoinops.org/en/newsletters/2019/12/04/#op-checktemplateverify-ctv …](https://bitcoinops.org/en/newsletters/2019/12/04/#op-checktemplateverify-ctv "https://bitcoinops.org/en/newsletters/2019/12/04/#op-checktemplateverify-ctv")) or some other covenant-enabling opcode will be activated, allowing richer layer 2 constructions like joinpools ([https://freenode.irclog.whitequark.org/bitcoin-wizards/2019-05-21#1558427254-1558427441 …](https://freenode.irclog.whitequark.org/bitcoin-wizards/2019-05-21#1558427254-1558427441 "https://freenode.irclog.whitequark.org/bitcoin-wizards/2019-05-21#1558427254-1558427441");).

Taken together with taproot and SIGHASH_NOINPUT, we'll get extremely rich and private off-chain contracts will be made possible.

Some of these things will happen in 2020, and some will take a bit longer, but they're all heading in the same direction: using the chain for what the chain's good for (h/t Andrew Poesltra).

That's to say: the block chain allows nodes to arrive at an agreed ledger state, while contracting and functionality move up onto layer two. Doing so is cheaper, more secure, more private and allows for more rapid innovation.

None of this is inevitable, and none can happen without the industry of many hands and the creativity of many minds. There are years of work ahead for developers, researchers, businesses and users.

If you run a Bitcoin business, you can help by supporting, sponsoring or hiring open source developers. If you're a Bitcoin user, you can help by \*demanding\* that any service you use supports the open source ecosystem.

If you're a developer, you can help by reviewing and testing PRs and releases. [https://bitcoincore.reviews/](https://bitcoincore.reviews/ "https://bitcoincore.reviews/") is a great place to start.

2020 is going to be a great year for Bitcoin and Lightning protocol development! /fin



***

{% include signup.md %}