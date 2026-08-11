---
title: "Against the Hard Fork"
permalink: "/against-the-hard-fork"

author: paulsztorc

tags:
  - Paul Sztorc
  - 2016 Q4
  - Money
  - Technology
  - Security

excerpt: Against the Hard Fork. Posted December 6, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Against the Hard Fork](http://www.truthcoin.info/blog/against-the-hard-fork)
### By [Paul Sztorc](https://twitter.com/truthcoin)
### Posted December 6, 2016

> The hard fork presents tremendous risk to the entire Bitcoin Ecosystem, in exchange for almost no marginal benefit. Instead, use extension blocks or sidechains.

### Intro

#### Overview of Problems

A [Hard Fork](http://www.truthcoin.info/blog/protocol-upgrade-terminology/#solution) is a categorical **replacement** of one protocol with another. When compared to an Alt-chain (an Altcoin or Sidechain), they have a number of obvious problems:

1. They attempt to break an existing contract, and replace it with an “updated” version . The entire purpose of a contract is, of course, that it is binding unless *all* parties agree to update it. However, such an agreement-to-update is often difficult to measure, due to many factors, the most important being the size, heterogeneity and clandestine nature of the Bitcoin Community. Due to monetary network-effects, contracts can be violated, by hard fork, even by [a small minority](https://medium.com/@nntaleb/the-most-intolerant-wins-the-dictatorship-of-the-small-minority-3f1f83ce4e15#.pxzomnaw9) of Community Members.
2. Relatedly, the Hard Fork introduces a non-peer “Authority” to answer the question “Which Bitcoin Network is the Real One?”. This is unambiguously [*not* Peer-to-Peer](http://www.truthcoin.info/blog/measuring-decentralization/#development-100-decentralized-unless-we-hard-fork)! Hence, it is not surprising that the Hard Fork also spits in the face of Nakamoto Consensus, as Satoshi’s Heaviest Chain Rule answers the very same question (and is the entire purpose that the Bitcoin software exists).
3. They reset the clock on the Accumulation of Security. Bitcoin has a chicken-and-egg problem, such that there’s no way to know if something is secure *until* people trust it with large amounts of money.
4. They virtually guarantee that, eventually, Users will have their funds stolen and Developers will be violently coerced.

I’ve [previously written](http://www.truthcoin.info/blog/measuring-decentralization/#hard-and-soft-forks) and [commented](https://medium.com/@octskyward/on-consensus-and-forks-c6a050c792e7#.xcm3u5kl4) about the first two, which (I think) are well known, so this post will focus primarily on the nexus of phenomena supporting #3 and, especially, #4 (which are more novel).

( But, if you blur your eyes, you’ll notice that all four are really the same reason: Satoshi created a [P2P network](http://www.truthcoin.info/images/p2p-misconception.txt) so that there would be no single point of [attack](http://www.truthcoin.info/images/p2p-misconception.txt). )

#### Benefits of Hard Forks

To be fair, I will point out the following advantages of Hard Forks.

* **Less Baggage**: Hard Forks are unambiguously ‘cleaner’ - they accomplish their goal directly and as simply as possible. An excellent metaphor is [the laryngeal nerve of the giraffe](https://www.youtube.com/watch?v=cO1a1Ek-HD0). If nature could ‘hard fork’ it would redesign the nerve, from scratch, to travel in a direct path of 2 inches. However, Mother Nature’s process of Darwinian evolution -being unable to ‘design’- will blindly preserve as much “backwards compatibility” as possible, thematically akin to our ‘soft fork’. As a result, the nerve is longer by a factor of ~140 for no reason; pure inefficiency.
* **More Transparent**: Hard Forks tell a user that they need to upgrade, and how to do so. There is no ‘secret’, behind-the-scenes forced upgrading.
* **More Sovereign**: A user can choose to outright reject a Hard Fork. This is a benefit when the change is bad, but it is also a severe drawback the change is good.
* **More Flexible**: Given that one is starting from scratch, a Hard Forks can be used to do anything. (Again, as many rival cryptosystems have discovered, this flexibility can cause many more problems than it solves. To continue with the biological metaphor, it might be analogous to the fact that over 99.999999% of mutations do *not* cause species-evolution, and instead cause the animal to simply die of cancer.)

In truth, few of these benefits are *marginal* benefits, given that ‘advanced soft forks’ ([extension blocks](https://www.reddit.com/r/Bitcoin/comments/39kqzs/how_about_a_softfork_optin_blocksize_increase/), [sidechains](http://www.truthcoin.info/blog/drivechain/)) can also score very highly on baggage, transparency, sovereignty, and flexibility. And most of the flexibility lost, by downgrading from HF to ASF, is flexibility that no one is interested in pursuing anyway (such as increasing the 21 million coin limit).

In general, such a paltry benefit is not enough to outweigh the tremendous costs, as I will now explain.

> Users don’t care about upgrades, and won’t tell you how little they care. Free work isn’t free, because you have to check it. Some people are un-upgradeable, and their contribution to the network effect might make the entire network un-upgradeable.

Keep these three thoughts in mind, when considering the strategy of protocol upgrades.

#### 1. Upgrade Reluctance

People are reluctant to upgrade their software.

![](/assets/images/2016/m12/against-the-hard-fork1.jpg)

##### Cell Phones

This attitude surprises many developers, but it doesn’t surprise [many](https://discussions.apple.com/thread/7448804?tstart=0) [cell phone users](http://www.forbes.com/sites/davidthier/2016/03/28/app-crashes-why-i-never-upgrade-my-iphones-ios-apple-app-crash/#36029e777786).

Upgrading your phone is tedious, and can often [break things](http://www.inquisitr.com/2769069/how-the-ios-9-update-is-killing-iphone-6-and-6-plus-units/). In return, **the benefits are usually zero** – after all, at any given time, most people are blissfully unaware that updates to their phone are even possible. Life’s serene tranquility is then ambushed by this random box on your phone that won’t go away.

Henry Ford / Steve Jobs can complain that ‘customers don’t know what they want’, but that maxim cuts both ways! How many *current Bitcoin users* were chomping at the bit, to use *RelativeCheckLocktimeVerify* (or even the lightning network, for that matter)?

##### ( Why? )

It is well-known that people have a bias towards the [status quo](https://en.wikipedia.org/wiki/Status_quo_bias). This is probably because [thinking consumes](https://en.wikipedia.org/wiki/Cognitive_miser#The_cognitive_miser_theory) [scarce biological resources](http://www.statisticbrain.com/human-brain-statistics/). Secondly, it is known that humans have a [loss aversion](https://en.wikipedia.org/wiki/Loss_aversion) bias. One synthesis of these phenomena, is to point out that ‘ignoring gains’ is free, but ‘ignoring losses’ is impossible – losses *might* require you to rewrite [your whole plan](http://www.mactrast.com/wp-content/uploads/2011/06/3.iCloud-it-just-works.png). And they therefore require some of your ([scarce](http://i.imgur.com/OTfytjA.jpg)) attention.

##### Upgrades Suck

The point is that upgrades suck. They can break your workflow in all kinds of ways!

![](/assets/images/2016/m12/against-the-hard-fork2.png)

For most people, it is rational to just avoid the whole upgrade process. And it is *most rational of all*, for these users **not to tell developers** how little they care about the incredibly sexy world or ‘version numbering’ and ‘release notes’. Upgrading will always be an uphill battle, and it will always be more-uphill than expected.

#### 2. The Cost of Free Work

Imagine that you need to hire someone for a job. (And conversely, recall your first job search). Who should you hire (how do you get hired)?

You do not care about how hard your employee works. He may produce something you ultimately cannot use, or never wanted. Conversely: people do not care how hard you work. Many toil in the farmlands, or construction sites, and their relative prosperity is low – they are out-earned by sloths residing in comfy offices.

Clearly you need an employee who produces something valuable – something you value. And, relatedly, their paychecks must sum to a cost that is less than the value they produce for you. The employee must be profitable.

But, even now, you face [a critical problem](https://en.wikipedia.org/wiki/Principal%E2%80%93agent_problem): checking the quality of your employee’s work. Assume the following: [1] a job takes 1 hour, [2] your time is worth 10 $/hr, and [3] you can hire someone to do this job in 2 hours at 3 $/hr. By hiring, you would be up +$4 ( = $10 - (2 * $3)). However, if it takes you 30 minutes to *check* your employee’s work, you have lost an additional $5 and are now at a net -$1.

Worse, your efforts to check your employee’s work might fail. Your employee might even hide something, and your hard-earned reputation might be damaged or destroyed.

![](/assets/images/2016/m12/against-the-hard-fork3.jpg)

Because work can’t be *checked* for free, **even ‘free’ work can *easily* cost you a fortune**.

Hiring is expensive! (This explains why, in our world, there’s simultaneously [1] plenty of work to do, and [2] many people who are willing to work, but can’t find a job.)

#### 3. Coordination and Ambiguity

##### a. March 2013

Consider [this writeup of Bitcoin’s March 2013 emergency](https://freedom-to-tinker.com/2015/07/28/analyzing-the-2013-bitcoin-fork-centralized-decision-making-saved-the-day/).

I agree that this case can help us understand Bitcoin Upgrades. I don’t agree that: “Without the central co-ordination of the Bitcoin Core developers and the strong trust that the community places in them, it is inconceivable that adopting this counterintuitive solution could have been successfully accomplished”, however.

In fact, it is *because* the Core developers were unable to coordinate, and *because* they were **not** able to convince (ie “get”) the community, that the (supposedly “counterintuitive”) solution would have *inevitably* manifest itself.

That said, the CoreDevs did minimize the damage. And you can’t knock that response time.

##### b. The Power of Being Unable

[Taleb recently noted](https://medium.com/@nntaleb/the-most-intolerant-wins-the-dictatorship-of-the-small-minority-3f1f83ce4e15#.vj521uua5) that certain conditions would produce a ‘tyranny of the minority’. network effects would allow the most intolerant person to win.

This would not have surprised [Tom Schelling, who noted](http://userpages.umbc.edu/~nmiller/POLI388/BARGAINING.TCS.pdf) in 1956 that the **most constrained** (ie, most intolerant) person would always hold a brutal negotiating advantage. Your boss and you agree that you are worth between $10 and $20 an hour – the smartest thing is to say “I **cannot** accept less than $20”, and to back-that-up by fastening on a collar that explodes if you indeed get <$20.

( Both pieces of writing are of superb quality. )

##### c. A Good Night’s Sleep

The central question of March 2013 was: “how do we re-merge the fork”, and the most relevant fact, in answering it, was the following:

```
23:30 Pieter Wuille: and we _cannot_ get every bitcoin user in the world
```

This outright disqualifies the “everyone upgrades” strategy – the “un-get-ables” are wearing explosive collars. By process of elimination, this leaves only the “everyone downgrades”. It is the kind of thing that is, apparently, “counterintuitive” to computer scientists; in [my experience](http://www.truthcoin.info/images/bitcoin-ng.txt), [game theory is not part of the CS curriculum](https://www.youtube.com/embed/91TufmffIDg?start=610&end=990&rel=0&autoplay=1).

The blockchain allows users to coordinate on a single network (by using a simple ‘heaviest valid chain’ rule, that a computer can automatically calculate). Schelling would say that successful coordination requires participants to read a ‘common signal’ from the situation itself (not [from each other](https://en.wikipedia.org/wiki/Cheap_talk)). Some participants will never get an ‘upgrade signal’, and some will ignore a signal they do get, and a third group will [actively fight the upgrade](http://trilema.com/2015/if-you-go-on-a-bitcoin-fork-irrespective-which-scammer-proposes-it-you-will-lose-your-bitcoins/).

Anyone concerned with ‘being on the wrong network’ would, inevitably, reach the same conclusion as Pieter Wuille: the downgrade would win. In any situation of ‘motivated ambiguity’, the downgrade will probably always win. Worse, this conclusion has momentum – the cleverer individuals would realize sooner, thus transmuting an initially-ambiguous situation into a ha-ha-losers-sorry-for-your-loss cutthroat meritocracy.

The Devs did minimize the transition period, however, which minimized the collateral damage.

Conclusion: Each of these three points favors the soft fork over the hard fork.

##### Footnote: Hashpower as an Upgrade Coordinator

Many argue that hashpower will provide the common signal (dooming the less-heavy chain to extinction).

This argument has many points in its favor: Hashrate is a good barometer of health (a neglected chain *cannot* proceed), and it is globally-available to all decision-makers (and this is [common](https://en.wikipedia.org/wiki/Common_knowledge_%28logic&29https://en.wikipedia.org/wiki/Common_knowledge_%28logic%29)).

However, the argument suffers, because of the inherent reactiveness of mining. First, notice that [1] there is an infinite number of hard-fork-paths forward, from any given block, and no objective criteria with which to disqualify any of them. The decision to bless one of them with hashpower, is, therefore, inherently both arbitrary and reversible. Second, notice that [2] if [investors support one chain](http://nakamotoinstitute.org/mempool/who-controls-bitcoin/), this [financial support will necessarily attract hashpower to the chain](https://www.youtube.com/embed/91TufmffIDg?start=1462&end=1810&rel=0&autoplay=1).

So, any decisions the miner makes can-and-will be reversed by investors. Hashrate would coordinate more-effectively, if Hashers could prove that they were **unable** to **ever** support a chain. Since they cannot prove this, the metric is flaky.

### The Game Theory of Bitcoin Upgrades

> Bitcoin’s Upgrades are safe, because they are optional.

#### Upgrade Model

Here is a simple game, where:

1. An update, which is one of two types (‘vulnerable’, or ‘not vulnerable’) is proposed,
2. Row Player decides whether to ‘upgrade’ or ‘not’,
3. Column player decides whether to ‘attack’ or ‘not’.

The Column Player knows [1] if attack is possible, and [2] how to attack (and can attack for free). The Row player bears an ‘investigation cost’ of “a” – it costs Row a units, to learn the update’s type.

```
        Payoff Matrix                      Interpretation
 
           |Attack | Don't |                |Attack  | Don't  |
 ---------------------------      -----------------------------
 Do        |     0 |     0 |      Do        |nothing |nothing |
 Nothing   | 0     | 0     |      Nothing   |happens |happens |
 ---------------------------      -----------------------------
 Check     |    -2 |     1 |      Check     |attack  |user    |
 First     |-a     | 3-a   |      First     |thwarted|paranoia|
 ---------------------------      -----------------------------
 Upgrade   |     4 |     1 |      Upgrade   |attacker| lucky  |
 w/o Check |-10    | 3     |      w/o Check |  wins! | user   |
----------------------------     ------------------------------
```

If the user declines to update, nothing changes (hence the zero payoffs). The attacker (left Column) prefers to succeed in his attack, scoring 4 if he can trick Row into upgrading. If the attack fails, the attacker is embarrassed and loses 2. Nice devs (right Column) score 1 if their good upgrades are installed. Row Player prefers to upgrade (scoring 3), but loses 10 if installs an Attack. Row must pay ‘a’ to learn the state of the upgrade (‘vulnerable’ or ‘not vulnerable’).

#### Equilibria of Game

For a>0, there is a Nash Equilibrium at { Do Nothing, Attack }, and when a=0 there is a second equilibrium at { Check First, Don’t Attack }.

![](/assets/images/2016/m12/against-the-hard-fork4.jpg)

When a is high, upgrades are very unsafe. However, when a=zero, everything changes. Not only is the new equilibrium {3,1} a Pareto improvement over the old {0,0} one, but, by [forward induction](https://www.youtube.com/watch?v=3Ql3rP4L2T4), we can assume that, if Column Player bothers to propose a software update, he is avoiding the { Do Nothing, Attack } equilibrium.

#### When is a=0 ?

Some people derive great pride and personal satisfaction from contributing to Free Software. Thus, for them, “a” may be zero or even negative.

If we discuss hard forks, the conversation ends with this tiny minority (<0.1%) of people. But what about mainstream users, who are accustomed to secure, high quality software, but who are completely unfamiliar with terms like “gitian”, “checksum”, “binaries”, etc? What’s the plan for reaching *those* users? Is there a plan?

Well, with soft forks, everyone (even grandma) can use “indirect evidence” to lower their a to zero. Simply, they wait for other people to install and use the software, while keeping an ear open in case anyone sounds the alarm. **By being slow to upgrade, they can “check” the software for free**. The more technically-illiterate users can simply choose a longer update-lag-time.

Soft forks “flip” the process of validating the new code – users can assume the code is bad, and falsify that hypothesis by watching their friends. It also “flips” the cost – with a hard fork, users must “pay” to validate the software,

### Who Protects The Developers?

> If Devs commit to a policy of Soft Forks, then an attacker gains nothing by coercing them.

A world of Hard Forks is a DevoCracy – whoever controls the devs, controls the software.

A world of Soft Forks is…what exactly? Our model (above), applies *regardless* of how many attacks are attempted by evil devs. Whether all the proposed updates are malicious, or none of them are, the process above will passively filter out all attacks (thus making each individual attack pointless).

The converse is true: if we *lack* a process for filtering out Dev-misbehavior, then there **is** a reason to attack.

The crucial point: **Dev’s inability to do harm is also their inability to be intimidated**.

Of course, such immunity is far from perfect. Historically, there *has* unfortunately been some intimidation of Devs, and more than a fair share of stress. But it is noteworthy that, for an enterprise of this size (billions of dollars) and quality (constant dark net criminal activity, scams, fraud, and misrepresentation, little/no identify verification or background checking) the harassment of developers has been so minimal. There has been some doxxing, and “mean comments on the internet”, and [this post](http://trilema.com/2015/theres-a-one-bitcoin-reward-for-the-death-of-pieter-wuille-details-below/) which I’m 95% certain is merely [a complex pun on Bitcoin’s concept of “verifiable”](http://trilema.com/2015/theres-a-one-bitcoin-reward-for-the-death-of-pieter-wuille-details-below/#comment-116089).

In fact, the [most threating thing to happen so far](http://www.truthcoin.info/images/jeremy-rubin-affair.txt), was not an attack on Bitcoin itself, and merely an example of the complete technical incompetence of today’s prosecutors, and their pedophilic obsession with a completely inert demo of an opt-in browser plugin.

I attribute this relatively continuous pacifism to our commitment to soft forks (notice: we have never actually hardforked). In other words, I attribute safety of the Bitcoin Developers and Researchers to the fact that we don’t actually control who gets paid. We cannot undo payments, reset passwords, etc. We can’t do any of that.

![](/assets/images/2016/m12/against-the-hard-fork5.png)

( Finally, consider the process of Mining: it not only discourages attackers from rewriting the chain, but also divorces *any individual* from the issuance process – this means that, if an attacker wanted to obtain newly-issued coins, there is no one for him to extort. )

### Supposed Counterexamples

Many readers will notice that Ethereum has hard-forked several times. BitShares also [hard-forked many times](https://bitsharestalk.org/index.php?topic=5381.0). And so has **everything**, really – VISA, SWIFT, Google, and so forth.

If hard forks appear in the wild, why can’t we conclude that they’re safe for Bitcoin?

#### 1. Jumping the Gun

One large piece of this puzzle is that these protocols were released too soon. In [the design state](http://www.truthcoin.info/images/vitalik-research-project.jpg), the protocol ‘hard forks’ innumerable times, in the mind of the designer. This is a normal part of the creative process – surely, [Satoshi revised his Bitcoin design in many ‘hard fork’ ways](http://satoshi.nakamotoinstitute.org/posts/bitcointalk/127/) before finally presenting the finished project. In contrast, **the Altcoin Community consistently releases too early**, because of the tremendous “FOMO effect” where projects scramble to grab anyone who is interested and has initiative.

( Note: This, in turn, results from the fact that there is no acceptable way to short bad ideas [[yet](http://bitcoinhivemind.com/)]. If we could short bad ideas, anyone who invested in them would be punished immediately, and capital would be diverted away from these malinvestments, toward productive activities. However, since malinvestments don’t die immediately, we have to endure this annoying pump-and-dump parade. )

#### 2. Product Differentiation

Secondly, the willingness to hard fork is an opportunity for Eth / BTS to distinguish themselves from Bitcoin. Bitcoin Unlimited behaves the same way, [priding itself on a willingness to hard fork](https://bitco.in/forum/threads/buip039-upgrade-via-extension-point.1641/) and on a general atmosphere of [flexibility, adaptability, and hospitality](https://www.bitcoinunlimited.info/articles). This is not so much “a hard fork” as much as it is an advertisement for centralization.

![](/assets/images/2016/m12/against-the-hard-fork6.png)

Above: Vitalik cites the blocksize debate as a negative for Bitcoin. While the debate can be annoying at times, [most people are *generally* happy that a debate is required](http://coinjournal.net/mits-cory-fields-contentiousness-in-bitcoin-is-sign-of-good-health/) to change the rules (and happy that the eventually-agreed-upon rules are enforced [as written](https://daohub.org/explainer.html)).

In keeping with this emphasis-on-flexibility, once Ethereum [hard-forked for an arbitrary reason](http://nakamotoinstitute.org/mempool/who-controls-ethereum/), despite the fact that many users decline to consent to the fork. When the chain split, ~90% of the project wealth stayed on Vitalik’s chain, which would seem to indicate that the fork had, relatively, succeeded.

But I see this as a reiteration of Reason 2. Ethereum desired to compete with Bitcoin, and to do that it wanted to be “the adaptive one”. In my opinion, Ethereum is not actually a computer network. To the extent that its owners have an investment thesis at all, they are [betting that cult-of-personality that is Vitalik Buterin](https://twitter.com/derosetech/status/755910174229934080) will exploit a second-mover-advantage to skillfully maneuver Ethereum into replacing Bitcoin.

### Conclusion

The hard fork is unacceptable in many ways – it breaks Bitcoin’s contract, risks user’s funds, and puts developers in danger.

This isn’t to say that we should *never* Hard Fork, ever – it may be appropriate when we have absolutely no other alternative.

Fortunately, everything you’d need to use a Hard Fork for, you can do with [sidechains](http://www.truthcoin.info/blog/drivechain/) or [extension blocks](https://www.reddit.com/r/Bitcoin/comments/39kqzs/how_about_a_softfork_optin_blocksize_increase/).

Cutting Room Floor Morgoth can explain all of this to you: But ever the Noldor feared most the treachery of those of their own kin, who had been thralls in Angband; for Morgoth used some of these for his evil purposes, and feigning to give them liberty sent them abroad, but their wills were chained to his, and they strayed only to come back to him again. Therefore **if any of his captives escaped in truth**, and returned to their own people, **they had little welcome, and wandered alone outlawed and desperate.** - J.R.R Tolkien, [The Silmarillion](http://www.ae-lib.org.ua/texts-c/tolkien__the_silmarillion__en.htm) Something tells me that Richard Stallman is a Soft Fork kind of guy. Even more interesting, killing / coercing CoreDevs , what does it accomplish ? We can return to our game three diagram .. ~~draw game tree~~ .. compare SoftWorld to HardWorld Trust a group of bankers / regulators / politicians / experts / CoreDevs, or Verify Everything Yourself. The implausibility of stealing, itself creates trust. It also alters the decision calculus of Bitcoins adversaries. If all upgrades are to be soft forks, there is nothing to be gained by, say, threatening to murder a CoreDev's family. Pareto Improvement -- unintentional ways of breaking critical workflow -- wielding the ability to 'pick winners and losers' is a dangerous obliteration of Bitcoin's raison d etre SegWit was an improvement on Bitcoin's design. solve malleability, it also allowed us to observe that the blockchain actually stores two classes of data -- public txn ID and private sig data. More efficient use. Was nonethless a new design. A *literal* requirement, to upgrade. Vs. the possibility of a practical requirement, to upgrade. Hard fork creates a new thing. Soft fork is a filtration -- this filtration can removal of bugs, or it can just remove everything. ### The Open Loop Hard fork is de-facto incompatible. Meaning that, to maintain compatibility, software itself is not sufficient. The Bitcoin software, acting alone, is *literally unable* to maintain consensus across multiple hard forks. Bitcoin Unlimited might be an instructive example here. BU creates a new system where one rule, the 1 MB limit, is removed, and consensus is maintained with proof-of-work alone. But the point is that this *new* system is incompatible with the existing system. After BU, someone could This drastically changes Bitcoin's threat model. ---- Ideally, a dropdown menu ------ Often, users do not want to have the ability to do know, or do, something. For example: * The convenience store safes, and stickers which say "Time-locked safe. Cashier cannot open store safe". THis prevents cashiers from being coerced. * A landlord who suspects his tennant of running a (lucrative) drug operation. If he 'knows', he is obliged to report it to the police, but if he merely 'suspects' he can collect the rent on time (and, perhaps, increase the rent). The landlord may prefer to be strategically blind or deaf. * Supposedly, a law was passed in ancient England, which put to death any individual who paid a ransom. This removed the ability to pay ransoms, which made kidnappping pointless. (The phrase "we don't negotiate with terrorists" attempts to invoke a version of this.) ---- Signaling Stubbornness What is better: stubborn or accomodating? If we are unsatisfied, we want to change something. This makes stubborn bad. But is 'accomodating' really much better? #### Gym Metaphor Say there are two Health Gyms in your neighborhood: Old Reliable and Nueva Du Jour. In OR, all of the equipment is bolted to the ground, but in NDJ, you are allowed to move the equipment around, and put it in-and-out of rooms and closets. You see, people go to GYMs for different reasons: to lose weight, to bulk up, to meet like-minded people, to take classes, to flirt, and to spend time with their friends. Some people go, it seems, solely to jusify the money they already spent on the membership. You might prefer to have all the freeweights on the main floor -- you can do your lifting, with lifting buddies, and not be distracted. Do you sign up at OR, or at NDJ? If you choose NDJ, you can move all the freeweights. Then they'll be right where you want them...for the present. Next week, you may arrive at the GYM to find that they have been moved to the closet. #### Investor Sovereignty One's choice of gym may be a matter of preference. But, when it comes to investments, NDJ is outright unacceptable. The investor is the one who researches the choices, and selects the one which is best for him. The 'flexibility' advertised by projects such as Ethereum, is a double-edged sword. It is as helpful today, as it is anti-helpful tomorrow. And by being inconsistent it contradicts the purpose of an investment. --- ### People Hate To Upgrade Core slack "it puzzles me why so many people and companies are anti software upgrade". To users, computer science is as incomprehensible. Even for programmers, reading code is as much work as is writing it, if not more. The upgrade might as well steal all of their BTC, keylog everything, hack all of their email, automatically scan all their emails for online accounts, reset all passwords, and hack into all of those. It could just cause their computer to melt, as far as they know. ~3 doors - upgrade 1 2 3 ~ The only **real** way to know that an upgrade isn't compromised is to take your time. ~sequence -- you first~ ----------------------------- Stability - can make plans accordingly If soft fork world, those plans will involve innovation, research, the creation of new products, technologies, and business models. In hard fork world, those plans might be the same. However, there is a real risk that they involve a lot of whining, campaigning, and coercion of prominent developers or community leaders. ## Two Worlds Soft -- someone can archive and circulate the old software, and it will continue to work, continue to allow you to send money. Once you make a contract, by depositing your fiat "into" BTC, the contract will be honored. Join today, and you're in the club forever. Your membership never expires. Hard -- you wake up from a coma, and Group Alpha tells you that Alpha is the correct Bitcoin software to install, and Group Omega tells you that Omega is the correct software. How do you decide? You have lost the protection of the 'longest chain rule'. (You still have your money, yes, but is it still as ) Even if you avoid comas diligently, the fact remains that you must expend effort, maintaining your software. You are obligated to check everything for exploits, bias/coercion of the developers, etc. This maintenance is just too expensive -- it makes running a node very very expensive. Bank of America maintains its own software for free, and they always refund you if they ever make any mistakes. ------------------- ### Practice Paradox backhand practice, use it less shield-aiming ---} weakest link If we shorten our walls, we will be safe. The enemy is not attacking our gate, we do not need to guard it. ### Truth Settlement Vitalik's Conflation ---} certainty on Linux kernel, principles of software-use, all hardware, laws of physics, axioms of logic, etc. Certainty on these accrues over time, and can be re-applied. I have never seen my Linux kernel malfunction, and why would this time be different? The rules of tennis are a subset of the laws of physics -- a "soft fork" of them, if you will. ##### Conclusion

Add Disqus comments.

comments powered by

Disqus

***

{% include signup.md %}
