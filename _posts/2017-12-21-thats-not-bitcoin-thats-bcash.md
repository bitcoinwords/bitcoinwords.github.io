---
title: "That's not Bitcoin, that's BCash"
permalink: "/thats-not-bitcoin-thats-bcash" 

author: stopanddecrypt

tags:
  - Stop and Decrypt
  - CY17 Q4

excerpt: Stop and Decrypt takes a critical look at the Bitcoin Cash community and how the branding is misleading on purpose. Posted December 21, 2017.

defaults:
  - scope:
      type: posts
---

# [That's not Bitcoin, that's BCash](https://hackernoon.com/thats-not-bitcoin-that-s-bcash-f730f0d0a837)
### By [Stop and Decrypt](https://twitter.com/StopAndDecrypt)
### Posted December 21, 2017

## Or, There and Back Again, a Full-Node's tale

## Introduction

I want to precede this article with some clarification to make things very clear. Just to kick this off the right way, when I say BCash, I mean the Bitcoin _copycat_, formally referred to as Bitcoin ' **Cash'**.

Out of their community's lack of enthusiasm for the BCash nickname everyone else has graced their project with, someone created a fakeproject actually called "BCash" as a laughable attempt to confuse bystanders and dismiss people from referring to Bitcoin **'Cash'** as BCash. Now they all source this fake project when you use the term, as if that negates whatever argument you were trying to debate.

Were you just in the middle of a conversation or debate and used the term BCash? Debate over... "BCash is a different coin, you must be confused or a troll."

Sorry, no, I'm neither one of those. You're just a liar.

This is fake:

![](/assets/images/cy17/cy17m12/sad-1.png){: .align-center}

