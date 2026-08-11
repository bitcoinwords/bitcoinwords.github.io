---
title: "Why Bitcoin is called Bitcoin"
permalink: "/why-bitcoin-is-called-bitcoin"

author: olegandreev

tags:
  - Oleg Andreev
  - 2015 Q2
  - History
  - Technology

excerpt: Why Bitcoin is called Bitcoin. Posted May 16, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Why Bitcoin is called Bitcoin](https://blog.oleganza.com/post/119110031273/why-bitcoin-is-called-bitcoin)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted May 16, 2015

— Would you like to know why it is called “Bitcoin”?

Jane touched her glasses to show she’s preparing for one of those lengthy and passionate discussions. She sipped her orange juice and continued, without waiting for an answer.

— The closest who has ever come to creating Bitcoin was Nick Szabo. Have you read his pieces on [bit gold](http://unenumerated.blogspot.fr/2005/12/bit-gold.html), [secure property titles](http://szabo.best.vwh.net/securetitle.html) and [smart contracts](http://szabo.best.vwh.net/smart_contracts_idea.html)?

— I’ve heard of bit gold. It was a precursor of Bitcoin which did not take off, right?

— Not quite. Nick never proposed any specific protocol or an algorithm, only an overview. Bit gold was just an open-ended idea. It was not clear how exactly such bit gold “coins” should be generated in a trustless manner and how their ownership could be verified. Also, in his proposal gold coins were not fungible. Their value depended on scarcity defined by complexity of per-coin proof-of-work. There were a few other problems. Nick identified the need for a secure title registry, but never proposed a concrete protocol to make it work on a global scale.

— So what ingredient was missing then?

Mike started feeling impatient. It’s not the first time he would be involved in a conversation filled with words “trustless”, “ledger” or “coins”. He prepared to listen for a hundredth time about mechanics of Bitcoin, signatures, hashing and all that.

— Ha! There was none.

Mike looked genuinely puzzled.

— Look, Nick actually laid down all the ideas necessary for a functional system: proof of work for scarcity, need for secure decentralized title registry, smart contracts. All pieces of the puzzle were there, just not arranged as needed.

Jane’s eyes sparkled and she made a dramatic pause.

— Enlighten me :)

— What if you make scarce not the bit gold coins themselves, but the entire title registry? And make it so scarce that there could only be one, which automatically solves the synchronization problem. Individual coins then become perfectly fungible because they all (eventually) share the same proof of work. And since the proof of work gets stale over time and we need to add new transactions, we could timestamp new transactions with extra proof of work thus maintaining the scarcity by piling up all proofs of work into a one giant proof. Issuance of new units follows naturally: some programmed amount could be allocated for each batch of proof-of-work.

— Impressive. Does that mean that Nick is Satoshi?

— I’m not sure. Satoshi did not mention Nick Szabo’s writings at all. Either Nick naively tried to hide his relation to Bitcoin, or it was someone inspired by Nick who tried to direct attention to him.

— Or it is still Nick and he tries to make us think precisely that :)

— Either way, Bitcoin is clearly a result of studying Nick Szabo’s work which was incomplete without this tiny, but powerful unifying idea.

— You promised to tell me why it is called “Bitcoin”.

— Don’t you see it already? The ledger, blockchain, is just a single coin of bit gold with scarcity maintained by a growing proof of work. Hence “bit coin”, singular.

— Whoa. And this coin records its own history of ownership in itself. Fascinating! Sounds like a science fiction.

— It gets better! There are a few other interesting things that become evident from that perspective.

— I’m all ears.

— It’s getting late now. Lets continue next time.

***

{% include signup.md %}
