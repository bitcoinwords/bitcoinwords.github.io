---
title: "Could Bitcoin's privacy benefit from Litecoin's EB MimbleWimble proposal?"
permalink: "/could-bitcoins-privacy-benefit-from-litecoins-eb-mimble-wimble-proposal" 

author: pieterwuille

tags:
  - Pieter Wuille
  - CY19 Q4
  - Privacy
  - Sidechain
  - Technology
  - Reddit Post
  - Confidential Transactions

excerpt: Pieter Wuille shares his thoughts on confidential transactions in a Reddit post. Posted December 2, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Could Bitcoin's privacy benefit from Litecoin's EB MimbleWimble proposal?](https://www.reddit.com/r/Bitcoin/comments/e65vdf/could_bitcoins_privacy_benefit_from_litecoins_eb/f9olxfy/)
### By [Pieter Wuille](https://twitter.com/pwuille)
### Posted December 2, 2019

It's not that simple.

I would personally very much like to see Confidential Transactions in Bitcoin. Hiding transaction amounts by default - while not a silver bullet for privacy on its own - would make CoinJoin a lot more powerful (right now you need to use matching amounts because you'd leak linkage otherwise anyway). I think it's fair to say that it may help achieve a level of privacy that is very hard to reach with existing on-chain techniques.

Confidential Transactions however very fundamentally change how transactions work, as cleartext amounts are currently expected in transactions. Without (extremely invasive) hard fork, this cannot be changed. Even if they're suddenly permitted, nobody can force existing wallets to suddenly adopt them. Doing so would break compatibility, and go against very basic expectations of not invalidating existing non-broadcast transactions. Such a change being successful probably implies Bitcoin lost some of its most valuable properties to begin with. Thus: CT (or any form of amount hiding) has to be opt-in.

But opt-in doesn't need to imply opt-in on a per-transaction basis. An extension block effectively does that: by having two clearly delineated sides and a need for explicit, possibly slow/expensive, operations to transfer between them, you create a world where CT is the default, and possibly even cheaper than the other side. Sure, people still have the option to use the legacy side, and for a long time they probably will due to compatibility reasons, but in the long term it probably means much better privacy than any solution with per-transaction choice for CT or not. It turns out that CT-in-an-EB is also far simpler and more efficient than trying to hack it into the existing transaction structure.

So, I believe that Extension Blocks are the only (somewhat) practical way of introducing CT to Bitcoin.

That said, there are many caveats:

* CT transactions are far more computationally expensive and larger than current transactions, and it would be very unfortunate if the more private choice ends up being more expensive to use.
* CT introduces a much stronger assumption on cryptography than we currently have. You can't just run through the UTXO set, sum up the values, and see that it doesn't exceed the expected subsidy.
* In fact, CT inherently either must make privacy condition on cryptographic assumptions, or soundness (=printing of money). Bitcoin currently relies on the ECDLP assumption for theft, but this can (in the long term) be upgraded to another assumption if necessary (e.g. because we believe ECDLP is on shaky grounds, quantum computing, ...). With CT this is not so easy anymore, as this assumption will now cover amounts as well.
* It's a pretty damn big change that would need a huge demand from the ecosystem to be successful.
* All the same issues apply to MW, and more. MW is a more advanced form of CT that has an even more invasive impact on basic data structures, and probably simply cannot be done without an EB at all, as it is so fundamentally different from Bitcoin's current blockchain (the MW blockchain can shrink over time!). It also removes Script or even the ability to have something Script-like.

Let me come back to point (3) above. There is a very fundamental result in zero-knowledge proof techniques that you cannot have both unconditional privacy and unconditional soundness. We however do know of ways to have either unconditional privacy or unconditional soundness, so there is a design choice between them.

* CT with unconditional privacy but computational soundness is the most common choice. This means that if somehow ECDLP breaks (math breakthrough, unexpected structure in secp256k1, quantum computer), someone could undetectably print coins, but the privacy of past (and future) transactions would be unaffected. To the best of my knowledge, Monero, ZCash, Grin, all use this model.
* CT with unconditional soundness but computational privacy is also possible. This means that an ECDLP break would not let anyone print coins, but the privacy of future (and past) transactions would be at risk. Unfortunately, this choice is much less efficient, and pretty much no systems use it.

Given Bitcoin's design focus on controlled inflation, I expect that many people would prefer the second model over the first if a choice needs to be made. There is however also a point to be made that if ECDLP is broken, the future of the system is inherently at risk, but we may not want to give up the privacy of the past when that happens - a point in favor of the first model.

The nice (or scary...) thing about an Extension Block based CT design is that we could have either, or both, and without actually directly affecting the value of the legacy chain. You'd need to move coins explicitly to the CT side, and if unexpected inflation would happen there, simply not all of it would be able to move back to the legacy side. Unexpectedly, this may actually mean a different exchange rate for coins on both sides, if the public's trust in the security for one is seriously affected.


***

{% include signup.md %}