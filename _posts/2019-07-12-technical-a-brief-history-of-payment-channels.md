---
title: "Technical: A Brief History of Payment Channels: from Satoshi to Lightning Network"
permalink: "/technical-a-brief-history-of-payment-channels" 

author: alanmanuelkgloria

tags:
  - almkglor
  - CY19 Q3

excerpt: Alan Manuel K. Gloria shares the bacakstory of payment channels and makes the case that Bitcoin scales! Posted July 12, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

# [Technical: A Brief History of Payment Channels: from Satoshi to Lightning Network](https://www.reddit.com/r/Bitcoin/comments/cc9psl/technical_a_brief_history_of_payment_channels/)
### By [Alan Manuel K. Gloria](https://www.reddit.com/user/almkglor/)
### July 12, 2019

Who cares about political tweets from some random country's president when payment channels are a much more interesting and are actually capable of carrying value?

So let's have a short history of various payment channel techs!

## Generation 0: Satoshi's Broken nSequence Channels

Because Satoshi's Vision included payment channels, except his implementation sucked so hard we had to go fix it and added RBF as a by-product.

Originally, the plan for `nSequence` was that mempools would replace any transaction spending certain inputs with another transaction spending the same inputs, but only if the `nSequence` field of the replacement was larger.

Since `0xFFFFFFFF` was the highest value that `nSequence` could get, this would mark a transaction as "final" and not replaceable on the mempool anymore.

In fact, this " `nSequence` channel" I will describe is the reason why we have this weird rule about `nLockTime` and `nSequence`. `nLockTime` actually only works if `nSequence` is not `0xFFFFFFFF` i.e. final. If `nSequence` is `0xFFFFFFFF` then `nLockTime` is ignored, because this if the "final" version of the transaction.

So what you'd do would be something like this:

1. You go to a bar and promise the bartender to pay by the time the bar closes. Because this is the Bitcoin universe, time is measured in blockheight, so the closing time of the bar is indicated as some future blockheight.
2. For your first drink, you'd make a transaction paying to the bartender for that drink, paying from some coins you have. The transaction has an `nLockTime` equal to the closing time of the bar, and a starting `nSequence` of 0. You hand over the transaction and the bartender hands you your drink.
3. For your succeeding drink, you'd remake the same transaction, adding the payment for that drink to the transaction output that goes to the bartender (so that output keeps getting larger, by the amount of payment), and having an `nSequence` that is one higher than the previous one.
4. Eventually you have to stop drinking. It comes down to one of two possibilities:
- You drink until the bar closes. Since it is now the `nLockTime` indicated in the transaction, the bartender is able to broadcast the latest transaction and tells the bouncers to kick you out of the bar.
- You wisely consider the state of your liver. So you re-sign the last transaction with a "final" `nSequence` of `0xFFFFFFFF` i.e. the maximum possible value it can have. This allows the bartender to get his or her funds immediately (`nLockTime` is ignored if `nSequence` is `0xFFFFFFFF`), so he or she tells the bouncers to let you out of the bar.

Now that of course is a payment channel. Individual payments (purchases of alcohol, so I guess buying coffee is not in scope for payment channels). Closing is done by creating a "final" transaction that is the sum of the individual payments. Sure there's no routing and channels are unidirectional and channels have a maximum lifetime but give Satoshi a break, he was also busy inventing Bitcoin at the time.

Now if you noticed I called this kind of payment channel "broken". This is because the mempool rules are not consensus rules, and cannot be validated (_**nothing**_ about the mempool can be validated onchain: I sigh every time somebody proposes "let's make block size dependent on mempool size", mempool state cannot be validated by onchain data). Fullnodes can't see all of the transactions you signed, and then validate that the final one with the maximum `nSequence` is the one that actually is used onchain. So you can do the below:

