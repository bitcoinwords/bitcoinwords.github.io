---
title: "#savetherobots — Cryptocurrency for Dummies: Bitcoin and Beyond"
permalink: "/savetherobots-cryptocurrency-for-dummies-bitcoin-and-beyond"

author: junseth

tags:
  - Junseth
  - 2015 Q3
  - Mining
  - Economics
  - Money

excerpt: #savetherobots — Cryptocurrency for Dummies: Bitcoin and Beyond. Posted August 10, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [#savetherobots — Cryptocurrency for Dummies: Bitcoin and Beyond](https://junseth.com/post/126347086117/cryptocurrency-for-dummies-bitcoin-and-beyond/amp)
### By Junseth
### Posted August 10, 2015

Cryptocurrency for Dummies: Bitcoin and Beyond

[This article was stupid](http://www.toptal.com/bitcoin/cryptocurrency-for-dummies-bitcoin-and-beyond), so re-wrote it so that it makes any sense at all.

When Bitcoin was first created, no one knew whether it would work. It was a giant experiment, and it made extraordinary claims. Reasonable people ridiculed it, but some of us really strange believers began to use it. At this moment, there are [over 700 AltCoin](http://coinmarketcap.com/) implementations, which use similar principles of CryptoCurrency. These altcoins are usually intentional scams though some are passive, accidental scams that are doomed to fail, no matter what you’ve heard of them. Generally, they provide no added value or functionality over Bitcoin. Nearly all of them, were created as nothing more than a money grab by their original programmers.

Recreating Bitcoin is trivial, since all you need is to download Bitcoind and change a few variables and numbers. Should you do it?

No. An alt coin that uses the Bitcoin daemon is nothing more than a Bitcoin that is not in consensus with the rest of the network. They are un-spendable Bitcoins that uninformed people believe have value because a group of people have branded what amounts to an orphaned chain. Starting an altcoin makes you complicit in stealing people’s money if you are aware of this distinction. Since miners are rational, while they may mine the out-of-consensus chain, they will eventually return to the main chain or turn their miners off altogether.

### **Decentralized Information Sharing Over the Internet**

Decentral information sharing over the internet was accomplished to some degree by protocols such as bittorrent. This peer-to-peer file sharing system is robust and amazing, but it doesn’t solve what’s known as the double spend problem. Files can be duplicated and reduplicated with no consequence to the original file sharer. As such, files are infinitely duplicable, and many users can have a copy of the original file without removing the ability of the original holder of the file to also keep it. Bitcoin solves this problem specifically, which is why it has value. A person can hold a Bitcoin at the consequence of someone else holding it. Simply put, if I have a Bitcoin, you cannot have it also.

It does this through a means of probabalistic consensus meaning that the network validates with the rest of the network where Bitcoins are at any given time and allows any user to look at where they once were. This is called consensus. The network essentially votes on what the network looks like. Those who do not like the state of the network can vote against what it looks like. in the event that there is disparity between members of the network regarding what the network’s current state is, there is a fork of the network. These are resolved through economic incentives: if you are not on the right fork, you will not have coins that are (as) valuable. The coins in any fork could be spent, but those spends will not be accepted by the network over the long term, meaning that spending from a fork to a person who accepts coins from that fork will result in the recipient of the coins holding coins that are not part of the consensus. This would be a double spend, which is why it’s so important that the network come to consensus and that individuals on that network.

Good news! This is very easy since these consensus forks are rare, and usually require an inordinate knowledge of the system to take advantage of. So if you are using Bitcoins, you probably don’t have too worry very much about this unless you are hosting a consequential node or mining on the network. For the most part, Bitcoin users will never be passively affected by this.

Consensus is amazingly difficult, and requires a huge number of users in order to be robust since it is a voting system whose solidity is in its ability to not be compromised. As such, having a majority of the voting power needs to be expensive. This is the biggest reason that competing Bitcoin implementations, also known as altcoins, rarely gain any traction. They are not secure because of the number of computers voting on their networks is trivial.

### **Hashing**

Hashing has a few meanings. It might refer to shredding potatoes, taking the contents of a file, sending it through an algorithm, and receiving a small string of letters that will validate the uniqueness of a files contents, or it might refer to the act of hashing by a Bitcoin miner. We will discuss the last of these.

Let me speak to hashing/mining by analogy, and then explain more specifically how mining works. The goal of a miner is to complete what’s called an asymmetric problem correctly. An asymmetric problem in this sense is a bit like a digital Rubick’s Cube. It is hard to do the problem itself, but it is really simple to validate. If the miner completes the problem correctly, he will then bundle transactions that are currently in the mempool (the place where all transactions made in Bitcoin go before they are validated), timestamp them, and then add them to the last list of transactions. Each of these lists is called a block. Every 2016 blocks, the network average how long it took the computers to complete these transactions. If the average is greater than 10 minutes, the difficulty of the problem is lessened. If it’s less than 10 minutes, the difficulty of the problem is increased.

So what is hashing?

When a miner hashes, he does a very simple calculation that takes a very predictable amount of work and whose results are predictable. The end result is a string of numbers. The network needs a string of numbers that looks a certain way. Once such a string has been found, that miner will submit the solution to the network, the network will validate it, and then add his block to the network if the network decides it’s the correct answer. Once once miner is declared the winner, all of the other miners sigh in defeat, and begin mining the next block. ONLY ONE MINER WINS EACH BLOCK. When a miner wins, he receives an award of Bitcoins by the network. The miner does not receive the award immediately, but will receive them 100 blocks later. This is how Bitcoins are created. Over time, the number of Bitcoins awarded goes down, however, and will become smaller and smaller until 21 million coins are distributed. Miners will still make money, however, even then, because users who use the network pay a small (right now it’s about 3 cents) fee that is given to the miner who wins the block as payment for their services. This fee is the same for a $1 transaction or a $1,000,000 transaction.’

Isn’t that cool? Sorry to be so condescending. But I’m trying to keep my readers engaged here.

### **Digital Signature (Where Your Bitcoins are)**

Bitcoins are held on a private key. This is a key that no one in the world except the holder of the coins on that key should know. Owning a private key is a little bit like holding a checkbook. Only the holder of a private key can sign for transactions just like the owner of a checkbook can sign checks that will give a bank permission to remove funds from his/her account.

From the private key, using complicated equations that you nor I really need to understand, a public key can be created. This key can be shown to the network. It will be associated with that secret, private key, but will allow you to keep your private key. This public key is the address to which Bitcoins can be sent. Like the private key, it is a long series of numbers. At the end of the public key is a hash (this is the hash that doesn’t have to do with making hash browns or Bitcoin mining). This hash is an important part of any Bitcoin address as it will prevent users from sending coins to the wrong address. The network can verify whether the address is a possible, valid address.

Isn’t Bitcoin neat!?!?

### **Sending Money**

Sending money is simple. In most cases, simply let your GUI do the work. If you’re a Bitcoin wizard, however, you might use a product like Armory or Electrum to actually sign the transactions yourself. This is more secure, but generally unneeded for the average user.

### **Blockchain - The Global Ledger**

The Blockchain is a history of every transaction from today until it’s beginning. It is a necessarily public resource that is secured by the mining. The transactions listed in the blockchain are not chronological in any sense, but, rather, they are included at the whim of miners who setup rules regarding how and whether to include transactions. The haphazard nature of this inclusion is, in part, why Blockchains are bad as databases. Knowing where things are in them or how to find any given transaction output often requires an external database.

Should two miners come up with a solution that is correct enough at the same time, the network will fight for consensus. What this means is that some miners will begin mining on one of the forks, while others will mine on the competing fork. When the next block is found, miners will append their block to one of these miners’ blocks. In most cases, this will cause the network to reject the other block and select the block on the longer chain. The other block will end up being rejected by the network. The rejected block is called an “orphaned block.” It will be forgotten and left to die a sad meaningless death. The miner that found it will not receive their Bitcoins 100 blocks later. Pobre cito.

How miners pick which block to mine on has a lot to do with propogation times. Like anything and everything, sending a blocks is limited by physics. Unless sent through some kind of time space continuum or a a worm-hole, blocks take (as a quick guestimation) take anywhere from 6 seconds to 12 seconds to go from one node in the network to all the nodes in the network. Usually, miners will begin mining the block they see first. As such, if two people submit a block to the network at the same time, work will begin to be put into both sides of the fork until one wins.

### **Controlling the Money Supply**

In Bitcoin, there will only ever be 21 million coins. These coins can be separated down to 8 decimal places. As such, the Bitcoin network has more units than are currency in the world. Nothing more to be said about this.

### **Now… Start “Printing” Your Own Currency… If You’re an Idiot or a Scammer**

***

{% include signup.md %}