This is not BCash. This is not a different coin. This is a distraction. The fake page above _(screenshot is outdated, Vinny has since blocked me)_ and the associated [empty Github](https://github.com/bcash-coin/bcash) page is what Roger refers to as "a completely separate project not related at all" in this clip below:

![](/assets/images/cy17/cy17m12/sad-2.png){: .align-center}
_"a paid operative": [Caller 1](https://twitter.com/FiatisShiat/status/961684534730268672)— [Caller 2](https://twitter.com/BTC4USD/status/961711048695992321)_

Here's another two clips, one from Roger, and the other Jihan Wu _(two of the projects largest advocates)_ getting very upset over the nickname. Clearly this isn't a joking matter, and we should try to treat their project/scam with more respect by calling it by its actual name:

![](/assets/images/cy17/cy17m12/sad-3.png){: .align-center}

In the [full interview](https://www.youtube.com/watch?v=OJT2CbfHTpo&t=7s), Bitcoin Jesus implicitly referred to BCash as "[his] project". 

![](/assets/images/cy17/cy17m12/sad-4.png){: .align-center}
[https://www.pscp.tv/w/1BdxYMDqezgxX](https://www.pscp.tv/w/1BdxYMDqezgxX) 

Again, for the rest of this article _(and whenever you see someone say it online)_, all references to BCash are references to Bitcoin **'Cash'**, _just in case there was ever any confusion_. I don't care about your feelings towards a nickname. This article isn't for those who are hurt by the nickname, its for those that barely even know what's going on. If that bothers you... _don't read it:_

![](/assets/images/cy17/cy17m12/sad-5.png){: .align-center}
[https://www.youtube.com/watch?v=EigRGcfSEcw](https://www.youtube.com/watch?v=EigRGcfSEcw) 

I don't like BCash, so I won't be using it, or its actual name. Moving along to the actual article...

![](/assets/images/cy17/cy17m12/sad-6.png){: .align-center}

## So what is BCash? Where did it come from? What is its purpose? Should I care? Why is it colored green?

There's no reason you should blindly trust me, but realistically if you just avoid it you have nothing to worry about. This article isn't for those who've been around for a long time _(except as a bookmark to reference)_, it's for newbies, unaware casuals, and the future waves of interest flowing into this space. Some of this info might seem dated or "old news", but the goal is to inform and archive. No one new to this community should have to browse years of Reddit comment history, Twitter threads, and watch hundreds of hours of Bitcoin conference panels/lectures, YouTube interviews, or Alex Jones' guest appearances just get a grasp on why they are being scammed if they listen to these frauds and buy BCash. I highly recommend reading my [first article](https://hackernoon.com/thats-not-bitcoin-this-is-bitcoin-95f05a6fd6c2) if you're just stumbling across this one casually. You'll get a better feel for some of the players involved in this scam.

Like my [second article](https://hackernoon.com/this-is-bitcoin-who-are-you-to-tell-us-otherwise-8fc5966d4ac4) on the failed 2X fork, I won't be discussing the entire years-old history of the scaling debate. I'll be aggregating as much information as I can into a digestible order, with a twist of my own opinions. Half the value in this post is from content shared here that is not mine so make sure you check the sources I've linked throughout this article, including an hour long video on block propagation. If you actually want to learn some things you should take the time to watch it and read all the other articles scattered throughout.

## Index

* **Delaying Segwit:** The gateway to Schnorr, MAST, Confidential Transactions, Lightning Network, and the convenient killer of ASICBoost.
* **Disinformation & Propaganda:** How to effectively destroy your entire reputation, but only to those who've been paying attention, and why that's a good business strategy in the cryptocurrency space.
* **Moore's _Observation_:** Increasing transistor counts on silicon over time has nothing to do with keeping Bitcoin's network decentralized.
* **Satoshi Dundee:** Craig Wright is a fraud, and Roger Ver is his friend.
* **Conclusion:** Words of advice.

## Why try to block and ridicule Segwit?

Understanding why begins with understanding all the benefits of Segwit, its negative effect on Bitmain's hardware operation, and then realizing that anyone trying to co-opt Bitcoin would lose whatever leverage they had if the upgrade to Segwit was successful, because it lays out the framework necessary for smooth and _inclusive_ soft-forks moving into the future, but I'll touch on that later. I couldn't begin to outline all the technical benefits of Segwit any better than the [actual post](https://bitcoincore.org/en/2016/01/26/segwit-benefits/) on the Bitcoin Core site _2 years ago_, go read it. Instead I'll summarize some of the things Segwit provides, and the most known up-and-coming developments I'm anticipating that require Segwit in order to implement efficiently _(not all may make it, and some may evolve over time)_.

### Segwit enables:

* [**Bech32 Address Encoding**](https://www.youtube.com/watch?v=NqiN9VFE4CU) — Built in error checking making it less likely a mistyped address will be considered valid, plus a means to allow future Segwit [script opcodes](https://en.bitcoin.it/wiki/Script#Opcodes) to be soft-forked in with ease.
* **Transaction Throughput Increase** — The theoretical size limit for a block has been increased from 1MB to 4MB, but the effective average size has been increased to 2MB+, so more than double the current capacity.
* [**Signature Aggregation (enabled with Schnorr Signatures)**](https://hackernoon.com/excited-for-schnorr-signatures-a00ee467fc5f)— Allows more transaction data _(via "compression")_ in a block, no matter the size of that block. _Nodes_ still have to process that extra data, but the _network_ doesn't take a hit because it's the same volume of data being sent around. **_Can be soft-forked in using SegWit script opcodes._**
* [**Merklized Abstract Syntax Tree (MAST)**](https://bitcointechtalk.com/what-is-a-bitcoin-merklized-abstract-syntax-tree-mast-33fdf2da5e2f) — Significantly reduces the amount of script data necessary in smart contracts & transactions. **_Can be soft-forked in using SegWit script opcodes._**
* [**Confidential Transactions**](https://www.youtube.com/watch?v=LHPYNZ8i1cU)— Allows the _amount_ of Bitcoin you send in a transaction to be hidden, but provable if desirable. **_Can be soft-forked in using_** [**_SegWit script opcodes_**](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2016-January/012194.html) **_._**
* [**Lightning Network**](https://lnmainnet.gaben.win/)— With Segwit's malleability fix, the Lightning Network is less complicated to implement, more efficient in its use of blockchain space. It's also now possible to have lightweight Lightning clients _(like mobile wallets)_ that outsource monitoring the blockchain, instead of each Lightning client needing to also be a Bitcoin full-node.

So Segwit allows a lot of great features to be implemented more smoothly down the line, like new opcodes that can be added without breaking the network via a hard-fork, making future upgrades more safe, and fixing some transaction formatting issues that hindered growth in other technological developments. But why bother, right?

![](/assets/images/cy17/cy17m12/sad-7.png){: .align-center}

Instead, let's make fun of it, try to prevent it, and when it ends up being successful anyway because it's good code, let's fork the chain and create a new altcoin _(BCash)_ without it. We'll continue to spread lies about what it is and how it works throughout this whole process, and even talk about potentially reversing Segwit as a fallback option just in case nobody likes or wants to buy our new altcoin we just made, like Rick Falkvinge did in this video:

![](/assets/images/cy17/cy17m12/sad-8.png){: .align-center}

I'll mention it briefly now, and touch on it later: **Infrastructure reinforces consensus code.** Segwit can't be reversed. The graph below shows a rough estimate _(~80%)_ of Segwit compatible nodes. All of which have been accepting Segwit formatted blocks since the beginning of August 2017. Any attempt to reverse Segwit would result in a hard-fork, splitting the network into _another_ 2 coins, and on that new chain you would make all Bech32 addresses open to having coins stolen, including _every single Lightning payment channel._ The original chain will keep functioning fine, because nothing changed, and nothing broke on it.

Simply put, _nobody would use the new chain._ Rick is deceiving you.

![](/assets/images/cy17/cy17m12/sad-9.png){: .align-center}
_Highlighted boxes are software implementations that are assumed to not be Segwit compatible because they're likely older than 0.12.1._

The reality is, not everyone here is working on the same "team". BCash was originally created by and for Jihan Wu, because Segwit would marginalize his companies profits by disabling covert ASICBoost, which is an "improvement" to mining that gave his mining operation significant leverage over others. You can read more about it below, it goes into much better detail:

[**ASICBoost, the reason why Bitmain blocked Segwit.** _Of course this happened while I was sleeping, but Greg Maxwell sent a very interesting mail._
medium.com](https://medium.com/@WhalePanda/asicboost-the-reason-why-bitmain-blocked-segwit-901fd346ee9f "https://medium.com/@WhalePanda/asicboost-the-reason-why-bitmain-blocked-segwit-901fd346ee9f") 

Jihan knew there was a minority community that wanted to go their own way and used that to his advantage. He actually made it very clear multiple times that Bitcoin is Bitcoin, and BCash is BCash, and they are not to be confused. What happened instead was, that minority community took the new fork and ran with it. Prominent figures tried to capture it and call it _The_ Bitcoin, to which even Jihan fought back and said no:

![](/assets/images/cy17/cy17m12/sad-10.png){: .align-center}
[https://twitter.com/JihanWu/status/928831035441274880](https://twitter.com/JihanWu/status/928831035441274880) 

Meanwhile, the whole time this was happening _(all of 2017)_, the 2X fork was on the horizon, and the very same people who were applauding BCash were simultaneously pushing for 2X to try and divide the Bitcoin community. [Read my 2X article for more on that.](https://hackernoon.com/this-is-bitcoin-who-are-you-to-tell-us-otherwise-8fc5966d4ac4) 

![](/assets/images/cy17/cy17m12/sad-11.png){: .align-center}

So again I ask, why try to block the most important upgrade to the Bitcoin network since its inception? Why play marketing and social media games?

## Why sprea **d disinformation & propaganda?**

One of the most notable things about the cryptocurrency community is how rapidly it's growing but how slow the education process is. I've learned a lot of what I know by speaking directly to some of the developers, and engaging with many less-involved people like myself, but that obviously doesn't scale. Lectures are nice, but "nobody" really watches them. Podcasts are good too but they rarely dive deep technically. Looking at all of this from the outside without any knowledge of its inner workings it's easy to think we have this all squared away, until you read posts like mine and many others that show you just how in its infancy all of this really is.

How many people do you know that are aware of Bitcoin fit this description?

1. Understands that it's _"a protocol"_nobody controls.
2. Knows that people _"mine"_ it.
3. Knows the price goes up and down.
4. _That's it._

I'm willing to bet it's most of them. Articles like this one I'm writing are _okay_, but it took 4 months for my first article to reach 20,000 "views". Most people just don't want to invest the time, or have the skill-set required to do their own research. On the other hand it took this tweet with a short video a couple of days to reach over 20,000 video views and 100,000 impressions, and that's still really not that much _(and it's only a short video):_ 

![](/assets/images/cy17/cy17m12/sad-12.png){: .align-center}

None of this is really surprising though, "nobody" understands how the Internet works. Those who do are less than 1% of the population, and the same will go for Bitcoin's protocol stack. As the community grows from Bitcoin adoption it stops looking like a community and starts looking like a population with a gradient of opinions, meanwhile the "actual" community keeps chugging along, continuing to discuss and build what Bitcoin was _(and still is)_ intended to be. That inner circle keeps growing, but nowhere near the rate of the outer circles with wildly different opinions.

![](/assets/images/cy17/cy17m12/sad-13.png){: .align-center}
[https://twitter.com/janeygak/status/967076813141786624](https://twitter.com/janeygak/status/967076813141786624) 

It does, but that's because most people aren't actually part of the "community", nor do they need to be, or ever will be. There is no "TCP/IP" community that consists of Internet Protocol engineers _and_ the average Facebook user. Let's take a look at some really over simplified categories of community growth as an example, growing by varying factors:

![](/assets/images/cy17/cy17m12/sad-14.png){: .align-center}
![](/assets/images/cy17/cy17m12/sad-15.png){: .align-center}

Putting real-world accuracy aside _(Coinbase is just a single platform)_, do you see what I see? I see 10,000,000 people that can potentially be manipulated into believing false premises and propaganda. How many of them would I have to convince if I wanted to sway enough opinions to appear competitive with the real community? **0.18%.** In a room of 1,000 people, I only need to convince 2 of them to believe me and take to Reddit or Twitter. So what do you do to combat that? Maybe you ignore it because you're unconcerned, maybe you argue with people on social media, or maybe you write an article to inform people.

Those numbers are obviously off, and I'm not interested in anyone trying to challenge them because it detracts from the point. It's very easy to lie in this space, profit off of it, get called out for it, and then lie again for more profit. People can have no clue what the following arguments mean, but if they are just getting in and they stumble across this they become instantly biased and they have no idea the goalpost was moved 10 times already:

![](/assets/images/cy17/cy17m12/sad-16.png){: .align-center}
[https://twitter.com/Falkvinge/status/967687732721004545](https://twitter.com/Falkvinge/status/967687732721004545)

> Segwit is a botched fix for a non-issue, Bitcoin can scale with larger blocks.
> Segwit as a soft-fork is a hack-job and would be much better as a hard-fork, we also need larger blocks.
> Segwit is being forced on the users who don't even know what it is, but I'll take it if it comes with bigger blocks.
> Lightning Network is vaporware and doesn't actually exist.
> Lightning Network won't be ready for 18 months and even then it's completely centralized.
> Lightning Network will be too complicated for the end user experience, and won't work without bigger blocks.
> BCash will have Lightning Network too, and BCash has bigger blocks, so it will work better, and we have no Segwit.

![](/assets/images/cy17/cy17m12/sad-17.png){: .align-center}
_Malleability wasn't the only thing added in with Segwit, and it was never just about Lightning._

![](/assets/images/cy17/cy17m12/sad-18.png){: .align-center}
_Bitcoin Unlimited failed. [About 400 of their fake nodes recently shut down too...](https://twitter.com/StopAndDecrypt/status/964974123905626112)_

![](/assets/images/cy17/cy17m12/sad-19.png){: .align-center}
_There's no infringement. [The patents referenced](https://patents.google.com/patent/US7370206) are owned by Adobe, would effect the entire Internet, and aren't enforceable. Segwit has nothing to do with this. At best Adobe owns these defensively._

![](/assets/images/cy17/cy17m12/sad-20.png){: .align-center}
_[The whitepaper](https://bitcoin.org/bitcoin.pdf) defines an electronic coin as a chain of signatures (section 2). This still exists with Segwit._

![](/assets/images/cy17/cy17m12/sad-21.png){: .align-center}
_Right..._

![](/assets/images/cy17/cy17m12/sad-22.png){: .align-center}
_Vitalik supports the Raiden Network (Ethereum's version of Lightning), and nothing about the Lightning Network changes the security of Bitcoin's base layer. It only adds features on top of it._

![](/assets/images/cy17/cy17m12/sad-23.png){: .align-center}
_Again...Lightning changes nothing about Bitcoin's base layer. It only adds features on top of it._

![](/assets/images/cy17/cy17m12/sad-24.png){: .align-center}
_The problem always existed. He just came into this space early, ignorantly spread what he believed to be true, while all the developers knew what would eventually happen. Also, [Satoshi conceived of payment channels.](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2013-April/002417.html)_

> Lightning sucks so bad, but if you like it, you can still have it on BCash! — Roger
> I never actually said that, this quote is libel. I'm telling my lawyers. — Roger

![](/assets/images/cy17/cy17m12/sad-25.png){: .align-center}
"More Users" and "More Nodes" are provably false. Notice his friend Fake Satoshi _(Craig)_ in the bottom right corner? We'll get back to that later...

> Bitcoin Cash can have everything Bitcoin has, plus bigger blocks. As a matter of fact, Bitcoin Cash **is**Bitcoin. Not yet though, but when it is, we can just drop the "Cash" from the name. 

That's why they **hate** the name BCash. It does exactly the opposite of what they want, it drops "Bitcoin" from the name instead, and they've been pushing _really hard_ to try and confuse people with this naming convention. Roger owns Bitcoin.com, and is _at the least_ working with the person who controls the @bitcoin Twitter account, who's been pushing "BCash is Bitcoin, Bitcoin **'Core'** is not" as well. Many suspect he controls the account and it isn't beyond belief because the style of responses are similar, and there's some other information that points to that conclusion as well. I don't think any of this information proves this theory correct but again, they are _at the least_ working together:

![](/assets/images/cy17/cy17m12/sad-26.png){: .align-center}
_[https://twitter.com/bitfinexeded/status/980205104707063808](https://twitter.com/bitfinexeded/status/980205104707063808)_

Roger doesn't like it when you comment on his tweets with polls because they go against him every time. Don't believe me? Give it a try, he'll block you. He's done it 3 times to me so far. This isn't a sockpuppet account, this is me being open about who I am, asking simple questions for the community. He claims censorship left and right and publicly takes pride in being for "free and open speech", so I have no qualms circumventing his choice to block me. The reason I'm showing this information is because what's really interesting to note is **the @bitcoin account blocked me at the same time Roger did**, even though this was a fresh account that never interacted with the @bitcoin twitter. What's even more interesting is, when it became clear that I was going to continue doing this _(high visibility polls that go against their narrative)_, and continue calling out both accounts for simultaneously blocking me, the @bitcoin account announced their "Twitter Blockchain" list, for plausible deniability. They really don't want you ruining their attempt to confuse you.

![](/assets/images/cy17/cy17m12/sad-27.png){: .align-center}

[I'm going to quote myself here:](https://hackernoon.com/thats-not-bitcoin-this-is-bitcoin-95f05a6fd6c2)
> Did you notice the 'Pro Bitcoin Unlimited' tag I have for the user in the old Bitcoin- _XT_ subreddit? Same campaign, different flag: **Take control of the network. Take control of the name Bitcoin.** 

As their ability to take over the network gets further and further away from reality _(you can't take_ **_infrastructure_** _like Lightning nodes and their channel balances with you when you hard fork)_ they focus more and more on the naming conventions, because it's the only thing they have left to try and trick people as the network becomes hardened. They started doing this late last year, _before_ the 2X fork day had passed:

![](/assets/images/cy17/cy17m12/sad-28.png){: .align-center}

Despite this announcement, Roger went ahead and promoted the 2X fork **as well** _(mentioned above)_, because he knew it might have an effect on dividing us. It's only built up since then and the use of the term "Bitcoin Core" has been added into their efforts so they can begin trying to drop "Cash" from BCash. As you can tell by the votes, despite intentionally misleading 800,000 potential voters, most of those that voted know what's going on and aren't having it. You can even replace the names with whatever you want, it doesn't matter:

![](/assets/images/cy17/cy17m12/sad-29.png){: .align-center}
![](/assets/images/cy17/cy17m12/sad-30.png){: .align-center}

None of this stops the attempts, and it seems like doubling down on his actions is all Roger knows how to do. The Bitcoin.com mobile wallet lists BCash first, now no longer creates an actual Bitcoin wallet by default, and his website is now defrauding visitors with the same tactics:

![](/assets/images/cy17/cy17m12/sad-31.png){: .align-center}
_[https://explorer.bitcoin.com/bch](https://explorer.bitcoin.com/bch)_

![](/assets/images/cy17/cy17m12/sad-32.png){: .align-center}
_[https://twitter.com/billsmith4lyfe/status/988803284038172672](https://twitter.com/billsmith4lyfe/status/988803284038172672)_ 

![](/assets/images/cy17/cy17m12/sad-33.png){: .align-center}
_[https://twitter.com/peterktodd/status/988693611943514113](https://twitter.com/peterktodd/status/988693611943514113)_

I have a strong feeling this is all going to come crashing down on him, but until then Bitcoin Jesus will keep on keeping on. He keeps getting interviews with people from outside the space who know nothing about his history or the context of the discussion they're about to have, and he keeps repeating the same-exact-mantra on every single one of them.

"Bitcoin Core is"

* "Slow"
* "Expensive"
* "Unreliable"
* " **Moore's Law means blocks can scale on-chain forever.**"

"Bitcoin Cash is"

* "Fast"
* "Cheap"
* "Reliable"
* "Thanks to **Moore's Law** it will keep scaling."

Watch these interviews _(if you can bear it)_ below and just yell "BINGO" when you hear all four of them get said in each one:

![](/assets/images/cy17/cy17m12/sad-34.png){: .align-center}
![](/assets/images/cy17/cy17m12/sad-35.png){: .align-center}

## Moore's Observation

_I published this section as a standalone piece so it can easily be referenced when someone makes this argument in the future._ [_You can find that here._](https://medium.com/@StopAndDecrypt/moores-observation-35f7b25e5773) 

![](/assets/images/cy17/cy17m12/sad-36.png){: .align-center}
_[https://twitter.com/ELEProbtc/status/963845795140292609](https://twitter.com/ELEProbtc/status/963845795140292609)_

> Moore's law is the observation that the number of [transistors](https://en.wikipedia.org/wiki/Transistor "Transistor")in a dense [integrated circuit](https://en.wikipedia.org/wiki/Integrated_circuit "Integrated circuit")doubles approximately every two years. — Wikipedia 

It's become commonplace to cite Moore's Law when people discuss raising Bitcoin's block size in an attempt to justify why the network can continue scaling this way. In short, the mantra goes something like this:

* Bitcoin has always scaled this way in the past when needed.
* Computers get more powerful all the time, _just look at Moore's Law._
* You don't need to run a node, only miners should decide what code is run.

Notice how the third one has nothing to do with the first two? That's because after you dismiss the claims about Moore's Law they fall back to how you just don't _need_ to run a node, so because you don't need to run one it's okay if they take away your _ability_ to run one. So let's dismiss Moore's Law, and make a solid argument for why being _able_ to run a Bitcoin node is of utmost importance.

1. Moore's Law is a measure of integrated circuit growth rates, which averages to 60% annually. It's not a measure of the average available bandwidth _(which is more important)_.
2. Bandwidth growth rates are slower. Check out [Nielsen's Law](https://www.google.com/search?q=Nielsen%27s+Law). Starting with a 1:1 ratio _(no bottleneck between hardware and bandwidth)_, at 50% growth annually, 10 years of compound growth result's in a ~1:2 ratio. This means bandwidth scales twice as slow in 10 years, 4 times slower in 20 years, 8 times in 40 years, and so on... _(It actually compounds much worse than this, but I'm keeping it simple and it still looks really bad.)_
3. Network **latency**scales slower than bandwidth. This means that as the average bandwidth speeds increase among nodes on the network, block & data propagation speeds do not scale at the same rate.
4. **Larger blocks demand better data propagation _(latency)_ to counter node centralization.**

![](/assets/images/cy17/cy17m12/sad-37.png){: .align-center}
_[https://twitter.com/ELEProbtc/status/963845795140292609](https://twitter.com/ELEProbtc/status/963845795140292609)_

> forever and ever 

...

> 4 times slower in 20 years, 8 times in 40 years, and so on... 

...

![](/assets/images/cy17/cy17m12/sad-38.png){: .align-center}
_Recycling this because it's applicable, and a good meme. I made it myself._

This is not new information either, he's been spouting this misconception for years. **He knows it's not relevant.** Even people who have hopped on the BCash bandwagon after knocking Bitcoin non-stop knew years ago that latency is the issue, but none of this stops this argument from being brought up over and over again. These tweets are from years ago ('15/'16) and the following Reddit post was in April of this year (2018):

![](/assets/images/cy17/cy17m12/sad-39.png){: .align-center}
_[https://twitter.com/adam3us/status/693847158693433344](https://twitter.com/adam3us/status/693847158693433344)_

![](/assets/images/cy17/cy17m12/sad-40.png){: .align-center}
_[https://twitter.com/el33th4xor/status/638399125474684931](https://twitter.com/el33th4xor/status/638399125474684931)_

![](/assets/images/cy17/cy17m12/sad-41.png){: .align-center}
[https://www.reddit.com/r/btc/comments/8e88xu/satoshis_original_whitepaper_talks_about/](https://www.reddit.com/r/btc/comments/8e88xu/satoshis_original_whitepaper_talks_about/) 

It's not about storing those transactions. It's about full-nodes being able to receive the transaction, check the UTXO set to verify the information in the transaction is correct, and consider it valid before sending it off to the next node to do the same. **This takes time.** This delays propagation. Then at some point a miner successfully finds a valid hash for a block and sends that block out to the network, which must then propagate to the nodes on the network and get validated just like all the transactions. There's ways to shortcut this by checking the block against transactions you've already validated, but again it still takes time, and increasing the block size directly effects this process. If you want to increase the block size, put in work that helps offset this issue.

This is real scaling:
![](/assets/images/cy17/cy17m12/sad-42.png){: .align-center}
_[https://www.reddit.com/r/Bitcoin/comments/7x4psl/advances_in_block_propagation_greg_maxwell/](https://www.reddit.com/r/Bitcoin/comments/7x4psl/advances_in_block_propagation_greg_maxwell/)_

So we've established _(again...)_ that all of this is important because of the centralizing effects on full-nodes. Good, now that we've completely dismissed that argument, we can forget it even happened. Why? All that work you put into arguing with someone online over this doesn't matter because:

> You don't need to run a node, only miners should decide what code is run. 

There's only two sides to this debate. "Non-mining" nodes matter, or they don't. Anyone arguing in between these two stances is missing the bigger picture, or knows that arguing the middle ground helps the side you're actually on win the tug of war.

![](/assets/images/cy17/cy17m12/sad-43.png){: .align-center}
_[https://twitter.com/VinnyLingham/status/936271705298812928](https://twitter.com/VinnyLingham/status/936271705298812928)_

...Let's discuss why that's a misunderstanding of the bigger picture, but first go over some simple concepts we should all be able to agree with.

* It's better to overshoot security than it is to undershoot security.
* If a change in consensus results in an increase in the number of individuals with the ability to operate a full node, _ceteris paribus_ **,**the network decentralizes by _some_ value.
* If a change in consensus results in a decrease in the number of individuals with the ability to operate a full node, _ceteris paribus_ **,**the network centralizes by _some_ value.
* Soft-forks are inclusive. Hard-forks are exclusive. Inclusiveness builds a healthy single network, exclusion divides.

Any change you propose that results in someone no longer being able to run their node, and the code they agree upon when they connected to the network, _is a bad thing to do_. You just created an enemy who has the financial incentive to oppose your change, and you downsized the network by _some_ degree. You also established a precedent that disincentivizes others from getting involved because they may fear being disconnected. _(Tangentially, this precedent is one reason why a Proof of Work change is also a bad idea. You're cutting off nodes_ **_and_** _hashpower.)_ 

Additionally, you run the risk of breaking infrastructure that is already in place. Right now this includes services that are dependent on running nodes, current and future services that make use of the Lighting Network, and anything else down the line that **will** get built on top of this network. Lightning is just the beginning. I wouldn't even say the network is secure right now because there's still too much risk of change, and I don't think it will be secure until there is sufficient layering and real-world negative consequences for even _attempting_ to make such a change to the underlying rules.

What do I mean by attempting?

The following is a "TCP segment". You don't have to know what that means, and I don't know much all about it past what I'm about to tell you.

![](/assets/images/cy17/cy17m12/sad-44.png){: .align-center}

> A TCP segment consists of a segment _header_ and a _data_ section. The TCP header contains 10 mandatory fields, and an optional extension field. The data section follows the header. Its contents are the payload data carried for the application. The length of the data section is not specified in the TCP segment header. It can be calculated by subtracting the combined length of the TCP header and the encapsulating IP header from the total IP datagram length (specified in the IP header). — Wikipedia 

Those are consensus rules. The **Internet** consensus rules.

If you change those rules and try to send that data across the Internet using your new rules nothing happens, it's unrecognized. **It's invalid.** 

If you implement network code or hardware that uses different rules, and then connect 2 computers together with those new rules, you just created a new network which is completely incompatible with the rest of the Internet.

If you do this with a datacenter full of new hardware and software, network them all together, and then try to connect to the outside world, nothing happens, _and you just wasted a lot of money and time._ 

If you're the AT&T CEO and you conspire with Verizon to roll out 4G LTE as a hard-fork, you have a few options:

* Surprise everyone, nobody has 4G phones, everyone switches to Sprint, and you lose so much money your mother rejects you as her child.
* Announce a hard-fork date. Everyone laughs at you. You scrub your idea.

In either scenario, if you were the CEO and wanted to do this, y _ou wouldn't even be able to._ If the entire Board of Directors voted yes, you still wouldn't be able to get it done. From your lawyer calling you all idiots down to the engineering group being told that in 6 months they need to offline all of their switches globally, and then subsequently laughing at the memo you just sent them. While just a sample of a much broader analogy I won't be making, **this is what enforced consensus really is.** My 3G phone enforces this consensus just by existing alongside millions of others, and asking the following question just sounds absurd, doesn't it?

> What's the minimum number of phones worldwide to ensure that you have sufficient decentralization? 

**Hard-forks don't happen in real life.** There are just too many layers to the entire system such that going against the grain and _refusing to cooperate with existing infrastructure_ would only result in _you_ getting cut off from the system. Try driving on the opposite side of the road as a _hard rule_. I've done it on an empty road, I've done it to pass slow cars, but actually as a hard rule? Never going back to the normal side? See how long that works out for you. Get back to me with the results.

Bitcoin's consensus security at full scale doesn't come from the amount of "users" running "nodes", it comes from an overall inability to change any old rules from the mining _or_ the client side. How we get to that point or when we get to that point I couldn't tell you, but we will never get to that point with a "hard-forks are okay" mentality, and we will never get to that point with a "miners can dictate consensus freely" mentality, as if the miners ever even had decentralization on their priority list...

## Satoshi Dundee

In an interesting turn of events, disdain has begun brewing within the BCash community surrounding Fake Satoshi _(Craig S Wright)._ Craig is starting to get called out by his own team and I think this is important because it's likely this will result in a perfect example as to why the "hard-forks are okay" mentality is actually not okay. Something that would normally be mundane, like a conflict between a community and a few individuals, would normally just result in those individuals disappearing or being known as "the loud mouths who won't go away". In this community, they have financial influence and control over various aspects of Internet/social platforms, and the potential result is a hard-fork of a multi-billion market cap technology. Sounds great, right?

It actually is. Remember inclusiveness versus exclusiveness? They both compound themselves with each iteration. Every time you try to hard-fork you end up with a minor community on its own that thinks they are all in agreement, until they're not again and _they_ hard-fork...again, and again, and again, splitting them up more and more. Conversely, the soft-fork community continues to build by being inclusive. Never kicking your node off the network, making sure the software you coded doesn't become incompatible, or ensuring the wallet you downloaded doesn't get disabled or confused on what to do or who to follow with each upgrade to the network.

Generally, each client that tried to fork, or proposed a fork for Bitcoin has had a single lead developer behind it:

* Mike Hearn — Bitcoin-XT
* Gavin Andresen — Bitcoin Classic
* Peter Rizun — Bitcoin Unlimited
* Jeff Garzik — 2X _(btc1)_
* Amaury Sechet _(deadalnix)_ — Bitcoin Cash
* Emin Gun Sirer — Bitcoin-NG _(fork proposal for Bitcoin Cash, no client yet)_

Ever since BCash successfully forked off, two of these old clients have been repurposed to be compatible with that chain. Mike, Gavin, and Jeff are gone, although the clients are stringing by, but there are really only three people who have potential influence on the code and direction of BCash at the moment: **Amaury, Peter, and Emin**.

I don't mean to discredit the other developers, but there's only three others that work on Bitcoin Unlimited along with Peter who claims lead as Chief Scientist, and a two developers patch-working XT. Amaury is the only developer committing code to [Bitcoin-ABC](https://github.com/Bitcoin-ABC/bitcoin-abc/graphs/contributors) _(the BCash reference client)_, and has helped repurpose the Bitcoin XT client to be compatible with the upcoming BCash hard-fork. This helps to put on the impression that BCash has "implementation decentralization" and that ABC is not the reference client... **_it is._** 

![](/assets/images/cy17/cy17m12/sad-45.png){: .align-center}

![](/assets/images/cy17/cy17m12/sad-46.png){: .align-center}
_[https://github.com/bitcoinxt/bitcoinxt/graphs/contributors?from=2018-01-01&type=c](https://github.com/bitcoinxt/bitcoinxt/graphs/contributors?from=2018-01-01&type=c)_ 

![](/assets/images/cy17/cy17m12/sad-47.png){: .align-center}
_[https://cash.coin.dance/nodes](https://cash.coin.dance/nodes)_ 

Since no one is actually running XT nodes, this leaves ABC, Unlimited and potentially "NG"in the future. [400 of those Unlimited nodes are fake](https://twitter.com/StopAndDecrypt/status/977240462208720897). Which brings me back to Craig, because **Peter** and **Emin** are the ones publicly calling him out on his bullshit. This leaves **Amaury** _(who has_ [_argued with Craig_](https://twitter.com/ProfFaustus/status/956985145306775553) _and his_ [_sockpuppet Mr. Scatman_](https://twitter.com/StopAndDecrypt/status/918437904069906432) _in the past, as well as having a_ [_history of not seeing eye-to-eye_](https://www.reddit.com/r/btc/comments/7y6rsp/this_is_not_a_healthy_ratio_of_clients/dueatln/) _with other members of that community)_ the eventual choice: Denounce Craig and his proposals, or accept them and implement them. The latter would result in BCash forking into two chains, but the former will result in all the active developers working on BCash shunning Craig, which puts his friend **Roger** in an interesting predicament...

![](/assets/images/cy17/cy17m12/sad-48.png){: .align-center}
![](/assets/images/cy17/cy17m12/sad-50.png){: .align-center}
_[https://twitter.com/StopAndDecrypt/status/988263156517621761](https://twitter.com/StopAndDecrypt/status/988263156517621761)_

Don't believe there's going to be an issue here? nChain, where Craig is deemed the "Chief Scientist", just put out their "[Open Bitcoin Cash License](https://nchain.com/app/uploads/2018/04/nChain-Open-BCH-Licence.pdf) ". Craig's been pretty open about his intent to put out patents for software related to BCash and how they intend on adding features to BCash that you can only use with nChain's permission. I think this short conversation below sums up the issue with that pretty well but hey, just remember that "hard-forks are okay", and all the BCash developers are in agreement. _(They're not.)_ 

![](/assets/images/cy17/cy17m12/sad-51.png){: .align-center}
_[https://www.reddit.com/r/btc/comments/8f1ffv/the_nchain_open_bitcoin_cash_license_pdf/](https://www.reddit.com/r/btc/comments/8f1ffv/the_nchain_open_bitcoin_cash_license_pdf/)_

The outlook doesn't look good for the _"other"_ camp, and they can't say we didn't tell them so. They've latched on to these people because they have money to help push the fork they originally wanted, but now that money is pushing further than they may have wanted and letting go is going to be difficult. If Craig get's pushed out what will Roger do? If Craig & nChain force a fork and Roger backs them, but half their community doesn't want it, what will the other developers do? What happens when nChain starts suing? What happens if the other developers compromise their morals and work with them?

## Conclusion

Consolidating everything above was already a process in itself. I wish I could include more but it would turn this article into what may already look like a Tumblr page. If I had to take everything above, in combination with my prior articles, I'd only conclude with advice for the _genuine_ few of those on the other end of this "debate":

* The BCash community needs to ditch Craig and Roger. If you sincerely believe that bigger blocks are the way, you're _never_ going to get anywhere with them still on your team. Cut the cord, they're legitimately holding you back. The worst part about it? You're going to realize that half of your community/support won't want to. They're too invested and dependent on them to support their claims, but it's something you need to do.

![](/assets/images/cy17/cy17m12/sad-51.png){: .align-center}
_[https://twitter.com/PeterRizun/status/983961846804725761](https://twitter.com/PeterRizun/status/983961846804725761)_

* Rebrand and move forward, it worked for Dash _(formerly DarkCoin)._ Just bite the bullet, because if it's all about Satoshi's Vision it shouldn't matter. Ditch the name game and [the focus on the title of the whitepaper](https://twitter.com/StopAndDecrypt/status/984435036857470978), ditch the infighting, and again, ditch the weight _(Roger)_ on your back that insists on making this the focus of debate.

![](/assets/images/cy17/cy17m12/sad-52.png){: .align-center}
_[https://twitter.com/CryptoCobain/status/963538894959644673](https://twitter.com/CryptoCobain/status/963538894959644673)_

* Give up on the conspiracy theories. I shouldn't even have to get into this but it makes your entire group look like lunatics. If you seriously believe "Bilderberg is behind Blockstream" you really need to watch this video below and reconsider your outlook on life. Stop liking stupid Twitter comments that suggest this idiocy or sharing articles like the one below. If you don't believe the theories, consider not giving voice to those "on your side" that propagate them _(Roger)_.

![](/assets/images/cy17/cy17m12/sad-53.png){: .align-center}
![](/assets/images/cy17/cy17m12/sad-54.png){: .align-center}
![](/assets/images/cy17/cy17m12/sad-55.png){: .align-center}

[**🅂🅃🄾🄿 (@StopAndDecrypt) | Twitter** _The latest Tweets from 🅂🅃🄾🄿 (@StopAndDecrypt). Fullstack Social Engineer: 10% FUD, 20% memes, 15% concentrated..._twitter.com](https://twitter.com/StopAndDecrypt "https://twitter.com/StopAndDecrypt")
