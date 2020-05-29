---
title: "Few Words on Decentralization and Anonymous Payments"
permalink: "/few-words-on-decentralization-and-anonymous-payments"

author: nopara

tags:
  - Nopara
  - 2020 Q2
  - Privacy
  - Payments
  - Money
  - Wasabi
  - Join Market
  - JoinMarket
  - E-cash

excerpt: Nopara discusses the many ways we definie anonymous payments. Posted May 6, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Few Words on Decentralization and Anonymous Payments](https://medium.com/@nopara73/few-words-on-decentralization-and-anonymous-payments-160782d30b9e)
### By [nopara](https://twitter.com/nopara73)
### Posted May 6, 2020

Something is centralized and something else is decentralized. Such binary thinking is prevalent in the Bitcoin community. Here I’d like to present a scale that describes reality in a better way. Our contenders are: **Legacy Banking System**, **Chaumian E-Cash**, **Wasabi Wallet**, **JoinMarket,** **Bitcoin, **and** Bitcoin-as-envisaged.**

I recall [an article](https://gendal.me/2014/11/14/the-unbundling-of-trust-how-to-identify-good-cryptocurrency-opportunities/) that brainstormed on a decentralization scale in the context of payment systems. I am intending to do the same in the context of anonymous payment systems. The article can be summarized with the following depiction:

![](/assets/images/2020/m5/n1.png)

## Chaumian E-Cash

Chaumian E-Cash (shall I say as-envisaged?) is a centralized anonymous payment system. I argue calling it centralized does it a disservice, because it is more decentralized than our legacy banking system. While in the legacy banking system the information of who pays who is centralized, too, in ecash it is not the case. Only the receiver and the sender of the payment knows who pays who. While the data is (not always), the information isn’t stored in a central location, like in the traditional banking system. This is important, because an ecash bank cannot pinpoint a specific user to steal its money, which increases its censorship resistance. There just isn’t as many things to censor.

![](/assets/images/2020/m5/n2.png)

## Wasabi Wallet

Wasabi Wallet is a Bitcoin wallet that uses Chaumian CoinJoin to bring privacy for its users. The main difference between ecash and Wasabi is that the latter cannot steal funds of its users. The users have complete control over their money, thus it decentralizes security. Thus it’s more decentralized than an ecash bank.

![](/assets/images/2020/m5/n3.png)

## JoinMarket

JoinMarket just like Wasabi also utilizes a CoinJoin protocol. However Wasabi uses a server, called the Coordinator, which has more responsibilities than JoinMarket’s server, which simply acts as a bulletin board. For example Wasabi coordinator could potentially blacklist UTXOs from participating in the mix. In fact this is by design, it’s doing it all the time as this is how Denial of Service protection filters out the malicious actors. Thus the argument is made the JoinMarket is more decentralized than Wasabi Wallet.

![](/assets/images/2020/m5/n4.png)

## Bitcoin vs Bitcoin-as-envisaged

While compared to JoinMarket Bitcoin does not require a bulletin board to work, it isn’t as decentralized as we would like it to be, since the dream decentralization of Bitcoin would be if every single Bitcoin user would be also a Bitcoin miner. But even that’s not ultimate decentralization. **The ultimate decentralization would be if every single person on this planet would have equal chance of mining the next block in the Blockchain and no one would ever learn payment information unless they were authorized to do so by the transacting parties. **But even if we’d reach this novel goal, we’d surely encounter terrific scaling issues after space colonization.

## Nuances

I’m going to destroy everything I built up so far.

In this article I showed you why calling things centralized and decentralized is more often a rhetoric rather than an argument and presented you a more accurate model: a scale of decentralization. In this section I’m going to hopefully convince you that even this scale of decentralization is a wrong model that suffers from a number of nuances that I conveniently skipped through.

*   Could one make a case that data mining payment information from the Bitcoin blockchain is easier than figuring out anything about Chaumian e-cash payments, thus the latter has a more decentralized way of handling payment information? “Chaumian E-Cash Analysis Companies” will never emerge, but “Blockchain Analysis Companies” do have a role to play.
*   The peer discovery of Bitcoin is another rabbit hole I didn’t want to go into.
*   Where would you put on the scale, services like Blockchain.info’s SharedCoin and Samourai Wallet where a central entity learns everything? The payment information is centralized there, so they would have a place behind Wasabi, however in ecash the payment information isn’t centralized, so would you put them behind ecash, too? Or you’d prefer the security aspect of centralization, as in these schemes the security is decentralized compared to ecash.
*   Where would you put Traditional Bitcoin Mixers? They’d obviously be between ecash and legacy banking, because not only the payment information is centralized, but also the security aspect. But do they win the decentralization game against traditional banks?
*   How about Bitcoin exchanges or Bitcoin casinos? Is there any difference between them and Traditional Bitcoin Mixers? Is the fact that the latter does not intend to store bitcoins only tunnel them through their system makes it more decentralized?
*   There’s also a rabbit hole on the information asymmetry of JoinMarket. There the taker of the CoinJoin learns the mapping so in this regard is it less decentralized than Wasabi and ecash? Oh, wait this gets more complex, the takers of JoinMarket are decentralized in the first place, so does learning the mapping even matter?

## Conclusion

Decentralization a meme. In practice it’s a nuanced topic and not at all a zero sum game.

***

{% include signup.md %}