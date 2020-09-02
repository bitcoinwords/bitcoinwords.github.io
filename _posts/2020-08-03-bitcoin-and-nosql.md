---
title: "Tweet Thread - Bitcoin and NoSQL"
permalink: "/bitcoin-and-nosql"

author: dhruvbansal

tags:
  - Dhruv Bansal
  - 2020 Q3
  - Database
  - Blockchain
  - Tweet

excerpt: Dhruv Bansal compares Bitcoin and NoSQL. Posted August 3, 2020

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Tweet Thread - Bitcoin and NoSQL](https://twitter.com/dhruvbansal/status/1290398087689703428)
### By [Dhruv Bansal](https://twitter.com/dhruvbansal)
### Posted August 3, 2020

\1 Try this one on:

Bitcoin is a distributed, append-only, eventually-consistent, content-addressable key-value store written to by public auction.

Multisig UTXOs are stateful synchronization primitives enabling "database transactions" for client applications at higher layers.

\2 Congrats if you made it past tweet #1! (Phew)

This thread explains the tweet above by comparing bitcoin to NoSQL databases.

To be clear, bitcoin is *much* more than "just" a database. But we might learn something from thinking about it like one.

First, a little history...

\3 At one time, "database" generally meant "relational database": a program with a sophisticated model for storing data and a general-purpose (sometimes Turing-complete) language for querying data ("SQL").

There were other types of databases, but "SQL databases" were ubiquitous.

\4 SQL databases run on a single *central* server (nerds: ignore sharding & replicas pls). As data volumes increase, the usual strategy is to make the server bigger.

But the huge volumes of data on the Internet led this "scale up" strategy to fail. Servers can only get so big...

\5 This led to a new strategy: "scale out," distributing your database across many servers.

SQL can't be scaled out; you need to start from a new design that understands it will be running in a distributed world.

The resulting family of distributed databases was called "NoSQL".

\6 There are many flavors of NoSQL but they share commonalities:

* Distributed (no "leader" or "single source of truth")
* Append-only (deletes are new writes, peers gossip & replay the full dataset)
* Eventually-consistent (disparate "forks" can exist)

Remind you of anything??

\7 I sold NoSQL to large companies. Customers worried

* It's too new, I don't understand it
* Seems really hard to use
* There are so many, which should I pick?
* It's too limited, why can't it do more?
* Forks? I need certainty!
* Compliance won't approve this

Seem familiar?

\8 Today NoSQL is widely accepted; it powers many Internet companies (including Twitter).

Bitcoin *is* NoSQL! It inherits all the historical objections NoSQL overcame PLUS a whole new set based on its social & economic innovations.

Let's dig more into bitcoin as NoSQL database.

\9 Most NoSQL databases are also, on some level, key-value stores. Unlike SQL's rich data structures, NoSQL keeps it simple:

> GET key1
(None)
> SET key1 value1
> GET key1
value1

Simplicity leads to scalability: KV stores like above are the largest databases in the world today.

\10 Bitcoin is also a key-value store. When you "look up the balance of an address" what are you really doing?

> GET address1
[utxo1, utxo2, ... ]

Addresses are the keys & UTXOs are the values, the state the database is storing.

But bitcoin is a particular *kind* of KV store.

\11 Bitcoin is content-addressable.

Content-addressing means asking for data by name, not location. http://google.com not 172.217.164.174.

URLs work because "centralized" DNS maps names to locations.

But how can a *distributed* system choose names? This is a hard problem.

\12 Bitcoin uses a common solution: names (addresses) are created by hashing content (scripts).

There is no "registry" of valid addresses, they are created as needed by hashing scripts & then directly sharing.

This makes bitcoin more distributed (though less human-readable).

\13 But wait, isn't an address a "location", not a name (e.g. `GET address1` above)?

No! You only think that if you don't know the address' script. If you do (likely because it's *your* address), then your wallet is actually doing

> GET hash(script1)
[utxo1, utxo2, ... ]

\14 So bitcoin is a distributed, eventually-consistent, content-addressable, key-value store. This is the "traditional" part of its design.

The novel part is using a public PoW auction to process changes.

Why does bitcoin do this expensive thing no other NoSQL database has to?

\15 NoSQL databases are operated by one party who ensures nodes trust each other.

Bitcoin is the first NoSQL database run by multiple, possibly adversarial parties who *cannot* trust each other.

A PoW public auction was the innovation needed to solve this (double-spend) problem

\16 This catches us up through the first sentence of tweet #1! What about the second?

We've already seen that UTXOs are the state bitcoin stores. The rest of the second sentence might not make a lot of sense right now.  We first need to talk about data structures & transactions.

\17 How can "simple" systems such as KV stores support complex systems such as Twitter?

Because programming is all about layers. Simple systems with just the right amount of power are actually the best foundations for more complex systems.

The trick is where one divides layers.

\18 A simple example of a social network app

> GET friends_of_alice
[bob]
> GET friends_of_bob
[alice]

Alice & Bob are no longer friends, so we delete:

> SET friends_of_alice []
> SET friends_of_bob []

An inconsistency will occur if the 1st SET succeeds but the 2nd SET fails.

\19 This is why databases offer "transactions" -- a sequence of several changes with a guarantee that either all the changes will occur or none will (never just some).

Transactions avoid inconsistencies like the one above and so are extremely useful for application developers.

\20 This is because the structure of the data in the database may not match that of the data in my application. Changes to one may require multiple steps to be mirrored to the other.

Transactions are thus the locus of division between two layers: the database and the application


\21 Database transactions are also useful b/c they separate rates of change.

A client may make a large number of changes and then "batch" them all to the database. This is more efficient than writing each change individually, esp. if earlier changes are undone by later ones.

\22 Finally, database transactions help multiplex different clients' access needs. If one client is engaged in a long-running transaction changing lots of data, the system shouldn't pause for others.  It should allow other clients who are changing *different* data to go ahead.

\23 Multisig UTXOs are *how* bitcoin coordinates "database transactions" for complex applications.

Stakeholders in the application hold keys in the multisig. The transaction only "commits to the database" if sufficient keyholders sign.

Meanwhile, all sorts of magic can happen.

\24 Offline data can be used by a signer to determine whether they'll sign (See [@unchainedcap's](https://twitter.com/unchainedcap) loans or a friendly wager on Caravan). This is the best current solution to the oracle problem.

A lightning network channel can process many "in-channel" payments before it commits.

\25 To close, just as it's possible to build any app you want on modern NoSQL databases it will be possible, through multisig UTXOs, to do the same on bitcoin.

No, we won't be storing all the world's data in a giant sharded blockchain.

But we will be building a world computer.


***

{% include signup.md %}