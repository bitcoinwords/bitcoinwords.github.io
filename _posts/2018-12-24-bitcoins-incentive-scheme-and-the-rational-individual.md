---
title: "Bitcoin's Incentive Scheme and the Rational Individual"
permalink: "/bitcoins-incentive-scheme-and-the-rational-individual" 

tags:
  - CY18 Q4
  - Hugo Nguyen

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---

# [Bitcoin's Incentive Scheme and the Rational Individual](https://medium.com/@hugonguyen/bitcoins-incentive-scheme-and-the-rational-individual-dc20effa4715)
### By [Hugo Nguyen](https://medium.com/@hugonguyen)
### December 24, 2018

**This is Part 4 of a 5 part series**
* [Part 1 - The Anatomy of Proof-of-Work](https://cryptowords.github.io/the-anatomy-of-proof-of-work)
* [Part 2 - Bitcoin, Chance and Randomness](https://cryptowords.github.io/bitcoin-chance-and-randomness)
* [Part 3 - How Cryptography Redefines Private Property](https://cryptowords.github.io/how-cryptography-redefines-private-property)
* [Part 4 - Bitcoin's Incentive Scheme and the Rational Individual](https://cryptowords.github.io/bitcoins-incentive-scheme-and-the-rational-individual)
* [Part 5 - Bitcoin: Two Parts Math, One Part Biology](https://cryptowords.github.io/bitcoin-two-parts-math-one-part-biology)

<br>

***

![carrot on a stick](/assets/images/cy18/cy18q4m12/hugo-1.png){: .align-center}

Unlike Proof-of-Work and Public-Key Cryptography, the third component of Bitcoin is not based on math, but human behavior. Specifically, Bitcoin relies on a system of financial incentives and people chasing these incentives to sustain itself.

That sounds a bit scary, and a sharp shift from the strong mathematical foundation that underlies most modern technologies, such as the computer or artificial intelligence. If we have learned anything from history, it is that humans are not always predictable. We are, after all, biological creatures made up of "wet" matter. We're not like "dry", cold-hearted machines who can calculate things accurately or consistently. We change our mind in a heartbeat. Not only that, we constantly bicker, and hardly seem to be able to agree on anything.

So **how can we create a technology out of fickle human behavior?** Bitcoin's 10-year track record is evidence that perhaps we can, and this aspect of Bitcoin is as innovative as the novel uses of Proof-of-Work and Public-Key Cryptography, which we explored in-depth in the first 3 parts of the series.

Bitcoin's incentive scheme relies on the assumption that people are _rational_ actors. If people are rational, they would be incentivized to participate in mining, buying and holding Bitcoin. The concept of rationality is incredibly important, but often taken for granted, so it's worth a background discussion.

### Economic Rationality

In economics, the definition of [rationality](https://www.britannica.com/topic/economic-rationality), or the _economically-rational individual_, has been a topic of great debate, and economists still disagree on the precise definition. At the heart of economic rationality however is the central premise that individuals act to maximize their expected utility. That is, when presented with several choices, individuals will choose the one that they think will make them the happiest, i.e., maximizing net benefit, which is equal to total benefits minus total costs. This is known as the [Expected Utility Theory](https://en.wikipedia.org/wiki/Expected_utility_theory).

Gabriel Cramer and Daniel Bernoulli gave birth to the idea in the 18th century, and it gained in importance as time went by. Nowadays, Expected Utility Theory dominates the field of economics and is widely used in many economic models and real-life policies.

Towards the later half of the 20th century however, doubts started to creep in: do people actually behave like economically-rational individuals, as described by the Expected Utility Theory?

When the choices and consequences are clear and measurable, we have little problem in making optimal decisions. But when the choices are complex, consequences less clear, less measurable, we can be wildly off the mark. And real-world situations are typically of the latter type. So perhaps humans are rational, but due to limited information and our own cognitive limitations, we can only be rational up to a certain point.

Put another way, humans are only rational when the math involved is relatively simple. This is the idea of "[bounded rationality](https://en.wikipedia.org/wiki/Bounded_rationality)", which Herbert Simon introduced in 1950s.

Going further, Daniel Kahneman and Amos Tversky, observing that irrational behavior is actually quite common and non-random, created what they termed the [Prospect Theory](https://en.wikipedia.org/wiki/Prospect_theory) in their [seminal paper](https://scholar.princeton.edu/sites/default/files/kahneman/files/prospect_theory.pdf) in 1979. Prospect Theory describes several systemic biases — such as [loss aversion](https://en.wikipedia.org/wiki/Loss_aversion) — in human behavior, which often cause us to act irrationally.

Prospect Theory became the foundation of the new field of Behavioral Economics. It also started a movement towards a better way of doing economics: theories that are based less on abstract, [normative](https://plato.stanford.edu/entries/rationality-normative-utility) ideas, and more on hard evidence and data.

### Rational Behavior: Biological Roots

> "We are survival machines — robot vehicles blindly programmed to preserve the selfish molecules known as genes."
"Prediction in a complex world is a chancy business. Every decision that a survival machine takes is a gamble, and **it is the business of genes to program brains in advance so that on average they take decisions that pay off**. The currency used in the casino of evolution is survival, strictly gene survival, but for many purposes individual survival is a reasonable approximation." — Richard Dawkins [1]

Rationality might also have roots in biology, especially if you view survival of the fittest as competition at the gene level and not at the individual level [2]. This is also known as the [Selfish Gene Theory](https://en.wikipedia.org/wiki/Gene-centered_view_of_evolution), developed by John Maynard Smith, W.D. Hamilton and Richard Dawkins, among others. The Selfish Gene Theory postulates that DNA is the main means of information transfer between generations and over time, populations will move towards [evolutionarily stable strategy](https://en.wikipedia.org/wiki/Evolutionarily_stable_strategy).

Because the world has very limited amount of resources and because each of us is wired biologically to survive and pass on our genes, we are bound to compete for these resources. That means that all else being equal:

* When the opportunity to extract gains (material or non-material) presents itself, our default mode of behavior is to take it to maximize our chance of survival, in the face of future uncertainty.
* When two or more such opportunities arise, we will take the one that gives us more gains, provided that the gains can be accurately measured. Again, this is so that we maximize our chance of survival, in the face of future uncertainty.

This is similar to Expected Utility Theory, only rephrased from the evolutionary standpoint.

In reality, measurement of gains are subjective and only transferable between individuals under a common Unit-of-Measurement (UoM), such as prices in dollar or gold. In the case of [Prisoners' Dilemma](https://en.wikipedia.org/wiki/Prisoner%27s_dilemma) for example, the UoM is the number of years in prison. Difficulty arises when there is no consistent UoM or UoMs are not easily convertible, e.g., how much money is worth staying one year in prison?

So rationality, even if coded at the gene level, is likely very rough heuristics. Genes, after all, can't make worldly information suddenly more available, or reduce the complex math inherent in the natural world. But genes can ensure a basic high-winning-percentage strategy: to program us to take resources in a resource-constrained world. You might end up taking more than you need, but it is better to err on the side of your action being _maybe_ unnecessary, than being _for sure_ sorry the next day.

### Bitcoin's Incentive Scheme

Above we have established that human behavior, although fickle and suffers from systemic biases, likely exhibits bounded rationality, coded at the gene level. The simpler the problem and the simpler the math involved, the more likely we will make the optimal, rational decision.

As it occurs, Bitcoin's incentive scheme mostly falls into this category. What is Bitcoin's incentive scheme?

(a) **Fixed supply**: There can be no more than [21 million bitcoins](https://satoshi.nakamotoinstitute.org/posts/bitcointalk/46/) ever.

(b) **Mining subsidy**: Bitcoins are [created](https://en.bitcoin.it/wiki/Mining#Reward) each time a miner discovers a block. The number of bitcoins generated per block is set to decrease geometrically, with a 50% reduction every 210,000 blocks, or approximately four years. As of this writing (Dec 2018), the current subsidy is 12.5 bitcoins per block.

(c) **Transaction fees**: Users include [transaction fees](https://en.bitcoin.it/wiki/Miner_fees) in their transactions as payment to miners for processing those transactions. Transaction fees follow the market forces of supply and demand. When blocks are full, fees are high. Vice versa, when blocks are empty, fees are at their lowest.

Let's briefly go through each one and see how rationality plays a role in making these incentives work.

(a) A fixed supply is Bitcoin's primary financial incentive. If successful, Bitcoin would be the scarcest asset ever existed — much scarcer than even gold and diamond. All else being equal, if people are rational, they should prefer the scarcest asset to store value in, given a number of available assets.

(b) Mining subsidy is a temporary incentive, but it is essential to the initiation of Bitcoin. Bitcoin, as with most networks, had a chicken-and-egg problem: why should the first few people participate in an infant network when there were barely anyone else? Relying purely on non-profit-minded volunteers to support the network would be unsustainable. Bitcoin solved this problem by giving early adopters higher amounts of rewards, in the form of subsidy. If people were rational, and estimated Bitcoin to have _any_ chance of success, then the subsidy should serve as a strong enough incentive to overcome the initial risks and uncertainty associated with Bitcoin mining. The subsidy bought Bitcoin time until it is strong enough to protect itself from external attacks. This was also the fairest way to distribute bitcoins: by giving them to people who most strongly believed in and contributed to the project when no one else did. However, mining subsidy is irrelevant in the long run, past the bootstrapping stage.

(c) Transaction fees are Bitcoin's true second main incentive. As stated, in the long run Bitcoin has to remove mining subsidy altogether in order to not violate the scarcity incentive from (a). As Satoshi [put it](https://satoshi.nakamotoinstitute.org/posts/bitcointalk/57): "In a few decades when the reward gets too small, the transaction fee will become the main compensation for nodes."

If transaction fees are high enough, and people are rational, there should be a healthy mining industry to keep the network secure. Worth noting that due to transaction fees being a [highly variable factor](https://twitter.com/hugohanoi/status/1004875492128768000) — which is a stark contrast to the predictability of a fixed supply and fixed inflation schedule — the math involved in calculating opportunity costs of pursuing transaction fees is more complex. Bitcoin's transition to a fee-driven model is untested, and it remains to be seen whether the transition would happen smoothly.

So we see how Bitcoin's sustainability greatly depends on rational human behavior at the core. This is a crucial point and an aspect where Bitcoin is inferior to gold, the previous standard of sound money. If people choose to stop using gold as money (perhaps irrationally), gold is fine. It would still exist in nature, and could make a comeback as money centuries later. If people choose to stop using or mining Bitcoin (perhaps irrationally), it will need to be bootstrapped later, or might fail to be bootstrapped ever again.

In return for this inferiority, Bitcoin is superior to gold in [almost all other departments](https://medium.com/@vijayboyapati/the-bullish-case-for-bitcoin-6ecc8bdecc1) desirable for a monetary asset, e.g., transferability and portability.

### Side Note: Development Incentive

Since Bitcoin exists as software and requires active development and maintenance [3], a few words are warranted on the issue of development incentive. Since this issue is more about resource allocation than the creation of digital scarce money itself, feel free to skip this section. Development incentive in general is orthogonal to Bitcoin's incentive scheme as described above.

Unlike miners, developers do not have a direct financial incentive in the protection and development of Bitcoin. Instead, Bitcoin software development relies on a voluntary [open-source-software](https://en.wikipedia.org/wiki/Open-source_software) system — where developers who are most philosophically-aligned with the cypherpunk ethos of Bitcoin are motivated to work on it on their own free time. This might seem inefficient, and perhaps due to the success of Bitcoin's incentive scheme so far, several altcoins have been trying to address this problem by adding development incentive to their protocols.

However, in-protocol development incentive is highly challenging. The reason is that it is very different to Bitcoin's original incentive scheme, which has some very special properties:

* The common goal can be **mathematically-defined**: miners get paid for a hash that is smaller than or equal to the current difficulty target.
* The common goal is **computationally-verifiable**: miners' work towards the goal is verifiable by anyone, cheaply; and miners only get rewarded after the fact.

This makes Bitcoin's incentive scheme _automatable_. That is, it doesn't need any human intervention to work, and can exist safely as fixed rules within the protocol. In general, in-protocol incentives make sense if the goals can be mathematically-defined and computationally-verifiable.

Development goals, however, are often highly fuzzy [4], neither mathematically-defined nor computationally-verifiable. For example, a typical development goal is to scale Bitcoin to handle twice the traffic without degrading overall network security or Bitcoin's essential attributes. However, opinions differ wildly on what "network security" or Bitcoin's "essential attributes" mean. These goals, even if somehow met, are hard to be verified or verified cheaply. Ultimately what that means is that these goals require subjective human inputs. Thus, they are poor candidates to be built into the protocol, adding overhead without being necessarily beneficial. Development incentive is better off being handled off-chain.

In summary, Bitcoin is unlike any other technologies ever created in that human behavior is one of its core moving parts. It is the first of its kind.

Bitcoin's reliance on human behavior implicitly assumes that humans are rational actors. This rationality assumption might break down in certain situations, such as when information is limited, or when the opportunity costs calculations become too complex. Or within a community of Buddhist monks who were trained from birth to reject material gains. Or imagine a world where resources are infinitely abundant: it's likely that the beings there will develop behavior not wired to compete or maximize utility [5].

Despite that, there is strong evidence that we humans do possess some degree of rationality, or at least a bounded version of rationality. It is this bounded rationality that Bitcoin's survival hinges on. Bitcoin needs rational actors to bootstrap its network. Bitcoin needs rational actors to buy into its promise of sound money, [HODL](https://en.bitcoinwiki.org/wiki/Hodl) at all costs, and consequently raise its price. Bitcoin needs rational actors to keep participating in mining and sustain the network for the next 100-1000 years. Can we, and future generations, stay rational at all times and forever? Or would we be foolish and prematurely abandon this idea, no matter how sound it is?

_*This is part 4 of the Bitcoin Fundamentals series. Check out the full series here:_ [_part 1_](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667) _,_ [_part 2_](https://medium.com/@hugonguyen/bitcoin-chance-and-randomness-ba49a6edf933) _,_ [_part 3_](https://medium.com/@hugonguyen/how-cryptography-redefines-private-property-34cd93d86036) _,_ [_part 4_](https://medium.com/@hugonguyen/bitcoins-incentive-scheme-and-the-rational-individual-dc20effa4715) _, and_ [_part 5_](https://medium.com/@hugonguyen/bitcoin-two-parts-math-one-part-biology-b45ef48a0422) _._

### Acknowledgements

Special thanks to [Murad Mahmudov](https://medium.com/@muradmahmudov), [Nic Carter](https://medium.com/@nic__carter) and [Steve Lee](https://medium.com/@moneyball) for their extremely valuable feedback.

_[1]:_ [_The Selfish Gene_](https://www.amazon.com/Selfish-Gene-Popular-Science/dp/0192860925) _, by Richard Dawkins._

_[2]: "Some research suggests there is a genetic basis for greed. It is possible people who have a shorter version of the ruthlessness gene (AVPR1a) may behave more selfishly;_ [_Ruthlessness gene discovered_](https://www.nature.com/news/2008/080404/full/news.2008.738.html) _." (_ [_Wikipedia_](https://en.wikipedia.org/wiki/Greed) _). Also see_ [_related work_](http://archive.boston.com/bostonglobe/ideas/articles/2012/05/13/webhed_are_we_born_to_be_poor_the_rise_of_genoeconomics/?page=full) _on the burgeoning field of Genoeconomics._

_[3]: Recently a consensus-critical bug,_ [_CVE-2018–17144_](https://bitcoincore.org/en/2018/09/20/notice/) _, has been discovered then quickly fixed in Bitcoin. If it was exploited, some Bitcoin nodes could have been tricked into accepting a block that inflates the supply beyond 21 million bitcoins. This event highlights the difficult nature of software development, despite the quality of development team (read my analysis of that bug_ [_here_](https://medium.com/@hugonguyen/code-reusability-vs-accidental-commonness-89e2b2b007cd) _). There is also a good chance that the Bitcoin protocol will get ossified at some point in the future, which lessens the need for active development, if not completely removes it (i.e.: critical bugs might still need to get fixed)._

_[4]: The fuzzy nature of software requirements and difficulty in writing precise "specs" are problems well-known within the software industry._

_[5]: Note that in this last example one can argue that this behavior is not really irrational in that context. However we are using "rationality" loosely here to mean utility maximization, not necessarily about being based on logic or reason._


Thanks to [Nic Carter](https://medium.com/@nic__carter?source=post_page).
