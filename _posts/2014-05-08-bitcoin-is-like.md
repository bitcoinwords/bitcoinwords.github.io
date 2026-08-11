---
title: "Bitcoin is like..."
permalink: "/bitcoin-is-like"

author: olegandreev

tags:
  - Oleg Andreev
  - 2014 Q2
  - Education
  - Philosophy

excerpt: Bitcoin is like.... Posted May 8, 2014.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin is like...](https://blog.oleganza.com/post/85111558553/bitcoin-is-like)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted May 8, 2014

**Bitcoin is like physical cash:** it is not reversible and you are responsible for handling it. If you lose your wallet, you lose your money. You can give bitcoins to someone to hold them for you, but it will be like with any bank: you have to trust them that they won’t run away with your cash.

**Bitcoin is unlike physical cash:** you can store as much as you want and it will not take any space. You can send it over the wire to anyone. It is impossible to counterfeit. You can’t give it in one second: to actually guarantee that transaction has happened, you have to wait 10-15 minutes for the cryptographic proof to be produced by the network. However, for small in-person payments you sometimes can accept zero-confirmation payments with relatively low risk of transaction being cancelled.

**Bitcoin is like gold:** it cannot be produced at will, there’s a limited amount of it and this amount is scattered in spacetime continuum (mostly time). To get some bitcoins someone should give them to you, or you should *mine* them. Like gold, Bitcoin is shiny: it attracts people with its beautiful engineering, built-in contract programming language, wise incentives, and libertarian promise of freedom from coercion.

**Bitcoin is unlike gold:** supply of Bitcoin is completely fixed via scheduled mining (only so much bitcoins are created per hour). You have a guarantee that no one will suddenly find a mountain of bitgold or mine it on asteroids. Unlike gold, Bitcoin difficulty is adjusted to the mining efforts to keep the schedule fixed. You may dig up all the gold in one day, but it will never be possible with Bitcoin no matter how fast computers will ever become. Growing mining efforts can only bend schedule slightly (network adjusts difficulty to producing 6 blocks per hour, but if network constantly grows it may produce 7-8 blocks per hour).

**Bitcoin is like bank:** there are computers, a database and transactions. Database stores entire history of all incoming and outgoing payments: who send how much to whom. Everything is digital. There are no vaults with gold or personal deposit boxes, only bookkeeping in a single “ledger”.

**Bitcoin is unlike bank:** everyone can verify the integrity of the ledger. There is no manager in charge of updating the ledger and making sure it is not tampered with. Any person may have as many accounts as they like and all accounts are anonymous (unless one reveals his identity himself). Ledger does not store names, only balances and account numbers. There is no possibility of “fractional reserve” when bank loans out more money than it actually has. In fact, there are no debts on bitcoin ledger: either you have money on your address and it is fully yours, or you don’t and you can’t use it at all. Also, Bitcoin allows to lock money with “contracts”: cryptographic puzzles designed to spread the decision making between several people or across time.

**Bitcoin is like Monopoly money:** there are abstract tokens that are not claims to any value. People value them because they choose to play the game. In fact, the same is true for gold or any other money.

**Bitcoin is unlike Monopoly money:** there is a limited supply of tokens and no one can counterfeit them. This makes them a good candidate for a universally recognized collectible like gold or silver coins.

**Bitcoin is like Git:** in Git (a distributed version control system) all your changes are organized in a chain protected by cryptographic hashes. If you trust the latest hash, you can get all the previous information (or any part of it) from any source and still verify that it is what you expect. Similarly, in Bitcoin, all transactions are organized in a chain (*the blockchain*) and once validated, no matter where they are stored, you can always trust any piece of blockchain by checking a chain of hashes that link to a hash you already trust. This naturally enables distributed storage and easy integrity checks.

**Bitcoin is unlike Git** in a way that everyone strives to work on a single branch. In Git everyone may have several branches and fork and merge them all day long. In Bitcoin one cannot “merge” forks. Blockchain is a actually a tree of transaction histories, but there is always one biggest branch (which has the value) and some accidental mini-branches (no more than one-two blocks long) that have no value at all. In Git content matters (regardless of the branch), in Bitcoin consensus matters (regardless of the content).

**Bitcoin is like Bittorrent:** the network is fully decentralized, there is no single “mint” or “bank”. The blockchain is like a single file on bittorrent: cryptographically authenticated and shared across many computers. Every participant, including miners are acting on equal grounds. If one part of the network becomes disrupted, transactions can flow through other parts. Even if the entire network goes down, information about transactions is still stored on many thousands of independent computers and no one’s money is lost. When people connect with each other again, they can continue sending transactions like nothing happened. Both Bitcoin and Bittorrent can survive a nuclear war because information does not become radioactive and can be safely replicated.

**Bitcoin is unlike Bittorrent:** instead of many independent “files”, there is one file that always grows: the blockchain. Also, the most important participants: miners are actually getting rewarded for their work with real money.

**Bitcoin is like freedom of speech:** every transaction is a short public message that can be pronounced no matter where or how. If some miners hear it, they will add it in the blockchain and that message will be forever in the history. Everyone will see it and no one will be able to erase it.

**Bitcoin is unlike freedom of speech:** saying something comes with a cost. Transaction moves coins that you must have to start with. So not every moron is allowed to shout, but only those who had a merit to acquire some coins in the first place. Also, miners may reject transaction if it’s spammy or does not contain enough fees. So no one provides anyone with freedom as “in beer”, but everyone tries to cooperate on a voluntary basis.

**Bitcoin is like magic internet money:** it simply is.

***

{% include signup.md %}
