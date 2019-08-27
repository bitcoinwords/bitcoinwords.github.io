---
title: "We Need Bitcoin Full Nodes. Economic Ones."
permalink: "/we-need-bitcoin-full-nodes-economic-ones" 

author: stadicus

tags:
  - Stadicus
  - CY19 Q3

excerpt: Stadicus makes the case for more full nodes. Posted August 1, 2019.

defaults:
  - scope:
      type: posts
---

# [We need Bitcoin full nodes. Economic ones.](https://medium.com/shiftcrypto/we-need-bitcoin-full-nodes-economic-ones-fd17efcb61fb)
### By [Stadicus](https://medium.com/@stadicus)
### Posted August 1, 2019

> Why is it important to run your own Bitcoin full node to have a say regarding Bitcoin consensus and verify your own transactions?

Bitcoin is about financial sovereignty. It's about holding a scarce bearer asset that cannot be counterfeited, seized or frozen. It' s about being part of a peer-to-peer network that does not employ middlemen to facilitate financial transactions. It is free speech money.

As a bearer asset that you truly own, private keys need to be in your possession, managed by a modern Bitcoin wallet application. It's hard to store digital secrets securely on potentially malware-riddled computers, so hardware wallets are a good way to keep your private keys out of the hands of hackers.

## But who guarantees that my bitcoin are really there?
A hardware wallet stores your private keys, but not your actual bitcoin. The wallet usually comes with a software companion app that allows you to manage your funds. But this software wallet is not downloading and verifying blocks from the Bitcoin network, so how can it know what your Bitcoin balance is?

Can it guarantee that your hard-earned bitcoin are really there? That an incoming transaction really confirmed on the blockchain?

The answer is that by default you are putting all your trust in a single party: your wallet provider. Lightweight software wallets are mostly nice interfaces to some Bitcoin application backend. Whoever runs this backend controls what you see in your wallet. Your provider tells you how much bitcoin you own. Your provider broadcasts all of your transactions and suggests what fees you have to pay. Your provider runs your access gateway to Bitcoin, assures you that this one big incoming transaction really happened and decides whether it is valid or not. Your provider enforces consensus rules for you and all other customers.

## A pretty good vantage point
Your access gateway to the Bitcoin network potentially knows everything. For example, it could easily correlate all your transactions, addresses and balances. As your network address is known, so is your approximate geographical location. Connecting many pseudonymous address clusters through their peer-to-peer transactions, connecting them to well known addresses of exchanges and merchants could give a very detailed account of the whole Bitcoin ecosystem.

As a wallet provider ourselves, we haven't chosen to run these backend systems, it's simply necessary to provide a good user experience. Most providers probably don't even want to take this role and the power this gives us. Of course, we and other providers promise not to misuse this power. We don't analyze transactions, nor keep logs on our Bitcoin servers. There's nothing to gain by betraying the trust of our customers.

But what about legal coercion through a court order? A rogue employee bribed by a malicious actor? Or a hacker gaining access to the backend applications, altering them just so slightly?

In the not so distant future, when big business and central banks realise that Bitcoin is challenging their financial monopolies, the fight will be on. Once we leave the honeymoon phase, Bitcoin cannot afford such centralized choke points.

