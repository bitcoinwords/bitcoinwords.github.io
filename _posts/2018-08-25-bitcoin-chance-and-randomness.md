---
title: "Bitcoin, Chance and Randomness"
permalink: "/bitcoin-chance-and-randomness" 

tags:
  - CY18 Q3
  - Hugo Nguyen

excerpt: By Hugo Nguyen, posted August 25, 2018. This is part 2 in a 5 part series.

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

# [Bitcoin, Chance and Randomness](https://medium.com/@hugonguyen/bitcoin-chance-and-randomness-ba49a6edf933)
### By [Hugo Nguyen](https://medium.com/@hugonguyen)
### August 25, 2018

**This is Part 2 of a 5 part series**
* [Part 1 - The Anatomy of Proof-of-Work](https://cryptowords.github.io/the-anatomy-of-proof-of-work)
* [Part 2 - Bitcoin, Chance and Randomness](https://cryptowords.github.io/bitcoin-chance-and-randomness)
* [Part 3 - How Cryptography Redefines Private Property](https://cryptowords.github.io/how-cryptography-redefines-private-property)
* [Part 4 - Bitcoin's Incentive Scheme and the Rational Individual](https://cryptowords.github.io/bitcoins-incentive-scheme-and-the-rational-individual)
* [Part 5 - Bitcoin: Two Parts Math, One Part Biology](https://cryptowords.github.io/bitcoin-two-parts-math-one-part-biology)

<br>

***

![Dice](/assets/images/cy18/cy18q3m8/hugo-1.png){: .align-center}*Randomness forms the cornerstone of Bitcoin’s Proof-of-Work (PoW). But how did we get here?*

### A brief history of the study of randomness [1]

Randomness has always been an essential part of life. Many ancient divination rituals were based on chance: the tossing of astragali (animal knucklebones) by the Greeks, Kau Cim sticks by the Chinese, Opele chain by West Africans. The use of dice-like devices in games & gambling also goes back thousands of years.

![Kau Cim sticks](/assets/images/cy18/cy18q3m8/hugo-2.png){: .align-center}*Kau Cim sticks*

Yet, it was not until the 16th century that we started gaining the necessary tools and languages to really understand chance and randomness. Those tools include arithmetic concepts such as fractions and the number zero.

Our study of chance and randomness began in earnest with a man named Gerolamo Cardano [2]. Born in Italy in 1501, Cardano was a polymath and one of the most influential mathematicians of the Renaissance. He was also a notorious gambling addict. Due to his gambling problem, Cardano eventually sunk into abject poverty and obscurity. It was his experience with gambling, however, that led him to write the "Book on Games of Chance" — the first systematic treatment of chance and randomness. Interestingly, Cardano intended to keep the book secrets to himself. The "Book on Games of Chance" was published a century after it was written, long after Cardano's death.

![Gerolamo Cardano](/assets/images/cy18/cy18q3m8/hugo-3.png){: .align-center}*Gerolamo Cardano (1501–1576)*

Cardano's main contribution to our understanding of chance and randomness was the idea of [sample space](https://en.wikipedia.org/wiki/Sample_space). At the most basic level, calculating the probability of an event involves the simple task of counting the number of scenarios that could lead to said event, then divide that by the total number of all possible scenarios (the "sample space"), assuming all scenarios are equally likely. This assumption only holds true for problems like dice rolling, but it was a good start.

Following in Cardano's footsteps was Galileo and Pascal. Galileo was the perfect embodiment of the rebellious intellectual spirit of that era: going against the powerful Catholic Church and proclaim that the Earth is not the center of the universe. Galileo produced many important work. One not very well-known work, "Thoughts about Dice Games", explored similar topics that interested Cardano.

Pascal, a contemporary of Fermat and Descartes, went a lot further than Cardano and Galileo did. He discovered what we now call the [Pascal's triangle](https://en.wikipedia.org/wiki/Pascal%27s_triangle). Although mathematicians in other civilizations (e.g.: Iran, China & India) had discovered the same triangle centuries before Pascal did, Pascal's work was the most comprehensive and added novel applications, specifically in the area of probability theory. Pascal also introduced the "Pascal's wager" and the concept of [mathematical expectation](https://en.wikipedia.org/wiki/Expected_value).

From the seed that Cardano, Galileo and Pascal planted, our understanding of chance and randomness gradually grew, over time becoming more sophisticated and refined. This was a common theme of the Renaissance: a few fundamental breakthroughs — such as astronomy, Newtonian physics, calculus, empiricism — laid the scientific foundation that brought forth new branches of knowledge and major technological innovations, which eventually led to the Industrial Revolution.

List of notable milestones in our journey of cracking chance and randomness:

* Sample Space
* Permutations & Combinations
* Pascal's Triangle
* Law of Large Numbers
* Law of Small Numbers
* Bayes Theorem — Conditional Probability
* The Bell Curve & Standard Deviations
* Regression Toward the Mean
* Random Walk
* Monte Carlo simulation
* Pseudorandomness

![distribution curve](/assets/images/cy18/cy18q3m8/hugo-4.png){: .align-center}*Normal Distribution a.k.a. the "Bell Curve" — image by [Dan Kernler](https://commons.wikimedia.org/w/index.php?title=User:Mathprofdk&action=edit&redlink=1 "User:Mathprofdk (page does not exist)")/ [CC 4.0](https://creativecommons.org/licenses/by-sa/4.0)*

Two major developments stand out: [_Monte Carlo simulation_](https://en.wikipedia.org/wiki/Monte_Carlo_method) and [_Pseudorandomness_](https://en.wikipedia.org/wiki/Pseudorandomness). Particularly because they're highly relevant in today's world.

The invention of the computer opened the door to a brand new application of randomness: computer simulation. For the first time in history, we have a way of "predicting" the future or uncovering hidden truths by cheaply performing experiments, over and over again. The large number of simulations afforded to us by the machines was previously unthinkable.

The invention of Monte Carlo simulation in the early 20th century marked a major turning point in human history. Prior to the Renaissance, humans often lived in fear of randomness, of uncertainty. Leading up to the 20th century, we slowly improved to gaining a better understanding of it, but still largely let randomness dictate the flow of things. With Monte Carlo simulation, we started making randomness work _for us_. The apprentice has become the master.

Notable early pioneers of Monte Carlo simulation included John von Neumann and Alan Turing, the two godfathers of the modern computer.

Nowadays, Monte Carlo simulation has a large number of applications: fluid mechanics, business, finance, artificial intelligence, to name a few. The recent case of [AlphaGo](https://www.theatlantic.com/technology/archive/2017/10/alphago-zero-the-ai-that-taught-itself-go/543450) is the perfect example of how Monte Carlo simulation (combined with other techniques) can guide us to new discoveries: AlphaGo outplayed the best human players with moves that completely surpassed our imagination and the rich literature of Go. AlphaGo challenges the idea that machines cannot be creative, and forces us to rethink what "creativity" really means.

The rising popularity of Monte Carlo methods was what spurred the development of "pseudorandomness" (a pseudorandom process is a process that appears to be random, but it's not), because a good simulation needs to be able to closely mirror the random nature of reality. Numbers generated by such a process are deterministic, but they pass statistical tests of what is considered "random". Pseudorandomness, in turn, became one of the building blocks of a brand new field — also a child of the computer age: modern cryptography.

Which brings us to Bitcoin.

### The role of randomness in Bitcoin

One of the major innovations in Bitcoin is the use of Proof-of-Work in establishing distributed consensus. PoW provides an objective yardstick which Bitcoin network participants can rely on to come to consensus, without trusting anyone on the network. This is unlike schemes like Proof-of-Stake which relies on a [subjective interpretation of consensus](https://medium.com/@hugonguyen/proof-of-stake-the-wrong-engineering-mindset-15e641ab65a2). This section assumes PoW is the only secure way to implement a blockchain. (For a refresher on PoW, read part 1: [the Anatomy of Proof-of-Work](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667).)

The "work" in Proof-of-Work involves searching for a hash output that has a minimum number of leading zeros. (There are some constraints on the hash input, such as formatting, timestamp, etc.)

Bitcoin PoW scheme uses a cryptographic hash function called SHA256. An important feature of cryptographic hash functions is that they are _one-way_. Meaning that it is infeasible to deduce the hash input just by looking at the hash output. And the reason they are one-way is largely due to _how random the hash output is_.

This turns out to be extremely critical because if the hash function doesn't generate sufficiently random ("pseudorandom") output, one can start with the desired output, i.e.: a string with a certain number of leading zeros, and work backward from there. This would render the proof less trustworthy at best, and useless at worst.

In simple terms, what a typical PoW scheme does is (a) it poses a problem whose solution lives in an incredibly large space, (b) there is no shortcut and (c) the only way to arrive at the solution is by brute-forcing and randomly searching the large space. Much like searching for a needle in a gigantic haystack. (The official computer science term for this is "unbounded probabilistic iterative procedure" — quite a mouthful.)

So the randomness of the hash function determines how strong the proof is.

### Hashing (provides) → Randomness (backs) → Proof-of-Work

> "...a good puzzle gives every miner the chance of winning the next puzzle solution in proportion to the amount of hash power they contribute. Imagine throwing a dart at a board randomly, with different sized targets corresponding to the mining power held by different miners."— Arvind Narayanan [3]

There is no formal proof that randomness is a mandatory requirement for PoW, but empirically, this seems to be true. There's also the simple observation that any problem whose solution is non-random, tends to require as much effort to verify as to compute the solution in the first place. Any such scheme would be seriously constrained in terms of scalability (keep in mind, Bitcoin is incredibly hard to scale as-is). It would also disproportionately favor the fastest miner — to the point where slightly slower miners earn nothing.

Another benefit of randomness-based PoW is that mining membership is highly open: miners can come and go whenever they like. It doesn't matter if they join immediately after a block has been found, or 5 minutes after, their chance of earning the next reward doesn't change.

What about hashing? Is it the only way to get randomness? Probably not. There are other known ways to simulate the process of random search besides hashing, such as integer factorization or discrete logarithm.

So it's highly likely that hashing is not the only means to achieve randomness, while randomness is a necessary precondition for creating digital Proof-of-Work.

PoW schemes fall into two major categories:

* Compute-bound: where the random search is bound by processor speed
* Memory-bound: where the random search is bound by memory accesses

It remains to be seen whether one PoW category is materially better than the other (I personally think memory-bound is worse [4]), but the underlying mechanism is the same: a probabilistic, random search in a huge solution space, and any solution can be verified cheaply.

In summary, for as long as humans have existed, we have struggled with randomness and uncertainty. The invention of the modern computer and Monte Carlo simulation in the 20th century allowed us, for the first time, to turn randomness to our advantage. The use of randomness in Bitcoin marked another milestone in this long journey. Randomness, in short, is what backs the "proof" in Proof-of-Work. Without randomness or really good pseudorandomness, Proof-of-Work would not work.

If Bitcoin succeeds in being money of the future, it would represent our most significant and largest-scale application of randomness thus far.

_*This is part 2 of the Bitcoin Fundamentals series. Check out the full series here:_ [_part 1_](https://bitcointechtalk.com/the-anatomy-of-proof-of-work-98c85b6f6667) _,_ [_part 2_](https://medium.com/@hugonguyen/bitcoin-chance-and-randomness-ba49a6edf933) _,_ [_part 3_](https://medium.com/@hugonguyen/how-cryptography-redefines-private-property-34cd93d86036) _,_ [_part 4_](https://medium.com/@hugonguyen/bitcoins-incentive-scheme-and-the-rational-individual-dc20effa4715) _, and_ [_part 5_](https://medium.com/@hugonguyen/bitcoin-two-parts-math-one-part-biology-b45ef48a0422) _._

### Acknowledgments

_Thanks_ [_Steve Lee_](https://twitter.com/moneyball) _&_ [_Nic Carter_](https://twitter.com/nic__carter) _for the valuable feedback._

_[1]: For a detailed history of randomness, check out_ [_The Drunkard's Walk: How Randomness Rules Our Lives_](https://www.amazon.com/Drunkards-Walk-Randomness-Rules-Lives/dp/0307275175) _, by Leonard Mlodinow._

_[2]: Not to be confused with the cryptocurrency Cardano, which ironically is based on Proof-of-Stake._

_[3]: Arvind Narayanan,_ [_Bitcoin and Cryptocurrency Technologies: A Comprehensive Introduction_](http://Bitcoin%20and%20Cryptocurrency%20Technologies:%20A%20Comprehensive%20Introduction) _._

_[4]: A couple of potential issues with memory-bound PoW schemes:_

* _Memory-bound PoW still requires computations, but operates under the assumption that memory technology has already plateaued, which makes memory the primary bottleneck in mining operation. But if this assumption is broken, instead of facing centralization forces on one front (ASIC), you'd potentially face centralization forces on two fronts (ASIC and memory)._
* _The memory used in memory-bound PoW is likely to be repurposable beyond mining. This might have a negative impact on network security because that opens up the possibility of an attacker renting memory from others (since anything repurposable would likely have an abundance of supply and occasional supply surpluses), which reduces the cost of a majority attack._ _Hardware repurposability in general is_ [_not desirable_](https://medium.com/@hugonguyen/bitcoin-stock-flow-c4d4db98b751) _for Bitcoin security._



Thanks to [Nic Carter](https://medium.com/@nic__carter?source=post_page).
