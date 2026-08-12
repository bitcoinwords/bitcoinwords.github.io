---
title: "SegWit2X And The Case For Strong Replay Protection (And Why It's Controversial)"
permalink: "/segwit2x-and-the-case-for-strong-replay-protection-and-why-its-controversial"

author: aaronvanwirdum

tags:
  - Aaron van Wirdum
  - 2017 Q3
  - Mining
  - Money
  - Privacy

excerpt: SegWit2X And The Case For Strong Replay Protection (And Why It's Controversial). Posted September 22, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [SegWit2X And The Case For Strong Replay Protection (And Why It's Controversial)](https://bitcoinmagazine.com/articles/segwit2x-and-case-strong-replay-protection-and-why-its-controversial)
### By Aaron van Wirdum
### Posted September 22, 2017

[CULTURE](https://bitcoinmagazine.com/culture)

[Prefer us on Google](https://www.google.com/preferences/source?q=bitcoinmagazine.com) [Download App](https://apps.apple.com/us/app/bitcoin-magazine-news/id6749723428) [Download App](https://play.google.com/store/apps/details?id=com.anonymous.bmapp)

Come November, the remaining signatories of the “[New York Agreement](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77)” (NYA) plan to deploy the “SegWit2X” hard fork to double Bitcoin’s block weight limit, allowing for up to 8 megabytes of block space. Since [not](https://en.bitcoin.it/wiki/Segwit_support)[everyone](http://nob2x.org/) supports this hard fork, this could well “split” the Bitcoin network into two incompatible blockchains and currencies, not unlike Bitcoin and Bitcoin Cash (Bcash) did two months ago.

But this NYA hard fork is controversial and not only because it lacks consensus. It’s also controversial because of design choices made by the development team behind [BTC1](https://github.com/btc1), the software client associated with the New York Agreement. Perhaps most importantly, this development team, led by [Bloq](https://www.bloq.com/) CEO Jeff Garzik, has so far refused to implement replay protection, a measure that Bcash did take. Partly for this reason, at least one NYA signatory —[Wayniloans](https://www.wayniloans.com/) — has [backed out](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-September/000303.html) of the agreement.

So what is replay protection, why should BTC1 implement it … and why doesn’t it?

#### What Is Replay Protection? (And What Are Replay Attacks?)

Bitcoin could see another “split” by November. (It’s arguably more accurate to consider the “splitting” nodes and miners as an entirely new cryptocurrency with a new blockchain and token — not an actual split of Bitcoin itself.) For the purpose of this article, we’ll refer to the blockchain and currency that follows the current Bitcoin protocol as “Legacy Bitcoin” and “BTC.” The blockchain and currency that follows the New York Agreement hard fork is referred to as “SegWit2X” and “B2X.”

If this split happens, the two blockchains will be identical. All past transactions and (therefore) “balances” are copied from the Legacy Bitcoin blockchain onto the SegWit2X blockchain. Everyone who owns BTC will own a corresponding amount of B2X.

Without replay protection, new transactions will be equally valid on both chains as well. This means that these transactions can be copied or “replayed,” from one chain to the other — in other words, for them to happen on both. This is called a “replay attack.”

So, let’s say Alice holds BTC at the time of split, which means she also owns B2X after the split. Then, after the split, she wants to send BTC to Bob. So, she creates a transaction that spends BTC from one of her Legacy Bitcoin addresses to one of Bob’s Legacy Bitcoin addresses. She then transmits this transaction over the Legacy Bitcoin network for a Legacy Bitcoin miner to pick it up and include in a Legacy Bitcoin block. The payment is confirmed; all is good.

But this very same transaction is perfectly valid on the SegWit2X blockchain. Anyone — including Bob — can take Alice’s Legacy Bitcoin transaction and also transmit it over the SegWit2X network for a miner to include in a SegWit2X block. (This can even happen by accident quite easily.) If this payment is also confirmed, Alice has inadvertently sent Bob not only BTC but also an equal amount of B2X.

And, of course, all of this is true in reverse as well. If Alice sends B2X to Bob, she might accidentally send him BTC as well. A lack of replay protection, therefore, is a problem for users of both chains. No one wants to accidentally send any money — not even if it was “free money.”

Technically, there are ways to “split” coins on both chains to ensure they can only be spent on one chain. This would, for example, require newly mined coins to be mixed into a transaction. Tiime-locks can also offer solutions. But this takes effort and is not easy, especially for average users — not to mention that many average users may not even know what’s going on in the first place.

To avoid this kind of hassle, at least one side of the split could add a protocol rule to ensure that new transactions are valid on one chain but not the other. This is called replay protection.

#### Why Should BTC1 Implement Replay Protection? (And Why Not Bitcoin Core?)

In case of a split, at least one side must implement replay protection. But many — Bitcoin Core developers and others — believe there’s only one viable option. It’s the splitting party — in this case BTC1 — that should do it.

There are several arguments for this.

First of all, it makes the most sense for BTC1 to implement replay protection because that requires the least effort. BTC1 is a new client that’s already implementing new protocol rules anyway, and it’s not very widely deployed yet. It would be relatively easy for BTC1 to include replay protection.

Meanwhile, it would not be sufficient for Bitcoin Core to implement replay protection on its own. While it is dominant, and even considered by some to be the protocol-defining reference implementation, Bitcoin Core is not the only Bitcoin implementation on the network. Bitcoin Knots, Bcoin, Libbitcoin and other alternative clients would all have to implement replay protection, too. (And that’s not even taking non-full node clients into account.)

But even more importantly, the reality of the current situation is that all deployed Bitcoin nodes do not have replay protection implemented. And logically, they can’t: Some of these nodes even predate the New York Agreement. So even if Bitcoin Core and other implementations were to implement replay protection in new releases of their software, it wouldn’t suffice. All users must then also update to this new version within about two months: a very short period of time for a network-wide upgrade.

If only some of the nodes on the network upgrade to these new releases, Bitcoin could actually split in three: Legacy Bitcoin, SegWit2X and “Replay Protected Bitcoin.” Needless to say, this three-way split would probably make the problem worse — not better.

Lastly, there is a bit of a philosophical argument. Anyone who wants to adopt new protocol rules, so the argument goes, has the responsibility to split off as safely as possible. This responsibility should not fall on those who want to keep using the existing protocol: They should be free to keep using the protocol as-is.

Many developers — including [RSK](https://www.rsk.co/) founder [Sergio Lerner](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-June/000010.html) who drafted the [SegWit2Mb](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-March/013921.html) proposal on which SegWit2X is based — have argued that BTC1 should implement replay protection. In fact, many developers think that any hard fork, even a hard fork that appears entirely uncontroversial, should implement replay protection.

But so far, the BTC1 development team will [only consider](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-September/000302.html) optional replay protection.

#### What’s Wrong With Optional Replay Protection?

Implementing optional replay protection, as [proposed](https://gist.github.com/gavinandresen/2a7474a3dd5b834ed3a7d10c74ec84c5) by former Bitcoin developer Gavin Andresen, for example, is currently [on the table](https://github.com/btc1/bitcoin/issues/34) for BTC1.

In short, this type of optional replay protection would make certain specially crafted (“OP_RETURN”) Legacy Bitcoin transactions invalid on the SegWit2X chain. Anyone who’d want to split their coins could spend their BTC with such a transaction. These transactions should then confirm on the Legacy Bitcoin blockchain but not on the SegWit2X chain. This effectively splits the coins into different addresses (“outputs”) on both chains.

Such optional replay protection is probably better than nothing at all, but it’s still not a definitive solution.

One problem is that the Legacy Bitcoin blockchain would have to include all these OP_RETURN transactions. This would probably result in more transactions on the network and would require extra data for each transaction. All this data must be transmitted, verified and (at least temporarily) stored by all Legacy Bitcoin nodes. It presents a burden to the Legacy Bitcoin network.

But more importantly, it would probably still not be very easy to utilize this option. It might suffice for professional users — exchanges, wallet providers and other service providers — as well as tech-savvy individual users. But these are generally also the types of users that would be able to split their coins even without replay protection. Average users, if they are even aware of what’s going on, would probably find it much more difficult to utilize optional replay protection.

Optional replay protection, therefore, offers help to those who need it least and does little for those who need it most.

#### Does the NYA Preclude Replay Protection?

While it’s unclear what was (or is) discussed behind closed doors, the New York Agreement seems to be a very minimal agreement. Published on May 23, 2017, it really only consists of two concrete points:

* Activate Segregated Witness at an 80 percent threshold, signaling at bit 4, and

* Activate a 2 MB hard fork within six months.

With the first point completed through [BIP91](https://bitcoinmagazine.com/articles/bip91-segwit-activation-kludge-should-keep-bitcoin-whole), the only remaining point is a hard fork to 2 megabytes before November 23. (This assumes that this hard fork wasn’t completed with the creation of Bitcoin Cash which is supported by a number of NYA signatories.)

Notably, a lot of details are not filled in. For example, the agreement does not even state that signatories must specifically run the BTC1 software: Any software implementation that implements a hard fork to 2 megabytes might do. This could even include a software implementation that implements replay protection. And, of course, nothing in the NYA stops BTC1 from implementing replay protection; some signatories may have even expected it.

#### Why Won’t BTC1 Implement Replay Protection?

There are really several reasons why BTC1 — both stated and speculated — might not want to add replay protection.

The first reason is that replay protection would require [simplified payment verification (SPV) wallets](https://bitcoin.org/en/glossary/simplified-payment-verification) and some other [thin clients](https://en.bitcoin.it/wiki/Thin_Client_Security) to upgrade in order to send and receive transactions on SegWit2X. Replay protection would, therefore,[in the words of](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-July/000246.html) BTC1 developer Jeff Garzik, “break” SPV wallets; they wouldn’t be compatible with SegWit2X until upgraded.

This framing and choice of words is disputed. If SegWit2X were to implement replay protection (and if SPV wallets don’t upgrade), these wallets could still send and receive transactions on Legacy Bitcoin perfectly fine. On top of that, they wouldn’t accidentally spend B2X when they don’t mean to.

Meanwhile, if the SegWit2X chain does not implement replay protection (and if SPV-wallets don’t upgrade), users may not be sure if their wallet is receiving or sending BTC transactions or B2X transactions or both. They also may not be sure if the balance in their wallet is a BTC balance or a B2X balance or both. And if hash power moves from one chain to another over time, these wallets could even switch from displaying BTC balances to B2X balances or the other way round without users knowing. (This problem could be solved, to some extent, through [another workaround](https://github.com/btc1/bitcoin/pull/46), but this is not yet implemented in either.)

Indeed, not implementing replay protection on SegWit2X could arguably “break” SPV wallets much worse.

The only (plausible) scenario where implementing replay protection would perhaps not break SPV wallets much worse is if there is no Legacy Bitcoin to speak of. Indeed, the New York Agreement very specifically intends to “upgrade” Bitcoin, rather than split off into a new coin as Bcash did. And based on miner signaling and statements of intent by several big Bitcoin companies, some NYA signatories claim that Legacy Bitcoin will not be able to survive at all.

Implementing replay protection is, therefore, sometimes considered an admission that SegWit2X will split off from (Legacy) Bitcoin into something new and will not be considered the upgraded version of Bitcoin.

But the assumption that Legacy Bitcoin won’t be able survive is a big one. In reality, miner signaling is [effectively meaningless](https://bitcoinmagazine.com/articles/miners-are-signaling-support-new-york-agreement-heres-what-means), while Bitcoin Core — the dominant Bitcoin implementation —[will not](https://en.bitcoin.it/wiki/Segwit_support) adopt the hard fork. There is also a [significant list](http://nob2x.org/) of companies that have not stated that they support the hard fork, including two top-10 [mining pools](https://bitcoinmagazine.com/bitcoin-mining/what-are-bitcoin-mining-pools). Similarly, it’s not clear if many (individual) users will support SegWit2X either. The implementation of wipe-out protection (another safety measure) also suggests that even BTC1 developers aren’t so sure that there will only be one chain.

And perhaps even more importantly, it’s not clear that replay protection would affect any of this. If miners, developers, companies and users are to consider SegWit2X an upgrade of Bitcoin, they will probably do so with or without replay protection.

This is why it has also been [suggested](https://bitcoinmagazine.com/articles/no2x-breaking-bitcoin-shows-no-love-segwit2x-hard-fork-paris) that BTC1 is rejecting replay protection for the specific purpose of being as disruptive as possible. If the Legacy Bitcoin chain is effectively made unusable, SegWit2X might stand the best chance of being recognized as “Bitcoin.”

*For more information and debate on replay protection, also see the [the](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-July/000196.html)[relevant](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-July/000206.html)[threads](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-August/000298.html) on the SegWit2X mailing list.*

Previous article[Vaultoro Continues on Its VC Funding Road to Future Growth With Finlab AG](https://bitcoinmagazine.com/business/vaultoro-continues-its-vc-funding-road-future-growth-finlab-ag)Next article[Patientory’s Journey to Change Healthcare](https://bitcoinmagazine.com/business/patientorys-journey-change-healthcare)

RELATED ARTICLES    [CULTURE](https://bitcoinmagazine.com/culture)         [GUIDES](https://bitcoinmagazine.com/guides)         [CULTURE](https://bitcoinmagazine.com/culture)

##### LATEST NEWS

[Load more](https://bitcoinmagazine.com/articles/segwit2x-and-case-strong-replay-protection-and-why-its-controversial#)

***

{% include signup.md %}
