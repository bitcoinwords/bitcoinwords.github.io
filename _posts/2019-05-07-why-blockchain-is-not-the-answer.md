---
title: "Why Blockchain is Not the Answer"
permalink: "/why-blockchain-is-not-the-answer" 

tags:
  - Jimmy Song
  - CY19 Q2

excerpt: A reexamination at a failed narrative. Jimmy Song makes the case that blockchain is nothing without Bitcoin. Posted May 7, 2019.

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

{% include donation.md %}

# [Why Blockchain is Not the Answer](https://medium.com/@jimmysong/why-blockchain-is-not-the-answer-3b7d5f612d11)
### By [Jimmy Song](https://medium.com/@jimmysong)
### Posted May 7, 2019

There's a persistent myth that blockchain tech is brand new and that if only given enough time, somebody will make something that's useful for something other than money. This is what I call the "blockchain, not Bitcoin" syndrome and in this article, I'm going to dispel the myth that uses for blockchain are just around the corner, that they're going to add decentralization to all the things, and that it's some revolutionary new tech.

![](/assets/images/cy19/cy19q2m5/song-1.png){: .align-center}
The concept is about as bankrupt as the company whose logo which this imitates.

## Blockchain not Bitcoin is 5 years old already

Corporate obsession with blockchain started in 2014, shortly after Bitcoin got on their radar. Instead of paying attention to the revolutionary, innovative, decentralized and digitally-scarce money that is Bitcoin, they instead took a concepts from the software and called it "blockchain".

Multiple industry groups were found at this time, like Hyperledger and R3 as well as companies like Digital Asset Holdings that tried to create a market around this tech.

![](/assets/images/cy19/cy19q2m5/song-2.png){: .align-center}

What they had in common was the use of the word blockchain as a panacea for a bunch of problems in all sorts of industries. In typical corporate fashion, they took the word "blockchain" and bastardized it to mean whatever they wanted it to mean.

## Ignorance meets hype

The life that the word "blockchain" took on around 2015 was incredible. Tons of people, especially people that weren't technical, often with only a vague sense of how Bitcoin worked, were saying things like "I believe in the technology, but I don't believe in Bitcoin". This was apparently the "consensus" response for business-types that wanted to seem like they were current on the technology.

You can understand why for two reasons. First, Bitcoin's reputation from 2011 to 2015 or so, and to some degree today, was unsavory. Bitcoin was associated with activities like buying drugs, paying for an ad on backpage or even being an anarcho-capitalist/libertarian/Ron Paul crazy. Second, by praising the technology, an executive could appear to be on the leading edge of something that's too technical for others to question effectively.

In other words, endorsing "blockchain" and not Bitcoin gave many business-types the appearance of expertise and knowledge about the topic without all the unsavory connotations associated with Bitcoin at the time. What's clear from the subsequent actions is that they had no idea what blockchain was and seeded the consequences of their own ignorance.

![](/assets/images/cy19/cy19q2m5/song-3.png){: .align-center}

Their ignorance led to mediocre engineers with very little understanding of incentive systems, game theory or even public key cryptography to masquerade as blockchain experts. These "experts" bamboozled business-types into believing that the solution to the biggest problem for a particular industry could be built with a blockchain, some developers and some money. But we're getting ahead of ourselves. Before the full fledged "blockchain, not Bitcoin" syndrome caught fire, plenty of fuel in the form of hype preceded it.

## Blockchain: the Panacea for All Ills

