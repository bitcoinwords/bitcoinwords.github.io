---
title: "No, Concentration Among Miners Isn’t Going to Break Bitcoin"
permalink: "/no-concentration-among-miners-isnt-going-to-break-bitcoin"

author: hasu

tags:
  - Hasu
  - CY20 Q1
  - Mining
  - Mining centralization
  - FUD
  - Centralization
  - Mining Concentration

excerpt: Hasu digs into mining centralization. Posted February 20, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [No, Concentration Among Miners Isn’t Going to Break Bitcoin](https://www.coindesk.com/no-concentration-among-miners-isnt-going-to-break-bitcoin)
### By [Hasu](https://twitter.com/hasufl)
### Posted February 20, 2020

## [Part 1](https://www.coindesk.com/no-concentration-among-miners-isnt-going-to-break-bitcoin)
A recent TokenAnalyst [report](https://www.bloomberg.com/news/articles/2020-01-31/bitcoin-s-network-operations-are-controlled-by-five-companies) claims a single entity could be in control of around 50 percent of bitcoin’s hashrate. The observation is based on the fact that five large mining pools have launched a new cloud mining service as a joint venture.

“In 2020, bitcoin has \[...\] become a highly centralized system that places an increasing amount of trust in a small number of large entities. Any centralization of bitcoin network hash power should be of concern as it erodes the trustless model of the network,” TokenAnalyst, a cryptocurrency research firm, says.

Its strong language is consistent with the folk theorem that [bitcoin](https://www.coindesk.com/price/bitcoin) (BTC) relies on the decentralization of hash power to be secure. But is it also correct?

### Concentration is inevitable

It is certainly true that one miner with 100 percent of the hash power would have more control over the network than miners with 10 percent hash power. A majority miner can reorganize the blockchain to double-spend his own transactions or even block any unwanted transactions from making it into the blockchain.

If a majority miner can misbehave and hurt users, does that mean users should try whatever they can to prevent centralization in hash power?

Former Bitcoin Core developer Greg Maxwell sees that as a futile task, [given that](https://www.reddit.com/r/Bitcoin/comments/ddddfl/question_on_the_vulnerability_of_bitcoin/) “\[an attack\] doesn't even depend on a single person having too much of the hash power. The attack would work just as well if there were 100 people each with an equal amount and a majority of them colluded to dishonestly override the result.”

This insight is important because it shows we can not rule out concentration, ever. Miners can always collude with each other and act as a single entity. It would be ludicrous to trust a system that can collapse after a single conference call – that’s all it would take to coordinate the behavior of the largest mining pools. And if miners could make more money by colluding with each other, we should expect that they will.

> RATIONALITY MEANS AGENTS DO WHAT IS BEST FOR THEM, EVEN IF THAT MEANS COLLUDING WITH OTHER MINERS TO ATTACK THE SYSTEM.

And – according to Maxwell – this problem might not have a solution because “any mechanism that would let you prevent one party (much less secret collusion) from having too much authority would almost certainly let you just replace mining entirely.”

So if the concentration of hash power in proof-of-work (PoW), or of stake in proof-of-stake, is inevitable, why am I not worried?

### Concentration is harmless

The answer is that bitcoin’s design doesn’t assume mining power is widely distributed. It’s simply not a requirement. Instead, it only assumes miners are rational, which is something completely different. Rationality means agents do what is best for them, even if that means colluding with other miners to attack the system.

Satoshi addressed this matter directly [in the white paper](https://bitcoin.org/bitcoin.pdf):

> The incentive may help encourage nodes to stay honest. If a greedy attacker is able to assemble more CPU power than all the honest nodes, he would have to choose between using it to defraud people by stealing back his payments, or using it to generate new coins. He ought to find it more profitable to play by the rules, such rules that favor him with more new coins than everyone else combined, than to undermine the system and the validity of his own wealth.

Let’s unpack this a bit. It is the incentive in the form of new coins and transaction fees that motivate the majority to “stay honest.” Satoshi realized the only way to prevent a “greedy attacker” from taking over is to make it more profitable to play by the rules than to attack the system.

This is the key to bitcoin’s assurances and at the same time the most widely misunderstood aspect of bitcoin’s design.

Economist Paul Sztorc even says he is “[most comfortable](https://www.truthcoin.info/blog/mirage-miner-centralization/) just assuming that everyone is always in perfect collusion with everyone else. Specifically, that all of the hash power is actually owned and operated by one guy, whom we might call 'Mr. Greed.' \[...\] Why doesn’t Mr. Greed double spend, you ask? (He can reorganize the chain at any time.) Well, Mr. Greed prefers to keep all of the new coins for himself, rather than undermine the system (and the validity of his own wealth).”

I must admit, I was not comfortable with what I perceived bitcoin’s security model to be initially. If bitcoin were vulnerable the moment a group of colluding miners obtains 51 percent of hash power, how could we possibly monitor – let alone prevent – this? Moreover, why are smaller forks like \[[bitcoin cash](https://www.coindesk.com/price/bitcoin-cash)\] BCH and \[[bitcoin SV](https://www.coindesk.com/price/bitcoin-sv)\] BSV not constantly under attack, given that several individual mining pools in BTC control more hash power than their entire networks?

The dissonance disappeared when I realized that hash power concentration doesn’t actually matter. Bitcoin is secure not because it is impossible to attack, but because it is costly to attack.

### The real cost of attack

The cost of an attack is directly related to how much hash power the attacker owns. That is the key finding of a [paper](https://uncommoncore.co/wp-content/uploads/2019/10/A-model-for-Bitcoins-security-and-the-declining-block-subsidy-v1.06.pdf) I released with Curtis and Prestwich in 2019. In a simplified model, we estimated the present value of all mining operations in bitcoin at around 658,800 BTC or $6 billion at current bitcoin prices. (Consequently, 60 percent of hash power is worth around 395,000 BTC or $3.6 billion, and so on.)

The present value of these miners depends on the value of the network because their future profit is exclusively from block rewards. They are priced in bitcoin’s native token, BTC. If something happened to bitcoin that would make users lose trust in the system, these 658,800 BTC could lose their value in real terms, incurring a large opportunity cost.

Let’s say an attacker with 60 percent hash power decided to attack the network. If the attack depresses the price of bitcoin by only 10 percent, a rather conservative guess, he would lose $360 million in future profit. This is the opportunity cost of his attack.

This number – also called security margin – gives us an idea of how much an attacker has to be able to gain just to break even with his attack. And it does not yet include the ability for the other 40 percent of hash power to push back, or the ability of users to respond with their own nuclear option of changing the PoW algorithm.

The same logic has been replicated in the recent paper “[Too Big to Cheat: Mining Pools' Incentives to Double Spend in Blockchain Based Cryptocurrencies](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3506748)” by Savolainen and Soria. The authors conclude that “the historically observed pool concentration does not indicate a higher risk of double-spending attacks. \[...\] This result demonstrates the well-known economic insight that feasibility does not imply desirability.”

### Takeaways

Mining concentration is inevitable. Mining concentration is also harmless as attacks on bitcoin incur an opportunity cost that scales with the amount of hash power an attacker controls. An attacker with a lot of hash power would incur a large cost.

As a result, the system ensures miners with more control have a stronger vested interest in its protection as well.

_Thanks to their feedback to Su Zhu, Nic Carter, Eric Wall, Mike Co and Loomdart._

# [Part 2 No, Concentration Among Miners Isn’t Going to Break Bitcoin – Part 2](https://blog.deribit.com/insights/no-concentration-among-miners-isnt-going-to-break-bitcoin-part-2/)

**Yesterday I published an [op-ed for CoinDesk](https://www.coindesk.com/no-concentration-among-miners-isnt-going-to-break-bitcoin) arguing that _concentration of hashpower is not going to break Bitcoin_. The reason is that miners who have more power in the network also have more to lose in terms of opportunity cost if they destroy the network or otherwise mess with its operations. (The same argument applies to stakers in PoS).** The article spawned many vivid discussions on Twitter, and I went back and forth talking to different people about it all day. Thanks so much for engaging with the article, it’s really the best thing a writer can hope for. In this follow-up post, I want to take the time and respond to some excellent questions and counterpoints.

### Wouldn’t it be better if hashpower was more distributed?

**Absolutely**. I regret not making that more clear in the article itself, but widely distributed hashpower is strictly better than concentrated hashpower. **Concentrated hashpower just doesn’t break the system**. That’s a big difference. You can think of Bitcoin having different layers of security guarantees, and as you peel them off, the security of the system degrades but doesn’t fall apart immediately. Imagine there are ten miners, each of whom controls ten percent of the hashpower and who never collude with each other, then most attacks are fundamentally impossible. Any attacker would race with a chain that outpaces his own nine to one – a huge uphill battle. That is the best possible scenario for the network. But even if a miner controlled more hashpower than that, Bitcoin has the nice property that the amount of value a miner has at stake scales linearly with his power in the network. So there is still an incentive to be honest because misbehavior is met with a steep penalty. At least as long as the block reward is sufficiently high. Nic Carter [summed that up](https://twitter.com/nic__carter/status/1230505791813275651?s=20) better than I did:

_“Bitcoin consensus is protected, effectively, by two layers of defense._ _**#1** it’s hard to obtain control at the network level_ _**#2** even if you have control, it’s not in your interest to interfere with the network”_

**Many people are not aware the #2 layer even exists, and I want to change that.** Folk wisdom still says that a network becomes insecure the moment a single party controls >50% hashpower. Of course, we would prefer that hashpower is widely distributed, but there’s only so much we can do in that regard without moving away from the idea of a permissionless system.

### If hashpower concentration doesn’t break Bitcoin, why have smaller systems been attacked?

Ethereum Classic and Bitcoin Gold are two examples from the top 50 of crypto assets that have been attacked before, and more than once respectively. The intuitive reaction may be to blame it on the size difference (Bitcoin is 175x larger than ETC and 985x larger than BTG). In my opinion that is not the primary reason these systems are insecure, but their **lack of forced commitment from miners**. It’s no coincidence both systems subscribe to a fallacy called ASIC resistance. The goal behind **ASIC resistance** is to keep mining competitive for hobbyists, which they achieve by using memory-hard hashing algorithms. But the perceived benefits for fairness come with significant downsides for system security. Bitcoin ASICs are so specialized, they are not useful for much else other than mining bitcoin. If Bitcoin ever went away, their market value would drop to zero. Miners in Bitcoin need to own a lot of Bitcoin ASICs, so their balance sheet is **necessarily** tied to the health of the Bitcoin network. GPU miners, on the other hand, are available to hobbyists because they are **not** specialized. Most people have one in their gaming PC and can continue to use them for gaming or mining other GPU coins (or sell them to other gamers or GPU miners). So their value is not tied to the value of a particular coin. Further, because many use cases require GPUs (e.g. machine learning or video processing) there are compute-marketplaces where such general-purpose hardware can be rented. The attacks on ETC and BTG have been executed with such rented hardware, allowing a miner to acquire temporary power over a network without forcing them to enter a long-term commitment to the particular network. So the reason that some smaller coins (but not others) are at risk, is that **miners incur no financial penalty from attacking them** – largely due to the fallacy of ASIC resistance. (Thanks to [Amrit Kumar](https://twitter.com/maqstik/status/1230464897294774273?s=20) for this question.) So Bitcoin miners are financially bound to the network, and attacking the network would be self-destructive. But this leaves wiggle room for a third party to force miners to attack the network against their will, or simply confiscate their equipment in a large-scale operation and use it to attack.

### By coercing miners, couldn’t the Chinese government attack Bitcoin for free?

In practice, I think this is not true because countries, similar to the private sector, **incur an opportunity cost** from attacking Bitcoin. By driving out a profitable industry such as mining, they would **sacrifice future tax revenue**. Bitcoin mining is great for countries with a lot of cheap energy but no way to use it domestically. Previously, aluminum refining has been used for the purpose of de-facto exporting electricity from low-cost countries to high-cost countries. Depending on how a mining crackdown happens, it can also **disrupt faith in local property rights and the rule of law**, which are important drivers of economic prosperity and foreign investment. Finally, no system is secure against an attacker who’s willing to incur an unlimited opportunity cost. If the US or China set their mind to destroying Bitcoin, no matter the cost, then there’s nothing that can be done about it. We can, however, **make it as painful as possible to destroy Bitcoin** by driving up that cost. That is the strongest deterrent we have. Concentration of hashpower may be inevitable unless we start vetting miners (effectively turning the system into a permissioned one), but this raises the question how Bitcoin with a single miner even differs from a centralized company like Paypal.

### Does this “more power, more to lose” argument not equally apply to centralized systems?

Before we start, let me point to the very first answer. We don’t want hashpower to be concentrated, it’s simply not possible to disprove that concentration exists. Don’t assume something you can’t prove, at least directionally! The way mining works, any moment now existing miners could reveal that they have been colluding on a secret chain. And the same applies to an entirely new miner, of course. Models that don’t consider collusion by miners by capping their maximum hashpower are simply not realistic and offer strictly worse security guarantees than models that do. Though I understand that may not necessarily convince you that the huge amounts of electricity we spend on PoW are “worth it” under that assumption. So let me try a different explanation. I will argue that, even as all hashpower is currently controlled by a single miner, Bitcoin still differs significantly from a system like Paypal or a commercial bank. So the worst case is not actually as bad as it may seem.

1.  **Bitcoin is fully auditable with no trust required**. Users can validate that the central miner follows the rules of the network. These validity rules apply to a 100% miner the same way they apply to ten 10% miners. Users can also transparently evaluate the work of that miner. If the miner double-spends or censors transactions, users will be aware of that.
2.  **Users can exit more easily**. Building on the previous idea, if users are unhappy with the work of the current miner, they can simply fire him by collectively forking to a different PoW algorithm. This is significantly easier to coordinate than collectively switching to a Paypal competitor – which may not even exist. All users have read access to the shared state – the UTXO set – making it really easy to take that state and leave if the need arises. If Paypal failed, and someone starts a new one, you would not get your Paypal balance back.
3.  **Governments have less leverage on miners**. Now you might respond that in capitalism, it is rarely the companies itself that hurt users – it’s usually a result of government intervention, whether via direct regulation or indirect pressure to cut off certain people. And I agree that nation-states are the biggest threat for Bitcoin, as they, in turn, see it as a threat to their monetary and fiscal sovereignty. But nation-states have very different leverage over Paypal or a commercial bank than they have over miners. Let’s dissect why:

1.  **Leverage is inversely correlated to mobility**. Someone who can pick up and walk away can not be coerced. This applies to miners! If miners expect the local policy to turn to worse, they can move to a different country with minimal effort. As a result, their leverage over local policy may actually be bigger than vice versa. We see evidence of that with the rise of “special economic zones” for mining in some countries.
2.  **The miner can be replaced**. If the local government “disappeared” the miner, that’s when the free entry to mining matters, as miners in other countries can simply come online and pick up the slacks. So the government must be aware that any shenanigans it can do by confiscating mining hardware, and possibly using it to attack, can only be done once. Finally, a miner can always be disrupted in an organic way by another miner who makes more profit. For example, if the old miner does not process some transactions (censorship), he creates an incentive for a new miner to step in a make more money by processing them.

(Thanks to [Raphael Auer](https://twitter.com/RaphAuer/status/1230579320042770434?s=20), [figo](https://twitter.com/FigoFinozeros/status/1230538832514363393?s=20), and [latetot](https://twitter.com/latetot/status/1230592028523847681?s=20) for asking this question.)

***

{% include signup.md %}