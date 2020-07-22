---
title: "Taproot: Why Activate?"
permalink: "/taproot-why-activate"

author: almkglor

tags:
  - almkglor
  - 2020 M7
  - Taproot

excerpt: almkglor makes the case for Taproot now. Posted June 15, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Taproot: Why Activate?](https://old.reddit.com/r/Bitcoin/comments/hrlpnc/technical_taproot_why_activate/)
### By [almkglor](https://old.reddit.com/user/almkglor)
### Posted June 15, 2020


This is a follow-up on [https://old.reddit.com/r/Bitcoin/comments/hqzp14/technical\_the\_path\_to\_taproot_activation/](https://old.reddit.com/r/Bitcoin/comments/hqzp14/technical_the_path_to_taproot_activation/)

Taproot! Everybody wants it!! But... you might ask yourself: sure, everybody **else** wants it, but why would **_I_**, sovereign Bitcoin HODLer, want it? Surely I can be better than everybody **else** because I swapped XXX fiat for Bitcoin unlike all those nocoiners?

And it is important for you to know the reasons why you, o sovereign Bitcoiner, would want Taproot activated. After all, your nodes (or the nodes your wallets use, which if you are SPV, you hopefully can pester to your wallet vendor/implementor about) need to be upgraded in order for Taproot activation to actually succeed instead of becoming a hot sticky mess.

First, let's consider some principles of Bitcoin.

*   You the HODLer should be the one who controls where your money goes. Your keys, your coins.
*   You the HODLer should be able to coordinate and make contracts with other people regarding your funds.
*   You the HODLer should be able to do the above without anyone watching over your shoulder and judging you.

I'm sure most of us here would agree that the above are very important principles of Bitcoin and that these are principles we would not be willing to remove. If anything, we would want those principles strengthened (especially the last one, financial privacy, which current Bitcoin is only sporadically strong with: you _can_ get privacy, it just requires effort to do so).

So, how does Taproot affect those principles?

## Taproot and Your /Coins

Most HODLers probably HODL their coins in singlesig addresses. Sadly, switching to Taproot would do very little for you (it gives a mild discount at spend time, at the cost of a mild increase in fee at receive time (paid by whoever sends to you, so if it's a self-send from a P2PKH or bech32 address, you pay for this); mostly a wash).

(technical details: a Taproot output is 1 version byte + 32 byte public key, while a P2WPKH (bech32 singlesig) output is 1 version byte + 20 byte public key hash, so the Taproot output spends 12 bytes more; spending from a P2WPKH requires revealing a 32-byte public key later, which is not needed with Taproot, and Taproot signatures are about 9 bytes smaller than P2WPKH signatures, but the 32 bytes plus 9 bytes is divided by 4 because of the witness discount, so it saves about 11 bytes; mostly a wash, it increases blockweight by about 1 virtual byte, 4 weight for each Taproot-output-input, compared to P2WPKH-output-input).

However, as your HODLings grow in value, you might start wondering if multisignature k-of-n setups might be better for the security of your savings. And it is in multisignature that Taproot starts to give benefits!

Taproot switches to using Schnorr signing scheme. Schnorr makes key aggregation -- constructing a _single_ public key from multiple public keys -- almost as trivial as adding numbers together. "Almost" because it involves some fairly advanced math instead of simple boring number adding, but hey when was the last time you added up your grocery list prices by hand huh?

With current P2SH and P2WSH multisignature schemes, if you have a 2-of-3 setup, then to spend, you need to provide two different signatures from two different public keys. With Taproot, you can create, using special moon math, a single public key that represents your 2-of-3 setup. Then you just put two of your devices together, have them communicate to each other (this can be done airgapped, in theory, by sending QR codes: the software to do this is not even being built yet, but that's because Taproot hasn't activated yet!), and they will make a _single_ signature to authorize any spend from your 2-of-3 address. That's 73 witness bytes -- 18.25 virtual bytes -- of signatures you save!

And if you decide that your current setup with 1-of-1 P2PKH / P2WPKH addresses is just fine as-is: well, that's the whole point of a **_soft_**fork: backwards-compatibility; you can receive from Taproot users just fine, and once your wallet is updated for Taproot-sending support, you can send to Taproot users just fine as well!

(P2WPKH and P2WSH -- SegWit v0 -- addresses start with `bc1q`; Taproot -- SegWit v1 --- addresses start with `bc1p`, in case you wanted to know the difference; in bech32 `q` is 0, `p` is 1)

Now how about HODLers who keep all, or some, of their coins on custodial services? Well, any custodial service worth its salt would be doing _at least_ 2-of-3, or probably something even bigger, like 11-of-15. So your custodial service, if it switched to using Taproot internally, could save a lot more (imagine an 11-of-15 getting reduced from 11 signatures to just 1!), which --- we can only hope! --- should translate to lower fees and better customer service from your custodial service!

So I think we can say, very accurately, that the Bitcoin principle --- that YOU are in control of your money --- can only be helped by Taproot (if you are doing multisignature), and, because P2PKH and P2WPKH remain validly-usable addresses in a Taproot future, will not be harmed by Taproot. Its benefit to this principle might be small (it mostly only benefits multisignature users) but since it has no drawbacks with this (i.e. singlesig users can continue to use P2WPKH and P2PKH still) this is still a nice, tidy win!

(even singlesig users get a minor benefit, in that multisig users will now reduce their blockchain space footprint, so that fees can be kept low for everybody; so for example even if you have your single set of private keys engraved on titanium plates sealed in an airtight box stored in a safe buried in a desert protected by angry nomads riding giant sandworms because you're the frickin' Kwisatz Haderach, you still gain some benefit from Taproot)

And here's the important part: **_if P2PKH/P2WPKH is working perfectly fine with you and you decide to never use Taproot yourself, Taproot will not affect you detrimentally_**. First do no harm!

## Taproot and Your Contracts

No one is an island, no one lives alone. Give and you shall receive. You know: by trading with other people, you can gain expertise in some obscure little necessity of the world (and greatly increase your productivity in that little field), and then trade the products of your expertise for necessities other people have created, all of you thereby gaining gains from trade.

So, contracts, which are basically enforceable agreements that facilitate trading with people who you do not personally know and therefore might not trust.

Let's start with a simple example. You want to buy some gewgaws from somebody. But you don't know them personally. The seller wants the money, you want their gewgaws, but because of the lack of trust (you don't know them!! what if they're scammers??) neither of you can benefit from gains from trade.

However, suppose both of you know of some entity that both of you trust. That entity can act as a trusted escrow. The entity provides you security: this enables the trade, allowing both of you to get gains from trade.

In Bitcoin-land, this can be implemented as a 2-of-3 multisignature. The three signatories in the multisgnature would be you, the gewgaw seller, and the escrow. You put the payment for the gewgaws into this 2-of-3 multisignature address.

Now, suppose it turns out neither of you are scammers (whaaaat!). You receive the gewgaws just fine and you're willing to pay up for them. Then you and the gewgaw seller just sign a transaction --- you and the gewgaw seller are 2, sufficient to trigger the 2-of-3 --- that spends from the 2-of-3 address to a singlesig the gewgaw seller wants (or whatever address the gewgaw seller wants).

But suppose some problem arises. The seller gave you gawgews instead of gewgaws. Or you decided to keep the gewgaws but not sign the transaction to release the funds to the seller. In either case, the escrow is notified, and if it can sign with you to refund the funds back to you (if the seller was a scammer) or it can sign with the seller to forward the funds to the seller (if you were a scammer).

Taproot helps with this: like mentioned above, it allows multisignature setups to produce only one signature, reducing blockchain space usage, and thus making contracts --- which require multiple people, by definition, you don't make contracts with yourself --- is made cheaper (which we hope _enables_ more of these setups to happen for more gains from trade for everyone, also, moon and lambos).

(technology-wise, it's easier to make an n-of-n than a k-of-n, making a k-of-n would require a complex setup involving a long ritual with many communication rounds between the n participants, but an n-of-n can be done trivially with some moon math. You can, however, make what is effectively a 2-of-3 by using a three-branch SCRIPT: either 2-of-2 of you and seller, OR 2-of-2 of you and escrow, OR 2-of-2 of escrow and seller. Fortunately, Taproot adds a facility to embed a SCRIPT inside a public key, so you can have a 2-of-2 Taprooted address (between you and seller) with a SCRIPT branch that can instead be spent with 2-of-2 (you + escrow) OR 2-of-2 (seller + escrow), which implements the three-branched SCRIPT above. If neither of you are scammers (hopefully the common case) then you both sign using your keys and **_never have to contact the escrow_**, since you are just using the escrow public key without coordinating with them (because n-of-n is trivial but k-of-n requires setup with communication rounds), so in the "best case" where both of you are honest traders, you _also_ get a privacy boost, in that the escrow never learns you have been trading on gewgaws, I mean ewww, gawgews are much better than gewgaws and therefore I now judge you for being a gewgaw enthusiast, you filthy gewgawer).

## Taproot and Your Contracts, Part 2: Cryptographic Boogaloo

Now suppose you want to buy some data instead of things. For example, maybe you have some closed-source software in trial mode installed, and want to pay the developer for the full version. You want to pay for an activation code.

This can be done, today, by using an HTLC. The developer tells you the hash of the activation code. You pay to an HTLC, paying out to the developer if it reveals the preimage (the activation code), or refunding the money back to you after a pre-agreed timeout. If the developer claims the funds, it has to reveal the preimage, which is the activation code, and you can now activate your software. If the developer does not claim the funds by the timeout, you get refunded.

And you can do that, with HTLCs, today.

Of course, HTLCs do have problems:

*   Privacy. Everyone scraping the Bitcoin blockchain can see any HTLCs, and preimages used to claim them.
    *   This can be mitigated by using offchain techniques so HTLCs are never published onchain in the happy case. Lightning would probably in practice be the easiest way to do this offchain. Of course, there are practical limits to what you can pay on Lightning. If you are buying something expensive, then Lightning might not be practical. For example, the "software" you are activating is really the firmware of a car, and what you are buying is not the software really but the car itself (with the activation of the car firmware being equivalent to getting the car keys).
    *   Even offchain techniques need an onchain escape hatch in case of unresponsiveness! This means that, if something bad happens during payment, the HTLC might end up being published onchain anyway, revealing the fact that some special contract occurred.
    *   And an HTLC that is claimed with a preimage onchain will also publicly reveal the preimage onchain. If that preimage is really the activation key of a software than it can now be pirated. If that preimage is really the activation key for your newly-bought cryptographic car --- well, not your keys, not your car!
*   Trust requirement. You are trusting the developer that it gives you the hash of an actual valid activation key, without any way to validate that the activation key hidden by the hash is actually valid.

Fortunately, with Schnorr (which is enabled by Taproot), we can now use the Scriptless Script constuction by [Andrew Poelstra](https://old.reddit.com/u/andytoshi). This Scriptless Script allows a new construction, the PTLC or Pointlocked Timelocked Contract. Instead of hashes and preimages, just replace "hash" with "point" and "preimage" with "scalar".

Or as you might know them: "point" is really "public key" and "scalar" is really a "private key". What a PTLC does is that, given a particular public key, the pointlocked branch can be spent only if the spender reveals the private key of the given public key to you.

Another nice thing with PTLCs is that they are _deniable_. What appears onchain is just a single 2-of-2 signature between you and the developer/manufacturer. It's like a magic trick. This signature has no special watermarks, it's a perfectly normal signature (the pledge). However, from this signature, plus some datta given to you by the developer/manufacturer (known as the _adaptor signature_) you can derive the private key of a particular public key you both agree on (the turn). Anyone scraping the blockchain will just see signatures that look just like every other signature, and as long as nobody manages to hack you and get a copy of the adaptor signature or the private key, they cannot get the private key behind the public key (point) that the pointlocked branch needs (the prestige).

(Just to be clear, the public key you are getting the private key from, is distinct from the public key that the developer/manufacturer will use for its funds. The activation key is different from the developer's onchain Bitcoin key, and it is the activation key whose private key you will be learning, not the developer's/manufacturer's onchain Bitcoin key).

So:

*   Privacy: PTLCs are private even if done onchain. Nobody else can learn what the private key behind the public key is, except you who knows the adaptor signature that when combined with the complete onchain signature lets you know what the private key of the activation key is. Somebody scraping the blockchain will not learn the same information even if all PTLCs are done onchain!
    *   Lightning is still useful for reducing onchain use, and will also get PTLCs soon after Taproot is activated, but even if something bad happens and a PTLC has to go onchain, it doesn't reveal anything!
*   Trust issues can be proven more easily with a public-private keypair than with a hash-preimage pair.
    *   For example, the developer of the software you are buying could provide a signature signing a message saying "unlock access to the full version for 1 day". You can check if feeding this message and signature to the program will indeed unlock full-version access for 1 day. Then you can check if the signature is valid for the purported pubkey whose private key you will pay for. If so, you can now believe that getting the private key (by paying for it in a PTLC) would let you generate any number of "unlock access to the full version for 1 day" message+signatures, which is equivalent to getting full access to the software indefinitely.
    *   For the car, the manufacturer can show that signing a message "start the engine" and feeding the signature to the car's fimrware will indeed start the engine, and maybe even let you have a small test drive. You can then check if the signature is valid for the purported pubkey whose privkey you will pay for. If so, you can now believe that gaining knowledge of the privkey will let you start the car engine at any time you want.
    *   (pedantry: the signatures need to be unique else they could be replayed, this can be done with a challenge-response sequence for the car, where the car gathers entropy somehow (it's a car, it probably has a bunch of sensors nowadays so it can get entropy for free) and uses the gathered entropy to challenge you to sign a random number and only start if you are able to sign the random number; for the software, it could record previous signatures somewhere in the developer's cloud server and refuse to run if you try to replay a previously-seen signature.)

Taproot lets PTLCs exist onchain because they enable Schnorr, which is a requirement of PTLCs / Scriptless Script.

(technology-wise, take note that Scriptless Script works only for the "pointlocked" branch of the contract; you need normal Script, or a pre-signed `nLockTime`d transaction, for the "timelocked" branch. Since Taproot can embed a script, you can have the Taproot pubkey be a 2-of-2 to implement the Scriptless Script "pointlocked" branch, then have a hidden script that lets you recover the funds with an `OP_CHECKLOCKTIMEVERIFY` after the timeout if the seller does not claim the funds.)

## Quantum Quibbles!

Now if you were **_really_** paying attention, you might have noticed this parenthetical:

> (technical details: a Taproot output is 1 version byte + 32 byte public key, while a P2WPKH (bech32 singlesig) output is 1 version byte + 20 byte public key hash...)

So wait, Taproot uses raw 32-byte public keys, and not public key hashes? Isn't that more quantum-vulnerable??

Well, in theory yes. In practice, they probably are not.

It's not that hashes can be broken by quantum computes --- they're still not. Instead, you have to look at how you _spend from_ a P2WPKH/P2PKH pay-to-public-key-hash.

When you _spend from_ a P2PKH / P2WPKH, you have to reveal the public key. Then Bitcoin hashes it and checks if this matches with the public-key-hash, and only then actually validates the signature for that public key.

So an unconfirmed transaction, floating in the mempools of nodes globally, will show, in plain sight for everyone to see, your public key.

(public keys should be public, that's why they're called public keys, LOL)

And if quantum computers are fast enough to be of concern, then they are probably fast enough that, in the several minutes to several hours from broadcast to confirmation, they have already cracked the public key that is openly broadcast with your transaction. The owner of the quantum computer can now replace your unconfirmed transaction with one that pays the funds to itself. Even if you did not opt-in RBF, miners are still incentivized to support RBF on RBF-disabled transactions.

So the extra hash is not as significant a protection against quantum computers as you might think. Instead, the extra hash-and-compare needed is just extra validation effort.

Further, if you have ever, in the past, _spent from_ the address, then there exists already a transaction indelibly stored on the blockchain, openly displaying the public key from which quantum computers can derive the private key. So those are still vulnerable to quantum computers.

For the most part, the cryptographers behind Taproot (and Bitcoin Core) are of the opinion that quantum computers capable of cracking Bitcoin pubkeys are unlikely to appear within a decade or two.

*   Current quantum computers can barely crack prime factorization problem for primes of 5 bits.
*   The 256-bit elliptic curve use by Bitcoin is, by my (possibly wrong) understanding, equivalent to 4096-bit primes, so you can see a pretty big gap between now (5 bit primes) and what is needed (4096 bit primes).
*   A lot of financial non-Bitcoin systems use the equivalent of 3072-bit primes or less, and are probably easier targets to crack than the equivalent-to-4096-bit-primes Bitcoin.

So:

*   Quantum computers capable of cracking Bitcoin are still far off.
*   Pay-to-public-key-hash is not as protective as you might think.
*   We will probably see banks get cracked before Bitcoin, so the banking system is a useful canary-in-a-coal-mine to see whether we should panic about being quantum vulnerable.

For now, the homomorphic and linear properties of elliptic curve cryptography provide a lot of benefits --- particularly the linearity property is what enables Scriptless Script and simple multisignature (i.e. multisignatures that are just 1 signature onchain). So it might be a good idea to take advantage of them now while we are still fairly safe against quantum computers. It seems likely that quantum-safe signature schemes are nonlinear (thus losing these advantages).

Summary
-------

*   If you are a singlesig HODL-only Bitcoin user, Taproot will not affect you positively or negatively. Importantly: Taproot does no harm!
*   If you use or intend to use multisig, Taproot will be a positive for you.
*   If you transact onchain regularly using typical P2PKH/P2WPKH addresses, you get a minor reduction in feerates since multisig users will likely switch to Taproot to get smaller tx sizes, freeing up blockspace for yours.
*   If you are using multiparticipant setups for special systems of trade, Taproot will be a positive for you.
    *   Remember: Lightning channels are multipartiicpiant setups for special systems of lightning-fast offchain trades!

I Wanna Be The Taprooter!
-------------------------

So, do you want to help activate Taproot? Here's what **_you_**, mister sovereign Bitcoin HODLer, can do!

*   **_If you have developer experience especially in C, C++, or related languages_**
    *   Review the Taproot code! There is one pull request in Bitcoin Core, and one in libsecp256k1. I deliberately am not putting links here, to avoid brigades of nontechnical but enthusiastic people leaving pointless reviews, but if you are qualified you know how to find them!
    *   **_But I am not a cryptographer/Bitcoin Core contributor/mathematician/someone as awesome as Pieter Wuille_**
    *   That's perfectly fine! The cryptographers have been over the code already and agree the math is right and the implementation is right. What is wanted is the dreary dreary dreary software engineering: are the comments comprehensive and understandable? no misspellings in the comments? variable names understandable? reasonable function naming convention? misleading coding style? off-by-one errors in loops? conditions not covered by tests? accidental mixups of variables with the same types? missing frees? read-before-init? better test coverage of suspicious-looking code? missing or mismatching header guards? portability issues? consistent coding style? you know, stuff any coder with a few years of experience in coding **_anything_** might be able to catch. With enough eyes all bugs are shallow!
*   **_If you are running a mining pool/mining operation/exchange/custodial service/SPV server_**
    *   Be prepared to upgrade!
    *   One of the typical issues with upgrading software is that subtle incompatibilities with your current custom programs tend to arise, disrupting operations and potentially losing income due to downtime. If so, consider moving to the two-node setup suggested by gmax, which is in the last section of [my previous post](https://old.reddit.com/r/Bitcoin/comments/hqzp14/technical_the_path_to_taproot_activation/). With this, you have an up-to-date "public" node and a fixed-version "private" node, with the public node protecting the private node from any invalid chainsplits or invalid transactions. Moving to this setup from a typical one-node setup should be smooth and should not disrupt operations (too much).
*   **_If you are running your own fullnode for fun or for your own wallet_**
    *   Be prepared to upgrade! The more nodes validating the new rules (even if you are a non-mining node!), the safer every softfork will be!
*   **_If you are using an SPV wallet or custodial wallet/service (including hardware wallets using the software of the wallet provider)_**
    *   Contact your wallet provider / SPV server and ask for a statement on whether they support Taproot, and whether they are prepared to upgrade for Taproot! Make it known to them that Taproot is something you want!

But I Hate Taproot!!
--------------------

That's fine!

*   Raise your objections to Taproot now, or forever hold your peace! Maybe you can raise them here and some of the devs (probably [/u/nullc](https://old.reddit.com/u/nullc), he goes everywhere, even in rbtc!) might be able to see your objections! Or if your objections are very technical, head over to the appropriate pull request and object away!
*   Maybe you simply misunderstand something, and we can clarify it here!
*   Or maybe you do have a good objection, and we can make Taproot better by finding a solution for it!

Discussions About Taproot Activation
------------------------------------

*   IRC logs for freenode.net ##taproot-activation: [http://gnusha.org/taproot-activation](http://gnusha.org/taproot-activation)
*   Telegram group: [https://t.me/bips_activation](https://t.me/bips_activation)
*   Reddit: [https://old.reddit.com/r/Bitcoin/comments/hqzp14/technical\_the\_path\_to\_taproot_activation/](https://old.reddit.com/r/Bitcoin/comments/hqzp14/technical_the_path_to_taproot_activation/)

***

{% include signup.md %}