---
title: "Tweet Thread: What is an xpub?"
permalink: "/tweet-thread-what-is-an-xpub"

author: dannydiekroeger

tags:
  - Danny Diekroeger
  - 2020 Q3
  - Tweet Thread
  - Technical
  - xpub
  - Explainer

excerpt: Danny lays out the basics of xpubs. Posted August 30, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Tweet Thread: What is an xpub?](https://twitter.com/dannydiekroeger/status/1300154226123984896)
### By [Danny Diekroeger](https://twitter.com/dannydiekroeger)
### Posted August 30, 2020

~ What is an xpub? ~  
  
An xpub ("extended public key") along with an xprv ("extended private key") allows you to generate a nearly endless number of bitcoin addresses without having to store and protect the individual private keys for every single one  
  
👇 Time for a thread 👇 

![](/assets/images/2020/m9/dd1.png)

1/ To protect your privacy, it's good practice to use a new bitcoin address for every transaction  
  
But each new address requires its own private key...  
  
Back in the old days (pre-2013), bitcoin wallets would generate and store a new private key for every new address 

2/ Imagine running a popular exchange that uses millions of addresses...  
  
You would be forced to store and protect millions of individual private keys  
  
What a headache! There had to be a better way... 

![](/assets/images/2020/m9/dd2.png)

3/ In 2013 [@pwuille](https://twitter.com/pwuille) authored BIP-32, which specified a standard for Hierarchical Deterministic Wallets  
  
This type of wallet allows you to generate a ton of addresses using only a single seed  
  
That single seed is called an xprv ("extended private key")  

[**bitcoin/bips** Bitcoin Improvement Proposals. Contribute to bitcoin/bips development by creating an account on GitHub. https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki) 

4/ If the concepts of private keys and public keys are confusing, now would be a good time to check out my previous thread that goes into more detail:  
  
[Threads on Twitter](https://twitter.com/dannydiekroeger/status/1283928379201212416) 

5/ Essentially an xprv is a private key, and an xpub is its public key, and each one is extended with additional data  
  
This extra data (called the "chain code") helps you generate a nearly endless number of additional keys 

6/ All these additional keys are generated using a standard pattern, so they can be re-calculated at any time!  
  
Why is this useful?  
  
Say you had a wallet with millions of addresses in it, and tragically all the data got destroyed... 

7/ As long as you still had your original seed (xprv), you would be able to re-generate all your addresses by following the standard pattern, and you'd be able to recover your whole wallet! 

8/ So what is this special pattern that allows you to generate so many addresses from a single seed?  
  
The math involves some hashing which I won't go into detail about here...  
  
But one concept you should be familiar with is a "Derivation Path" 

9/ Derivation Paths are like instructions that tell you how to generate an address, and they look something like this: 

![](/assets/images/2020/m9/dd3.png)

10/ Each Derivation Path provides all the instructions needed to calculate the address and its corresponding private key  
  
By applying the Derivation Path to the xpub, you get the address  
  
And by applying the Derivation Path to the xprv, you get the private key 

![](/assets/images/2020/m9/dd4.png)

11/ Note, I'm skipping over the concept of "Hardened Derivation", in which the xprv is also used to generate the addresses  
  
But let's keep it simple for now...  
  
Just think:  

* Xpub generates Addresses  
* Xprv generates Private Keys 

12/ Using HD wallets is a nice way to organize your addresses, as the different numbers in the Path allow you to organize your addresses in a tree-like structure...  
  
A common use case is to put all Receiving addresses on one branch, and all Change addresses on another branch 

![](/assets/images/2020/m9/dd5.png)

13/ A note of caution though - it's a good idea to keep your xpub private!  
  
If somebody has your xpub, and you're using normal derivation paths, then they'll be able to calculate all your addresses and see the entire contents of your wallet! 

14/ This is why auditors might ask for your wallet's xpub  
  
Without the xpub, they'd have no way of knowing that all your different addresses are connected (assuming you don't send transactions between them) 

15/ So to recap:  
  
* An xpub is public key with some additional data that lets you generate a ton of addresses  
* An xprv is the private key that lets you generate a ton of private keys that correspond to these addresses 

16/ And together they are the foundation for HD wallets, which are a neat way to organize your wallet without having to store a bunch of individual private keys 

17/ Hope this was helpful! Shoutout to [@PeterMcCormack](https://twitter.com/PeterMcCormack) for the original question  
  
I hope that everyone feels comfortable asking questions, and I hope everyone can be more friendly about explaining complex topics to others  
  
This stuff is complicated! 18/ For more educational threads on all the basic technical concepts behind Bitcoin, check out this mega-thread where I've linked all my previous ones:

18/ For more educational threads on all the basic technical concepts behind Bitcoin, check out this mega-thread where I've linked all my [previous ones](https://twitter.com/dannydiekroeger/status/1282000262782042117).

19/19 And check out [my email list](https://dannydiekroeger.substack.com/) to stay connected with me

***

{% include signup.md %}

