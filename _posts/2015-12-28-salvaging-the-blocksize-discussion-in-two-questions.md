---
title: "Salvaging the Blocksize Discussion, in Two Questions"
permalink: "/salvaging-the-blocksize-discussion-in-two-questions"

author: paulsztorc

tags:
  - Paul Sztorc
  - 2015 Q4
  - Mining
  - Money
  - Politics

excerpt: Salvaging the Blocksize Discussion, in Two Questions. Posted December 28, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Salvaging the Blocksize Discussion, in Two Questions](http://www.truthcoin.info/blog/blocksize-conversation)
### By [Paul Sztorc](https://twitter.com/truthcoin)
### Posted December 28, 2015

> A recipe for productive conversation.

Well, here they are:

#### The Magic Discussion Template

1. “Why do you think we have a blocksize?”
2. “What has changed, between the time that the blocksize was introduced ([July 15th, 2010](http://sourceforge.net/p/bitcoin/code/103/tree/trunk/main.h?diff=515630145fcbc978e39dbaa5:102&diformat=regular)), and today, which motivates us to make a corresponding change in the constraint?”

Now, if everyone just makes an extra effort **not to be a sore winner**, the crisis will be solved!

You’re welcome!

Now, I guess I’ll explain about those two questions in greater detail.

### Motivation and Background

> Because of the way Bitcoin is designed, in-fighting is inevitable. In fact it will be getting worse. Those who understand this problem can, at least, feel better about it.

#### [A Lost Cause](https://en.wikipedia.org/wiki/A_Conflict_of_Visions#The_Constrained_Vision)

I don’t expect this post to help very much. The debate is already over, and everybody lost. We’re [full tribalism](https://www.youtube.com/watch?v=X6WHBO_Qc-Q)* on this issue; anyone who pokes a curious head into the conversation is [mind-killed immediately](http://lesswrong.com/lw/gw/politics_is_the_mindkiller/) and with extreme prejudice.

Nearly everyone is doing exactly those things which should be avoided (assuming bad faith, stonewalling, outright coercion/death-threats). Worst, those who were originally happy to not have an opinion, are now “selecting” an opinion, just to defend their friends and allies.

* I can already see my inbox and comments section filling up with “praise” from people who think that I am in their tribe, and ““criticism”” from people who think that I am not in their tribe. It’s a sad state of affairs.

#### Why Write This?

My only purpose here, is to comfort those who are frustrated. I hope to explain *why* the blocksize conversation is so horrible, and help move it forward.

If you aren’t interested in that, now’s the time to navigate elsewhere.

#### Background: Zero-Sum Games, Software Forks, and Bitcoin

##### Zero-Sum Games

A “zero-sum game” is a term in game-theory, referring to a situation where “you doing well” is indistinguishable from “your opponent doing badly”. Examples include: two guys who are romantically interested in the same girl, two politicians competing for the same office, a race where only one person can come in 1st place, etc. These ZSGs are brutal; your opponent has every reason to try to make you do worse. This permanent, unalterable antagonism can be a very distressing experience. Why - even *your success* is dangerous, as, if you are currently winning, your opponent may become more desperate and more unpredictable.

too funny to print Just axe Leon Trotsky. /*rimshot

##### Software Forks

Open source software is (mostly) liberated from this dark reality, thanks to the ability to ‘fork’ the software. If you don’t like something - anything - you can change it! A fork is the opposite of a zero-sum game: instead of conflict being unavoidable, conflict is completely impossible.

##### Bitcoin

But, here’s the bad news: **Bitcoin’s design does not allow software forks**, at all. It does allow “upgrades”, and we have labeled these upgrades “soft forks” and “hard forks”, but these phrases *do not actually refer to the split of one project into two*. Bitcoin is designed to take many, many, possible forks (one per miner) and use the ‘heaviest chain rule’ to select the - The - single block to be the only valid one. There can’t be two blockchains…by definition. The project can’t split.

If Bitcoin ever did split, for any reason, we’d either have [1] an unexpected and instantaneous doubling of the money supply, or [2] the reversal of an arbitrary subset of transactions. Both are terrible not-Bitcoin-ness.

##### Hard Fork = Conflict

Bitcoin (despite being open source, and despite being on GitHub), is a zero-sum game. XT’s success is Core’s failure. The stakes are high – the two cannot coexist.

[Until we have sidechains, of course.](http://www.truthcoin.info/blog/drivechain/)

#### Background: Why Does Bitcoin Have Limits, Anyway?

To invoke von Mises: “human action is purposeful action”. Why would someone purposefully choose to take an action which limits his/her future actions?

##### A Contract is a Mutual Limitation

Bitcoin is a protocol, or ‘set of rules’. Every ‘rule’ everywhere is, of course, a limitation or constraint. It *harms* our ability to “act purposefully”. This ‘binding’ of everyone in the Bitcoin Network under the same, agreed-upon rules, gives each of us less autonomy (we can each do fewer things); however, we can more easily work *together* (our expectations of others are more reliable). For example, I “give up” my “right” to create 50 million Bitcoin out of thin air, but you give up that right as well. As a result: no counterfeiting.

By definition, every one of Bitcoin’s rules is an inconvenience – something obstructing our *individual* puposeful action! Obviously, we tolerate these inconvenient rules **because they themselves serve some purpose** in helping us work together.

### First Half: What *is* a Blocksize Limit, anyway?

> The biggest stumbling block so far.

It turns out, surprise surprise: people don’t agree on “what a blocksize limit is”.

This is a big problem, because if we can’t talk *about* x at all, then we certainly can’t *use conversation* to compare different versions of x to see which x-version is the best.

boring, belongs elsewhere A general recipe for success, then, would be to: 1. Agree on the definitions (including our definition of "should", ie our "objective"). 2. Agree on the relationship between our defined terms and our objectives. Typically this is done by 'analysis', ie by breaking concepts down into smaller / easier-to-understand (but slower and less-generalizable) sub-concepts. 3. Select the action which most-achieves our objective.

So, below, I present: the **Common Blocksize-Arguments, grouped by Flavor**.

By ‘flavor’, I mean the core assumption of the form “the blocksize exists … [ reasons ]”.

Note: I have changed the word 'Camp' to 'Flavor', because it is more obvious that a person can not be a 'Flavor'. Flavors are for arguments, *Tribes* are for (unlucky) people. Tribes != Flavors == Camps. I regret using the word Camp, as it was unclear, and primed people to react defensively. I have made minor edits (viewable on

GitHub

) to emphasize this difference. It is a confusing topic, because each individual *should* care **most** about one single Flavor, at which point they could be said to be, for example, "in Camp D".

Notice that it is the *arguments* which come in flavors, not their *arguers*. Someone who is particularly unwary might accidentally mix all kinds of Flavors together, unaware of their potential for logical inconsistency. ( This is **not** to be confused with the concept of ‘caution’, where someone is *knowingly* concerned about multiple things at once. )

What is a blocksize limit?

Help me end the madness:

#### Flavor A: It isn’t anything (not anything useful, anyway).

##### Sample Arguments

This flavor includes phrases such as:

* “We must raise the limit, because we are about to hit it!”
* “We don’t have time to try anything else [Lightning Network].”
* “7 transactions per second isn’t enough to compete with VISA!”

As well as:

* “The soft limit imposed by individual miners will work just fine.”
* “The blocksize limit will never be a binding constraint, anyway.”
* “Let the free market (“something else”) determine [transaction fees / the block size].”

It does **not** include an argument of the form:

1. We are about to hit the limit.
2. Hitting the limit is bad.
3. We should *do something* to avoid hitting the limit (options include: rewrite wallet software, warn users, increase limit, …).

##### Implications

Flavor

A necessarily implies that the blocksize limit should be removed altogether.

#### Flavor B - It Stops Validators from Being Robbed by Users

Each Bitcoin transaction needs to be..

* ..routed to all of the full nodes (“validators”) in the network.
* ..independently verified by each full node.
* ..stored forever by each full node.

In other words, Bitcoin transactions aren’t free.

Who should pay for them? Clearly, the user (ie “they who wish to transact”). The problem is that *miners* get 100% of the transaction fees, but do not need to pay all of the bandwidth or storage costs (in fact, [some miners don’t even pay the validation cost](https://bitcoin.org/en/alert/2015-07-04-spv-mining)).

( For Full Nodes, it is actually reversed: they get 0% of the transaction fees, but must pay *all* of these costs! )

##### Sample Arguments

The

Flavor

B arguments include:

* “The number of full nodes has been falling.”
* “It will be too difficult for X to run a full node.”
* “More individuals will resort to light-clients.”

And so forth. It does not necessarily contradict the premise that a blocksize increase could cause a higher quantity full nodes (by, perhaps, causing greater interest in Bitcoin).

##### Implications

This Flavor, to be logically consistent, concludes that the blocksize limit should increase when “running a node” becomes easier. Correspondingly, Flavor B concludes that the limit should *decrease*, when/if running a node becomes too difficult.

It seems that this Flavor’s ideal blocksize limit (IBL) would be primarily driven by the availability of bandwidth, and by improvements in hardware (fiber / CPUs / hard drives) and by improvements in the software which utilizes that hardware.

##### SubFlavor B2 - Selfish mining / block-propagation

This flavor emphasizes the validation performed by miners. Specifically, these arguments emphasize that miners will be unable or unwilling to validate properly (and that this lack-of-validation is bad).

For B2, any technology which improves block propagation (improved bandwidth, the miner relay network, “weak” blocks, IBLTs, …) would favor a higher IBL.

##### SubFlavor B3 - O(n^2) Fundamentalism

The B3 Flavor implies that everyone is running a full node (or needs to be able to do so). From this, it is clear that each new Bitcoin user (n) will receive payments at a full node, and all other nodes (* (n-1)) must also receive, validate, and permanently store the transactions sent to this new node (in contrast to, for example, the lightning network, where this is not a requirement).

Someone invoking B3-flavors, may be interested in new technology (ie, ‘fraud proofs’ enabled by segregated witness, ability to quickly compare reports from different full nodes, resistance to Eclipse attacks, zk-SNARKS) that enables users to trust full nodes which they did not create. However, such individuals may also reject these technologies as insufficient substitutes for a full node.

B3 will always tend to advocate a very low blocksize, as, from principles of mathematics, we know that f(n)=n^2 reacts explosively as n increases. However, individuals can be expected to leave B3 if/when Bitcoin’s adversarial environment changes. For example, if the entire world uses only Bitcoin, few would be interested in attacking it and SPV security would probably be fine.

#### Flavor C - It is a Stabilizer

Some believe that the Blocksize limit removes fluctuations from Bitcoin’s state. This belief is associated with questions like:

* “What would happen to transactions fees in the absence of a blocksize limit?”
* “Without a limit, how will we fund Bitcoin’s security in the future?”
* “When transaction fees dominate the miner reward, how can we ensure that mining continues ‘when the sun is over the Pacific’?”

And tends to be associated with the phrase “constant backlog of transactions”.

##### Implications

A C-Flavor would tend to support a blocksize which slowly and continually increases, until problematic fluctuations arise, or are expected to arise (at which point the limit is halted or decreased).

The IBL of Flavor C would be driven by..

1. ..demand for BTC transactions, (which is in turn driven by “substitutes” [off-chain alternatives, altcoins, …] and “compliments” [SilkRoad, JoyStream, …]).
2. ..improvements the technology which manages payments (fee-aware / fee-minimizing wallet software, lightning network).

As these drivers improve, we can have a higher IBL without the risk of severe fluctuations.

Thus, Flavor C is more focused on the long term, and those who take arguments from Flavor C are likely also to borrow from other Flavors.

#### Flavor D - It represents Decentralization / a Contract (and must be upheld, on Principle).

If Bitcoin’s rules can be changed by someone, then what matters isn’t the rules themselves, but the people who control these rules. Some arguments object to this, implying that things are *inherently better for Bitcoin* if no one is in charge.

For example:

* “People need to change themselves to fit Bitcoin, not the other way around.”
* “It is the policy of X Organization not to support any ‘contentious’ hard fork.”
* “Developers at X are controlled by Y corporation or agents of Z government (and we don’t want them in charge).”
* “We want hard forks to be rare/difficult.”

##### Implications

Flavor D would lose relevance if the decision-making process became more transparent (or longer, and more difficult to subvert), or, perhaps, if Satoshi reappeared (or new info was learned about his design).

However, Flavor D rarely, if ever, allows the blocksize (or anything else about Bitcoin) to change. Perhaps the sole counterexample would be an existential threat: if Litecoin, or Ethereum, ever grew so as to be taken seriously, this might persuade Flavor D aficionados to rethink the relevance of the social contract, and increase the blocksize.

##### SubFlavor D2 - “Moral Hazard” / Antifragility

Some people try to avoid doing things “the easy way”. There’s some wisdom to it: “the crutch begets atrophy”, “comfort is where we stop growing”, “necessity is the mother of invention”, and so forth.

Arguments in D2 ask: would we ever *have heard of* the Lightning Network (or Segregated Witness, …) if the blocksize had simply been raised earlier this summer (as many advocated)? Certainly, as the need for Lightning Network diminishes, it becomes less and less of a development priority (and you become less famous for having invented/worked on it). It is possible, as with the [US Debt Limit](http://cdn.theatlantic.com/static/mt/assets/business/assets_c/2011/04/Debt%20Ceiling%20History-thumb-570x314-49343.png), that the quick-and-easy thing (raising the limit) is consistently chosen over the more-difficult, more fundamental changes.

##### Implications

D2 would want to stall all “easy changes” (of any cost, no matter how small or ambiguous) while: [1] good ideas are still being worked on, [2] good ideas are still being theorized and introduced regularly, and [3] there exists a shortage of good developers.

### Part Two: Using the Blocksize

> If the blocksize acts to help solve problem X, then we simply move the limit up as problem X becomes less relevant, and down as problem X becomes more relevant.

### Relationships Between Concepts If the purpose of 'a jacket' is to keep you warm, then you know that "Do I need my jacket?" and "Do I need to keep warm?" are related. If you don't leave your house, or if the weather outside is already warm, then you don't need the jacket! However, if the purpose of the jacket is because it is a badass leather jacket that makes you look fukin' awesome and women will be falling over themselves to sleep with you if you wear it to a bar, well, then the questions "Do I need my jacket?" and "Do I need to look good?" are related. If you have the flu, or aren't going to a bar, then you might not need the jacket. #### What do you want? It's like any other recipe: if you have [1] the inputs [2] the relationship between the inputs and the output, then, you can swap those inputs for an output!. If you have peanut butter, jelly, bread, a knife, a plate, paper towels, ... and you know what to do, then you can make a pretty mean PB&J sandwich! The blocksize debate is so messy because of [2]. As I mentioned in my Montreal talk, this is often because we haven't even *stated* (let alone *agreed* on) *what the output <b>should</b> be*!

#### Example

[Let’s assume](https://www.reddit.com/r/Bitcoin/comments/3giend/citation_needed_satoshis_reason_for_blocksize/ctygzmi) that Satoshi introduced the blocksize limit “to prevent an attacker from **DoS-attacking** with a large block”.

Well, if that’s true, we would now ask “Is the Bitcoin network still vulnerable to the use of a large block in a DoS-attack?”.

* Since the blocksize served a specific purpose, a statement like “But we are about to hit the limit!” is irrelevant, as is “But we need to fund network security in the future!”. The network is either vulnerable to **DoS-attacks** or it isn’t.

Then, we would continue: “Is the Bitcoin network (effectively) 8 times less-vulnerable today, than it was when Satoshi inserted the limit?” If the answer is yes, then the limit can increase from 1 MB to 8 MB.

* Not only did we settle on a purpose, but, we have an *implied goal*, which is “a network which is resistant to DoS-attacks”. Maybe, you don’t want “a network which is resistant to to DoS-attacks”. Instead, you may want “a high quantity of Bitcoin nodes”. If so, you may reject the above conclusion.

At this point, you may want to begin a new argument. For example: “a larger blocksize may cause more people to be interested in Bitcoin, which will more than offset the decline in some people’s ability to …”

This, however, is precisely what derails the conversation and makes it confusing.

#### Trade-offs

You see, there are some changes which don’t hurt anybody. No one cares about those. They are “uncontroversial”.

However, Actual Important Discussions are always about trade-offs: they help X, by hurting Y.

If you want X, and someone else wants Y, then nothing can really be done. Hopefully, you can both *at least* agree that “pointless argument” is a waste of both of your time, and that you can “agree to disagree”, and that you should peacefully go your separate ways (but…if one of you refuses to drop the argument, you are mortal enemies and one of you will eventually have to violently destroy the other; it is a sad reality of our imperfect universe).

So, if someone wants “a high quantity of Bitcoin nodes” and someone else wants “all Bitcoin nodes to be cheap” and someone else wants “cheap payments” and someone else wants “high transaction fees”, these people really have nothing to say to each other.

Just take out your machine guns and get it over with!

Or, search for common ground: As I presented in Montreal, I suggest that [the Bitcoin Exchange Rate be the common ground](https://www.youtube.com/watch?v=TgjrS-BPWDQ&t=25m53s).

Or, best of all, search for a better way of doing things, one which eliminates the trade-off: the sidechain.

#### Bottlenecks

Nothing prevents someone from using arguments from several Flavors at once (unless they draw from Flavor A, of course). After all, you can wear a leather jacket for more than one reason: to look stylish *and* to stay warm on a cold day.

If two blocksize-purposes are equally relevant, then the blocksize limit can only increase when circumstances have improved in both areas. You’d need it to be a warm-enough day, and you’d need to be not-interested in looking stylish (perhaps because you have the flu or something).

However, at each point in time, we can expect one single constraint to be the most constraining…the “bottleneck” constraint. So, while one can mix flavors, one flavor should dominate. Someone who predominantly uses arguments from a single flavor, for example Flavor D, could be said to be “in Camp D”.

### Final Thoughts

> Politics, the eternal science, the terminal brain-disease to which all eventually succumb.

#### It isn’t a tech problem.

All changes to Bitcoin require carefully-crafted, high quality code…written and reviewed by the best and brightest.

Unfortunately, the problem of the community-wide hard fork concerns two *additional* problems: [1] “how information spreads”, which could be described as “media”, and [2] “how disagreements are resolved” which could be described as ‘governance’. They’re big problems, and there’s no reason to suggest that skilled developers or cryptographers will be any good at solving them.

Fortunately, [I came up with some promising stuff already](http://www.truthcoin.info/blog/win-win-blocksize/)! Sadly, this first solution required [a technique that frequently embarrasses intellectuals](http://0055d26.netsolhost.com/friedman/pdfs/other_commentary/Farmand.02.12.1966.pdf), making it a non-starter among today’s Bitcoin elites.

I anticipated this resistance, and have [an uncensorable version](http://bitcoinhivemind.com/) on the way. It has been primarily delayed, in my view, by the blocksize debate itself (which has derailed progress on sidechains). Once it is on, we shouldn’t need to worry about this.

I’ve also [solved this problem a second time](http://www.truthcoin.info/blog/drivechain/), with the two-way peg. This one is even simpler, and likely to be popular.

#### If You Insist

If you’d rather “talk things out” like some kind of Communist (I am not joking.), well, I can win on that playing field as well (as I’ve tried to demonstrate in this post).

I’d be happy to moderate some kind of debate, [or forum or something](https://www.reddit.com/r/BitcoinHardforks), to facilitate this discussion.

But I’m not sure anyone would *really* be interested. Instead, I think people will just try to capture the forum and [use it to punish the people who insulted them](http://lesswrong.com/lw/gt/a_fable_of_science_and_politics/).

I also doubt that it would really be helpful – if it actually concluded anything, individuals who disagreed would just de-legitimize and ignore it.

After all, I’ve already done this twice before, and no one says “This blocksize controversy sucks, we need to create the two-way peg as fast as possible!”. Instead people start with “That other guy, who insulted me, he can’t get away with this! …how could you side with *them*?!” and cover it up as best they can.

#### More Food for Thought

* In my opinion, Reddit is a highly biased and irrelevant source of information. Reddit manipulation software is cheap, and it can automatically solve captchas, down/upvote, [write sentences](https://wordai.com/), etc. For a single individual to control a supermajority of Reddit votes, probably costs <$100. Moreover, I estimate that /r/bitcoin accounts for a very small percentage of the total Bitcoin community (and this minority tends to be younger and less-educated). What reddit does well, I think, is aggregate and present links to websites which are *not* reddit. Those who make use of this useful feature, usually don’t have accounts on the site, and (unfortunately) don’t participate in the voting-feedback process.
* Its possible that Big Bitcoin CEOs *want* to get users away from running full nodes, and are nefariously supporting bigger blocks (after all, their service competes with node-running). Or, they are merely pandering to potential-customers (ie, the individuals who don’t run nodes).
* Its possible that most Blockstream / Bitcoin Core developers actually are very blocksize-liberal (or don’t care), but the recent gmaxwell smear campaign has reverse-motivated them to close ranks on a consistent message (and/or destroy this Threat to Bitcoin). Similarly, it is possible that BitcoinXT developers are actually blocksize-conservative, but can’t understand theymos / bitcoin.org ‘s arbitrary manipulation of the conversation, and have concluded “anything *that* suspicious has got to be bad”.
* Although Satoshi argued that the limit could (not “should”) be eventually removed, he did made a few claims which he later walked back, and a few which later turned out to be unreasonable. Satoshi himself inserted the blocksize limit, and he did not insert any code phasing this limit out. So his original position is very ambiguous, and I’m sure he would prefer people to stop talking about it.
* In a complex system, it is logically defensible to say “I don’t know what the rule is for, but we should keep it right where it is anyway.” In fact, civilization practically depends on this (namely, our laws).
* People choose to speak up (or not speak up) for many reasons. The result is that determining “what most people think” is very very difficult. My guess is that most individuals, and most Btc, favor a 1 Mb blocksize. Of those people who I’ve physically met, in real life, mostly at Scaling Bitcoin conferences, >50% favored keeping 1 MB blocks for many months
* The process of ‘governance’ is one which answers the timeless question: “How are disputes resolved?”. If we set a bad governance precedent today, where disputes are resolved by a tiny group of people making incomprehensible decisions, or by backroom deals, or by reddit upvotes, we will regret it in the future.

To say that “the conversation is a lost cause”, isn’t to say that Bitcoin is a lost cause, or the blocksize battle itself is a lost cause (for anyone).

In fact, at 9 PM EST today I will drink a toast (you are welcome to join me) – to the Bitcoin software, for lasting this long!

Add Disqus comments.

comments powered by

Disqus

***

{% include signup.md %}
