---
title: "Corrections: Redactable Bitcoin"
permalink: "/corrections-redactable-bitcoin"

author: elaineou

tags:
  - Elaine Ou
  - 2016 Q3
  - Technology
  - Immutability

excerpt: Corrections: Redactable Bitcoin. Posted September 25, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Corrections: Redactable Bitcoin](https://elaineou.com/2016/09/25/corrections-redactable-bitcoin/)
### By [Elaine Ou](https://twitter.com/elaineou)
### Posted September 25, 2016

*This is a follow-up to an earlier post about Accenture’s creation of a [Redactable Bitcoin](https://elaineou.com/2016/09/21/redactable-bitcoin/).*

**Bitcoin Porn:**

[Jeff Garzik](https://twitter.com/jgarzik/status/778959607637151744) points out that porn can be embedded in any medium, whether it’s smoke signals or semaphore. So it’s not fair to say that porn can’t exist on the Bitcoin blockchain. Granted, the “porn” will look like nothing more than a series of [transactions](https://garzikrants.blogspot.com/2013/04/on-bitcoin-data-spam-and-evil-data.html), unless you know how to decode and interpret it.

**Accenture and the Mutable Blockchain:**

[Previously](https://elaineou.com/2016/09/21/redactable-bitcoin/) I said that Accenture’s redactable Bitcoin uses proof-of-work, an assumption made based on the specs of an [earlier prototype](https://eprint.iacr.org/2016/757). Accenture’s Media Relations rep contacted me to say that their new prototype still uses Bitcoin core, but without the mining. Also, in response to my characterization of their thing as a [horribly inefficient Excel spreadsheet](https://www.bloomberg.com/view/articles/2016-09-21/when-a-blockchain-isn-t-a-blockchain), he says:

*“That small addition*[of a master key] *is actually likely to make DLT*[distributed ledger technology]*more efficient (enabling pruning, compression, potentially reducing the number corrective transactions by half).”*

So not only did Accenture solve Bitcoin’s immutability problem, they also solved the blockchain-is-too-damn-long problem. And because the nodes receive updates from a “designated authority”, they also solved the [network broadcast problem](https://bitcoinmagazine.com/articles/how-a-bitcoin-backbone-gives-small-miners-a-leg-up-matt-corrallo-s-relay-network-1447961203).

![](/assets/images/2016/m9/corrections-redactable-bitcoin1.gif)

> Don’t ever take a fence down until you know the reason why it was put up. –G.K. Chesterton

Bitcoin is one of the most secure pieces of financial infrastructure in existence. It’s not missing a master key simply because Satoshi somehow overlooked that feature. Bitcoin is missing a master key because it was entirely designed to avoid a master key!

Decentralization is a substitute for a designated authority. See, blockchains doesn’t store information, nodes do. The raw transaction blocks that make up a “blockchain” are mainly used to relay information to others. Nodes themselves maintain an unspent-transaction-output (UTXO) database to validate new blocks and transactions[<sup>1</sup>](https://elaineou.com/2016/09/25/corrections-redactable-bitcoin/#utxo). After processing each new block into the UTXO database, nodes can [prune](https://bitcoin.org/en/release/v0.11.0) or archive their local blockchains to save disk space. They don’t need a designated authority to tell them how to do this.

Bitcoin works because every node enforces identical rules, and decentralization prevents them from colluding to break the rules. Bitcoin miners could mine invalid blocks with all the hashpower in China; it won’t matter as long as nodes commit to ignoring invalid blocks.

Bitcoin users ascribe value to bitcoin with the expectation that nodes continue to enforce predetermined rules. The minute that Bitcoin nodes allow exceptions to the rules via master key, the price of Bitcoin will fall to zero[<sup>2</sup>](https://elaineou.com/2016/09/25/corrections-redactable-bitcoin/#nation).

I make fun of [R3 Consortium](https://www.bloomberg.com/view/articles/2016-09-01/maybe-blockchain-really-does-have-magical-powers) for pretending to do blockchain while actually producing [data standards](http://r3cev.com/blog/2016/8/24/the-corda-non-technical-whitepaper), but they did get one thing right. If you want to create a decentralized clearing and settlement system, the first thing you gotta do is get everyone to agree to the same rules.

**1.** Bitcoin uses double-entry bookkeeping, where every transaction has a corresponding debit and credit. The unspent transaction outputs represent remaining credits.

**2.** It’s comparable to the value of a fiat currency where the central bank takes too many liberties with its monetary policy. People lose confidence in the government’s ability to keep its promises, and thus devalue the currency.

***

{% include signup.md %}
