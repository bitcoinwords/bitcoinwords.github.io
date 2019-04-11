---
title: "Bitcoin: Two Parts Math, One Part Biology"
permalink: "/bitcoin-two-parts-math-one-part-biology" 

tags:
  - CY19 Q1
  - Dan Held

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---

# [Bitcoin: Two Parts Math, One Part Biology](https://medium.com/@hugonguyen/bitcoin-two-parts-math-one-part-biology-b45ef48a0422)
### By [Hugo Nguyen](https://medium.com/@hugonguyen)
### January 3, 2019

**This is Part 5 of a 5 part series**
* [Part 1 - The Anatomy of Proof-of-Work](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667)
* [Part 2 - Bitcoin, Chance and Randomness](https://medium.com/@hugonguyen/bitcoin-chance-and-randomness-ba49a6edf933)
* [Part 3 - How Cryptography Redefines Private Property](https://medium.com/@hugonguyen/how-cryptography-redefines-private-property-34cd93d86036)
* [Part 4 - Bitcoin's Incentive Scheme and the Rational Individual](https://medium.com/@hugonguyen/bitcoins-incentive-scheme-and-the-rational-individual-dc20effa4715)
* [Part 5 - Bitcoin: Two Parts Math, One Part Biology](https://cryptowords.github.io/bitcoin-two-parts-math-one-part-biology)

<br>

***

> "The Times 03/Jan/2009 Chancellor on brink of second bailout for banks"

Ten years ago today Satoshi Nakamoto immortalized these words by embedding them in Bitcoin's very first block — the genesis block. They are a solemn reminder of the unfair and broken system we all live under, and likely the reason Satoshi created Bitcoin in the first place: to wrest control of money back from governments and central bankers [1].

The last 10 years has been nothing short of a miracle. The Bitcoin network has been up 24/7, boasting an impressive record of 99.98% [uptime](http://bitcoinuptime.com) [2]. What is most amazing is that Bitcoin achieved this without anyone being in control.

Bitcoin is a unique invention because it uproots the very foundation of our society: it redefines money. Money, together with language, are considered the 2 most important tools we humans use to cooperate and build civilizations.

My personal journey into Bitcoin has also been extremely rewarding. Very few things are as intellectually stimulating as Bitcoin. Grokking Bitcoin means going down the rabbit hole that is finance, money, history, economics, computer science and biology. It means retracing the footsteps of giants such as Cardano, Pascal, Turing, Plato & Aristotle, Locke, Hume, Adam Smith, Nash, Kahneman & Tversky, Darwin, John Maynard Smith, Dawkins, Diffie, Hellman & Merkle, Szabo, to name a few. It means asking fundamental questions about the nature of the world we live in — much of which we often take for granted. Bitcoin sends you on an exhilarating and never-ending quest for truth.

Over the last several months I have written a series of articles — which I have called the Bitcoin Fundamentals series. My goal is to go down the rabbit hole as far as I could, to see what Bitcoin is really made of.

Writing these concepts down also forces me to articulate my thinking and helps my understanding of Bitcoin. I hope they will help others as well. The rest of this article will sum up what we have learned in the series.

Full index of the series:

* [Part 1 - The Anatomy of Proof-of-Work](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667)
* [Part 2 - Bitcoin, Chance and Randomness](https://medium.com/@hugonguyen/bitcoin-chance-and-randomness-ba49a6edf933)
* [Part 3 - How Cryptography Redefines Private Property](https://medium.com/@hugonguyen/how-cryptography-redefines-private-property-34cd93d86036)
* [Part 4 - Bitcoin's Incentive Scheme and the Rational Individual](https://medium.com/@hugonguyen/bitcoins-incentive-scheme-and-the-rational-individual-dc20effa4715)
* [Part 5 - Bitcoin: Two Parts Math, One Part Biology](https://medium.com/@hugonguyen/bitcoin-two-parts-math-one-part-biology-b45ef48a0422)

### The three sublayers of Bitcoin

Bitcoin is composed of 3 fundamental building blocks:

(i) Randomness-based Proof-of-Work

(ii) Public-key cryptography

(iii) Incentive scheme

If we consider Bitcoin as a base layer upon which further layers can be built upon (such as the Lightning Network, TumbleBit or sidechains), then these building blocks can be viewed as sublayers within the base layer.


![BTC protocol layers](/assets/images/cy19q1/cy19q1m1/hugo-1.png){: .align-center}*The 3 sublayers of Bitcoin base protocol*


There is an implicit hierarchy among these sublayers. That is:

**Sublayer 1**: Proof-of-Work (PoW) forms the first sublayer. PoW approximates energy burnt and is the bridge between the digital world and the physical world. PoW gives digital blocks — which are just strings of 1s and 0s — real-world significance. With PoW, the Bitcoin ledger becomes an unforgeable and costly asset, with real weight behind it.

**Sublayer 2**: Public-key cryptography (PKC) forms the second sublayer. If PoW enables a new digital asset, then PKC and specifically digital signatures "tokenize" that asset, chopping it into pieces. Individuals can then store these pieces privately and exchange them with each other.

**Sublayer 3**: Finally, Bitcoin's incentive scheme forms the third sublayer, which sustains the system created by sublayers 1 and 2. Bitcoin is a dynamic network. It resembles a living organism whose heart beats roughly every 10 minutes. Bitcoin's incentive scheme provides the engine for this heartbeat, and is built on the token natively generated by sublayer 2.

Sublayer 2 wouldn't matter without sublayer 1. Sublayer 3 wouldn't matter without sublayers 1 and 2.

These sublayers together form the three-legged stool that is the foundation of the entire Bitcoin ecosystem. [3][4]

### **Two Parts Math, One Part Biology**

From the exploration in the series, we have also learned that under the hood:

* Randomness-based PoW is based on math
* Public-key cryptography is also based on math
* Incentive scheme is based on human behavior

It can be said then, that Bitcoin is two parts math, one part biology.

It's worth noting that both randomness-based PoW and PKC rely on the same mathematical concept underneath, namely [one-way function](https://en.wikipedia.org/wiki/One-way_function), but they form very distinct parts of the system. PoW creates the digital asset, while PKC tokenizes it.

The third sublayer of Bitcoin, incentive scheme, is arguably Bitcoin's weakest link. Unlike the first 2 sublayers, it relies on human behavior, which is less consistent and rigorous than mathematical principles. Human behavior exhibits [bounded rationality](https://en.wikipedia.org/wiki/Bounded_rationality), which is coded at the gene level, but imperfect. Humans are prone to miscalculations and occasional irrational behavior.

It remains to be seen whether Bitcoin's incentive scheme would be strong enough to hold the network together for the long term.

### Final Words

I would like to close out the series by saying that in no way does this constitute a complete understanding of Bitcoin. But I hope it will serve as a good starting point for someone who is new to Bitcoin. Some of the content in this series are my own personal opinions. The reader would do well to do his or her own research and form their own opinions. "Don't trust, verify" works equally well in Bitcoin and in learning.

### Acknowledgements

Special thanks to [Nic Carter](https://medium.com/@nic__carter), [Steve Lee](https://medium.com/@moneyball), [Jimmy Song](https://medium.com/@jimmysong), [Hasu](https://medium.com/@hasufly), [Murad Mahmudov](https://medium.com/@muradmahmudov) and [Dan Held](https://medium.com/@danhedl) for their extremely valuable feedback in the writing of this series.

_[1] The genesis message also doubled as proof that Satoshi did not unfairly premine before January 3rd, 2009._

_[2] Bitcoin has experienced_ [_a dozen hours_](https://www.reddit.com/r/Bitcoin/comments/8d4fp3/bitcoin_has_worked_non_stop_for_9_years_without) _of "downtime": a combined total of 77 blocks where the network accidentally split, from 2 incidents in 2010 and 2013. This record is as impressive if not better than that of AWS, Google Cloud and Microsoft Azure._

_[3] The term "cryptocurrency" derives from the use of public-key cryptography (sublayer 2), which ironically captures only one of many crucial aspects of this technology._

_[4] These are the high-level building blocks. In practice the high-level building blocks are implemented using even smaller blocks. This includes hardware devices, software components, and communication protocols such as TCP/IP — each one bringing their own unique set of challenges._


Thanks to [Dan Held](https://medium.com/@danhedl?source=post_page).