---
title: "Tweet Storm - About Schnorr Sigs"
permalink: "/tweetstorm-about-schnorr-sigs"

author: bencarman

tags:
  - Ben Carman
  - 2020 Q4

excerpt: enter excerpt here

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

0/ For [#TaprootWeek](https://threadreaderapp.com/hashtag/TaprootWeek) today we are going to talk about adding Schnorr signatures to [#Bitcoin](https://threadreaderapp.com/hashtag/Bitcoin), why they are great, what optimizations we can get with them, and we'll tease the cool applications they can enable.  
  
👇👇👇

1/ First let's start out with hopefully what you ask yourself first about a new digital signature schema: are Schnorr signatures actually secure?  
  
In short, Yes.  
  
Today Bitcoin uses ECDSA for signatures which we must obviously consider secure. 

2/ It turns out Schnorr signatures can be considered slightly more secure as their security proof has less assumptions than ECDSA and no new ones! So if we consider ECDSA secure, then Schnorr must be secure as well! 

3/ If you want to get in deep with the actual security proof I recommend checking out waxwing's blog on the subject  
  
[joinmarket.me/blog/blog/liar…](https://joinmarket.me/blog/blog/liars-cheats-scammers-and-the-schnorr-signature/) 

4/ So, Schnorr is secure, but why do we want them?  
  
Switching to Schnorr signatures can actually gives a lot of efficiency gains, both in block space as well as in actual computation time.  
  
Let's talk about block space first 5/ Digital signatures generally consist of two 32 byte numbers, so naturally you'd think a signature is 64 bytes. Well sadly today in Bitcoin that is not the case, they are actually around ~72 bytes. This is because bitcoin currently uses something called DER encoding. 

6/ DER encoding requires we add a few extra bytes around our two 32 byte numbers which in general isn't necessary for Bitcoin because we don't need to support multiple types of signature encoding for each signature schema. 

7/ DER encoding isn't anything fancy or necessary it is just a result of the design decisions Satoshi made when initially creating bitcoin likely because of the use of the OpenSSL library.  
  
If you want to know more I recommend reading BIP 66:

[**bitcoin/bips** Bitcoin Improvement Proposals. Contribute to bitcoin/bips development by creating an account on GitHub.](https://github.com/bitcoin/bips) 

8/ Getting back to Schnorr, since we are adding a new signature schema to the protocol we can also define a new way to encode these signatures. So, what we are doing is just putting the two 32 byte numbers next to each other resulting in a smaller 64 byte signature. 

9/ Another way we can save block space by using Schnorr signatures is something called key aggregation, better known as MuSig. With key aggregation we can have one public key represent an arbitrary number of signers. 

10/ Key aggregation is a HUGE win because today any multisig contract today requires a key and signature (in total ~100 bytes) for every signer which can get very expensive. Reducing this to a single key and signature will save users on lots of block space and thus on fees! 

11/ The last and smallest gain we get is from switching to 33 byte public keys to 32 byte public keys. This isn't a huge gain, but with us switching to a whole new signature schema we can now store the public keys in the most compact way being 32 byte keys! 

12/ That entails the primary ways that we save on block space by using Schnorr: smaller public keys, smaller signatures, and key aggregation.  
  
Now, let's move on to the computation efficiency gains. 

13/ With Schnorr Signatures we can batch verify signatures.  
  
Today with ECDSA we need to take each signature and verifying them individually that they are correct. This is generally fine for something like checking a new transaction in your mempool but not ideal for an IBD. 

14/ Today Bitcoin has had ~589 million transactions all with at least one signature. This is a lot to verifying and optimizing this verification can help a lot with bootstrapping new nodes doing an initial block download. 

15/ With Schnorr we can take batches of signatures and verifying them together saving a lot on computation time. In BIP 340 [@pwuille](https://twitter.com/pwuille) has a graph showing the actual improvements. 

![](/assets/images/2020/m11/bc1.png)

16/ To further quantify this improvement, let's say it takes 1 unit of time to verifying a signature.  
  
Today without batch verification it takes n units of time to verifying n signatures.  
  
With Schnorr and batch verification, to verifying n signatures will instead be n/log n 

17/ Those are the majority of the base improvements of adding Schnorr signatures to Bitcoin. There are a lot of cool things we'll talk about tomorrow on different applications they enable and you'll see later how Taproot itself benefits from using Schnorr as well!






***

{% include signup.md %}