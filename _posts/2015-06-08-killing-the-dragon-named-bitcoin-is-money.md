---
title: "Killing the Dragon Named “Bitcoin is Money”"
permalink: "/killing-the-dragon-named-bitcoin-is-money"

author: beautyon

tags:
  - Beautyon
  - 2015 Q2
  - Mining
  - Money
  - Privacy

excerpt: Killing the Dragon Named “Bitcoin is Money”. Posted June 8, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Killing the Dragon Named “Bitcoin is Money”](https://hackernoon.com/killing-the-dragon-named-bitcoin-is-money-b6dce5b86535)
### By Beautyon
### Posted June 8, 2015



![](/assets/images/2015/m6/killing-the-dragon-named-bitcoin-is-money3.jpg)

A recent academic paper [*“A First Look at the Usability of Bitcoin Key Management*](http://www.internetsociety.org/sites/default/files/05_3_3.pdf?ref=hackernoon.com)*”* by Shayan Eskandari, David Barrera, Elizabeth Stobert, and Jeremy Clark of Concordia University, ETH Zurich and Carleton University, has yielded an unexpected gem to anyone interested in the correct technical definition of Bitcoin. In this paper, there is a very precise and vivid description of *exactly* what Bitcoin is:

> *A. Bitcoin is a cryptographic currency deployed in 2009 which has reached a level of adoption unrealized by decades of previously proposed digital currencies (from 1982 onward). Unlike many previous proposals, Bitcoin does not distribute digital monetary units to users. Instead, a public ledger maintains a list of every transaction made by all Bitcoin users since the creation of the currency. A transaction in its simplest form describes the movement of some balance of the Bitcoin currency (XBT or BTC) from one or more accounts (called input addresses) into one or more accounts (called output addresses). Bitcoin addresses are indexed by the fingerprint of a public key from a digital signature scheme. They are not centrally allocated or registered in any way — the addresses become active when the first transaction moving money into them is added to the ledger.*

> *In Bitcoin, every transaction must be digitally signed using the private signing key associated with each input address in the transaction. In order to spend Bitcoin, users require access to the signing key of the account holding their Bitcoin. Thus users do not maintain any kind of units of currency; they maintain a set of keys that provide them signing authority over certain accounts recorded in the ledger.*

> *The ledger (known as the blockchain) is maintained and updated by a decentralized network using a novel method to reach consensus that involves incentivizing nodes in the network with the ability to generate (known as mining) new Bitcoin and collect transaction fees. The details of the Bitcoin consensus model are not relevant to this paper, but we note that clients in the network participate in the consensus model by downloading and cryptographically verifying the integrity of the blockchain. As of writing, the Bitcoin blockchain is roughly 25 GB in size.*

> *One subtlety of Bitcoin’s transaction architecture is that in order to spend Bitcoins, the entire value of unspent outputs (i.e., from previous transactions) must be spent. To accommodate this, Bitcoin clients automatically spend the full amount of unspent outputs and create multiple components in the transaction: one component will send part of the unspent coins to the intended recipient, and the other component will send the remaining inputs back to the sender as change. It is technically possible (and some clients behave this way) to send change back to the sending address. However, to enhance anonymity, the reference client generates fresh addresses (and corresponding private keys) to receive the remaining transaction amount.*

> *As more transactions are made, Bitcoin clients must keep track of multiple private keys for use in future transactions. Many clients prominently display a Bitcoin balance on the main screen, which represents the sum of all unspent outputs for which private keys are available.*

This is **a very significant paper,** because it has a rarley seen, clear, terse and precise description of what Bitcoin is, and it puts to death several widely held misconceptions about Bitcoin which have caused it to be mischaracterized as money, resulting in the disastrous “BitLicense” (for the unlucky residents of New York) misapplication of Anti Money Laundering and “Know Your Customer” (AML and KYC) regulations, Bitcoin being banned entirely in poverty stricken and backwards countries like [Thailand, Viet Nam, Iceland and Bangladesh](http://en.wikipedia.org/wiki/Legality_of_bitcoin_by_country?ref=hackernoon.com).

Now for some observations.

First, the fact that Eskandari, Barrera, Stobert, and Clark use the word *“currency”* in their paper does not mean that Bitcoin is money. It is well understood even by laymen that the simple use of a good in exchange does not make that good *money*. The misuse of English is one of the big problems facing anyone trying to explain what Bitcoin is, and the paper approaches this problem and identifies it as one of the main usability hurdles faced by anyone trying to make Bitcoin more user friendly.

When we present Bitcoin to the layman, we can use whatever nomenclature and design that we like to contextualize our service. Bitcoin is software that presents a software interface that we can “paint” over to achieve our service goals and expose our features.

This is what companies like *Abra* are doing by abstracting away Bitcoin from their users so they only see a dollar balance and three buttons. Their users will not even know they are using Bitcoin.

The Bitcoin wallet *Blockchain* does something similar by showing users a balance and removing all the complexity of transaction signing, generation and network broadcast via four buttons and a familiar timeline.

![](/assets/images/2015/m6/killing-the-dragon-named-bitcoin-is-money4.jpg)

The Blockchain Wallet interface. It abstracts away the complexity of creating Bitcoin transactions, and shows the user a plain number that represents the amount of Bitcoin his private key can assign to another address. There are other pieces of information made user accessible, like previous signature events and a user address book, all of which have nothing to do with the nature of Bitcoin. These elements could be represented in any form for any purpose.

The authors assert correctly that Bitcoin **does not distribute digital monetary units to users**, and that instead, a *public ledger maintains a list of every transaction*. This line alone kills the idea that Bitcoin is money. The fact that in a Bitcoin wallet the user sees an integer representing her balance *has no bearing on the nature of Bitcoin*. That display is only *for the convenience of the user*; it is [a metaphor](http://en.wikipedia.org/wiki/Metaphor?ref=hackernoon.com), a convention, a symbol, shorthand, a sign *only,* a familiar point of reference that hides the incredible complexity of everything happening “under the hood” of Bitcoin transactions and “balances”.

The authors assert correctly that Bitcoin users do not maintain any kind of currency (despite in their own words, Bitcoin being a currency!) and that users only maintain control over *a set of keys* that provide them *authority over entries* in the public ledger. In this perfect explanation, we see that not only do Bitcoin users **never receive or send Bitcoin**, but that all they control is **a set of keys**, that are not even physical keys, but are themselves **pieces of text**. The fact that users never receive or send Bitcoin, negates the idea that Bitcoin is “sent” or “received” or that any *actual* *transaction* or *exchange* has actually taken place. A Bitcoin transaction is automated digital signing of a piece of text that is *a contract without terms*; all it is is the handing over of control of a piece of meaningless text from one set of cryptographic keys to another, without any context or meaning.

The security of these pieces of text that is the subject of this paper, but that subject is for another post; it should be clear to anyone that can think that **Bitcoin is not money**. **It never was, and never will be money**. It is something *very different*, and as I have said before, the uses to which this software can be put (including acting as a sound money substitute) are being discovered, and it is incredibly useful; more useful than any mere money.

Even if you believe this characterization is wrong, and want to maintain that because the illusion of “balances” are moved from one address to another on the Blockchain that that makes Bitcoin money, what you *cannot* say is that any user of Bitcoin ever *takes possession of Bitcoin*, no matter who he is. Bitcoin, if you insist on calling it money, is money that is *never collected or redeemed*. It remains forever on the Blockchain, which is the only place where the text entries that make up Bitcoin have any useful context.

As more and more academics begin to grasp what Bitcoin is (and these will most likely be specialists in math and software, not economists) the idea of Bitcoin being money will continue to die, and this is an entirely good thing. We can fully expect economists, especially the dreaded Keynesians to completely misunderstand Bitcoin and even lie about it, but this is stating the obvious; what is important is the effect of rigorous papers like the one cited here will have in bringing forward the date where the ultimate confrontation between the State and math takes place.

[**Bitcoin is math, not money**](https://medium.com/bitcoin-think/the-bitlicense-is-a-bad-idea-that-must-die-cb413c076d85?ref=hackernoon.com). The State cannot claim that it has the right to govern the performance or execution of mathematics. When this goes to court, every academic, writer, user and developer of software will come under direct threat from the consequences of Bitcoin regulation, for the following reasons.

If the State succeeds in enshrining its Bitcoin regulation in law, they will inevitably try and regulate other areas of software development. If the State is forced to back down, then the Bitcoin developers will have an iron clad case to demand that restrictions be removed from them, since the practices they use to develop software are no different to the practices used by developers of any other type of software.

All software development is threatened by BitLicense and the deeply ignorant and perverted thinking behind it. Anyone who codes anything, from [a command line customization tool](http://ohmyz.sh/?ref=hackernoon.com) to an [Open Source word processor](https://www.libreoffice.org/?ref=hackernoon.com) will face the possibility of compulsory licensure and prior restraint of code releases. The [evil](http://www.capx.co/5-jobs-that-inexplicably-require-a-licence-in-the-us/?ref=hackernoon.com) State [licenses people to perform haircuts](https://www.nh.gov/cosmet/?ref=hackernoon.com) and [puts them in gaol if they refuse to comply](http://www.freerepublic.com/focus/news/1399802/posts?ref=hackernoon.com); do you really think its impossible that software developers will never face licensing? For an industry that powers and controls **literally everything on Earth?**

The State, if it were run by rational men with a long term view who were not computer illiterate, would see these challenges coming and remove themselves from the firing line entirely. By their logic, whatever the means of making a profit is, it is exposed to taxation by them; the law saying activities should be taxed has nothing to do with defining reality. By trying to redefine reality, the competence of the State is called into question, and since software mediates much of man’s activities today, this is very dangerous ground for them to be goosestepping across.

Bitcoin is nothing more than a distributed public ledger controlled by keys that are in turn controlled by the users. Bearing this in mind, how can anyone claim that KYC/AML applies to Bitcoin? If they can claim that the law has something to say about Bitcoin private keys, then surely the law should have something to say about SSL private keys that are used to secure all e-commerce globally? If not, *why not?* It is exactly the same software technology that powers SSL behind Bitcoin; the only difference is in the novel arrangement of Bitcoin. Billions of dollars are secured by SSL; how is it that e-commerce, which is clearly a matter of national security, remains completely unregulated, but Bitcoin, whose market cap is miniscule, comes under suffocating regulation of the BitLicense? It does not make any sense at all.

Next the hysterical Bitcoin regulation fanatics will claim that this novel arrangement of cryptographic software *alone* is to be regulated, but if that is the case, then *all novel arrangements* (inventions) in software are potentially subject to regulation, simply because some ignoramus claims that it should be so.

##### When to use s, ss or ß? The German government decrees how these letters are to be used in the German language. By law. In that country, you can expect laws that are totalitarian, but in a free country like the United States of America, the idea of the State legislating how English is defined is absolutely absurd. The same is true for math. How math is conducted or communicated and the means by which this is done is an entirely private matter, not a matter for the State or regulation. This is the default that you expect in a free country. In Germany, not so much.

If you think this is an exaggeration, you are mistaken. The New York *“BitLicense”* has a provision written in it that says not only that the state should control the software behind Bitcoin businesses, but the State must have *prior approval on any new software innovation in Bitcoin* before it is made available to the public. That means any new wallet or service must have prior approval *before it is released*. The authors and administrators of the BitLicense clearly do not have the intelligence or competence to assess cryptographic software, and they know nothing about the future of software and how the market will interact with it. That they claim to have the power to veto software is a clear violation of the First Amendment of the Constitution, on top of being *insane*.

Leaving aside that software is speech and that this regulation clearly violates the First Amendment, since all citizens have the right to transmit speech, this law makes improvements to how Bitcoin software is written impossible and puts the public at risk. It also puts all entrepreneurs in New York at a disadvantage on the global software stage. BitLicense is a problem easily solved for any entrepreneur with a passport or a PATH ticket, but the residents of New York who cannot move are stuck living under the Software [Fascism](http://legacy.fordham.edu/halsall/mod/mussolini-fascism.asp?ref=hackernoon.com) of Laski, “Donaudamptcryptishfahrtselektrizitätenhauptbetriebswerkbauunterbeamtengesellschaft” of New York.

Bitcoin is no different to email, SSL, Apache, Ngnix or any other software that is used in business world-wide. None of those pieces of software are regulated, and neither should they or Bitcoin be; Bitcoin is nothing more than another tool in the software developers toolkit, to be employed and stretched to the limit of man’s imagination. Treating it differently to any other software is absurd, insulting and unacceptable, and it will be robustly challenged both inside and and outside of court and everywhere the internet touches, as people use it without permission, peer to peer.

Bitcoin regulation is unacceptable to any rational man. The idea that Bitcoin is money should be completely abandoned because it is *incorrect*, and in addition to that, it is confusing to the Statists, and extremely corrosive to the fabric of modern society, the basis of which is software.

Computer illiterates, fascists, and [crony capitalists](http://www.courierpress.com/news/no-headline-ev_cosmetics?ref=hackernoon.com) must not be permitted to set global standards and define reality; they must be made to take their proper place as rank and file consumers and be **quiet**, as the men who make the world get on with their difficult work.

If you like the content and feel so obliged to send some love via BTC donations you can do so at the address below:↴

![](/assets/images/2015/m6/killing-the-dragon-named-bitcoin-is-money5.png)

***

{% include signup.md %}