It is dangerous for Bitcoin users to outsource their direct network participation to a centralized node. There are a few really big nodes in the network, processing a lot of economic activity. They are actively validating blocks, processing transactions and updating balances. They verify how many bitcoin belong to which address and can judge whether miners behave according to the desired consensus rules. Some lightweight Bitcoin wallets (like our own [BitBox App](https://shiftcrypto.ch/app/)) independently check at least proof-of-work requirements and verify if a transaction has been mined using Merkle branch proofs, but these checks cannot provide definitve proof.

The good news is that it's not that hard to run a Bitcoin full node yourself. After all, that's what the Bitcoin Core application is all about. Run it on your regular computer, an old laptop or as an always-on network appliance like a Raspberry Pi. Run a node and support the network! But unless you are using your node to verify your transactions, just running an idle full node is not really achieving anything.

## A harsh truth: only economic nodes matter
Propagating transactions and serving blocks to other peers is nice, but the network doesn't really need additional nodes to do that. In an ad-hoc network like Bitcoin, more nodes do not make it faster or more efficient. What the Bitcoin network really needs are more nodes that enforce the Nakamoto consensus: rules each node follows and applies to decide whether a block or a transaction is valid.

Enforcing consensus: but against whom? Well, anyone that likes to profit just that little bit more. So pretty much everyone. Miners might give themselves a bigger block reward, regular users spend the same bitcoin twice or a business tries to spend a multi-signature contract unilaterally. Why not cheat on the Lightning Network and create a transaction that ignores a timelock?

But ultimately, it comes down to the miners. While I can create and broadcast as many fake transactions as I'd like for free, a miner that includes it in a block will lose the whole block reward while bearing the full operational costs of producing that invalid block.

## Dystopia: let's think it through
Imagine a worst-case scenario, where there are only two big economic nodes, some miners and a hundred idle nodes. What happens if there is business- or miner-driven desire to change the consensus rules, for example to allow bigger blocks? Let's take a look:

1. Some big miners decide that it's time for bigger blocks, because more transactions mean more fees in total.
2. The two big economic nodes think that this is a good idea, as cheap transactions are good for business.
3. The idle nodes don't like that and threaten to not accept bigger blocks.
4. But the miners don't care. All they want is to sell their newly minted bitcoins, which will be accepted by the economic nodes. So they start producing bigger blocks.
5. The economic nodes accept these blocks, bringing them into the Bitcoin ecosystem and giving them value.
6. The hundred idle nodes reject these blocks and the Bitcoin network silently undergoes a hardfork. Unfortunately for the idle nodes, their side of the fork does not have any economic activity, so nobody even notices.
7. As the owners of the idle nodes also use the two economic nodes to send and receive Bitcoin, they are forced to accept the new consensus rules.

That was quick!

Of course it's not as clear cut. For example, customers of the big economic nodes would complain. But without running their own economic nodes, they don't really have a say. This extreme example demonstrates that idle nodes don't really count. Now the good news: in aggregate, many small nodes with just a little economic activity have a huge say when it comes to consensus rules. In the end, it's about threatening to reject transactions which you cannot do if your incoming transactions are processed by someone else.

## Relationship status: it's complicated
It's important that we learn to be direct participants in the Bitcoin network. There are different ways to do that, but unfortunately Bitcoin Core is not yet sufficiently in love with hardware wallets.

**Run** [**Bitcoin Core**](https://bitcoincore.org/) **as your wallet.**The Bitcoin reference client is the most popular implementation of the Bitcoin protocol: a full node that validates the whole blockchain on your regular computer and is best used with it's own included software wallet. It's not made with hardware wallets in mind, and while support for them is coming, it's not yet ready for non-techies.

**Run an Electrum server.**As Bitcoin Core is not made to serve other wallets, the traditional way is to run Bitcoin Core plus an Electrum server. This way, you can use the Electrum desktop application that works seamlessly with most hardware wallets. Our [BitBox App](https://shiftcrypto.ch/app/)lets you specify your own Electrum server, so you can easily use the [BitBox hardware wallet](https://shiftcrypto.ch/bitbox02/) in private.

There are several server implementations: [electrs](https://github.com/romanz/electrs/blob/master/README.md), [ElectrumX](https://electrumx.readthedocs.io/en/latest/) or [Electrum Personal Server](https://github.com/chris-belcher/electrum-personal-server/blob/master/README.md).

**Buy a Full Node appliance** (or build it yourself)
The most convenient way to run a full node is to buy a ready-made Bitcoin and Lightning Network appliance, or you can build your own (that's how we started). But hardware wallet integration is not quite as seamless as it could be which is why are working on our [BitBox Base](https://shiftcrypto.ch/base/) appliance. The BitBox Base integrates directly into the [BitBox App](https://shiftcrypto.ch/app/) so you are truly sovereign. You can use other wallets too as this is about providing the appropriate privacy for all of us.

![](/assets/images/cy19/cy19m8/stad-1.png){: .align-center}

If you want to learn and grow, then my [RaspiBolt](https://stadicus.github.io/RaspiBolt/) guide as well as the more feature-rich [RaspiBlitz](https://github.com/rootzoll/raspiblitz/blob/master/README.md) project are well worth your time investment.

## Mass adoption? Only with better solutions.
While the Lightning Network gave a boost to the number of Bitcoin full nodes, many are not used to verify economic transactions and secure the Bitcoin network. In my experience, many users are not aware that this is an absolute necessity. I believe that better solutions need to be built, especially for usage with hardware wallets. This is the main reason why I'm dedicating all of my time to the BitBox Base.
