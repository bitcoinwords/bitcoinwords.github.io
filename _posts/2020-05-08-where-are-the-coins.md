---
title: "Where are the coins?"
permalink: "/where-are-the-coins"

author: fabianjahr

tags:
  - Fabian Jahr
  - 2020 Q2
  - Coins
  - Chain Analysis
  - Lost Coins
  - Coin Supply
  - UTXO

excerpt: Fabian Jahr examines missing coins. Posted May 8, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Where are the coins?](https://fjahr.com/posts/where-are-the-coins/)
### By [Fabian Jahr](https://twitter.com/fjahr)
### Posted May 8, 2020

**EDIT: An earlier version of this post linked to a BitcoinTalk post that speculated on the cause of BIP30 being the introduction of LevelDB. Pieter Wuille kindly informed me that LevelDB was [introduced after BIP30 occured](https://github.com/bitcoin/bitcoin/pull/1677) , which means that post was definitely false.**

The third Bitcoin halving is coming up quickly as I write this. I thought this would be a great time to write down what I learned about the amount of BTC in the UTXO set. Everyone is talking about coin supply at the moment but detailed, granular information on this topic seemed to be hard to find. Strangely, I only found this [excellent StackExchange answer by Pieter Wuille](https://bitcoin.stackexchange.com/a/38998/83363) very late into writing this article and there is a lot of overlap. If you like this post I recommend you read Pieter’s as well since it basically approaches the same question from the angle of future total coin supply and it’s a quick read. 

My insights on the current coin supply and the UTXO set mostly stem from my work on [#18000](https://github.com/bitcoin/bitcoin/pull/18000). There I am working on an index for coin statistics with the main goal to make the [RPC command](https://bitcoin.stackexchange.com/questions/24163/what-does-the-bitcoin-rpc-mean-and-how-is-it-used) `gettxoutsetinfo` faster. Even much earlier before starting the work on [#18000](https://github.com/bitcoin/bitcoin/pull/18000), I remember being thrown off by `gettxoutsetinfo` because of the `total_amount`. To my surprise, it was a very crocket number and that has not changed. At the time of this analysis, the blockheight is `629038` and the `total_amount` reported is `18362804.82079165`. 

This is weird because one of the first things most people learn about Bitcoin is that supply is pre-determined through the inflation schedule. It prescribes that the block rewards were 50 BTC initially, then 25 BTC, currently still 12.5 BTC. So the number should be evenly divisible by 12.5 theoretically but it is clearly not. In short, the reason for that discrepancy is that `gettxoutsetinfo` does not report the theoretical number of the inflation schedule but the actual number of unspent coins that the node knows about. Among others, the most intuitive reason for this is to save disc space. If these unspendable outputs would not be removed they could bloat the UTXO set and take up disc space on every full node, forever.

## The UTXO set

I want to briefly recap what the UTXO set (unspent transaction output set) is and why it exists to make a bit more sense of what is coming next. You probably know that Bitcoin has a blockchain and that every (fully-validating) node in the network is validating the whole blockchain. Simply put, the UTXO set is both the product of that validation process and helps speed it up as well. Each Bitcoin transaction has outputs and all non-coinbase transactions consume previous outputs as inputs. Outputs can only be spent once and need to be spent in full. If that is not the case a transaction, and a block that contains such a transaction, is invalid. For every valid block in the chain, all the unspent outputs created in a block are written into a database, the UTXO set. At the same time, every output that gets consumed by a transaction in a block as an input is considered spent and gets removed from the UTXO set. The UTXO set helps to speed up the transaction validation processes considerably since it gives a very quick overview of all the outputs that are valid and can be spent. 

Now, the RPC `gettxoutsetinfo` iterates over all these unspent outputs in the database and aggregates the total amount. One might say, `getutxosetinfo` would have been the better name to match today’s widely used terminology. But as we already established earlier, there seems to be some kind of a ‘leak’ since it reflects fewer bitcoins than expected. 

So how many coins are lost exactly and where are they? During my initial search for the answer, [I only found some high-level ideas](https://bitcointalk.org/index.php?topic=5220871.0) but not a detailed analysis of this. That’s what I am trying to provide here.

### The amount of missing coins

The Bitcoin supply schedule started with 50 BTC for every new block, with the reward halving every `210,000` blocks. That means we should currently have:

```
210000 * 50 + 210000 * 25 + ((629038 + 1) - 420000) * 12.5
= 10500000 + 5250000 + 2612987.5
= 18362987.5 BTC
``` 

Where does the +1 come from? It’s the Genesis block which is special because it is hardcoded into the codebase and located at index 0 of the blockchain. It also has a coinbase reward. So we are missing exactly:

```
18362987.5 - 18362804.82079165 = 182.67920835 BTC
```

## Finally, where did these coins go?

### Genesis Block

We just added it in with the +1 in the last paragraph and now we are taking it out again. Well, this post is about going into the details so it would be wrong to ignore this. The [Genesis block](https://blockstream.info/block/000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f) has [a coinbase reward](https://github.com/bitcoin/bitcoin/blob/b549cb1bd2cc4c6d7daeccdd06915bec590e90ca/src/chainparams.cpp#L106) but it is not spendable, and that’s why it also not part of the UTXO set. It is not spendable because Satoshi’s implementation is [skipping the Genesis block in validation](https://github.com/bitcoin/bitcoin/blob/b549cb1bd2cc4c6d7daeccdd06915bec590e90ca/src/validation.cpp#L1960), meaning it is also not adding the coinbase output to the UTXO set. They probably did this because block validation generally includes checking that the block has a valid ancestor, the previous block in the chain, as well. And if they had not skipped validation altogether they would have needed to code a special exception there which would have been more difficult. But that is speculation.

```
182.67920835 - 50 = 132.67920835 BTC
```

Status: **132.67920835 BTC still missing!**

### BIP 30

[BIP 30](https://github.com/bitcoin/bips/blob/master/bip-0030.mediawiki) describes a bug from the early days of Bitcoin. It turned out that there was no measure against duplicate transaction ids (TXIDs) in the earlier versions of Bitcoin. This was probably overlooked because a normal user can not simply create a transaction with a specific TXID. Each transaction depends, among other things, on the TXIDs of the outputs it spends. Since the TXID is a SHA256 hash and the previous TXIDs make it’s content unique, achieving a duplicate id would require the user to find a hash collision in SHA256, breaking one of the main security assumptions in Bitcoin itself. 

But there is an exception to that. Coinbase transactions don’t have parent tx’s, so their input is all zeros, which means the content of the SHA256 hash is not necessarily unique. So, unfortunately, a duplicate coinbase transaction id used to be both possible and valid and it happened twice in bitcoins history before it could be fixed:

* [Block 91722](https://blockstream.info/block/00000000000271a2dc26e7667f8419f2e15416dc6955e5a6c6cdf3f2574dd08e) coinbase TXID is repeated in [Block 91880](https://blockstream.info/block/00000000000743f190a18c5577a3c2d2a1f610ae9601ac046a38084ccb7cd721)
* [Block 91812](https://blockstream.info/block/00000000000af0aed4792b1acee3d966af36cf5def14935db8de83d6f9306f2f) coinbase TXID is repeated in [Block 91842](https://blockstream.info/block/00000000000a4d0a398161ffc163c503763b1f4360639393e0e4c8e300e0caec)

The implementation of BIP 30 in the Bitcoin Core code base still has the [overriding blocks hardcoded into the codebase](https://github.com/bitcoin/bitcoin/blob/b549cb1bd2cc4c6d7daeccdd06915bec590e90ca/src/validation.cpp#L2014). 

The reason why this is a problem may not be completely obvious but the term ‘transaction ID’ gives a hint. TXIDs also serve as the identifier for coins that are stored in the UTXO set. In this case, an existing output of the last coinbase got overridden by the next tx with the same TXID. 

As a fix, transactions with TXIDs that are already present in the UTXO set, i.e. that have existed before and still have unspent outputs, [are declared invalid](https://github.com/bitcoin/bitcoin/blob/b549cb1bd2cc4c6d7daeccdd06915bec590e90ca/src/validation.cpp#L2084). TXIDs can reappear but only after all outputs have been spent. But the rewards of the two overridden coinbase transactions mentioned above were lost forever. Since the block subsidy was 50 BTC at the time, that’s 100 BTC lost.

```
132.67920835 - 100 = 32.67920835 BTC
```

Status: **32.67920835 BTC still missing!** By the way, the more long term fix for this issue was implemented with [BIP34](https://github.com/bitcoin/bips/blob/master/bip-0034.mediawiki). It prescribed the introduction of a new block version (v2) which [required coinbase transactions to start with the height of the current block](https://github.com/bitcoin/bitcoin/blob/7bcc42b4035b878719d13201286e322989b415c5/src/validation.cpp#L3542). Since this part made coinbase transactions unique it is now virtually impossible to introduce a duplicate coinbase transaction by accident.

### OP_RETURN

For somewhat more experienced bitcoin users this opcode might come to mind first when they think of unspendable or ‘burned’ outputs. Producing those is the whole purpose of OP\_RETURN. Yes, the use of OP\_RETURN means that the output is automatically marked invalid and cannot be spent anymore. Because of that, these outputs are also [not included in the UTXO set](https://github.com/bitcoin/bitcoin/blob/b549cb1bd2cc4c6d7daeccdd06915bec590e90ca/src/script/script.h#L536). 

Looking at the blockchain I found `3.72417931 BTC` have been “burned” with the use of OP\_RETURN. That number still expands steadily, by the way, so the OP\_RETURN opcode is still frequently used. I imagine services like [OpenTimestamps](https://opentimestamps.org/) are responsible for most of it today.

```
32.67920835 - 3.72417931 = 28.955029039 BTC
```

Status: **28.95502904 BTC still missing!**

### Script too large

Another reason for an output to be [marked as not spendable](https://github.com/bitcoin/bitcoin/blob/b549cb1bd2cc4c6d7daeccdd06915bec590e90ca/src/script/script.h#L536) in the future is a script size that is too large. The threshold is defined in `MAX_SCRIPT_SIZE` and set to 10000 bytes. 

I did not find evidence of any specific cases of this, but since the rule was explicit in the code, I figured I should look into it. But it appears there were no coins that were excluded from the UTXO set specifically for this reason. 

Status: **28.95502904 BTC still missing!**

### Unclaimed Miner Rewards

This may sound weird at first, but there is a possibility that miners don’t claim their full block reward in a block they mined. The mining reward in the coinbase transaction is not checked against a specific value but rather to [not exceed the valid block reward](https://github.com/bitcoin/bitcoin/blob/b549cb1bd2cc4c6d7daeccdd06915bec590e90ca/src/validation.cpp#L2190). So a block with a reward smaller than the sum of the current block subsidy and the total fees would still be valid. But for a miner who has mined a block with a smaller reward, there is also no way to claim these funds later. After the block is included in the blockchain these coins are also lost forever and will never appear in the UTXO set. 

Why would a miner do this? I can not think of any good reason, it seems much more likely that this is always the result of a bug. 

Thankfully Pieter Wuille lists some known incidents in his [StackExchange answer](https://bitcoin.stackexchange.com/a/38998/83363) saving me from writing more custom code and hours of research:

> *   Block 124724 tried to intentionally claim 0.00000001 BTC less than allowed, but accidentally also failed to claim the fees, losing 0.01000001 BTC.
> *   Between block 162705 and block 169899, 193 blocks claimed less than allowed due to a bug, resulting in a total loss of 9.66184623 BTC.
> *   Between block 180324 and block 249185, another 836 blocks claimed less than allowed, resulting in a total loss of 0.52584193 BTC.
> *   Block 501726 had no transaction outputs (except a 0-value commitment), losing the entire 12.5 BTC subsidy.
> *   Block 526591 didn’t claim half of the block reward, losing 6.25 BTC.

Pieter describes a loss of `28.94768817 BTC` in his answer. I found a few more satoshis that miners lost, most likely by miscalculating the total fee. My analysis showed `28.95502904 BTC` went missing this way, which is `734087 sats` more than Pieter accounted for.

```
    28.95502904 - 28.95502904 = 0 BTC
```

Status: **0 BTC still missing!**

### Other unspendable outputs

These are not all the outputs that are known to be unspendable. There are several more types of outputs that are impossible to spend (see the [list in this BitcoinTalk post](https://bitcointalk.org/index.php?topic=675321.0) by user DeathAndTax for example). However, these are still included in the UTXO set. An update on the numbers of these other unspendable outputs would certainly be interesting as well.

## Final thoughts

![Missing coins distribution](/assets/images/2020/m5/fj1.png) 

Pfew, I am really happy that worked out evenly at the end ;) So now you know why the `total_amount` is not the number you probably expected at first. I found it very satisfying to explore these internals of Bitcoin Core, especially because it had been an open question for me from the very first time I spun up a node. I hope you enjoyed reading this post as much as I enjoyed figuring these things out and writing them down. 

Special thanks to James, Max, Freerk, Felix and Elaine for reading and providing feedback on an earlier version of this post. 

You can find the custom code I used to collect these numbers [here](https://github.com/fjahr/bitcoin/commits/where-are-the-coins).


***

{% include signup.md %}