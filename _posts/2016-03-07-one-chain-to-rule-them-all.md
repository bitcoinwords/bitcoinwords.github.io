---
title: "One Chain to Rule Them All"
permalink: "/one-chain-to-rule-them-all"

author: paulsztorc

tags:
  - Paul Sztorc
  - 2016 Q1
  - Mining
  - Money
  - Technology

excerpt: One Chain to Rule Them All. Posted March 7, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [One Chain to Rule Them All](http://www.truthcoin.info/blog/one-chain)
### By [Paul Sztorc](https://twitter.com/truthcoin)
### Posted March 7, 2016

> Bitcoin will reign supreme as “the” blockchain, no matter how many blockchains there are.

### Quarrels of the Ignorant

#### How Many Blockchains?

[Bitcoin Maximalism](https://www.youtube.com/watch?v=TMkb8E5JDZM&feature=youtube_gdata_player) is [an extremely pro-Bitcoin approach](http://blog.oleganza.com/post/140634349543/bitcoin-maximalism). It says: “Bitcoin is the best, and will remain so”. It strongly [rejects Altcoins](http://bitcoinhivemind.com/blog/crowdsales/#altcoins) – if an Altcoin invents something cool ([~0% likely](https://download.wpsoftware.net/bitcoin/alts.pdf)), Bitcoin can (and will) join it in doing that cool thing!

However, [some people](https://www.youtube.com/embed/c9CjWz2N5Hs?start=2031&end=2070.6&rel=0&autoplay=1) disagree. They believe that there will be [many blockchains](https://ripple.com/insights/financial-professionals-believe-in-billions-of-blockchains/).

But, even if we allow many chains, notice this: Viewpoint A, [“one chain to rule them all”](http://networkcultures.org/moneylab/2014/12/16/one-chain-to-rule-them-all/), doesn’t actually contrast with Viewpoint B, [“a billion blockchains”](https://www.youtube.com/embed/mLWhU3f0xlc?start=2948.1&end=2980.2&rel=0&autoplay=1).

After all, **the phrase “them all” is plural.**

#### Merged Mining

All true blockchain-experts can remember a time, April 2011, when [Namecoin](https://wikipedia.org/wiki/Namecoin) *merged* with Bitcoin, so that they could coexist in productive harmony. Namecoin was a “second” blockchain, but it was “ruled” by Bitcoin. Thanks to something called “merged mining” (another [Satoshi invention](https://bitcointalk.org/index.php?topic=1790.msg28696#msg28696)), anyone who mined Namecoin could re-use that mining for Bitcoin. Merged-mining allowed Namecoin blocks to exist “inside” Bitcoin blocks!

Right-click > “view” to enlarge.

![](/assets/images/2016/m3/one-chain-to-rule-them-all1.png)

[Left link](https://namecoin.webbtc.com/block/c72836f9e996b9ee788826a4fa70c112252ed03ea8e5db1cd091533366b02d1f.json). [Right link](http://www.yogh.io/#block:height:401615)

Namecoin demonstrated that *any number* of chains could hide inside Bitcoin, and simultaneously share the same PoW. Specifically, Namecoin was allowed to use all of Bitcoin’s PoW **for free** if only the miners would run the Namecoin software!

Merged-mining is a [waterwheel](http://pool.twincitiesdailyphoto.com/2008/water_wheel_como_park.jpg) which, if you clip *more* machines on it, does not slow down *and can actually spin faster*.

( This is why we always say “[using] **the** blockchain” or just “[using] **Bitcoin**”, in contrast to the clueless people who say “[using] blockchain” or “[using] blockchain**s**”. )

Even though *[**no one** uses Namecoin](http://randomwalker.info/publications/namespaces.pdf) today*, the NMC chain is currently [**271,844 times** more secure](https://etherscan.io/charts/hashrate) than [Ethereum](https://bitinfocharts.com/) (the current [#2 coin by marketcap](http://coinmarketcap.com/)), and [**187,919 times**](https://bitinfocharts.com/) more secure than Litecoin (the 2nd most secure proof-of-work coin).

#### Anchoring

The story is even better for those who want immutability, but don’t need blockchain-consensus.

The [process of “anchoring”, or using a PoW-blockchain to create an unalterable time-stamp](https://bitcoinmagazine.com/articles/the-rediscovery-of-bitcoin-s-blockchain-the-world-s-most-powerful-anchor-1449084048), is so breathtakingly convenient that *it has **no** requirements*. Thanks to some [fancy crypto](https://en.wikipedia.org/wiki/Merkle_tree), anyone can anchor *any number* of files, of *any size* (even whole databases) at a cost of **zero**. Bitcoin miners don’t need to run new software, and users don’t even need to send their data anywhere.

Whether you choose to *merge-mine* a blockchain, or to *anchor* a file, you will want to use **Bitcoin** (aka “the blockchain”) as your base-layer blockchain, because…

### Only Bitcoin’s Hashrate Stands a Chance

Hashrate is graded “pass/fail” – either yours is high enough to achieve “immutability”, or it isn’t.

Let me use a new mining-analogy to explain this.

#### The All-or-Nothing Radio

##### Antithesis

Let me first explain how PoW-security does *not* work.

It does not work like a car radio.

When I was younger, I wanted to listen to my iPod in my car. Unfortunately, my 2001 Jimmy was too new to have a cassette player. ( Recall that the [1/8th-inch-to-cassette adapter](http://ecx.images-amazon.com/images/I/91WBmv1GAcL._SX355_.jpg) was $5-$10, and worked perfectly. ) So, I had to get a (much more expensive) device which functioned as [a mini radio broadcast tower](https://auxcarkits.files.wordpress.com/2014/12/lates-ipod-car-adapter.jpg). You’d set it to broadcast on some unused frequency, and then you’d simply tune your car radio to pick up that frequency.

The funny thing is, every now and then, you’d meet someone on the road who, evidently, had the same setup as you did (down to the same ‘unused’ channel). As you approached each other, there would be static interference. Sometimes, you would hear their music instead of yours, or both audio tracks at the same time! And, I assume, other drivers could occasionally hear my music (without my realizing it). My broadcaster, however, seemed to be pretty weak (it lost a lot) probably because it was a cheaper model.

Anyway, that is an example of broadcasting-interference on a *continuous* scale. The static starts small, and continuously increases as the rival cars approach each other.

Blockchains are *not* like that.

##### Thesis

Instead, imagine that all the miners are power plants, producing power. They use this power to broadcast from their mini-towers. Each separate blockchain system (for example, Bitcoin, Litecoin, Ethereum) would be on a different radio frequency – they don’t interfere with each other, they aren’t aware of each other.

However, let us turn our attention to attackers: competing broadcasts on the same frequency.

This is where we’d expect “static” to arrive. If the honest miners were broadcasting “A” on 88.5 with 90% of the power, and attackers were broadcasting *something different*, (“B”) also on 88.5 (the Bitcoin channel) with 10% of the power, we might expect to hear a distorted version of “A”. But we hear nothing of the kind; just pure, crisp, crystal-clear “A”.

In fact, we can get clarity with <50% of the hashpower. Image only 40% of the miners are broadcasting “A”. If 5 different (non-identical) attacker groups, of 20%, 20%, 10%, 5%, 5%, are broadcasting overwhelmingly-similar-but-not-identical-to-A versions of “A”, then *everyone on the network* would still hear pure, unmolested “A”. No static.

On the other hand, if a fully-coordinated attacker group got 51% of the mining power, they could broadcast “B” (or “C” or “Q” or whatever they like). The original “A” message wouldn’t come through at all – everyone would be listening to “B” (and “B” would be coming in crystal-clear).

Bitcoin’s offer to share its hashpower is a generous one. It allows you to broadcast whatever you like, on 88.5, with 100% of 88.5’s voltage.

##### Join The City’s Hottest Party!

Bitcoin currently has *the maximum available hashrate on the planet*, making it immune to attack from the world’s supercomputers.

![](/assets/images/2016/m3/one-chain-to-rule-them-all2.png)

Again, recall that this offer is (nearly) **free** (requiring only that miners choose to run your software). With certain tweaks, it *is* completely free.

### Conclusion

There will be “one chain to rule them all”. Being “ruled by Bitcoin” is awesome. It’s like living in your own personal copy of the world’s most heavily-secured, most luxuriously-appointed mansion…rent free!

Those who resist Bitcoin’s blockchain, don’t understand the deal they are turning down. It’s that simple.

Add Disqus comments.

comments powered by

Disqus

***

{% include signup.md %}