1. Become friends with Jihan Wu, because he owns >51% of the mining hashrate (he totally reorged Bitcoin to reverse the Binance hack right?).
2. Slip Jihan Wu some of the more interesting drinks you're ordering as an incentive to cooperate with you. So say you end up ordering 100 drinks, you split it with Jihan Wu and give him 50 of the drinks.
3. When the bar closes, Jihan Wu quickly calls his mining rig and tells them to mine the version of your transaction with `nSequence` 0. You know, that first one where you pay for only one drink.
4. Because fullnodes cannot validate `nSequence`, they'll accept even the `nSequence`=0 version and confirm it, immutably adding you paying for a single alcoholic drink to the blockchain.
5. The bartender, pissed at being cheated, takes out a shotgun from under the bar and shoots at you and Jihan Wu.
6. Jihan Wu uses his mystical chi powers (actually the combined exhaust from all of his mining rigs) to slow down the shotgun pellets, making them hit you as softly as petals drifting in the wind.
7. The bartender mutters some words, clothes ripping apart as he or she (hard to believe it could be a she but hey) turns into a bear, ready to maul you for cheating him or her of the payment for all the 100 drinks you ordered from him or her.
8. Steely-eyed, you stand in front of the bartender-turned-bear, daring him to touch you. You've watched Revenant, you know Leonardo di Caprio could survive a bear mauling, and if some posh actor can survive that, you know you can too. You make a pose. "Drunken troll logic attack!"
9. I think I got sidetracked here.

### Lessons learned?

* Bears are bad news.
* You can't reasonably invoke "Satoshi's Vision" _**and**_ simultaneously reject the Lightning Network because it's not onchain. Satoshi's Vision included a half-assed implementation of payment channels with `nSequence`, where the onchain transaction represented multiple logical payments, exactly what modern offchain techniques do (except modern offchain techniques actually work). `nSequence` (the field, but not its modern meaning) has been in Bitcoin since BitCoin For Windows Alpha 0.1.0. And its original intent was payment channels. You can't get nearer to Satoshi's Vision than being a field that Satoshi personally added to transactions on the very first public release of the BitCoin software, like srsly.
* Miners can totally bypass mempool rules. In fact, the reason why `nSequence` has been repurposed to indicate "optional" replace-by-fee is because miners are already incentivized by the `nSequence` system to always follow replace-by-fee anyway. I mean, what do you think those drinks you passed to Jihan Wu are, other than the fee you pay him to mine a specific version of your transaction?
* Satoshi made mistakes. The original design for `nSequence` is one of them. Today, we no longer use `nSequence` in this way. So diverging from Satoshi's original design is part and parcel of Bitcoin development, because over time, we learn new lessons that Satoshi never knew about. Satoshi was an important landmark in this technology. He will not be the last, or most important, that we will remember in the future: he will only be the first.

## Spilman Channels

Incentive-compatible time-limited unidirectional channel; or, Satoshi's Vision, Fixed (if transaction malleability hadn't been a problem, that is).

Now, we know the bartender will turn into a bear and maul you if you try to cheat the payment channel, and now that we've revealed you're good friends with Jihan Wu, the bartender will no longer accept a payment channel scheme that lets one you cooperate with a miner to cheat the bartender.

Fortunately, Jeremy Spilman proposed a better way that would not let you cheat the bartender.

First, you and the bartender perform this ritual:

1. You get some funds and create a transaction that pays to a 2-of-2 multisig between you and the bartender. You _**don't**_ broadcast this yet: you just sign it and get its txid.
2. You create another transaction that spends the above transaction. This transaction (the "backoff") has an `nLockTime` equal to the closing time of the bar, plus one block. You sign it and give this backoff transaction (but not the above transaction) to the bartender.
3. The bartender signs the backoff and gives it back to you. It is now valid since it's spending a 2-of-2 of you and the bartender, and both of you have signed the backoff transaction.
4. _Now_ you broadcast the first transaction onchain. You and the bartender wait for it to be deeply confirmed, then you can start ordering.

The above is probably vaguely familiar to LN users. It's the funding process of payment channels! The first transaction, the one that pays to a 2-of-2 multisig, is the funding transaction that backs the payment channel funds.

So now you start ordering in this way:

