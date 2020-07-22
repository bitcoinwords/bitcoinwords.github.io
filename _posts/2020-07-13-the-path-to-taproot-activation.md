---
title: "The Path to Taproot Activation"
permalink: "/the-path-to-taproot-activation"

author: almkglor

tags:
  - almkglor
  - 2020 M7
  - Taproot
  - Technical
  - UASF

excerpt: almkglor provides an overview of how we will enable Taproot. Posted June 13, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Path to Taproot Activation](https://old.reddit.com/r/Bitcoin/comments/hqzp14/technical_the_path_to_taproot_activation/)
### By [almkglor](https://old.reddit.com/user/almkglor)
### Posted June 13, 2020

Taproot! Everybody wants to have it, somebody wants to make it, nobody knows how to get it!

(If you are asking why everybody wants it, see: [Technical: Taproot: Why Activate?](https://old.reddit.com/r/Bitcoin/comments/hrlpnc/technical_taproot_why_activate/))

(Pedants: I mostly elide over lockin times)

Briefly, Taproot is that neat new thing that gets us:

*   Multisignatures (n-of-n, k-of-n) that are just 1 signature (1-of-1) in length!! (MuSig/Schnorr)
*   Better privacy!! If all contract participants can agree, just use a multisignature. If there is a dispute, show the contract publicly and have the Bitcoin network resolve it (Taproot/MAST).
*   Activation lets devs work get back to work on the even newer stuff like!!!
    *   Cross-input signature aggregation!! (transaction with multiple inputs can have a single signature for all inputs) --- needs Schnorr, but some more work needed to ensure that the interactions with SCRIPT are okay.
    *   Block validation - Schnorr signatures for all taproot spends in a block can be validated in a single operation instead of for each transaction!! Speed up validation and maybe we can actually afford to increase block sizes (maybe)!!
    *   `SIGHASH_ANYPREVOUT` \- you know, for Decker-Russell-Osuntokun ("eltoo") magic!!!
    *   `OP_CHECKTEMPLATEVERIFY` \- vaulty vaults without requiring storing signatures, just transaction details!!

So yes, let's activate taproot!

## The SegWit Wars

The biggest problem with activating Taproot is PTSD from the previous softfork, SegWit. Pieter Wuille, one of the authors of the current Taproot proposal, has consistently held the position that he will not discuss activation, and will accept whatever activation process is imposed on Taproot. Other developers have expressed similar opinions.

So what happened with SegWit activation that was so traumatic? SegWit used the BIP9 activation method. Let's dive into BIP9!

### [BIP9 Miner-Activated Soft Fork](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki)

Basically, BIP9 has a bunch of parameters:

*   **bit** \- A field in the block header, the `nVersion`, has a number of bits. By setting a particular bit, the miner making the block indicates that it has upgraded its software to support a particular soft fork. The **bit** parameter for a BIP9 activation is _which_ bit in this `nVersion` is used to indicate that the miner has upgraded software for a particular soft fork.
*   **timeout** \- a time limit, expressed as an end date. If this timeout is reached without sufficient number of miners signaling that they upgraded, then the activation fails and Bitcoin Core goes back to the drawing board.

Now there are other parameters (**name**, **starttime**) but they are not anywhere near as important as the above two.

A number that is **_not_** a parameter, is 95%. Basically, activation of a BIP9 softfork is considered as actually succeeding if at least 95% of blocks in the last 2 weeks had the specified **bit** in the `nVersion` set. If less than 95% had this bit set before the **timeout**, then the upgrade fails and never goes into the network. This is not a parameter: it is a constant defined by BIP9, and developers using BIP9 activation cannot change this.

So, first some simple questions and their answers:

*   Why not just set a day when everyone starts imposing the new rules of the softfork?
    *   This was done classically (in the days when Satoshi was still among us). But this might argued to put too much power to developers, since there would be no way to reject an upgrade without possible bad consequences. For example, developers might package an upgrade that the users do not want, together with vital security bugfixes. Either you live without vital security bugfixes and hire some other developers to fix it for you (which can be difficult, presumably the best developers are already the ones working on the codebase) or you get the vital security bugfixes and implicitly support the upgrade you might not want.
    *   Sure, you could fork the code yourself (the ultimate threat in the FOSS world) and hire another set of developers who aren't assholes to do the dreary maintenance work of fixing security bugs, but Bitcoin needs strong bug-for-bug compatibility so everyone should really congregate around a single codebase.
    *   Basically: even the devs do not want this power, because they fear being coerced into putting "upgrades" that are detrimental to users. Satoshi got a pass because nobody knew who he was and how to coerce him.
*   Why 95%?
    *   Suppose the threshold were lower, like 51%. If so, after activation, somebody can disrupt the Bitcoin network by creating a transaction that is valid under the pre-softfork rules, but are invalid under the post-softfork rules. Upgraded nodes would reject it, but 49% of miners would accept it and include it in a block (which makes the block invalid) And _then_ the same 49% would accept the invalid block and build on top of _that_, possibly creating a short chain of doomed invalid blocks that confirm an invalid spend. This can confuse SPV wallets, who might see multiple confirmations of a transaction and accept the funds, but later find that in fact it is invalid under the now-activated softfork rules.
    *   Thus, a very high threshold was imposed. 95% is considered safe. 50% is definitely not safe. Due to variance in the mining process, 80% could also be potentially unsafe (i.e. 80% of blocks signaling might have a good chance of coming from only 60% of miners), so a threshold of 95% was considered "safe enough for Bitcoin work".
*   Why have a **timeout** that _disables_ the upgrade?
    *   Before BIP9, what was used was either flag day or [BIP34](https://github.com/bitcoin/bips/blob/master/bip-0034.mediawiki). BIP34 had no flag day of activation or a **bit**, instead, it was just a 95% threshold to signal an `nVersion` value greater than a specific value. Actually, it was two thresholds: at 75%, blocks with the new `nVersion` would have the new softfork rules imposed, but at 95% blocks with the old `nVersion` would be rejected (and only the new blocks, with the new softfork rules, were accepted). For one, between 75% and 95%, there was a situation where the softfork was only "partially imposed", only blocks signaling the new rules would actually have those rules, but blocks with the old rules were still valid. This was fine for BIP34, which only added rules for miners with negligible use for non-miners.
    *   The same activation process for BIP34 was used for [BIP66](https://github.com/bitcoin/bips/blob/master/bip-0066.mediawiki). After BIP66 reached 95%, [however, a single miner mined an invalid-for-BIP66 block that still signalled BIP66 support](https://bitcoin.org/en/alert/2015-07-04-spv-mining). It turned out that of the 95% signaling BIP66 support, only about 50% were actually imposing the BIP66 new rules. The rest signalled support **_without upgrading their software to support new rules_**. This lead to many chainsplits and chaos with SPV nodes.
    *   The reasons miners signalled support was because they felt they were being pressured to signal support. So they signalled support, with plans to actually upgrade later, but because of the widespread signalling, the new BIP66 version locked in _before_ upgrade plans were finished. Thus, the timeout that _disables_ the upgrade was added in BIP9 to allow miners an escape hatch.

### The Great Battles of the SegWit Wars

SegWit not only fixed transaction malleability, it also created a practical softforkable blocksize increase that also rebalanced weights so that the cost of spending a UTXO is about the same as the cost of creating UTXOs (and spending UTXOs is "better" since it limits the size of the UTXO set that every fullnode has to maintain).

So SegWit was written, the activation was decided to be BIP9, and then.... miner signalling stalled at below 75%.

Thus were the Great SegWit Wars started.

#### BIP9 Feature Hostage

If you are a miner with at least 5% global hashpower, you can hold a BIP9-activated softfork hostage.

You might even secretly _want_ the softfork to actually push through. But you might want to extract concession from the users and the developers. Like removing the halvening. Or raising or even removing the block size caps (which helps larger miners more than smaller miners, making it easier to become a bigger fish that eats all the smaller fishes). Or whatever.

With BIP9, you _can_ hold the softfork hostage. You just hold out and refuse to signal. You tell everyone you will signal, if and only if certain concessions are given to you.

This ability by miners to hold a feature hostage was enabled because of the miner-exit allowed by the **timeout** on BIP9. Prior to that, miners were considered little more than expendable security guards, paid for the risk they take to secure the network, but not special in the grand scheme of Bitcoin.

#### Covert ASICBoost

ASICBoost was a novel way of optimizing SHA256 mining, by taking advantage of the structure of the 80-byte header that is hashed in order to perform proof-of-work. The details of ASICBoost are out-of-scope here but you can [read about it elsewhere](https://www.mit.edu/%7Ejlrubin/public/pdfs/Asicboost.pdf)

Here is a short summary of the **two** types of ASICBoost, relevant to the activation discussion.

*   Overt ASICBoost - Manipulates the unused bits in `nVersion` to reduce power consumption in mining.
*   Covert ASICBoost - Manipulates the order of transactions in the block to reduce power consumption in mining.

Now, "overt" means "obvious", while "covert" means hidden. Overt ASICBoost is obvious because `nVersion` bits that are not currently in use for BIP9 activations are usually 0 by default, so setting those bits to 1 makes it obvious that you are doing something weird (namely, Overt ASICBoost). Covert ASICBoost is non-obvious because the order of transactions in a block are up to the miner anyway, so the miner rearranging the transactions in order to get lower power consumption is not going to be detected.

Unfortunately, while Overt ASICBoost was compatible with SegWit, Covert ASICBoost **was not**. This is because, pre-SegWit, only the block header Merkle tree committed to the transaction ordering. However, with SegWit, another Merkle tree exists, which commits to transaction ordering as well. Covert ASICBoost would require more computation to manipulate two Merkle trees, obviating the power benefits of Covert ASICBoost anyway.

Now, miners want to use ASICBoost (indeed, about 60->70% of current miners probably use the Overt ASICBoost nowadays; if you have a Bitcoin fullnode running you will see the logs with lots of "60 of last 100 blocks had unexpected versions" which is exactly what you would see with the `nVersion` manipulation that Overt ASICBoost does). But remember: ASICBoost was, at around the time, a **novel** improvement. Not all miners had ASICBoost hardware. Those who did, did not want it known that they had ASICBoost hardware, and wanted to do Covert ASICBoost!

But Covert ASICBoost is incompatible with SegWit, because SegWit actually has two Merkle trees of transaction data, and Covert ASICBoost works by fudging around with transaction ordering in a block, and recomputing two Merkle Trees is more expensive than recomputing just one (and loses the ASICBoost advantage).

Of course, those miners that wanted Covert ASICBoost did not want to _openly admit_ that they had ASICBoost hardware, they wanted to keep their advantage secret because miners are strongly competitive in a very tight market. And doing ASICBoost Covertly was just the ticket, but they could not work post-SegWit.

Fortunately, due to the BIP9 activation process, they could hold SegWit hostage while covertly taking advantage of Covert ASICBoost!

#### UASF: BIP148 and BIP8

When the incompatibility between Covert ASICBoost and SegWit was realized, still, activation of SegWit stalled, and miners were still not openly claiming that ASICBoost was related to non-activation of SegWit.

Eventually, a new proposal was created: [BIP148](https://github.com/bitcoin/bips/blob/master/bip-0148.mediawiki). With this rule, 3 months before the end of the SegWit **timeout**, nodes would reject blocks that did _not_ signal SegWit. Thus, 3 months before SegWit **timeout**, BIP148 would force activation of SegWit.

This proposal was not accepted by Bitcoin Core, due to the shortening of the timeout (it effectively times out 3 months before the initial SegWit timeout). Instead, a fork of Bitcoin Core was created which added the patch to comply with BIP148. This was claimed as a User Activated Soft Fork, UASF, since users could freely download the alternate fork rather than sticking with the developers of Bitcoin Core.

Now, BIP148 effectively is just a BIP9 activation, except at its (earlier) timeout, the new rules would be activated anyway (instead of the BIP9-mandated behavior that the upgrade is cancelled at the end of the **timeout**).

BIP148 was actually inspired by the [BIP8](https://github.com/bitcoin/bips/blob/fcd34618d7ce594db2a7e9badc4e70f1a2fab6db/bip-0008.mediawiki) proposal (the link here is a historical version; BIP8 has been updated recently, precisely in preparation for Taproot activation). BIP8 is basically BIP9, but at the end of **timeout**, the softfork is activated anyway rather than cancelled.

This removed the ability of miners to hold the softfork hostage. At best, they can delay the activation, but not stop it entirely by holding out as in BIP9.

Of course, this implies risk that not all miners have upgraded before activation, leading to possible losses for SPV users, as well as again re-pressuring miners to signal activation, possibly without the miners actually upgrading their software to properly impose the new softfork rules.

#### BIP91, SegWit2X, and The Aftermath

BIP148 inspired countermeasures, possibly from the Covert ASiCBoost miners, possibly from concerned users who wanted to offer concessions to miners. To this day, the common name for BIP148 - UASF - remains an emotionally-charged rallying cry for parts of the Bitcoin community.

One of these was SegWit2X. This was brokered in a deal between some Bitcoin personalities at a conference in New York, and thus part of the so-called "New York Agreement" or NYA, another emotionally-charged acronym.

The text of the NYA was basically:

1.  Set up a new activation threshold at 80% signalled at bit 4 (vs bit 1 for SegWit).
    *   When this 80% signalling was reached, miners would require that bit 1 for SegWit be signalled to achive the 95% activation needed for SegWit.
2.  If the bit 4 signalling reached 80%, increase the block weight limit from the SegWit 4000000 to the SegWit2X 8000000, 6 months after bit 1 activation.

The first item above was coded in [BIP91](https://github.com/bitcoin/bips/blob/fcd34618d7ce594db2a7e9badc4e70f1a2fab6db/bip-0091.mediawiki).

Unfortunately, if you read the BIP91, _independently_ of NYA, you might come to the conclusion that BIP91 was only about lowering the threshold to 80%. In particular, BIP91 never mentions anything about the second point above, it never mentions that bit 4 80% threshold would _also_ signal for a later hardfork increase in weight limit.

Because of this, even though there are claims that NYA (SegWit2X) reached 80% dominance, a close reading of BIP91 shows that the 80% dominance was only for SegWit activation, without necessarily a later 2x capacity hardfork (SegWit2X).

This ambiguity of bit 4 (NYA says it includes a 2x capacity hardfork, BIP91 says it does not) has continued to be a thorn in blocksize debates later. Economically speaking, Bitcoin futures between SegWit and SegWit2X showed strong economic dominance in favor of SegWit (SegWit2X futures were traded at a fraction in value of SegWit futures: I personally made a tidy but small amount of money betting against SegWit2X in the futures market), so suggesting that NYA achieved 80% dominance even in mining is laughable, but the NYA text that ties bit 4 to SegWit2X still exists.

Historically, BIP91 triggered which caused SegWit to activate before the BIP148 shorter timeout. BIP148 proponents continue to hold this day that it was the BIP148 shorter timeout and no-compromises-activate-on-August-1 that made miners flock to BIP91 as a face-saving tactic that actually **removed** the second clause of NYA. NYA supporters keep pointing to the bit 4 text in the NYA and the historical activation of BIP91 as a failed promise by Bitcoin developers.

## Taproot Activation Proposals

There are [two primary proposals I can see for Taproot activation](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-July/018043.html):

1.  BIP8.
2.  [Modern Softfork Activation](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-January/017547.html).

We have discussed BIP8: roughly, it has **bit** and **timeout**, if 95% of miners signal **bit** it activates, at the end of **timeout** it activates. (EDIT: BIP8 has had recent updates: at the end of **timeout** it can now activate or fail. For the most part, in the below text "BIP8", means BIP8-and-activate-at-timeout, and "BIP9" means BIP8-and-fail-at-timeout)

So let's take a look at Modern Softfork Activation!

### Modern Softfork Activation

This is a more complex activation method, composed of BIP9 and BIP8 as supcomponents.

1.  First have a 12-month BIP9 (fail at timeout).
2.  If the above fails to activate, have a 6-month discussion period during which users and developers and miners discuss whether to continue to step 3.
3.  Have a 24-month BIP8 (activate at timeout).

The total above is 42 months, if you are counting: 3.5 years worst-case activation.

The logic here is that if there are no problems, BIP9 will work just fine anyway. And if there are problems, the 6-month period should weed it out. Finally, miners cannot hold the feature hostage since the 24-month BIP8 period will exist anyway.

## PSA: Being Resilient to Upgrades

Software is very brittle.

Anyone who has been using software for a long time has experienced something like this:

1.  You hear a new version of your favorite software has a nice new feature.
2.  Excited, you install the new version.
3.  You find that the new version has subtle incompatibilities with your current workflow.
4.  You are sad and downgrade to the older version.
5.  You find out that the new version has changed your files in incompatible ways that the old version cannot work with anymore.
6.  You tearfully reinstall the newer version and figure out how to get your lost productivity now that you have to adapt to a new workflow

If you are a technically-competent user, you might codify your workflow into a bunch of programs. And then you upgrade one of the external pieces of software you are using, and find that it has a subtle incompatibility with your current workflow which is based on a bunch of simple programs you wrote yourself. And if those simple programs are used as the basis of some important production system, you hve just screwed up because you upgraded software on an important production system.

And well, one of the issues with new softfork activation is that if not enough people (users and miners) upgrade to the newest Bitcoin software, the security of the new softfork rules are at risk.

Upgrading software of any kind is always a risk, and the more software you build on top of the software-being-upgraded, the greater you risk your tower of software collapsing while you change its foundations.

So if you have some complex Bitcoin-manipulating system with Bitcoin somewhere at the foundations, consider running two Bitcoin nodes:

1.  One is a "stable-version" Bitcoin node. Once it has synced, set it up to `connect=x.x.x.x` to the second node below (so that your ISP bandwidth is only spent on the second node). Use this node to run all your software: it's a stable version that you don't change for long periods of time. Enable txiindex, disable pruning, whatever your software needs.
2.  The other is an "always-up-to-date" Bitcoin Node. Keep its stoarge down with pruning (initially sync it off the "stable-version" node). You can't use `blocksonly` if your "stable-version" node needs to send transactions, but otherwise this "always-up-to-date" Bitcoin node can be kept as a low-resource node, so you can run both nodes in the same machine.

When a new Bitcoin version comes up, you just upgrade the "always-up-to-date" Bitcoin node. This protects you if a future softfork activates, you will only receive valid Bitcoin blocks and transactions. Since this node has nothing running on top of it, it is just a special peer of the "stable-version" node, any software incompatibilities with your system software do not exist.

Your "stable-version" Bitcoin node remains the same version until you are ready to actually upgrade this node and are prepared to rewrite most of the software you have running on top of it due to version compatibility problems.

When upgrading the "always-up-to-date", you can bring it down safely and then start it later. Your "stable-version" wil keep running, disconnected from the network, but otherwise still available for whatever queries. You do need some system to stop the "always-up-to-date" node if for any reason the "stable-version" goes down (otherwisee if the "always-up-to-date" advances its pruning window past what your "stable-version" has, the "stable-version" cannot sync afterwards), but if you are technically competent enough that you _need_ to do this, you are technically competent enough to write such a trivial monitor program (EDIT: [gmax notes](https://www.reddit.com/r/Bitcoin/comments/hqzp14/technical_the_path_to_taproot_activation/fy3j9dg/?context=3) you can adjust the pruning window by RPC commands to help with this as well).

This recommendation is from [gmaxwell](https://old.reddit.com/u/nullc) on IRC, by the way.

***

{% include signup.md %}