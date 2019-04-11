---
title: "Bitcoin Mining Explained in 15 Tweets"
permalink: "/bitcoin-mining-explained-in-15-tweets" 

tags:
  - CY19 Q1
  - Yan Pritzker

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

# [Bitcoin Mining Explained in 15 Tweets](https://twitter.com/skwp/status/1106380867071549440?s=21)
### By [Yan Pritzker](https://twitter.com/skwp)
### Posted March 14, 2019

**A Tweetstorm Series featuring Yan Pritzker**

Bitcoin Mining Explained. There is lots not covered here, but shooting for an intro rather than deep dive.

1/ Bitcoin is a ledger of accounts where thousands of people have a copy. In order to ensure consistency of the ledger, only one person can write to the ledger at a time.

2/ To ensure only one write, we implement a lottery system. The lottery will allow the winner to write to the ledger. It will also reward the winner with newly created Bitcoin. This is how we make Bitcoin distribution “fair”.

3/ A lottery system needs tickets, but we can’t trust anyone to sell tickets. Instead, players must burn energy to buy the tickets. Each ticket costs a certain amount of electricity. Electricity costs money because of 1st law of thermodynamics.

4/ Each ticket consists of a run of a “hashing algorithm.” This is a piece of code that takes data and creates a fingerprint of that data. The number of possible fingerprints is roughly 2²⁵⁶, or about the number of atoms in the universe. We can visualize it as a number line.

![yan-1](/assets/images/cy19q1/cy19q1m3/yan-1.png){: .align-center}

5/ To generate a ticket, you take the payments that everyone wants to make (the transactions), you add a random number, and you produce this “hash”. The hash is a number between 0 and the number of atoms in the universe and lands somewhere on this number line.

6/ Ahead of time, everyone has agreed that in order to win, you have to find a hash that’s under a specific Target Number. Let’s say that number is 100,000,000,000. That means every time you roll your random generator, you have to land in a tiny space on this number line to win.

![yan-2](/assets/images/cy19q1/cy19q1m3/yan-2.png){: .align-center}

7/Most of the time, you miss. Roughly once every 10 minutes somewhere in the world, someone hits a number that’s lower than the Target Number and wins the Block Reward of newly minted Bitcoin. In order to win, they present to the network all the data they used to get the hash.

8/ Since the chances of hitting that tiny space are very very small, by proving that they generated such a number, they are proving that they’ve done the work of burning a certain amount of energy.

9/But if more people start mining, doesn’t that increase the chances that we’d find a winning number more frequently? Yes! So, every 2016 blocks, every node checks for how often blocks have been coming and adjust the Target Number proportionally.

10/ If blocks came too fast, the Target is decreased, making it less likely to hit the Target, meaning you have to spend more energy to find a winning combination.

![yan-3](/assets/images/cy19q1/cy19q1m3/yan-3.png){: .align-center}

11/ And if blocks are coming too slowly, because too few miners are active, then we can increase the Target, making it more likely that you’d hit the Target with fewer rolls of the die, and thus more profitable. This will attract more miners.

![yan-4](/assets/images/cy19q1/cy19q1m3/yan-4.png){: .align-center}

12/ The data that produces the hash consists basically of the transactions we want to write to the ledger, the hash of the prior block, and a random number. This connects every found block to the prior block, ensuring a consistent chain of history.

13/ A large amount of energy goes into mining each block, and the block’s hash acts as a fingerprint on the data that’s in the block. If someone wants to modify an old record in the Bitcoin ledger, they have to re-mine that block by producing a new hash. This is very expensive!

14/ If they try to tamper with an old block, that block’s hash will change. But because every subsequent block used that block’s hash as part of its hash, then every subsequent block will change too. That means you have to re-mine the entire chain from the point of tampering.

15/ This makes it extremely expensive to change the Bitcoin ledger. You would have to spend as much energy as the entire honest mining network.

Fin. If you found this insightful, I would appreciate a retweet of the first tweet in this thread.