1. For your first drink, you create a transaction spending the funding transaction output and sending the price of the drink to the bartender, with the rest returning to you.
2. You sign the transaction and pass it to the bartender, who serves your first drink.
3. For your succeeding drinks, you recreate the same transaction, adding the price of the new drink to the sum that goes to the bartender and reducing the money returned to you. You sign the transaction and give it to the bartender, who serves you your next drink.
4. At the end:
* If the bar closing time is reached, the bartender signs the latest transaction, completing the needed 2-of-2 signatures and broadcasting this to the Bitcoin network. Since the backoff transaction is the closing time + 1, it can't get used at closing time.
* If you decide you want to leave early because your liver is crying, you just tell the bartender to go ahead and close the channel (which the bartender can do at any time by just signing and broadcasting the latest transaction: the bartender won't do that because he or she is hoping you'll stay and drink more).
* If you ended up just hanging around the bar and never ordering, then at closing time + 1 you broadcast the backoff transaction and get your funds back in full.

Now, even if you pass 50 drinks to Jihan Wu, you can't give him the first transaction (the one which pays for only one drink) and ask him to mine it: it's spending a 2-of-2 and the copy you have only contains your own signature. You need the bartender's signature to make it valid, but he or she sure as hell isn't going to cooperate in something that would lose him or her money, so a signature from the bartender validating old state where he or she gets paid less isn't going to happen.

So, problem solved, right? Right? Okay, let's try it. So you get your funds, put them in a funding tx, get the backoff tx, confirm the funding tx...

Once the funding transaction confirms deeply, the bartender laughs uproariously. He or she summons the bouncers, who surround you menacingly.

"I'm refusing service to you," the bartender says.

"Fine," you say. "I was leaving anyway;" You smirk. "I'll get back my money with the backoff transaction, and posting about your poor service on reddit so you get negative karma, so there!"

"Not so fast," the bartender says. His or her voice chills your bones. It looks like your exploitation of the Satoshi `nSequence` payment channel is still fresh in his or her mind. "Look at the txid of the funding transaction that got confirmed."

"What about it?" you ask nonchalantly, as you flip open your desktop computer and open a reputable blockchain explorer.

What you see shocks you.

"What the --- the txid is different! You--- you _**changed my signature**_?? But how? I put the only copy of my private key in a sealed envelope in a cast-iron box inside a safe buried in the Gobi desert protected by a clan of nomads who have dedicated their lives and their childrens' lives to keeping my private key safe in perpetuity!"

"Didn't you know?" the bartender asks. "The components of the signature are just very large numbers. The sign of one of the signature components can be changed, from positive to negative, or negative to positive, and the signature will remain valid. Anyone can do that, even if they don't know the private key. But because Bitcoin includes the signatures in the transaction when it's generating the txid, this little change also changes the txid." He or she chuckles. "They say they'll fix it by _sep_arating the _sig_ natures from the transaction body. They're saying that these kinds of signature malleability won't affect transaction ids anymore after they do this, but I bet I can get my good friend Jihan Wu to delay this 'SepSig' plan for a good while yet. Friendly guy, this Jihan Wu, it turns out all I had to do was slip him 51 drinks and he was willing to mine a tx with the signature signs flipped." His or her grin widens. "I'm afraid your backoff transaction won't work anymore, since it spends a txid that is not existent and will never be confirmed. So here's the deal. You pay me 99% of the funds in the funding transaction, in exchange for me signing the transaction that spends with the txid that you see onchain. Refuse, and you lose 100% of the funds and every other HODLer, including me, benefits from the reduction in coin supply. Accept, and you get to keep 1%. I lose nothing if you refuse, so I won't care if you do, but consider the difference of getting zilch vs. getting 1% of your funds." His or her eyes glow. "GENUFLECT RIGHT NOW."

### Lesson learned?

* Payback's a bitch.
* Transaction malleability is a bitchier bitch. It's why we needed to fix the bug in SegWit. Sure, MtGox claimed they were attacked this way because someone kept messing with their transaction signatures and thus they lost track of where their funds went, but really, the bigger impetus for fixing transaction malleability was to support payment channels.
* Yes, including the signatures in the hash that ultimately defines the txid was a mistake. Satoshi made a lot of those. So we're just reiterating the lesson "Satoshi was not an infinite being of infinite wisdom" here. Satoshi just gets a pass because of how _**awesome**_ Bitcoin is.

