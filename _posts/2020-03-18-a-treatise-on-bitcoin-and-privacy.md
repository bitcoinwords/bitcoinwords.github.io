---
title: "A Treatise On Bitcoin And Privacy"
permalink: "/a-treatise-on-bitcoin-and-privacy"

author: giacomozucco

tags:
  - Giacomo Zucco
  - CY20 Q1
  - Privacy
  - Security
  - Monetary Properties
  - Deniability
  - Fungibility
  - Trust
  - Mixing
  - Lightning
  - DEX
  - FUD

excerpt: Giacomo Zucco shares a very thoughtful 2 part series on Bitcoin privacy. Posted March 18, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [A Treatise On Bitcoin And Privacy Part 1: A Match Made in the Whitepaper](https://bitcoinmagazine.com/articles/a-treatise-on-bitcoin-and-privacy-part-1-a-match-made-in-the-whitepaper)
### By [Giacomo Zucco](https://twitter.com/giacomozucco)
### Posted March 18, 2020

## Introduction
How one’s focus can shift in just two weeks! While today everybody in the Bitcoin space seems more concerned with price fluctuations in response to the global financial panic (understandably so), it’s important to remember perennial issues that never go away, like the importance of maintaining your privacy when you transact in bitcoin. Throughout this month especially, we’ve been hearing reports of KYC/AML-compliant exchanges freezing user accounts due to suspected use of CoinJoin software (more on that later), followed by yet another case of a famous and respected early Bitcoin proponent [promoting his new illiquid altcoin](https://jimmysong.substack.com/p/trace-mayer-and-the-perils-of-being) as something that “will replace Bitcoin, which isn’t private enough!” 

If you want to take a short break from global pandemics, financial meltdowns and price volatility, here’s an attempt at analyzing claims, facts and context of this latest “Bitcoin drama.” To begin with, in Part 1 of this two-part series, we’ll start by looking at the fundamental relationship between Bitcoin and privacy by going back to the beginning with the whitepaper. Then, in Part 2, we’ll focus on some the ways that Bitcoin privacy is being maintained and improved upon — and strike down a few “red herrings.”

## Money Needs Privacy
Bitcoin is designed to perform monetary functions, and money needs a strong separation of personal identity from specific monetary units and transactions in order to work sustainably at scale. There are at least two fundamental components to this separation.

### Deniability
We could call the first component “deniability.” This describes the possibility for an individual using a monetary tool to credibly deny any connection with it later on. 

The reason for this is that money has been developed to facilitate individual saving and voluntary exchange among people. But the positive-sum game of voluntary exchange is not the only way to increase one’s wealth: The other way is the negative-sum game of violent confiscation. As the sociologist and political economist Franz Oppenheimer [brilliantly put it](https://oll.libertyfund.org/titles/oppenheimer-the-state), there are two different paradigms for wealth acquisition within societies: 

> “These are work and robbery: one’s own labor and the forcible appropriation of the labor of others. I propose in the following discussion to call one’s own labor and the equivalent exchange of one’s own labor for the labor of others, the economic means for the satisfaction of needs, while the unrequited appropriation of the labor of others will be called the political means.” 

While the temptation to resort to political means is always present in extended social contexts, it becomes particularly strong when money is involved: The same features that make money an especially good tool for exchange and for storing economically acquired wealth make it also particularly interesting as a target of confiscation — and as a way to store politically acquired wealth. 

Individuals exchanging and storing money are more easily and more often targeted by political rent-seekers, since it’s most efficient to rob them than to rob participants in simple barter or insulated hermits who don’t exchange at all. Quite often political organizations prefer to present confiscation as conditional upon the specific type of exchange engaged in by the victim: taxes, imposts, tolls, tariffs, tributes, fines, bribes, penalties, excise duties, protection money, etc. 

Privacy in communication is important, and economic exchanges are among the most important, sensitive, private and potentially dangerous forms of communication in adversarial environments. Money talks. Somebody whose financial and commercial life is completely exposed runs a higher risk of suffering robbery, blackmail, kidnapping or political expropriation. 

For all these reasons, it becomes paramount for economic agents to be able to detach their own public identity from the specific monetary transactions they have taken part in and, thus, to be able to deny such connection.

### Fungibility
The second component is called “fungibility.” By this, we mean the possibility for an individual receiving a monetary tool to safely ignore any connection between that tool and any particular individual or use case it interacted with in the past. 

Fungibility is more an economical category than a political one: It basically means that any random amount of money is practically indistinguishable from any other, thus making the validation cost for a money receiver way lower. One $50 bill is as good as any other, and you don’t need to know who has used it in the past in order to accept or use it as payment today. Indeed, if a receiver had to evaluate the history of every individual unit before being able to assess its value, verification costs would increase exponentially. 

Ironically, one of the relatively recent trends of “Know Your Customer” regulations around the world is, indeed, that money was mostly adopted as a way for merchants to avoid knowing (and trusting) their customers! Customers are already somehow required to “know their merchant,” since they have to trust them about the quality and the dependable delivery of the product or service they purchase. But merchants, when they scale up from trivial systems of barter or credit to actual markets, use money to be free from the burden of knowing all their customers. “KYC” regulation is just a political control tool marketed with a paradoxical expression which exudes economic illiteracy. 

This isn’t an ideological problem but a functional one: A good cannot easily pass over many hands (as a monetary good is required to do) if every current receiver has to verify the entire political status of every previous owner in order to know how much political risk (including persecution, censorship, taxation, debt) he is actually inheriting. Non-fungible goods can’t work as money. 

Some goods are ideal for mitigating both deniability and fungibility problems: “bearer instruments” which don’t carry the personal information of previous owners, making it easy for everyone to deny having been involved in any specific transaction.

## Bitcoin: Born for Privacy
Satoshi Nakamoto created Bitcoin as a tool for privacy. The entire cypherpunk quest, which Satoshi was an active part of and which the Bitcoin experiment is the coronation of, was all about personal and financial privacy. Most of the early messages and publications by Satoshi (including the famous [whitepaper](https://bitcoin.org/bitcoin.pdf), which devotes a paragraph to it) are heavily concerned with its privacy features. 

The first consideration made in the whitepaper about privacy is that centralized online payment intermediaries are easy targets for regulation. As such, it is easy to push these intermediaries to actively mediate disputes and thus to make most transactions reversible. This requirement, as a consequence, forces merchants, scared by risks of chargebacks, to be very “wary of their customers, hassling them for more information than they would otherwise need.” Merchants get pushed back to the “KYC paradox” once again. Being decentralized and impossible to regulate, Bitcoin cannot be forced to actively mediate disputes. For this reason, Bitcoin transactions can quickly become irreversible, making any inquiry into the personal identity of a payer absolutely redundant and unnecessary. 

The second consideration concerns the fact that Bitcoin’s base layer (the “timechain,” developed to avoid double-spending without the need of a trusted third party) requires the publication of every settlement transaction, thus limiting the chance to apply the traditional “privacy through obscurity” technique of centralized providers. This limitation is mitigated by the anonymity of the cryptographic public keys, which are intended to be used only once, without any association with identities to work. In Satoshi’s words, “The traditional banking model achieves a level of privacy by limiting access to information to the parties involved and the trusted third party. The necessity to announce all transactions publicly precludes this method, but privacy can still be maintained by breaking the flow of information in another place: by keeping public keys anonymous. The public can see that someone is sending an amount to someone else, but without information linking the transaction to anyone. This is similar to the level of information released by stock exchanges, where the time and size of individual trades, the ‘tape,’ is made public, but without telling who the parties were.”

## Privacy and Trust: All or Nothing
An interesting feature of this transparent setting, discussed by Satoshi and by many other early Bitcoin contributors and researchers, is the all-or-nothing nature of its privacy guarantees. A trusted third party can, indeed, promise to keep your sensitive information safe from potential kidnappers, robbers or stalkers, while still being forced to provide any detail to more powerful political entities (nation-states with their tax agencies, financial authorities, secret services, etc.). 

In a (pseudo)anonymous but public setting, it’s safe to assume that in every case where the latter type of adversary is able to access sensitive financial information, the former type will find a way as well. When somebody’s privacy on the timechain is broken, it is broken to the benefit of all snoopers with an internet connection: governments, bandits, hackers, business competitors, personal enemies, haters, ex-spouses, etc. This should serve as a strong incentive for users to protect their “on-chain” deniability, thus protecting fungibility for all. 

Bitcoin base-layer transactions, on the other hand, already show perfect fungibility internally. What this means is that, although every transaction is public, there is no public data about who, within a certain transaction, was in control of the private keys that spent a specific input, or who is now in control of the private keys that will spend a specific output. 

Bitcoin’s rules assure us that the total amount of satoshis spent with all the inputs is equal to or less than the total amount of satoshis “locked” in all the outputs (transaction can’t create inflation, they can only leave out “blockspace fees” for miners). But there’s technically no way to be sure, from public timechain data alone, if a transaction with 10 inputs and 10 outputs is moving satoshis from one payer to ten payees, or from two payers to one payee, or from one entity to himself. Of course, some probabilistic inferences are possible, based on heuristics and common patterns, but nothing can be proven with public timechain data at the individual transaction level. 

While having one or more entities controlling the outputs is trivial, having more entities controlling the inputs is a little bit trickier, requiring some real-time coordination among all the payees before the transaction gets broadcasted. Luckily, though, the atomicity of Bitcoin transactions is such that this process doesn’t require any trust among different, unknown payees.

## The Fungibility Factor
This fungibility feature of Bitcoin transactions has been part of Bitcoin’s design since the very beginning, but its privacy implications were explicitly pointed out by different contributors only later on. Finally, in 2013, the label CoinJoin was created by Gregory Maxwell, to refer to the best practices a bitcoin wallet should implement in order to fully leverage such preexistent internal fungibility. Many variants of the technique have been proposed over time (PayJoin, JoinMarket, CoinSwap, P2EP and Zerolink implemented in wallets Wasabi and Samourai), all with the same goal: taking advantage of the fundamental fungibility of the protocol.

Another dynamic with the potential of boosting Bitcoin’s privacy is its layerization. Upper layers of the protocol stack, like the Lightning Network, don’t need to use the timechain to confirm every single transaction; rather transactions are only used as “anchors” to open and close “contracts” enabling payments elsewhere. Satoshi already imagined such kinds of “payment channels” early on: 

“The parties hold this tx in reserve and if need be, pass it around until it has enough signatures. […] They can keep updating a tx by unanimous agreement. The party giving money would be the first to sign the next version. If one party stops agreeing to changes, then the last state will be recorded at nLockTime. If desired, a default transaction can be prepared after each version so n-1 parties can push an unresponsive party out. Intermediate transactions do not need to be broadcast. Only the final outcome gets recorded by the network. Just before nLockTime, the parties and a few witness nodes broadcast the highest sequence tx they saw.” 

This did not turn out to be the exact way payment channels have been introduced (it was flawed), but they are now a common tool for many Bitcoin users. They can be used directly or collectively via routing. While often presented as a “scalability” solution, the Lightning Network and, in general, Layer 2 techniques have the big privacy advantage of massively reducing the amount of public information available on the timechain.

## Starting Off on the Wrong Foot
Of course, it was not trivial to implement privacy best practices in everyday bitcoin wallets and tools. First of all, while reducing the amount of information leaked on-chain, Layer 2 techniques and CoinJoin often increase the amount of network-level information to manage and protect (mostly because of the need for real-time interactivity, up-to-date lists of reachable peers, publicly available liquidity, etc.). The Lightning Network, in particular, was not really easy to bootstrap until [a protocol upgrade was adopted by users in late 2017](https://bitcoinmagazine.com/articles/long-road-segwit-how-bitcoins-biggest-protocol-upgrade-became-reality). 

While CoinJoin, unlike the Lightning Network, was possible to implement in theory since day zero (although with many practical challenges regarding coordination, liquidity and amount obfuscation), most actual bitcoin wallets didn’t bother to find a way to do it. By not doing so, they consolidated a dangerous trend: The large majority of on-chain transactions were considered as created, signed and broadcast by one single entity, in complete control of the private keys associated with all the inputs. Bitcoin transactions started to be seen as always one-to-one or one-to-many. Thus, one of the most effective fungibility features of the protocol hasn’t actually been turned into a wallet best practice until very recently, even though it has always been available. 

But there’s more, unfortunately. Other, simpler best practices, included in Bitcoin’s design as trivial defaults, have been mostly ignored by tool builders who have been less concerned with privacy and more focused on user experience during the early years. One obvious example is address reuse. Satoshi’s words about the anonymity of public keys were written under the assumption that users would generate a one-off address every time they received bitcoin, which would then be discarded after it’s spent again and never reused. (Maybe the word “address,” itself, wasn’t a good choice after all, being often linked to permanent references: email, IBAN, ecc.; while the word “invoice,” now used for Lightning Network transactions, would have been a cleaner choice.) 

Implementing this design was not entirely trivial either (especially before the introduction of HD wallets which made it easier to re-derive thousands of keys with just one “master” backup). So we ended up with massive reuse of static addresses, decreasing the entropy and facilitating analysis and deanonymization. Users started to link the same address to their profiles on forums, social networks and blogs. For many early users, making a payment meant giving the payee a complete overview of all their past and future financial life in Bitcoin. 

Another major incident was the proliferation of “light clients”: applications unable to download, validate and store the timechain directly, but able to store private keys and query other nodes (in the best cases, a trusted third party, like a wallet provider; in the worst cases, random nodes, in so-called “SPV wallets”) for the validity of the transactions involving the corresponding public keys. Besides creating a systemic risk in terms of security, these clients become a common hazard in terms of privacy. 

Some other minor implementation best practices have been initially overlooked by tool providers in this regard (including privacy-oriented coin selection, merge-avoidance, change management, etc.), but, for the most part, these three practices represent the basis for the heuristics employed by “chain-analysis” companies hired by eavesdroppers to spy on Bitcoin users. 

As of today, most of these problems have brilliant technical solutions and modern tools that implement them. But it’s difficult to push the best practices (which sometimes present small but existent coordination costs) in an ecosystem already “drugged” with easy, if dangerous, shortcuts. And privacy, as they say, loves company: Even if you have the best tools and follow the best practices, it doesn’t really help if you are the only one doing so (in fact, it may even hurt by making your efforts stand out in comparison, putting you under the spotlight). 

In Part 2, we’ll look at some of the techniques that are threatening our privacy as bitcoin users, common misconceptions about privacy, and finally, how innovations in Bitcoin are going to make privacy more secure and easier to maintain.

# [A Treatise On Bitcoin And Privacy Part 2: Don’t Be Misled By Red Herrings](https://bitcoinmagazine.com/articles/a-treatise-on-bitcoin-and-privacy-part-2-dont-be-misled-by-red-herrings)
### By [Giacomo Zucco](https://twitter.com/giacomozucco)
### Posted March 18, 2020

In [Part One](https://bitcoinmagazine.com/articles/a-treatise-on-bitcoin-and-privacy-part-1-a-match-made-in-the-whitepaper) of this treatise, we examined the fundamental relationship between Bitcoin and privacy by going back to the beginning with the whitepaper. In spite of some excellent privacy preserving options  that have been available to users since those early days, we seem to have taken a few wrong turns. But to fix it, in order to make Bitcoin’s privacy “great again,” we must be able to distinguish between real privacy and red herrings that can only lead us further off the path.

## Fiat Gateways Lead to Privacy Graveyards
Bitcoin is an effective system to transfer and store wealth, but that wealth has first to “enter” the system somehow, very often coming from fiat money. (Of course, you can also earn satoshis directly in exchange for goods and services you provide, instead of buying them with fiat.) 

Fiat-enabled bitcoin on-ramps (often known as “cryptocurrency exchanges”), acting as liquidity bridges, created huge privacy problems in Bitcoin. In order to manage fiat, exchanges will have to use traditional bank accounts. In order to get those, they have to meekly accept all the rules, conditions and limitations banks require. Traditional fiat banks, in turn, will pass over the extremely complex and heavy “compliance” burden they received from governments and regulatory agencies, including that concentration of economic illiteracy called “KYC/AML regulation.” 

So, fiat-to-bitcoin bridges will almost always end up demanding a scary amount of personal information from their user, linking that information to a few deposit and withdrawal addresses (often incentivizing continuous reuse) and then even hiring “chain-analysis” companies in order to follow, trace, tail and stalk all the previous and following economic activity on-chain.

### Why Chain Analysis?
The first and most important reason for doing so is because these on-ramps are scared to lose the privilege of having a fiat bank account. Bitcoin was, is and will always be considered a “borderline” reality by governments and government-sanctioned legal cartels like modern fiat banks. Thus, it’s realistic to assume they would close down operative accounts to any exchange which couldn’t guarantee the same level of financial surveillance that fiat banks routinely enact. 

For this reason, fiat-enabled gateways not only keep promoting wrong and dangerous uses of the Bitcoin protocol, discouraging security best practices and hiring “chain-analysis” spy companies: They often even go to great lengths to publicly praise “KYC/AML” nonsense regulations and to push the narrative that “Bitcoin is completely traceable,” marketing some probabilistic assumptions as “legal proofs” and ignoring even the existence of the fundamental privacy features of the protocol. 

For a while now, these businesses have been freezing or confiscating users’ accounts because of what theoretical “chain-analysis” heuristics (dishonestly promoted as “facts”) suggest these users may have been doing way before or way after their interaction with the exchange, basically trying to break fungibility in Bitcoin. 

We often see this happening for activities that aren’t even explicitly considered illegal in the specific jurisdiction under which they happened: online gaming, adult services, political campaigns, etc. Anything considered even remotely controversial has been depicted as forbidden, and any statistical guess about “on-chain” activity, based on common patterns and typical tools, has been depicted as “proven.” 

Of course, there’s nothing really proven in “chain-analysis” heuristics, so the spy companies arbitrarily decide how many “on-chain hops” to look for, arbitrarily assuming who is doing what. Even assuming that such heuristics are correct (they have never been 100 percent reliable, and they are less and less so each day, while Bitcoin developers build better tools and Bitcoin users start employing best practices), this behavior is unacceptable. It is the digital equivalent of your physical bank sending private investigators to follow your every move for days after you withdraw cash at the ATM, and then freezing or confiscating your bank account entirely if that PI comes back with a report that says that “you may have,” with some probability, engaged in controversial actions with that cash. 

More recently, this shady behavior has extended beyond some generically controversial activities engaged by “somebody somehow connected with customers” to encompass even the very act of trying to use Bitcoin’s security and privacy best practices!

### Closing the Blinds
In January 2020, a company that operates a regulated exchange froze a customer’s account once they discovered possible hints that somebody, possibly the customer himself (but after some “hops” following the withdrawal transaction, that is, not even directly), was using a wallet enabling privacy best practices. Again, imagine your physical bank sending a private investigator to follow your steps for days after you withdraw some cash at the ATM, and then freezing or confiscating your bank account if that PI reports that says that “you may have,” with some probability, closed your shutters at home, or pulled your shower curtains while naked, or put a lock on your personal journal, or used HTTPS within your web browser! 

Furthermore, the specific message to the customer was tragically hilarious: It said that the business “can’t condone activities such as peer-to-peer (sic!) mixing or gambling.” All this while talking about Bitcoin, which is literally a peer-to-peer protocol whose transactions can natively work as mixers, and coming from a business that operates in cryptocurrency trading, which some consider not that different from gambling!

## Don’t Fall for Red Herrings
There have been many reactions from Bitcoin users and analysts to these dodgy examples of behavior, many of which are based on logical fallacies or straight-on distortion of the facts. A classical example is the absurd notion that “Bitcoin users should not use privacy best practices, because that’s dangerous.”

### Red Herring #1: “Being Private Will Get You Into Trouble”
The pseudo-argument goes something like this: Since some overzealous business may use unreliable heuristics to accuse you of adopting privacy and security best practices that they have arbitrarily defined as “unacceptable,” possibly freezing or even confiscating your account, or flagging it as “suspicious,” you should just stop using those security best practices and move to insecure alternatives instead. In other words, to use our physical bank example, since your bank might flag your account if the PI they sent after you comes back with a report that says that you may have, with some probability, used some privacy best practices a few days after a cash withdrawal, you should just stop closing your shutters while home, or pulling the shower curtains while naked, or putting a lock on your personal journal, or using HTTPS within your web browser. 

This is nonsense, of course. If anything, it’s **not** using privacy and security best practices that would turn out to be extremely dangerous — not just for your financial safety but also for your physical safety. Reminder: Bitcoin’s privacy is all-or-nothing! Once a business is able to attach your physical identities, not just to an on-chain address but also to all the future and past history connected with it, all it takes is a little leak (by the business itself, by its spy-contractors or by one of the countless government agencies which will receive and pass along that information) to direct very dangerous enemies to your doorstep. 

Incidentally, the pseudo-argument is flawed more fundamentally as well: Even if you were so reckless as to decide to trust this third party with a complete account of your future and past transactions, in spite of the risk to your physical security (and that of your loved ones), you may achieve the very same result just by sending it the cryptographic proofs of all the inputs you ever signed (either on-chain or on upper layers), allowing the meddling gateway to read through each of your CoinJoin or Lightning Network routing — all without giving up generic privacy best practices. You are still risking a leak, but at least you are not giving every random guy with an internet connection an easy way to deanonymize and stalk you (and others you interact with).

### Red Herring #2: “If You’re Just Using Bitcoin to Invest, You Don’t Need to Worry About Privacy”
Usually this red herring comes with some distorted vision of Bitcoin’s utility. “If users just want to invest in bitcoin as an uncorrelated financial asset with some disinflationary features,” they say, “then they don’t need privacy at all.” This pseudo-argument is severely flawed. 

Here’s the bad news: Gold was, for many many centuries up until 1933, a typically “uncorrelated financial asset with some disinflationary features” that people in the United States and elsewhere could invest in. But then came [Executive Order 6102](https://www.presidency.ucsb.edu/documents/executive-order-6102-requiring-gold-coin-gold-bullion-and-gold-certificates-be-delivered). Gold was confiscated all across the nation, and all the investors who didn’t protect their privacy (which was especially hard with “paper gold,” kept in custody by trusted third parties eager to comply with the order, but also pretty hard with actual physical gold, difficult to hide in large amounts or to smuggle across a border) had to give it to the government. 

A good general heuristic is this: If you are a privileged “first-world” investor, with a good KYC identity, and you are looking for some kind of investment that is politically uncontroversial now and likely to remain that way, then you will soon be able to access that type financial product from you favorite fiat bank. If that describes you, don’t even concern yourself with complex stuff like private keys, blockchain fees, addresses: leave the real protocol to real users. Just call your good old bank over the phone and ask to buy some “bitcoin-flavored risk”: certificates, futures, ETNs, ETFs, CFDs, etc. 

If, on the other hand, you are not as privileged (like the majority of the world population today, which doesn’t have a KYC-friendly identity), or if you think that the financial asset you seek is a bit controversial today already or likely to become so in the future, then you will eventually need some very strong privacy techniques to acquire it and to safely store it, since “legally compliant” exchanges, brokers and marketplaces will do everything they can to keep you out of it or take it from you.

### Red Herring #3: “Just Use a Magical ‘Privacy Coin!’”
A second typical reaction, even more absurd, is to suggest “[privacy altcoins](https://bitcoinmagazine.com/tags/privacy-coins)” as a “solution” to this problem. A regulated exchange will flag your account if you use best practices such as CoinJoin, or Lightning Network, or address-reuse-avoidance. Then, instead of bitcoin, just use some illiquid bitcoin-clone whose design has been altered in such a way that it’s said to offer “more fungibility,” right? 

The superficial problem with this approach is that such “magic privacy coins” don’t actually exist in the real world. On one hand, that’s because most of the changes marketed as “privacy improvements” are either entirely fake or greatly exaggerated. They also tend to come with serious trade-offs which make these clones otherwise unusable at scale over the long run (usually including a completely centralized development process, trivial to compromise). 

On the other hand, even if such a coin were to exist, from a technological point of view, it couldn’t work in practice from an economical point of view. Remember: Privacy loves company. A huge chunk of the bitcoin economy and its users would have to move to the very same bitcoin-clone as you. Otherwise, your transactions will have a lower liquidity and a smaller anonymity set, regardless of how perfect and sci-fi-worthy the privacy tech you are using is.

## More on These Magical Privacy Coins and Why They Are Useless
### The Bitcoin + Privacy-Coin Combo Fallacy
There are variants of this red herring which are based on some kind of “bimetallic standard” idea: Those proponents will suggest that you use bitcoin as your fundamental store of value (which centralized illiquid clones can’t be for obvious economic reasons), and then add a particular “privacy altcoin” for privacy in transactions. 

Of course that can’t work in most real-world scenarios. Assuming that the payer and the payee both use bitcoin as a long-term store of value, the payee would have to move satoshis from his personal storage solution to some kind of market (regulated or not, it doesn’t really matter here) with the same privacy issues as any other bitcoin transaction; then exchange those satoshis for altcoins on some low-liquidity shared order book with very low privacy; and then move the altcoins over their native system with a low anonymity set to an address provided by the payee. Then the payee would have to repeat the same steps in reverse. 

The privacy guarantees of the whole process would be, overall, way lower than a normal bitcoin transaction performed following the best practices. Of course, these guarantees can be increased if either the payee or the payer “batch” many transactions in one big altcoin reserve, exchanging satoshis only once, way before or way after the single individual transactions. But this would require the altcoin to be a reliable store of value for long periods of time — which illiquid and centralized bitcoin-clones (often crippled by unbalanced trade-off choices between privacy features and other very delicate aspects) can’t be. 

The deeper problem with this approach is that, even if feasible, it would become completely useless pretty quickly. The very same reasons that convinced some regulated exchanges to actively discourage or even prevent their customers from adopting privacy best practices on Bitcoin, would readily convince the very same exchanges to just delist any “privacy-focused” bitcoin-clone. The “smaller” the altcoin, the weaker the incentive to list it. The “bigger” the altcoin, the stronger the regulatory pressure to delist it. It’s as simple as that.

### The “Mandatory” Privacy vs “Opt-In” Privacy Fallacy
Some weak attempts at steel-manning this approach focus on the distinction between **mandatory privacy** and **opt-in privacy**. “With Bitcoin,” the altcoin proponents say, “you are not forced to use the fungibility features at the protocol level, so it’s easy for the exchange to ask you not to use them. But with my altcoin, you have no choice, so the regulated exchange will also have no choice but to allow you to use them.” 

Again, this is nonsense; it’s not true that a privacy feature can ever be “mandatory at the protocol level.” 

As the history of Bitcoin teaches us, it’s mostly about tools: Even when the base protocol includes strong fungibility capabilities, if the most widespread tools don’t leverage them, then people will simply not use them. They’ll just resort to using whatever is easy and available, even if that mean adopting bad practices instead.

It doesn’t matter which protocol you use: If the tools are inadequate, so is your privacy. Just as you can have a bitcoin wallet that is incompatible with CoinJoin and that forces address reuse, you can also have a [monero](https://bitcoinmagazine.com/articles/battle-privacycoins-why-monero-hard-beat-and-hard-scale) wallet that leaks confidential information about amounts and always constructs “ring-signatures” between every single user and himself. If such a wallet is widespread, spy companies can assume such behavior as common and build de-anonymization heuristics. 

Of course, altcoin proponents may just build and market tools that actually use the privacy features already present in their clone at the protocol level. But then again they would need just as much time, money and effort that is required for building and marketing tools that actually use the privacy features already present in Bitcoin at the protocol level.

## What Really Matters: Incentives
A more useful distinction to examine is the one between privacy features that are economically **convenient** to use and privacy features that are **costly** to use. The perfect (bad) example would be that of “shielded transactions” in the altcoin [Zcash](https://bitcoinmagazine.com/articles/battle-privacycoins-zcash-groundbreaking-if-you-trust-it): Since they take way more space inside blocks, and way more computation time to be verified and signed (making this last action almost impossible on a light client), economic incentives push the already-few users of the coin to “unshielded” transactions, which are just an outdated version of the traditional bitcoin ones. 

As a **direct** effect, many users will think they have “more privacy” when this process, in fact, makes tracking and deanonymizing far easier. An **indirect** effect will be that the very few users who do decide to pay the extra cost for “shielded” transactions will find themselves within an even smaller anonymity set, ending up exposed instead of protected. 

An opposite example would be the Lightning Network on Bitcoin: Since block space is expensive, users often have strong economic incentives to switch to payment channels to save fees, reducing the “timechain footprint” to just opening and closing channels.

## Same Old Story
Ultimately, it’s not surprising at all that some of the most vocal proponents of the “CoinJoin is risky because your account will get flagged” narrative turn out to be also promoters of new, illiquid “privacy” altcoins, which they hope to push to profit from “pump-and-dump” schemes. Same old story: “Bitcoin’s fees are too high: buy my low-fee altcoin!” or “Bitcoin signatures aren’t quantum-proof: buy my quantum-ready altcoin!” or “Bitcoin’s smart contracts aren’t flexible enough: buy my Turing-complete altcoin!” or “Bitcoin is not fungible enough: buy my privacy altcoin!”

## Solutions Are Coming
Are there real solutions and ways to mitigate the threat that regulated exchanges pose to the privacy and the security for Bitcoin users, beyond the red herrings? Yes: many. 

The ultimate solution, albeit very slow, will eventually come from the evolution of the market. While more and more resources will leave the fiat world to enter Bitcoin over the years, more and more parts of the bitcoin economy will move from fiat gateways to satoshi-denominated trades among users. Gateways will still be important, but gradually less so, making their bargaining power lower and lower over time. Fiercer competition will also help: People will be happy to leave meddling PI-hiring banks who force them to keep shower curtains open if they have alternatives.

### More Tools

Another mitigation will come from the evolution of Bitcoin tools. While more and more modern wallets will make it harder to reuse addresses or merge inputs, and easier to coordinate CoinJoin rounds, regulated exchanges will have a harder time forcing their customers to use only old, outdated or inferior wallets instead.

### Lightning Network

Yet another mitigation will come from the adoption of the Lightning Network. Since block space in the base layer will become more expensive, users will be strongly incentivized to route transactions over payment channels instead. It will be harder for regulated exchanges to arbitrarily ban customers due to a probabilistic link between the satoshis they deposited or withdrew on the Lightning Network, especially when the latter will be ubiquitous, thanks to economic incentives.

### Protocol Upgrades

Additional improvements may possibly come from the next protocol upgrades in Bitcoin, especially the one called “cross-input Schnorr signature aggregation.” This upgrade will make coordinating with several different parties within CoinJoin rounds extremely convenient, from an economical perspective.

### Decentralized Exchanges

Another hope comes from the idea of decentralized exchanges (DEXes). So far, they suffer from liquidity limitations and their security remains tricky: While the Bitcoin “leg” of any trade can be easily trust-minimized, the fiat leg remains ultimately trust-based, making complex and expensive escrow mechanisms necessary. (In turn, escrow mechanisms tend to prove very difficult to decentralize effectively.) 

Your privacy is in your hands — just keep calm and be diligent. Don’t submit to dangerous privacy violations. Don’t reuse addresses. Use CoinJoin. Close your shutters when you’re at home. Pull the shower curtains when you’re naked. Put a lock on your personal journal. Use HTTPS when surfing the web. 

In the end, Bitcoin fixes this.


***

{% include signup.md %}
