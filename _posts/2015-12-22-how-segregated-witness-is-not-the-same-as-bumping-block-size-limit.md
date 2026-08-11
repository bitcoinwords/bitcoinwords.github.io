---
title: "How segregated witness is not the same as bumping block size limit"
permalink: "/how-segregated-witness-is-not-the-same-as-bumping-block-size-limit"

author: olegandreev

tags:
  - Oleg Andreev
  - 2015 Q4
  - SegWit
  - Block Size
  - Technology

excerpt: How segregated witness is not the same as bumping block size limit. Posted December 22, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [How segregated witness is not the same as bumping block size limit](https://blog.oleganza.com/post/135710722553/how-segregated-witness-is-not-the-same-as-bumping)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted December 22, 2015

“Segregated witness” (“segwit”) is a proposed feature to improve transaction mutability, enable smooth script upgrades and double Bitcoin capacity by moving signature scripts out of the transaction inputs into a separate data structure committed to a block using a new rule compatible with older nodes.

Bumping block size limit is a hard fork: first, everyone must agree to follow new rules, then everyone willing to verify a payment to themselves has to download and verify bigger blocks. So a minority of less-powerful miners and/or recipients is out of luck: they have to beef up their bandwidth and CPU resources or disconnect from the network. This is how “hard fork” works.

Segregated witness, among other things, increases capacity of the blocks without forcing everyone to validate bigger blocks. If you expect old-style transactions, you can still validate 1 Mb base blocks as you always did. However, if you wish to accept payments using segwit transactions, you have two options: 1) either validate additional data (that is, loading and validating all segregated signature scripts that do not fit into base blocks); 2) or trust majority of miners to validate these for you, then you can validate only base blocks ignoring segwit data, or even just use SPV proofs.

Segregated witness can only be used safely if the super-majority of miners enforce it. This can be done in two ways: validating segwit transactions according to the new rules, or not mining segwit transactions yourself and only trusting other miners to mine segwit transactions correctly (see below on why it’s not a huge security hole).

If you are a **miner with sufficient resources**, you can fully enforce and validate segwit transactions at the expense of larger consumed bandwidth and higher CPU consumption.

If you **receive payments and have sufficient resources**, you can accept both old-style and segwit transactions doing full validation yourself (at the expense of higher consumed bandwidth and higher CPU consumption).

If you wish to **receive only old-style transactions**, you can safely ignore all extra overhead of segwit transactions.

If your **resources are very constrained**, you can opt into accepting old-style transactions at old costs and using SPV proofs (trusting miners) to validate segwit payments. You may choose supporting segwit transactions for lower-value payments and require old-style transactions for higher-value payments if you only can afford old-style validation.

If you are **mining with constrained resources**, then you may resort to not mining segwit transactions at all and trust other miners to validate segwit transactions (if any) correctly. You can validate old-style transactions at no extra cost. Why can you trust others not to mess with you? It’s easy. Imagine some miner with 20% hashrate directs half of their hashrate (10%) to create blocks with invalid segwit data. They make you lose 10% of earnings, but they themselves lose 50% of their income because half of their blocks are invalid. The cost of attacking a constrained minority of miners is hugely asymmetric: large-scale attack makes the attacker run out of money much faster than the victim.

As a result, segwit allows scaling Bitcoin capacity in a opt-in way. Those who want to take advantage of extra capacity need to expend extra resources, **but those who do not want to use the feature (no matter how small that minority is), do not need to expend any extra resources at all**. Therefore, censorship-resistance property of Bitcoin remains unchanged.

***

{% include signup.md %}