This pretense of knowledge led to books like _The Blockchain Revolution_, which promised fixes to pretty much every sector in the economy while giving just enough tantalizing technical concepts in vague enough terms that many executives felt the adolescent fear of missing out on the new technical trend of ["blockchain technology"](https://medium.com/@jimmysong/why-blockchain-is-hard-60416ea4c5c).

![](/assets/images/cy19/cy19q2m5/song-4.png){: .align-center}

To be fair, many were taken in by promises of solutions to real problems for their industry. For health care, "blockchain" would somehow make patient history available to care providers at exactly the right time without violating patient privacy. For law, "blockchain" would somehow create perfectly fair contracts without the need for expensive lawyers. For supply chains, "blockchain" would somehow prove whose fault it was that some parts were substandard or that not enough parts were delivered. For art, music and TV, "blockchain" would somehow reward the creators what they were due while combating piracy and taking out the middle men. For online ads, "blockchain" would somehow make tracking accurate, reduce fraud and take out the many different middle men that collectively take a large portion of the profit. We could go on and on and on about the impossibly difficult problems that "blockchain" supposedly would solve.

It's not a coincidence that these promises correspond to giant problems in each industry. Blockchain became a blank canvas onto which any problem could be painted as being solvable. Literally hundreds of startups and industry consortiums, many using ICOs, promised to solve the biggest inefficiencies in every industry using "blockchain".

Many of these startups were created by veterans of a given industry who thought that the only missing piece was developers to write the blockchain system that would solve everything. They reasoned that they had the expertise to know what the problems were and that getting a few blockchain experts would be all that would be needed to make their industry so much better and create tremendous profit for themselves.

## The Reality of Blockchain

This would work if only these developers could deliver on what the industry veterans wanted! How hard could it be to make a flawless, auditable, decentralized, encrypted database that execute terabytes of smart contracts quickly and efficiently using oracles that check each other using zero-knowledge proofs? Surely a few lines of code in Solidity could create a scalable, provably correct, maintainable system that would solve the biggest pain points of industry X, right? Well, no.

![](/assets/images/cy19/cy19q2m5/song-5.png){: .align-center}
No, because no such explanations exist

Blockchain became a meaningless buzzword that meant "solving the biggest challenge in industry X" using fancy jargon to convince people that the challenge could be met. The reality was far different. What most of these startups discovered is that blockchain is not a panacea. They ran head first into [problems that we've known for a long time](https://medium.com/@jimmysong/the-truth-about-smart-contracts-ae825271811f) like the oracle problem, or the consensus problem, or the analyzability of Turing-complete contracts, or the free rider problem. It turns out blockchain, far from being a panacea is actually a hindrance to creating these solutions because of the requirement, at least nominally, of decentralization.

To make matters worse, the developers tasked with creating these systems were often completely ignorant about user and node incentives and possible exploits in [an adversarial environment](https://www.youtube.com/watch?v=ivgxcEOyWNs&t=30m35s).

## The Utter Failure

The results of such shenanigans are sadly predictable. When you promise more than you can deliver with mediocre talent in a technology that few people understand, you're not going to be able to deliver much. Most of these efforts have accomplished nothing. The few that created proof-of-concepts have not progressed to full-fledged products. The few products that have launched have [very little traction](https://dappradar.com/rankings) (less than 2000 users per day is considered a complete failure for an app or website).

![](/assets/images/cy19/cy19q2m5/song-6.png){: .align-center}

Despite all this, ICOs touting decentralized blockchains for industry X, enterprise blockchain efforts to optimize Y and even public blockchains for some service Z continue to be touted as the future. Several different arguments generally come up when this discrepancy between promises and results are pointed out.

### How can you be sure nothing will come out of blockchain technology other than Bitcoin?

It's true, it only takes one counterexample to disprove my thesis that blockchain is really only useful for sound money. However, without bastardizing the word blockchain, the essence of [what blockchains provide](https://medium.com/@jimmysong/why-blockchain-is-hard-60416ea4c5c) is decentralized, authoritative, expensive to alter data. This is not a surprise as these properties are exactly what you want for sound money like Bitcoin.

Unfortunately, what non-monetary projects generally need, given that it's software for an industry that's regulated, changing and growing, is a centralized, upgradeable and scalable system. Each need is made greatly more difficult when combining with a blockchain. In other words, blockchain is the wrong tool for the job.

Even if by some miracle a popular app is created on a blockchain, a centralized equivalent without the extraneous blockchain will be cheaper, faster, more reliable, more maintainable while having the exact same single points of failure as the "decentralized" blockchain-y version. Or put another way, any popular dApp is destined to lose against a centralized competitor on cost, speed, features and scale.

### So many people are working on this! Something has to come out of it.

Lots of people working on something doesn't mean desires magically turn into reality (see: alchemy, cold fusion, flying cars, etc).

![](/assets/images/cy19/cy19q2m5/song-7.png){: .align-center}

That's even overstating the point. Flying cars are at least possible. What most of these projects are working on are square circles or perpetual motion machines: decentralized services that have centralized control, that is, logical impossibilities.

I can hear my critics now, "Jimmy is against experimentation, entrepreneurship and trying new things!" This is a classic bait and switch tactic. Experimentation is fine to start. Pouring more money into failed experiments is just putting good money after bad. These "blockchain" experiments have a history of being futile and have little basis in reality. They are wastes of capital and human effort and don't lead to any useful goods or services. All they do is allow charlatans to rent-seek.

### Lots of money has gone into it! Someone is going to come up with something!

Certain engineering challenges are simply not a matter of funding, they are a matter of innovation. What's worse, when a company is handcuffed by being required to use a particularly cumbersome technology like blockchain, there's even less chance of anything coming out of it. This is the classic error of a [solution looking for a problem](https://medium.com/@jimmysong/crypto-keynesian-lunacy-16bb9193a58?source=your_stories_page---------------------------). And no, more money won't magically find you a profitable market problem for which a blockchain happens to be the most optimal solution.

![](/assets/images/cy19/cy19q2m5/song-8.png){: .align-center}

## Conclusion

"Blockchain, not Bitcoin" is not a new idea. The past five years have produced nothing with this so-called "blockchain" technology and we're unlikely to see anything in the next five. The only thing that blockchain seems to be good at is promising to fix the biggest problems while delivering very little and consuming tremendous capital.

![](/assets/images/cy19/cy19q2m5/song-9.png){: .align-center}

Blockchain is a solution looking for a problem. Too many people have been taken in by "blockchain" and pretend to see clothes on a naked emperor. The imaginary clothes may seem like perfect solutions to the biggest problems of their industry. Unfortunately, wishful thinking is not reality.

Sorry to be the bearer of bad news, but the emperor has no clothes. Blockchain without Bitcoin is a big nothing burger.

<iframe width="560" height="315" src="https://www.youtube.com/embed/hPjHvfSvuSo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Thanks to [Neil Woodfine](https://medium.com/@nwoodfine?source=post_page), [chandra duggirala](https://medium.com/@csentropy?source=post_page), [Vijay Boyapati](https://medium.com/@vijayboyapati?source=post_page), [Michael Flaxman](https://medium.com/@michaelflaxman?source=post_page), [Ben Kaufman](https://medium.com/@ben.kaufman10?source=post_page), and [DOC](https://medium.com/@docallag1?source=post_page).
