---
title: "The History of Bitcoin (and the people that built it)"
permalink: "/the-history-of-bitcoin-and-the-people-that-built-it"

author: moritzkremb

tags:
  - Moritz Kremb
  - 2020 Q2
  - Money
  - Monetary Policy
  - Store of Value

excerpt: The History of Bitcoin (and the people that built it). Posted May 17, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The History of Bitcoin (and the people that built it)](https://medium.com/in-bitcoin-we-trust/the-history-of-bitcoin-and-the-people-that-built-it-73c23932ba47)
### By Moritz Kremb
### Posted May 17, 2020

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it1.jpg)

The History of Bitcoin

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it2.png)

*Where it all started: The original Bitcoin white paper*

On October 31st 2008, a document was posted into a popular cryptography mailing list. The title of this 9-page document was: **Bitcoin, a peer-to-peer electronic cash system.**

In it, the anonymous author going by the name of Satoshi Nakamoto describes a form of electronic cash, which the world had never seen before. To understand the significance of this document and why it kickstarted arguably the biggest revolution of our financial system, we have to go all the way back to the origins of money.

## History of money

So why was there a need for money in the first place? Well because exchanging goods directly for other goods is pretty inconvenient. You need to find someone that wants the exact good you’re selling, and can give you the exact good that you need. In other words, there needs to be a **double coincidence of wants**, where one person wants exactly what the other person wants, in order for the transaction to happen.

The solution to this problem is obvious to us now. You need to introduce a third good into this system that everyone wants. Ideally this third good should also be scarce, so that any one person can’t quickly produce huge amounts of it. Throughout history many different things have been used as this third good, such as grain, cattle, shells and precious metals. One of the most popular ones is gold, which established itself over time as a means of exchange and store of value.

However, starting around the 7th century, people began to realise that using precious metals as a means of exchange had a major disadvantage, especially when trade was taking place over great distances. Large amounts of gold aren’t that easy to move from one place to another. It also posed a high security risk, since the gold could be intercepted and stolen in transit.

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it3.jpg)

*Constantin Stoiloff — The Siberian Gold Convoy*

The genius solution to this problem was to have a person, or institution, basically protect your gold for you and give you a contract in exchange for it. This piece of paper would guarantee, that you can retrieve your gold when you want it back. Now all of a sudden, instead of trading gold, people were able to trade these pieces of paper (which of course were much easier to transport) all while the actual gold that it represented was sitting somewhere in a vault. Worldwide trade accelerated and we came to call these pieces of paper money.

The concept, where all the money that is being used on the market, is backed by actual gold in a vault, is also called the gold standard. These institutions (or banks) that would take your gold and exchange it to paper money and back, were initially run as private companies. Eventually, this function was taken over by governments creating central banks.

This system was very successful for a very long time. But the problem was, governments were able to abuse it, which came to a culmination in the 20th century. In order to finance wars, especially World War I&II, governments across the world started printing more and more paper money, bringing the whole system out of balance. Essentially they were creating money out of thin air, which basically means shifting value from the population to the government. The increased money supply meant that the paper money was not sufficiently backed by the gold in the reserves anymore causing people to lose trust in it. Eventually the gold standard had to be officially abandoned. This official scrapping of the gold standard happened only as recently as 50 years ago.

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it4.gif)

*The Nixon Shock, 1971: Removing the Gold Standard*

After that we created so-called fiat money, which is the money we are using today. Most of us grew up with this type of money and are thus taking it for granted, but it’s useful to remember that we are actually taking part in a very new experiment in history. This type of money has value merely because the government says it does. In other words, it’s value is by decree, and it’s solely “backed” by the respective government issuing the money and not by any other asset in a vault.

## Digital money

As the world became more digitalised, consumers wanted their payments to be digital too. Banks began creating technologies like credit cards, debit cards and online banking, which basically replaced paper money with digital information stored on computers. When I pay someone digitally today, my bank reduces my balance, which is stored on their servers, and increases the other person’s balance. No physical cash is moved, only numbers in a database are changed. Even if the other person’s account is at a different bank, physical cash is hardly ever moved.

While digital money is convenient, it created a whole new problem: privacy. With cash, your payments were private and there was no way for institutions to know what you were spending your money on, they were just pieces of paper. But the combination of digital transactions and banks as central institutions controlling the supply of money, meant a loss of privacy for the consumer. This is significant because transactions are the basis of all our economic activity, it governs almost every aspect of our daily lives. Giving institutions the transparency to see them in detail, shifts an unprecedented amount of power to a select number of people. History tells us that the balance of power is a fragile thing. Too much power in a few people’s hands, usually leads to bad outcomes.

