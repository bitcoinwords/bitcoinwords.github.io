---
title: "Bitcoin turning into a multi layered system is the most interesting thing in crypto in 2018"
permalink: "/bitcoin-turning-into-a-multi-layered-system-is-the-most-interesting-thing-in-crypto-in-2018" 

author: berkessels

tags:
  - Ber Kessels
  - CY18 Q1
  - Scaling
  - Lightning

excerpt: Ber Kessels shares his opinion and excitement about Lightning network.

defaults:
  - scope:
      type: posts
---

# [Bitcoin turning into a multi layered system is the most interesting thing in crypto in 2018](https://berk.es/2018/02/09/bitcoin-turning-into-a-multi-layered-system-is-the-most-interesting-thing-in-crypto-in-2018/)
### By [Bèr Kessels](https://twitter.com/berkes/)
### Posted February 2, 2018


When you use Tinder, and you swipe someone, you probably don't sit there thinking "Let's create some TCP packages and send them over IP, hoping they reach the phone of that nice looking fellow there". You probably just think in terms of "lets swipe this nice fellow, Leo"

I'm bringing Tinder into this story to show the power of a layered architecture. You can swipe Leo because the Internet is made out of layers that You, Tinder, your phone, apps, your browser, can use for "free". Disclaimer: I don't actually have a Tinder, so I actually don't know if "swiping" is the right term. But, well, this is a story about Bitcoin.

So, TCP/IP is made up out of four layers: Link layer, Internet Layer, Transport Layer and Application Layer. For this story, only the last two are interesting. On the internet, data is transported in the transport layer. Applications such as your browser, Tinder, your email-client or even the security camera at your front-door, use the transport layer to transport data. The power of this design becomes apparent if you turn it around: Applications don't need to invent, maintain or run their own network, cables, or protocols. They can just tell the Transport layer "Hey, I've got a swipe, for Leo, can you deliver it to the Tinder servers? (so they can send it along to Leo)".

Now, back to Bitcoin. The Bitcoin community is rolling out this thing called "[Lightning Network](https://lightning.network) ". It is a layer on top of Bitcoin, in which value can be transported between people (aka "make payments"). It is _one_ of the possible layers that can run on top of Bitcoin, but it is the first, and an important one: making payments is one of the most important features of Bitcoin today, so logically that this is the first thing to be moved into an application layer.

