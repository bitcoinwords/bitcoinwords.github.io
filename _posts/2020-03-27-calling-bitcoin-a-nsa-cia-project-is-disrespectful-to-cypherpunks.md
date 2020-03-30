---
title: "Calling Bitcoin a NSA/CIA Project Is Disrespectful to Cypherpunks"
permalink: "/calling-bitcoin-a-nsa-cia-project-is-disrespectful-to-cypherpunks"

author: vladcostea

tags:
  - Vlad Costea
  - CY20 Q1
  - History
  - Politics
  - Cypherpunks
  - CIA
  - NSA

excerpt: Vlad Costea takes a look at Bitcoin's history and defends the cypherpunks legacy. Posted March 27, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Calling Bitcoin a NSA/CIA Project Is Disrespectful to Cypherpunks]()
### By [Vlad Costea](https://twitter.com/TheVladCostea)
### Posted March 27, 2020

![](/assets/images/2020/m3/vc1.png)

I’ve recently asked my Twitter followers to mention their favorite Bitcoin conspiracy theory. Surprisingly, most respondents [have mentioned](https://twitter.com/TheVladCostea/status/1242849736203304965?s=20) the CIA, the NSA, or another “three-letter agency” as the potential creators of the cryptocurrency. Deater Bob [suggested](https://twitter.com/AwyeeDeaterBob/status/1242851205962969094?s=20) that Satoshi Nakamoto might have leaked the Bitcoin project from sources within the US government. Gilroy [pointed out](https://twitter.com/xGilroyx/status/1242855403781869568?s=20) to a master plan that would eventually use Satoshi’s coins as the foundation for a new US treasury. The likes of [Juan Galt](https://twitter.com/JuanSGalt/status/1242887221763547136?s=20) and [Jack](https://twitter.com/Jackof_/status/1242850947208003585?s=20) have also suggested that the NSA might have been involved. And in spite of some creative replies (such as Wladimir Van Der Laan’s theory about [Bitcoin being a fungus](https://twitter.com/orionwl/status/1242880224200663040?s=20) and Bmo Masari’s [suggestion](https://twitter.com/BmoMasari/status/1242851746667548673?s=20) that the internet itself might have attained consciousness in order to create Bitcoin), I couldn’t stop thinking about the popular associations between the creation of Bitcoin and governmental agencies.

![](/assets/images/2020/m3/vc2.png)

Therefore, I will explain why the association is wrongful – and even if Satoshi Nakamoto was the CIA or the NSA, Bitcoin no longer belongs to him, and it isn’t even as innovative as most people think. Bitcoin didn’t come out of nowhere and borrows multiple breakthroughs that cypherpunks have previously made. To Satoshi Nakamoto’s credit, he/she/they/it have created the best solutions for the [Byzantine Generals Problem](https://en.wikipedia.org/wiki/Byzantine_fault), and is/are responsible for releasing a form of decentralized electronic money that actually succeeded. The [difficulty adjustment](https://en.bitcoin.it/wiki/Difficulty) every 2016 blocks is also a fine touch, and one which has been crucial for the survival of the network. However, there is a cypherpunk tradition that precedes Satoshi’s emergence by 20+ years. And this article will present only a few of the inventions that have taught Satoshi how to design Bitcoin and which proven flaws to avoid.

![](/assets/images/2020/m3/vc3.gif)

## Satoshi Nakamoto might be the CIA/NSA, but Bitcoin is rooted in the cypherpunk tradition.

Lots of nocoiners, precoiners, and poorly informed bitcoiners think that Satoshi Nakamoto invented the blockchain and deserves all the credits for the accounting system which spawned an entire industry. Like many other cryptographic inventions, the blockchain was first conceptualized by David Chaum during his PhD at Berkeley University. His 1979 [Vault system](https://decentralize.today/blockchain/david-chaum-vault-system-first-blockchain) even includes checks and balances that very much resemble Bitcoin’s: watchers (block explorers), doers (nodes), executives (miners), czars (developers). Chaum also created the first form of digital money ([ecash](https://en.wikipedia.org/wiki/Ecash)) with the [DigiCash](https://www.chaum.com/ecash/) corporation. It was designed to fix the trust issues of online credit card payments with a form of money that is private enough to conceal personal data that is irrelevant to the transaction. However, its centralization ultimately led to a disappointing demise in the late 1990s. Interestingly, Satoshi doesn’t mention Chaum in the Bitcoin whitepaper.

![](/assets/images/2020/m3/vc4.png)

Let’s get back to the blockchain: the idea of an hash chain that is used for [linked timestamping](https://en.wikipedia.org/wiki/Linked_timestamping) is also presented in a 1991 research paper by Stuart Haber & W. Scott Stornetta. Unlike David Chaum’s work, Satoshi does reference this breakthrough in the Bitcoin whitepaper. Also, cypherpunk Jameson Lopp [has cited the research](https://twitter.com/lopp/status/1005612763245400064?s=20) as a precursor to Bitcoin’s blockchain. Then there’s the choice of Elliptic Curve Digital Signature Algorithm (ECDSA), [published in 1998](http://www.cs.miami.edu/home/burt/learning/Csc609.142/ecdsa-cert.pdf) by Canadian computer science researchers Don Johnson, Alfred Menezes, and Scott Vanstone. With [ECDSA](https://en.bitcoin.it/wiki/Elliptic_Curve_Digital_Signature_Algorithm), public keys, private keys, and signatures get generated in order to guarantee that the bitcoins can only be spent by the rightful owners. A popular theory says that Satoshi Nakamoto picked ECDSA over Schnorr signatures out of convenience, as more libraries were available to suit his/their specific needs when designing Bitcoin. Yet there are lots of [privacy concerns](https://www.schneier.com/blog/archives/2013/09/the_nsa_is_brea.html#c1675929) (that do involve the NSA’s tendency to implant backdoors) that will eventually replace ECDSA with Schnorr signatures (thanks, Pieter Wuille!). The idea of cryptography that uses public keys is also not proprietary to Satoshi Nakamoto: Ralph Merkle was [researching the topic in 1980](http://www.merkle.com/papers/Protocols.pdf) (as acknowledged by the Bitcoin creator in the whitepaper), and Phil Zimmermann’s private e-mailing tool PGP (on which Hal Finney has worked for many years) has been [available on the internet for free since 1991](https://www.philzimmermann.com/EN/background/index.html).

![](/assets/images/2020/m3/vc5.png)

Speaking of Hal Finney, Bitcoin makes use of his Reusable Proof of Work ([RPOW](https://nakamotoinstitute.org/finney/rpow/index.html)) breakthrough. However, it’s Adam Back who gets cited in the whitepaper for inventing [the hashcash](http://www.hashcash.org/) system in 1997 and perfecting it to prevent e-mail spam. Without these cryptographic breakthroughs, Bitcoin could have never reached the same degree of security and the brilliant mining incentives most likely wouldn’t have existed. Yet another great cypherpunk who doesn’t get cited in the whitepaper but has basically solved 90% of Satoshi’s problems is Nick Szabo. His [Bit gold system](http://unenumerated.blogspot.com/2005/12/bit-gold.html) successfully connects many puzzle pieces from amongst the most brilliant cryptographic discoveries, and also creates the “digital gold” principles that are rooted in Austrian economics (scarcity, fixed issuance rate which avoids the pitfalls of hyperinflation, easy verification). Unfortunately, the Bit gold design relied on a majority of network participants and could be easily become subjected to 51% attacks. What Satoshi Nakamoto did was to replace the rule of CPUs with the rule of hash power.

## These cypherpunks were all about privacy and resisting the NSA

The “punk” in “cypherpunk” should successfully delineate the movement from government servitude. According to Tim May’s 1994 opus “[The Cyphernomicon](https://nakamotoinstitute.org/static/docs/cyphernomicon.txt)“, the cypherpunks were very much against surveillance and sought to keep their privacy on the internet while inventing tools to also help others. Compliance in itself was synonymous with an ideological capitulation. David Chaum wrote “[Blind Signatures for Untraceable Payments](http://www.hit.bme.hu/~buttyan/courses/BMEVIHIM219/2009/Chaum.BlindSigForPayment.1982.PDF)” in 1983, and “[Security Without Identification: Card Computers to Make Big Brother Obsolete](https://www.chaum.com/publications/Security_Wthout_Identification.html)” in 1985.

![](/assets/images/2020/m3/vc6.png)

In an October 1995 report by the NSA (which was [declassified in 2008](https://www.nsa.gov/Portals/70/documents/news-features/declassified-documents/communicators/Communicator-III-43.pdf)), some concerns were expressed in regards to the ways in which DigiCash can be used for criminal activities. The existence of this particular document proves that Chaum’s intentions were real and he truly was concerned with privacy. It’s very unlikely that cypherpunks like Finney, Szabo, Back, Haber, and Stornetta worked for the NSA, CIA, or any other governmental agency. Otherwise their work would have been classified and restricted to only be used by authorized personnel. And even if we assume that the open source work was released as such to get further improved by other voluntary cryptographers on the internet, the fact that these tools work against the monopolistic interests of the NSA/CIA also makes the cypherpunks look pure at heart. If the NSA decides to use RPOW or the ideas behind Bit gold to build a system of their own (which most likely happened already to some extent), it doesn’t mean that the inventors of these systems were their employees.

## Bitcoin was invented by Satoshi, but it never belonged to him

At most, a returning Satoshi Nakamoto can move his coins and spend them. There is no backdoor key, there is no reserved lead developer position, and there is no active developer who awaits the return of the creator. Like it or not, Bitcoin is not the same network it was in 2009. It has undergone numerous improvements and will continue to leave Satoshi Nakamoto’s legacy behind as more parts get replaced. After all, the point of Bitcoin is not to remain unchanged over time, but to keep its monetary policy, guarantee that Satoshi can return at any time and move the coins, and preserve decentralization. There is a lot that Satoshi Nakamoto got right, but also plenty of code that was removed or replaced by developers. Hal Finney has spent a lot of time fixing design flaws in Bitcoin (and even added extra zeroes to define the system’s smallest monetary unit as 1/100.000.000 BTC) and he set a precedent for future devs to seek more elegant and efficient fixes for an otherwise rigid project.

![](/assets/images/2020/m3/vc7.gif)

Bitcoin as a monetary system is set in stone with a fixed supply, a predictable inflation until 2140, clear mining rewards, and convenient difficulty adjustments every 2016 blocks. But Bitcoin as a network is bound to receive lots of upgrades that make it faster, more private, and more efficient. Improvement proposals like [Schnorr signatures](https://bitcoincore.org/en/2017/03/23/schnorr-signature-aggregation/), [Taproot](https://bitcoinmagazine.com/articles/taproot-coming-what-it-and-how-it-will-benefit-bitcoin), [MAST](https://bitcointechtalk.com/what-is-a-bitcoin-merklized-abstract-syntax-tree-mast-33fdf2da5e2f), and [Grafroot](https://www.reddit.com/r/Bitcoin/comments/7vcyip/graftroot_private_and_efficient_surrogate_scripts/) are designed to bring greater privacy and block efficiency (transactions will get smaller and more affordable). Then there are lots of privacy improvements that are being explored on altcoin networks and sidechains (it’s only a matter of time until Confidential Transactions or MimbleWimble get added to the base layer to some degree). In the future, it’s likely for transaction privacy to become more popular, and smart tricks that still guarantee supply auditability and inflation resistance will be implemented. If Satoshi returned, he probably wouldn’t recognize his own invention. But that’s for the better, as the network is growing and becoming much more efficient for its purpose. Bitcoin is like a muscle car which receives upgrades without ever changing the body frame – it will always retain the main design qualities, but with a better engine and bulletproof windows.

![](/assets/images/2020/m3/vc8.gif)

## If Satoshi Nakamoto is the NSA/CIA, then Bitcoin does not belong to them anyway

Is Bitcoin designed by a three-letter agency? It’s definitely possible. Could the CIA and NSA use Bitcoin for transactions? That’s even more likely. But neither of these two probabilities lead to a conclusion that puts a governmental agency in control. Right now, Bitcoin may possibly be the most decentralized computer network on the planet. It has functioned for almost 11 years with only two instances of downtime (due to [an inflation bug](https://en.bitcoin.it/wiki/Value_overflow_incident) in 2010 and due to [poor network synchronization](https://github.com/bitcoin/bips/blob/master/bip-0050.mediawiki) in 2013) and has ~10000 [nodes operating worldwide](https://bitnodes.io/) (not counting the ones running on Tor and the ones that didn’t open the [8333 port](https://bitcoin.org/en/full-node#port-forwarding)). Some argue that backdoors may exist: and the most damage they can do is break the signatures (which can lead to funds being stolen) or break the cryptography behind [SHA256](https://en.bitcoinwiki.org/wiki/SHA-256). In either case, it’s possible for the community to hard fork to a new chain, replace both ECDSA and SHA256 with existing alternatives that have already been already been developed, and restore previous coin ownership on the basis of cryptographic proof. The solution seems unpopular now, but may prove to be the last resort in the event of a serious attack of the kind which Bitcoin never really faced. The battle against Big Brother is relentless, and it’s clear that government officials understand the trade-offs involved in launching attacks or momentarily lack the means to engage. It’s also probable that the CIA and the NSA find the existence of Bitcoin convenient, as they use it themselves and have their own ways to track transactions on the blockchain by looking at communications between participants and other network-level clues. But even if we assume that Satoshi Nakamoto was the father of all CIA agents, the experiment has escaped his hands and he is no longer in control – and nor will he ever be again, unless the network becomes more centralized (as it happened with BCH and BSV).

![](/assets/images/2020/m3/vc9.gif)

And even if half of the Bitcoin community is under CIA’s paycheck, then the other half can still resist attacks by moving to another chain which retains the rules but changes the security. It’s all open-source software and the means to protect one’s property should be enforced. Yet thanks to the brilliant network incentives, it’s better for everyone (CIA agents or not) to stick together and protect the same network. For as long as greed works, Bitcoin will remain secure and adversarial in terms of who it onboards and for what reasons. The “don’t trust, verify” motto mostly refers to other people’s nodes and implies having your own node as a way of proving that the funds exist and are rightfully yours. Therefore, it’s an assumption that everyone else is out there to rob you – because you know, [everyone’s a scammer](https://nakamotoinstitute.org/mempool/everyones-a-scammer/).

Muh Satoshi
-----------

The Satoshi Nakamoto we know from forum posts and the [cypherpunk mailing list](https://cryptoanarchy.wiki/getting-started/what-is-the-cypherpunks-mailing-list) was pretty humble and down-to-earth. He was willing to help anyone understand how Bitcoin works – with the exception of Daniel Larimer, [who got dismissed in a pretty badass way](https://bitcointalk.org/index.php?topic=532.msg6306#msg6306). However, turning him into some sort of Messianic figure who gave us the power of the Holy Spirit and departed to return “someday” is definitely wrong. We can’t deny Satoshi’s contributions to the world of cryptography, but we can’t exaggerate his work either. Sure, the story of the unknown computer programmer who released an innovative digital money system out of nowhere seems romantic. It attracts newcomers and it keeps the media busy with [phony investigations](https://www.newsweek.com/2014/03/14/face-behind-bitcoin-247957.html). Yet the genius of Satoshi Nakamoto is overstated and there is very little that he added to the otherwise impressive but lesser popular inventions of his peers. It’s the classic example of Isaac Newton and [Gottfriend Wilhelm Leibniz](https://en.wikipedia.org/wiki/Gottfried_Wilhelm_Leibniz): everyone knows about the former and his story with the apple, but tends to forget about the latter. They both discovered integral mathematical calculus around the same time, but the glory appears to be on the side of the English polymath to an unfair extent. The bottom line is that it doesn’t matter who Satoshi Nakamoto really was and it’s extremely irrelevant at this point in Bitcoin’s development. Also, the NSA/CIA stories are pretty unfortunate given the cypherpunk origins of Bitcoin. **While Satoshi might have been the NSA, then Bitcoin clearly isn’t.**

![](/assets/images/2020/m3/vc10.png)

Enjoyed the article? Donate to the Bitcoin Takeover project: 37EmPGG6mw2BSq54WVEs8EJJToNZXopKV4



***

{% include signup.md %}