## CLTV-protected Spilman Channels

Using CLTV for the backoff branch.

This variation is simply Spilman channels, but with the backoff transaction replaced with a backoff branch in the SCRIPT you pay to. It only became possible after `OP_CHECKLOCKTIMEVERIFY` (CLTV) was enabled in 2015.

Now as we saw in the Spilman Channels discussion, transaction malleability means that any pre-signed offchain transaction can easily be invalidated by flipping the sign of the signature of the funding transaction while the funding transaction is not yet confirmed.

This can be avoided by simply putting any special requirements into an explicit branch of the Bitcoin SCRIPT. Now, the backoff branch is supposed to create a maximum lifetime for the payment channel, and prior to the introduction of `OP_CHECKLOCKTIMEVERIFY` this could only be done by having a pre-signed `nLockTime` transaction.

With CLTV, however, we can now make the branches explicit in the SCRIPT that the funding transaction pays to.

Instead of paying to a 2-of-2 in order to set up the funding transaction, you pay to a SCRIPT which is basically "2-of-2, OR this singlesig after a specified lock time".

With this, there is no backoff transaction that is pre-signed and which refers to a specific txid. Instead, you can create the backoff transaction later, using whatever txid the funding transaction ends up being confirmed under. Since the funding transaction is immutable once confirmed, it is no longer possible to change the txid afterwards.

## Todd Micropayment Networks

