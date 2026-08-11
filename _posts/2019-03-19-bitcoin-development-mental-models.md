---
title: "Bitcoin Development: Mental Models"
permalink: "/bitcoin-development-mental-models"

author: nopara73

tags:
  - nopara73
  - 2019 Q1
  - Mining
  - Privacy
  - Politics

excerpt: Bitcoin Development: Mental Models. Posted March 19, 2019.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin Development: Mental Models](https://medium.com/@nopara73/bitcoin-development-mental-models-9ac944435709)
### By nopara73
### Posted March 19, 2019

As I’m gaining more and more experience in Bitcoin development, from time to time I have an epiphany that completely changes the way I think, what I consider and how I handle the basic building blocks in my wallet softwares. In fact, every time this happened, I completely rewrote the wallet I was creating with the new insight in mind.
The past few days I think I recognized there’s another, even better way to do the things I am doing right now. Unfortunately rewriting my wallet is not an option this time, since Wasabi Wallet has a significant user base and it may be too risky to refactor the very essence of the software. But at least I can share these insights with you.

#### 1. Addresses Mental Model

A Bitcoin wallet has addresses and these addresses have balances.
I created my very first Bitcoin wallet: [DotNetWallet](https://github.com/nopara73/DotNetWallet), with an article accompanying it: [Build your own Bitcoin wallet](https://www.codeproject.com/Articles/1115639/Build-your-own-Bitcoin-wallet). This used this mental model. But the Bitcoin network doesn’t work this way. There are no addresses on the Blockchain and organizing your basic data structures around addresses prevents you to do anything remotely advanced in the future.

#### 2. Transactions Mental Model

The next step was to think in transactions instead of addresses. My second Bitcoin wallet: [HiddenWallet](https://github.com/zkSNACKs/WalletWasabi/tree/hiddenwallet-v0.6) worked this way. I had a bunch of transactions and whenever I had to do something, show the balance to the user, find the unspent UTXOs, I calculated everything from the transactions. This finally enabled me to have correct wallet-state at all times and do all kinds of advanced stuff, but this turned out to be terribly inefficient and I needed to add all kinds of helper data structures to make it less painful.

#### 3. Coins Mental Model

Next I changed to UTXO model, or rather coin model. My coins are smart, they know a bunch of things: who spent them, who they spend, labels, anonymity set, etc… This turned out to be a breeze to work with. The next iteration of my wallet, [Wasabi Wallet](https://github.com/zkSNACKs/WalletWasabi/) uses this data structure as base and in Wasabi everything revolves around coins.
Transactions would come in and I would organize the relevant utxos into coins.

The problem with this, as the software evolved, algorithms those are examining my Coins List are terribly slow when the wallet gets too fat. Thus, I became also vary of adding coins those are outside of the wallet, which would solve some edge cases, but I got scared if it would make everything even slower, this would just be another performance hit. I need a way to properly examine the relationship between these coins, and here are where graphs come in.

#### 4. Graph Mental Model

My next piffany is the Graph mental model. If I would to create a Graph data structure, where nodes would be my coins and the weighed edges would note the relationship between coins that may work out great.

The current coins would be the vertexes, however I would move some things to the edges. The edges are the important parts here.
The issue with the Coins Mental Model is that, coins are connected to each other through txids: which tx a coin is in and which tx spends the coin. But in reality there are various connections between coins. For example coins those share scripts should be connected, too. Coins those share the same label should be connected, too.

Ok, but why bother with weights? To do more accurate blockchain analysis, than we currently do. Take this transaction for example:

Let’s say input #0 (Coin #0) and output #2 (Coin #1) are from the same user and there are 6 different outputs, so the anonymity set of Coin #1 would be 6. But what if Coin #0 and Coin #1 is actually on the same address? Then the anonymity set of Coin #1 would be 1. We handle this relationship in Wasabi, but, these additional checks and heuristics are resource intensive and are all over the code base. It would be much better to add this relationship to the edges of the graph and drop the anonymity set concept altogether and go with a probabilistic model instead.

And then we could say things like this:

* If there’s no label or script match, the strength of Coin #1 and Coin #0 link is 1/6.
* If there’s label or script or script match, the strength of the link is 1 regardless of the transaction.

Introduce more connections and realize that the strength of the link is the weight of the graph. This would enable us to do a host of crazy graph theory things. For example we would be able to decide which coins are the most reasonable to merge together that would result in the least privacy compromise by just looking at the weights!

#### Butterfly Effect

Concepts like these may seem insignificant at first, but changing and tweaking things in these levels result in far reaching consequences.

Previously I talked about small changes resulting in far reaching consequences in a quite entertaining way, so you may want to give it a try. I’m off to[learn graph theory](https://mrpandey.github.io/d3graphTheory/)!

[https://gist.github.com/nothingmuch/864595842ffb08af61b77cfa003a4033](https://gist.github.com/nothingmuch/864595842ffb08af61b77cfa003a4033)

***

{% include signup.md %}
