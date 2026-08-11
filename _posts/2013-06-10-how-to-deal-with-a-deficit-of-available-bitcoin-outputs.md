---
title: "How to deal with a deficit of available Bitcoin outputs"
permalink: "/how-to-deal-with-a-deficit-of-available-bitcoin-outputs"

author: olegandreev

tags:
  - Oleg Andreev
  - 2013 Q2
  - Technology
  - UTXO

excerpt: How to deal with a deficit of available Bitcoin outputs. Posted June 10, 2013.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [How to deal with a deficit of available Bitcoin outputs](https://blog.oleganza.com/post/52623059869/how-to-deal-with-a-deficit-of-available-bitcoin)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted June 10, 2013

You just installed a Bitcoin wallet and received your first 10 bitcoins. Do you think you can easily spend these 10 bitcoins in 10 shops during a visit to a mall? Not really.

Bitcoins do not exist as individual items. Once you received your first bitcoin payment, all you have is a single “transaction output” that you can spend. Once spent, it is no longer valid. In its place you’ll have two new outputs: one as a payment to someone else and another one as a “change” sent to yourself. To pay the second person you need to use this new output (“change”). But this new transaction will not be accepted or even relayed by the network before its parent transaction (you first payment) is included in the blockchain. So to make a second payment you’d have to wait 5-15 minutes before the first one is included. And to make another one, you’d have to wait another 5-15 minutes after that.

In addition, if you try to send a small amount from a relatively “fresh” output, people would ask for transaction fees to relay or mine your transaction. This is done to prevent DDoS attacks on the network. If you wait 24 hours after creating a new “change” output, you could send it for free, but doing so earlier will result in unpredictable and lengthy delays. Although, the usual transaction fee is very-very small at current prices (around 5 cents), you’d still have to wait for all previous transactions to be included in the blockchain before you can successfully publish another transaction.

In a sense, you may call a single output a “coin” (with some amount written on it). The more “coins” you have, the cheaper and faster your transactions will be. Think of it like having a single $50 bill when you need a quarter to pay for parking. You’d need to go somewhere to exchange that $50 for smaller bills and coins. Unlike real coins, transaction outputs are not displayed in any wallet app, so you don’t know in advance how many transactions can you spend. And even if they were displayed, it would add unnecessary complexity for the user.

This side of Bitcoin obviously sucks, but can be managed easily.

First, you may ask to receive money in multiple outputs. E.g. if you receive a big monthly payroll, you may ask to send you money in a single transaction with 10–20 distinct outputs, so you could spend several of them right away. They all may use the same address and your wallet will figure everything out automatically. The only thing you’ll notice is that you don’t have to pay extra or wait longer to get a couple of your simultaneous payments to get through.

Secondly, you can split your money by yourself in multiple outputs. This will result in the same result as above, except now it’s you who will pay transaction fees (fees are calculated per Kb, and for smallest transactions they are rarely required).

Third, your bitcoin wallet can keep track of your spendable outputs and it is running short of them, it may add an extra “change” output to the next transaction to increase amount of outputs. I don’t know if any of the existing apps can do that already.

Also, bitcoin wallet can make automatic transactions on your behalf using rarely needed outputs to split them in a more useful collection of different “denominations”. It can also mix these coins with other users to increase you privacy (so that random merchants wouldn’t know how much do you have in your pocket).

As of today, people don’t pay ten times a day with Bitcoin, but when this happens, we would need an automatic solution to have our transactions relayed quickly and cheap. Hopefully, developers of bitcoin wallets will take a note and think on solving this problem.

***

{% include signup.md %}