The old hub-spoke model (that isn't how LN today actually works).

One of the more direct predecessors of the Lightning Network was the hub-spoke model discussed by Peter Todd. In this model, instead of payers directly having channels to payees, payers and payees connect to a central hub server. This allows any payer to pay any payee, using the same channel for every payee on the hub. Similarly, this allows any payee to receive from any payer, using the same channel.

Remember from the above Spilman example? When you open a channel to the bartender, you have to wait around for the funding tx to confirm. This will take an hour _at best_. Now consider that you have to make channels for everyone you want to pay to. That's not very scalable.

So the Todd hub-spoke model has a central "clearing house" that transport money from payers to payees. The "Moonbeam" project takes this model. Of course, this reveals to the hub who the payer and payee are, and thus the hub can potentially censor transactions. Generally, though, it was considered that a hub would more efficiently censor by just not maintaining a channel with the payer or payee that it wants to censor (since the money it owned in the channel would just be locked uselessly if the hub won't process payments to/from the censored user).

In any case, the ability of the central hub to monitor payments means that it can surveill the payer and payee, and then sell this private transactional data to third parties. This loss of privacy would be intolerable today.

Peter Todd also proposed that there might be multiple hubs that could transport funds to each other on behalf of their users, providing somewhat better privacy.

Another point of note is that at the time such networks were proposed, only unidirectional (Spilman) channels were available. Thus, while one could be a payer, or payee, you would have to use separate channels for your income versus for your spending. Worse, if you wanted to transfer money from your income channel to your spending channel, you had to close both and reshuffle the money between them, both onchain activities.

## Poon-Dryja Lightning Network

Bidirectional two-participant channels.

The Poon-Dryja channel mechanism has two important properties:

* Bidirectional.
* No time limit.

Both the original Satoshi and the two Spilman variants are unidirectional: there is a payer and a payee, and if the payee wants to do a refund, or wants to pay for a different service or product the payer is providing, then they can't use the same unidirectional channel.

The Poon-Dryjam mechanism allows channels, however, to be bidirectional instead: you are not a payer or a payee on the channel, you can receive or send at any time as long as both you and the channel counterparty are online.

Further, unlike either of the Spilman variants, there is no time limit for the lifetime of a channel. Instead, you can keep the channel open for as long as you want.

Both properties, together, form a _**very powerful scaling property**_ that I believe most people have not appreciated. With unidirectional channels, as mentioned before, if you both earn and spend over the same network of payment channels, you would have separate channels for earning and spending. You would then need to perform onchain operations to "reverse" the directions of your channels periodically. Secondly, since Spilman channels have a fixed lifetime, even if you never used either channel, you would have to periodically "refresh" it by closing it and reopening.

With bidirectional, indefinite-lifetime channels, you may instead open some channels when you first begin managing your own money, then close them only after your lawyers have executed your last will and testament on how the money in your channels get divided up to your heirs: that's just two onchain transactions in your entire lifetime. That is the potentially very powerful scaling property that bidirectional, indefinite-lifetime channels allow.

I won't discuss the transaction structure needed for Poon-Dryja bidirectional channels --- it's complicated and you can easily get explanations with cute graphics elsewhere.

There _**is**_ a weakness of Poon-Dryja that people tend to gloss over (because it was fixed very well by [/u/RustyReddit](https://www.reddit.com/u/RustyReddit/)):

* You have to store all the revocation keys of a channel. This implies you are storing 1 revocation key for every channel update, so if you perform millions of updates over your entire lifetime, you'd be storing several megabytes of keys, for only a single channel. [/u/RustyReddit](https://www.reddit.com/u/RustyReddit/) fixed this by requiring that the revocation keys be generated from a "Seed" revocation key, and every key is just the application of SHA256 on that key, repeatedly. For example, suppose I tell you that my first revocation key is SHA256(SHA256(seed)). You can store that in O(1) space. Then for the next revocation, I tell you SHA256(seed). From SHA256(key), you yourself can compute SHA256(SHA256(seed)) (i.e. the **previous** revocation key). So you can remember **just** the most recent revocation key, and from there you'd be able to compute _every_ previous revocation key. When you start a channel, you perform SHA256 on your seed for several million times, then use the result as the first revocation key, removing one layer of SHA256 for every revocation key you need to generate. [/u/RustyReddit](https://www.reddit.com/u/RustyReddit/) not only came up with this, but also suggested an efficient O(log n) storage structure, the shachain, so that you can quickly look up any revocation key in the past in case of a breach. People no longer really talk about this O(n) revocation storage problem anymore because it was solved very very well by this mechanism.

Another thing I want to emphasize is that while the Lightning Network paper and many of the earlier presentations developed from the old Peter Todd hub-and-spoke model, the modern Lightning Network takes the logical conclusion of removing a strict separation between "hubs" and "spokes". Any node on the Lightning Network can very well work as a hub for any other node. Thus, while you might operate as "mostly a payer", "mostly a forwarding node", "mostly a payee", you still end up being at least partially a forwarding node ("hub") on the network, at least part of the time. This greatly reduces the problems of privacy inherent in having only a few hub nodes: forwarding nodes cannot get significantly useful data from the payments passing through them, because the distance between the payer and the payee can be so large that it would be likely that the ultimate payer and the ultimate payee could be anyone on the Lightning Network.

### Lessons learned?

* We can decentralize if we try hard enough!
* "Hubs bad" can be made "hubs good" if everybody is a hub.
* Smart people can solve problems. It's kinda why they're smart.

## Future

After LN, there's also the Decker-Wattenhofer Duplex Micropayment Channels (DMC). This post is long enough as-is, LOL. But for now, it uses a novel "decrementing `nSequence` channel", using the _**new**_ relative-timelock semantics of `nSequence` (not the broken one originally by Satoshi). It actually uses multiple such "decrementing `nSequence`" constructs, terminating in a pair of Spilman channels, one in both directions (thus "duplex"). Maybe I'll discuss it some other time.

The realization that channel constructions could actually hold more channel constructions inside them (the way the Decker-Wattenhofer puts a pair of Spilman channels inside a series of "decrementing `nSequence` channels") lead to the further thought behind Burchert-Decker-Wattenhofer channel factories. Basically, you could host multiple two-participant channel constructs inside a larger multiparticipant "channel" construct (i.e. host multiple channels inside a factory).

Further, we have the Decker-Russell-Osuntokun or "eltoo" construction. I'd argue that this is " `nSequence` done right". I'll write more about this later, because this post is long enough.

Lessons learned?

* Bitcoin offchain scaling is more powerful than you ever thought.
