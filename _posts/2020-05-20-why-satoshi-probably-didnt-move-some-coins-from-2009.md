---
title: "Why Satoshi (probably) didn’t move some coins from 2009"
permalink: "/why-satoshi-probably-didnt-move-some-coins-from-2009"

author: jimmysong

tags:
  - Jimmy Song
  - 2020 Q2
  - Mining
  - Cypherpunk
  - Technology

excerpt: Why Satoshi (probably) didn’t move some coins from 2009. Posted May 20, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Why Satoshi (probably) didn’t move some coins from 2009](https://medium.com/@jimmysong/why-satoshi-probably-didnt-move-some-coins-from-2009-ad967d40582a)
### By Jimmy Song
### Posted May 20, 2020

On block 631058 was mined [a transaction](https://blockstream.info/tx/cb1440c787d8a46977886405a34da89939e1b04907f567bf182ef27ce53a8d71) which spent an output from February of 2009, that is a month after the Bitcoin network went live. This has caused a bit of a price swing, not to mention, a lot of speculation, about whether this is Satoshi Nakamoto moving these coins or not.

In this article, I’m going to lay out the case for why it probably wasn’t Satoshi and the bit of digital forensics we can use to figure this out.

## What Happened

On May 20, 2020, a transaction with the id of [cb1440c787d8a46977886405a34da89939e1b04907f567bf182ef27ce53a8d71](https://blockstream.info/tx/cb1440c787d8a46977886405a34da89939e1b04907f567bf182ef27ce53a8d71) was broadcast onto the Bitcoin network and included in block 631058. The transaction’s input was from block [3654](https://blockstream.info/block/00000000a70ba4a405c67310757606dd955cf1a3a8e5c042335d78394ea6cb67), specifically the [coinbase transaction](https://blockstream.info/tx/f38d6f043c070ce9805ee81f46db4d32d0c9f148d62bbfbc0378bc5847c7dc70?output:0), which was mined on or around February 9, 2009. As the genesis block was created after January 3, 2009, this is a mere 37 days after the Bitcoin network’s inception.

There weren’t that many people mining on the network (or even knowing what it was), so the speculation is that this output may belong to Satoshi Nakamoto. Given that a private key is required to unlock the output, the fact that this output was spent suggests that the spender has access to the private key. If this is Satoshi, this would suggest that there may be a lot more Bitcoins to be dumped. The price of Bitcoin dropped around 5% as of this writing, perhaps based on that speculation.

## Bitcoin Back in 2009

February 2009 is about as far back as we can go in Bitcoin. At the time, Bitcoin was known to very few people, mostly people from the cypherpunk mailing list and most were mining because they thought it was an interesting experiment. Back then, there weren’t many transactions on the network other than Coinbase transactions, as people weren’t sending Bitcoins around. One notable exception is in block 170, where [Satoshi Nakamoto sent Hal Finney 10 bitcoins](https://blockstream.info/tx/f4184fc596403b9d638783cf57adfe4c75c605f6356fbc91338530e9831e9e16).

So for one thing, we know that Satoshi Nakamoto mined block 9, at least, and may have mined more. That said, there were other people mining on the network, not the least of which was Hal Finney:

![](/assets/images/2020/m5/why-satoshi-probably-didnt-move-some-coins-from-20091.png)

Because Bitcoin was so new and there was only one choice of software, everyone running the Bitcoin software at the time was mining.

## What We Can Infer

Because everyone was mining and there were few, if any, transactions that weren’t coinbase transactions back then, we can try to piece together some information based on the code back in Bitcoin v0.1.

Back in v0.1, there was a specific function in main.cpp that created proof-of-work. Of course, it was very easy to find proof-of-work back then by today’s standards, but it still required a good deal of CPU power to find. We can see the code that creates the coinbase transaction [here](https://github.com/trottier/original-bitcoin/blob/master/src/main.cpp#L2183).

The key piece of information we can gather in the coinbase transaction, besides the output, is something called the **extra nonce**:

![](/assets/images/2020/m5/why-satoshi-probably-didnt-move-some-coins-from-20092.png)

You can see in line 2190 that bnExtraNonce gets set to 0. Further in line 2212, the same variable increments in the while loop for generating coins (aka mining). Lastly, also in line 2212, the bnExtraNonce is added to the the coinbase transaction’s scriptSig via the “<<” operator. This is where we can use some forensics as this variable gets set to 0 and increments as long as the program is running. If the program restarts, this gets reset to 0. Thus, the longer the bitcoin software was running, the higher this number would be and further, this number would show up in the coinbase transaction’s scriptSig field, which we can examine on the blockchain.

This is where [Sergio Lerner’s examination of the early blocks](http://satoshiblocks.info/) have led to his labeling of certain coinbase transactions as having been from “Patoshi”. The coins in the graph are green if spent and blue if unspent with the y-axis being the extra nonce value and you can see the large blue strands:

![](/assets/images/2020/m5/why-satoshi-probably-didnt-move-some-coins-from-20093.png)

These are what are suspected to be Satoshi’s coins as the extra nonce value increases when a block is mined. These are also pretty long running processes that seem to get restarted every week or so. To be fair, we don’t know if these are specifically Satoshi’s coins, except something like block #9, but there’s decent forensic evidence given how the blue strands line up (when one ends, another one begins soon after), that these coinbase outputs have a good argument of being Satoshi’s.

## The Block in Question

Looking at block 3654, and specifically, [the coinbase transaction](https://blockstream.info/tx/f38d6f043c070ce9805ee81f46db4d32d0c9f148d62bbfbc0378bc5847c7dc70), we can look at the scriptSig to find the extra nonce value:

![](/assets/images/2020/m5/why-satoshi-probably-didnt-move-some-coins-from-20094.png)

The scriptSig has a 4-byte bits number (0xffff001d, which is the proof-of-work threshold) and then the extra nonce, which is 0xdd01. This number is in little-endian hexadecimal, which works out to be 477 in decimal.

Compare this with the nearest blue dots from one of the strands, blocks right before and after this block, which are blocks 3653 and 3655. They have extra nonces of 2367 and 2372 respectively.

## Conclusion

It’s possible, of course, that Satoshi was running Bitcoin on multiple computers and that this is from another computer than the blue strands for blocks 3653 and 3655, but given the clear blue pattern of all the coins that haven’t been spent, it seems likely that this isn’t the same person that owns the million or so Bitcoins.

***

{% include signup.md %}
