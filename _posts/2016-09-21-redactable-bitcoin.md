---
title: "Redactable Bitcoin"
permalink: "/redactable-bitcoin"

author: elaineou

tags:
  - Elaine Ou
  - 2016 Q3
  - Technology
  - Immutability

excerpt: Redactable Bitcoin. Posted September 21, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Redactable Bitcoin](https://elaineou.com/2016/09/21/redactable-bitcoin/)
### By [Elaine Ou](https://twitter.com/elaineou)
### Posted September 21, 2016

***Update:** I made some redactions [corrections](https://elaineou.com/2016/09/25/corrections-redactable-bitcoin/).*

Bitcoin people frequently criticize banks for claiming to build blockchains while discarding proof-of-work, so [here comes Accenture](https://elaineou.com/wp-content/uploads/2016/09/redactableblock.pdf) with their own version of a blockchain. It keeps Bitcoin’s proof-of-work, and adds a master key.

(More specifically, it takes Bitcoin’s exact protocol but replaces the double-SHA256 hash with a chameleon hash inside a SHA256 hash. A chameleon hash is a hash function that contains a trapdoor.)

![](/assets/images/2016/m9/redactable-bitcoin1.jpg)

I suspect that Accenture’s Financial Services group does not know what it is actually getting here. Their [whitepaper](https://elaineou.com/wp-content/uploads/2016/09/accenture.pdf) begins by asserting that Bitcoin’s blockchain contains illegal porn that needs to be redacted. Good grief.

Then they spend two pages talking about the DAO.

The problem isn’t the redactability – sure, maybe Accenture’s Group Exec wants to scrub those bookings at the no-tell hotel from his credit card statement. I can sympathize with that. The problem is that Accenture misrepresents what a blockchain even *is*.

Accenture employees might be clueless, but their academic co-authors cannot possibly be ignorant of the fact that an application that runs on a blockchain ([the DAO](https://elaineou.com/2016/05/16/why-i-am-participating-in-the-daos-crowdsale/)) is separate from the blockchain itself (Ethereum). And, having modified Bitcoin Core, they know full well that porn cannot be stored on Bitcoin’s blockchain.

Look, it’s fine if people want to make [grandiose claims](https://elaineou.com/2016/09/20/how-blockchains-will-save-billions-in-clearing-and-settlement-costs/) about how blockchains will revolutionize the universe. It’s good for business around here. But now you guys are just making shit up to exploit the technological ignorance of banks. This is exactly how industries start getting regulated. Cut it out.

**Bitcoin and child porn:**
 [Yes](https://bitcointalk.org/index.php?topic=191039.msg1980099#msg1980099), Bitcoin’s blockchain contains transactions that have encoded URLs of child porn sites. So does this web page. In fact, this is an encoded URL, right here: “[1HJCcziSCEkUcDq5aRC68vxVdx6enWUrvf](https://blockchain.info/tx/dde7cd8e8f073a525c16c5ee4e4a254f847b7ad6babef257231813166fbef551)” (the link goes to a transaction in the Bitcoin blockchain explorer, not a porn site). If you know where to find this data on the blockchain, AND you know the algorithm for decoding the data, AND you actively take the time to decrypt it, AND you paste the decrypted URL into your web browser, then yes, I suppose you can get child porn from Bitcoin’s blockchain. You’ll have a hard time blaming Bitcoin for this one though.

**See Also:**
 G. Ateniese, et al. [Redactable Blockchain — or — Rewriting History in Bitcoin and Friends](https://eprint.iacr.org/2016/757). Cryptology ePrint Archive: Report 2016/757
 [When a Blockchain isn’t a Blockchain](https://www.bloomberg.com/view/articles/2016-09-21/when-a-blockchain-isn-t-a-blockchain) *–Bloomberg*

***

{% include signup.md %}