A group of people, very concerned about privacy in the digital age, came together and started discussing solutions to this problem. They communicated through an online mailing list and became collectively known as the cypherpunks.

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it5.jpg)

*Founder of the cypherpunks: Tim May, Eric Hughes, John Gilmore (1992)*

The goal was to create some new form of digital money that is not only private, but also not controlled by banks. However, removing banks out of the picture makes this a very difficult task, not just from a political but mainly from a technological perspective. No one had yet found a way to do this.

For something to work as money, it needs to have scarcity. This is one of the functions that a bank fulfils. So digital money that is not controlled by a bank, would need to find another way to be scarce. But anything digital is really just a string of bits, a series of 1s and 0s stored on a computer. How can they be scarce when it is really easy to just copy them? It helps to stop and really think about how challenging this problem is.

Essentially, there were three big puzzle pieces that the cypherpunks needed to solve. First, a way had to be found to make truly **scarce** digital money. Same way you can’t just copy your $100 bill and spend it twice, double spending should not be possible in this digital currency. Second, **privacy** had to be built into this new form of money. And finally, the holy grail of it all, the solution should be designed in a way that is not controlled by an entity, but rather **decentralised** throughout the network of people using it, to prevent the same kind of power concentration we have today with banks and the state.

## David Chaum’s eCash

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it6.jpg)

*David Chaum*

The first attempt at solving one of these puzzle pieces came in the 1980s. David Chaum, a well-known computer scientist and cryptographer developed a technology called eCash. By using new developments in cryptography and inventing something known as blind signatures, Chaum was able to create a currency where transactions were completely private. It worked like this: Let’s say Alice wanted to pay Bob privately…

1. First a bank would issue the eCash currency to Alice. The ID of the issued currency would be cryptographically “scrambled”, meaning that there was no way to track it. This was made possible by blind signatures.
2. Alice could now pay Bob in that currency.
3. When Bob exchanges that currency at the bank, there would be no way to know that the payment actually came from Alice, since the ID had been scrambled.

eCash was considered a big achievement and it motivated many of the later cypherpunk members, since it showed that a **private** digital currency can exist. However, it still had many flaws. Scarcity and no double spending were only achieved because of the centralised nature of it’s architecture. Technically eCash was not a standalone currency, since you still needed banks to operate and control it. It was in no way decentralised. The technology eventually did not gain enough adoption and the company that Chaum founded went bankrupt.

## Hashcash by Adam Back

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it7.jpg)

*Adam Back*

The next milestone came with the invention of Hashcash by Adam Back in the late 90s. Although the name suggests some relation to “cash”, this was actually not it’s main purpose. It was initially a method developed to fight email spam. The idea was that computers had to contribute some amount of computing power to solve a mathematical puzzle. This was done with a mathematical function known as the hash function. Essentially, it takes an input and spits out a number that looks totally random, but really isn’t. Like this:

> Input: “Hello World”
>
> Output: A591A6D40BF420404A011733CFB7B190D62C65BF0BCDA32B57B277D9AD9F146E

And if you change the input only slightly, the output will change completely.

> Input: “Hello World 1”
>
> Output: 1AED4D8555515C961BFFEA900D5E7F1C1E4ABF0F6DA250D8BF15843106E0533B

So if you only see the output, there is no way to find out what the input was, other than trying all possible combinations of letters and numbers and throwing them into the function to see if the result matches your output. **The function is a one way street.**

Now for Hashcash, this concept was used and expanded. Let’s say, in order to send an email, your computer would have to find an input which creates an output that HAS to **start with 10 zeros**. For example:

> Input: Your email text + **some random number that you have to find**
>
> Output: **00000000000**74880DBF76B9B8CC00832C20A6EC113D682299550D7A6E0F345E25

The only way to do this, is if your computer tries a bunch of random numbers, drops it into the hash function, until at some point, by pure luck, the output happens to have 10 zeros at the beginning. Let’s say a typical computer would take about 3s to do this (since they can do millions of calculations per second). 3s would be an acceptable time if you wanted to send one email. But if a spammer wanted to send 1000 emails, they would take around 3000s, or 50min to do this. So you can see how this turned out to be an effective way to fight spam.

But more importantly, what Hashcash essentially managed, was, for the first time, to provide scarcity to digital information. Requiring computers to find a number by brute force, was proof that they had put in the work to do so. This meant that whatever the computer was now producing, was a scarce good. You can think of it like producing gold through mining. You need a bunch of equipment and manpower to mine the gold. This necessary work that you put in to produce gold, makes gold limited and thus scarce. In the same way, the Hashcash output was now scarce, because you had to put in a certain amount of work to produce it. The scarcity puzzle had been solved.

## Almost there