This Lightning Network can be [used today](https://berk.es/2018/02/09/bitcoin-turning-into-a-multi-layered-system-is-the-most-interesting-thing-in-crypto-in-2018/). Sure, Leo needs to have a Lightning Network enabled [client](https://play.google.com/store/apps/details?id=fr.acinq.eclair.wallet) as [do you](https://github.com/lightninglabs/lightning-app), you might need to compile some stuff, might need to run your own server and so on, but it _is_ possible. Today.

Essentially Lightning Network is the birth of an application layer on top of Bitcoin. This might seem uneventful, but the birth of this second layer gives Bitcoin a new purpose: it "degrades" Bitcoin to a mere transport layer for value. This is not some "Pop! And we're done" event, but a long process. Right now, Bitcoin is that transport layer, but is also, still an application layer: you can buy pizza, or buy beekeeping-gear through this transport layer, just fine. So it isn't very layered _yet_.

This new layer is going to be so much better at this "paying" thing, that it will take an important feature "away" from Bitcoin: payments. But, before you get all angry: like with TCP/IP, one can use a layer directly, if you wish. You can just skip the transport layer, and deliver data directly over one of the lower layers, if you insist. You application can skip all the application layer stuff and interact with the transport layer directly, which happens a lot, actually. You've probably seen these "Use TCP/IP | use UDP"-toggles in some settings of some app. Here an app can bypass, say, HTTP, TCP and so on, and use a much more raw way of delivering. You can still interact with Bitcoin, in order to transfer or manage funds, just fine. It's just that with this new Application layer, it will become much easier to just use that instead.

If you want to [buy takeway](https://bitcoinmagazine.com/articles/ordering-meals-with-bitcoins-takeaway-com-bitcoins-pizza-home-1385160906/), or [beekeeping gear](https://imkershop.nl/), today, both you and the recieving party interact with the Transport layer directly. Tomorrow, we both will interact with an application layer; probably the Lightning Network, to settle that payment instead.

There will be more layers on top of Bitcoin, there will be layers on top of layers on top of layers, but deep down below, Bitcoin is the Layer that ensures value is transferred from you to Leo.

To me, this proves, again, that Bitcoin, as a project, "Gets It". Bitcoin does not need to be everything: it only needs to be a system to store and transfer value. Nothing more!

It does not need to invent, develop and maintain all the layers, just like Tinder does not need to maintain and invent everything from cables to how-to-get-a-swipe-to-Leo-protocols. Bitcoin needs to be a very secure, very solid, very stable layer to maintain these funds for all the layers on top of it. And Bitcoin is just that.

We should note, though, that a layered architecture was not envisioned by the inventor and early adopters of Bitcoin. They envisioned it more as a monolith: a single piece of software that handles all the possible use-cases and features in itself. At least, that is how I read the whitepaper: no-where was there a mention of "Application layers" or even "layers".

Second layers can choose different models, use-cases, or different parameters. Lightning Network is complex but also (very) secure. It is decentralised, albeit maybe (time will tell) less so than Bitcoin itself. Other networks might opt for less security. Or even more centralisation. Or tweak other parameters.

If, for example, all you need to register is "I still owe you a beer", there could very well be a layer that maintains "all the beers owed by everyone" in a central database (or it's own blockchain) and which registers a daily "state of the beer" on the Bitcoin layer. The possibilities are endless.

A lot of altcoins (or their advocates) did not design a layered system either. So many of these altcoins offer some "feature", like "speed", or "programmability", or "the ability to track bananas" in their core. They often present those built-in features as "the Bitcoin killer", but frankly, most of them have implemented these feature in the wrong place: as core part of their entire system, rather than as additional layers on top of standard value-transport-layers.

When you start looking at Bitcoin as "merely" _a the transport-layer for value_, you might start to see the opportunities for other layers on top. And you might see a missing feature as good design, rather than as a missed opportunity, or as a sign that Bitcoin is doomed.

You don't need "instant transactions, zero-fee" in your transport-layer, you need that in your application layer. So saying that "Ripple is better because it can scale up to Visa-Scale" is nonsense, because you should also mention the trade-off: Ripple has chosen to give away a lot of security maybe even all of it, in order to gain speed. And yes, I'm picking out Ripple because I consider that the biggest scam of the 21st century (closely followed by the Roger Ver Coin, by the way). Also, I'm not saying that it is a zero-sum game: that you can choose either speed or security. But making trade-offs is part of the game. Bitcoin does not make trade-offs if that hurts the decentralisation-property, or if it hurts security.

TCP/IP is not a very efficient system. A lot of resources are spent to ensure your "swipe for Leo" ends up at Leo's phone and not at Marks' phone, or even your current boyfriends phone. In some cases this overhead can be "ridiculous": sometimes far more data is sent around ensuring that your swipe arrives at the right place, than the actual content of, say, the swipe itself. I mean: TCP/IP is brilliant, but it needs a lot of trade-offs to be fault-tolerant, decentralised, secure and stable. Sometimes systems choose different protocols because TCP/IP is just not fast enough: you don't connect your computer-screen over the network to your computer, you use HDMI, or VGA: some other protocol that is much better at delivering pixels to your screen.

Bitcoin's function is similar: it needs to be solid and secure. It must be slow and clunky, if that is what is needed to be solid and secure. It's sole function is to guarantee that your funds are secure, that transactions are valid and that there is no single party that can take over the network or your funds.

As such, Bitcoin does not include a "programming language", like Ethereum does (Note: I actually _do_ like Ethereum but for different reasons), because Bitcoin chooses security over "fancy" new features like programming languages. It leaves things like "smart contracts" or "programmability" to another layer. Instead of including it in the base layer. Note, though that such a smart-contract-layer does not (really) exist yet, but nothing fundamental stops it from being rolled out.

Nor does Bitcoin offer very good privacy (compared to e.g. Monero or Dash). But there could very well be an application layer, some alternative to Lightning Network that enhances privacy. So, rather than building it into the base layer, it leaves increased privacy to the application layer.

Bitcoin does not offer an exchange in it's base-layer either (Like e.g. Stellar does). Nor does it offer file-storage, computing power or [tracking of Banana's](https://bananacoin.io/) in it's base layer.

By _not_ implementing features, by choosing to be conservative, Bitcoin remains the most secure, most solid, and most predictable Transport Layer for transporting value. Ever. Exactly the features you want from such a basic layer.

As a closing note, I'd like to stress that there certainly are altcoin-projects that are completely layered by design. Quite some "cryptocurrency projects" are actually an application layer on top of another transport layer: a vast majority of altcoins are basically tokens on Ethereum: they _are the Application layer_ on top of Ethereum! So: I'm not saying that all altcoins are wrong and only Bitcoin get's it right: I'm only offering an alternative way to view Bitcoin: not as a polished, finished, fancy project to be downloaded from the iTunes store, but as a single, technical layer. An important component in a vast and rapidly changing new field: managing value online.

Positive feedback, as well as images of cats, calling me _literally hitler_ for hating on your beloved altcoins, or other comments are very welcome at [my twitter](https://twitter.com/berkes) or [on reddit](https://www.reddit.com/u/berkes).