With 2 of the 3 problems solved, the finish line was clearly in sight. The bits and pieces of the puzzle were there, now the cypherpunks just had to find some architecture that would tie all of these concepts together. The final part was to find a way to solve the holy grail of decentralisation.

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it8.jpg)

*Wei Dai*

A first design was proposed by Wei Dai, a computer scientist who later worked at Microsoft. In a blog post he described a design called **B-money**. In it the money creation system would use something similar to the Hashcash proof of work system. Furthermore, he proposed a decentralised accounting system, where everyone participating in the network would keep a list of all the transactions. A shared ledger so to say that would make the system decentralised. Compare this to a conventional currency where the ledger is held only by the banks. This architecture came pretty close to how bitcoin was later designed, but it was still missing some crucial parts.

Most notably, Wei Dai didn’t quite figure out how users would agree on the same ledger. In his system, it would be quite easy to have discrepancies between the ledgers, which meant double spending would be possible. B-money was never implemented, but it did provide a first draft, if you will, for Bitcoin.

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it9.jpg)

*Nick Szabo*

The closest ever design to Bitcoin was proposed by Nick Szabo. In 2005 he published a description of a design called **Bit Gold** on his blog. Bit Gold had a lot of the components in place that Bitcoin would eventually have. For example, Szabo described a mechanism where the proof of work outputs, would be chained together, to create an unforgeable chain. This can be seen as a description of the blockchain that underlies Bitcoin today. However, just like B-money, Szabo never actually got as far as to implement Bit Gold. In 2008, in the same year that Bitcoin was created, he left a comment on his Bit Gold blog post, asking if “anybody wanted to help him code this up”?

![](/assets/images/2020/m5/the-history-of-bitcoin-and-the-people-that-built-it10.jpg)

*Hal Finney*

In that same year, Satoshi Nakamoto, whose identity is unknown to this day, released the Bitcoin white paper. A few months later he implemented a coded version with the help of another computer scientist called Hal Finney, who would continue to do much of the crucial initial work for Bitcoin.

Bitcoin went from relatively unknown to a mass media phenomenon in less than 10 years. Inspired by Bitcoin, thousands of developers are now working on various types of cryptocurrencies, millions of people are discussing their significance and governments are starting to take them seriously. The blockchain technology has the potential to flip our entire financial industry on its head, change how we interact with each other on the internet and give us entirely new ways of governing systems. So far Bitcoin has withstood the test of time. The question is, will we one day look back at it as one of the most important technological inventions of our time?

Watch the video:

Follow me on Twitter: [https://twitter.com/moritzkremb](https://twitter.com/moritzkremb)

### [Subscribe to In Bitcoin We Trust free newsletter](https://inbitcoinwetrust.substack.com/).

### Sources:

[https://bitcoinmagazine.com/articles/genesis-files-hashcash-or-how-adam-back-designed-bitcoins-motor-block](https://bitcoinmagazine.com/articles/genesis-files-hashcash-or-how-adam-back-designed-bitcoins-motor-block)

[https://youtu.be/bBC-nXj3Ng4](https://youtu.be/bBC-nXj3Ng4)

[http://www.hashcash.org/](http://www.hashcash.org/)

[https://en.wikipedia.org/wiki/History_of_bitcoin](https://en.wikipedia.org/wiki/History_of_bitcoin)

[https://en.wikipedia.org/wiki/DigiCash](https://en.wikipedia.org/wiki/DigiCash)

[https://bitcoin.org/bitcoin.pdf](https://bitcoin.org/bitcoin.pdf)

[https://en.wikipedia.org/wiki/Gold_standard#Bimetallic_standard](https://en.wikipedia.org/wiki/Gold_standard#Bimetallic_standard)

[https://satoshi.nakamotoinstitute.org/posts/](https://satoshi.nakamotoinstitute.org/posts/)

[https://bitcoinmagazine.com/articles/genesis-files-how-david-chaums-ecash-spawned-cypherpunk-dream/](https://bitcoinmagazine.com/articles/genesis-files-how-david-chaums-ecash-spawned-cypherpunk-dream/)

[https://bitcoinmagazine.com/articles/genesis-files-how-david-chaums-ecash-spawned-cypherpunk-dream/](https://bitcoinmagazine.com/articles/genesis-files-how-david-chaums-ecash-spawned-cypherpunk-dream/)

[https://passwordsgenerator.net/sha256-hash-generator/](https://passwordsgenerator.net/sha256-hash-generator/)

[http://unenumerated.blogspot.com/2005/12/bit-gold.html](http://unenumerated.blogspot.com/2005/12/bit-gold.html)

[https://www.wired.com/1993/02/crypto-rebels/](https://www.wired.com/1993/02/crypto-rebels/)

[https://www.chaum.com/ecash/](https://www.chaum.com/ecash/)

***

{% include signup.md %}
