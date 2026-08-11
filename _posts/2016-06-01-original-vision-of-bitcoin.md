---
title: "Original vision of Bitcoin"
permalink: "/original-vision-of-bitcoin"

author: olegandreev

tags:
  - Oleg Andreev
  - 2016 Q2
  - History
  - Philosophy
  - Satoshi

excerpt: Original vision of Bitcoin. Posted June 1, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Original vision of Bitcoin](https://blog.oleganza.com/post/145248960618/original-vision-of-bitcoin)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted June 1, 2016

Some people feel bad about Bitcoin being harder to scale than any successful centralized system such as Myspace or Altavista. They often [claim](https://twitter.com/rogerkver/status/737665373219213312) that “I signed up for a P2P Electronic Cash System, not a settlement layer” which is a way to say that Satoshi envisioned something else than what we have today.

I’d like to challenge this argument, even though I realize that it is absolutely irrelevant: whatever Satoshi thought he was doing, existence and evolution of Bitcoin is not subject to anyone’s wishful thinking, but to a humankind’s ability to actually improve it.

So Satoshi called Bitcoin an “electronic cash system”. What does that mean?

First of all, “cash” means something else than “quick settlement”. It primarily means a bearer instrument as opposed to a contract with a third party providing credit (as with credit cards, for instance). When accepting “cash” instead of a credit card, I am somewhat protected against reversal of the transaction by a third party — a credit card company. But how exactly am I protected? Turns out, there is another third party involved: a centrally controlled mint (e.g. a central bank) that provides difficult-to-counterfeit notes and uses a subsidized (by taxes) police force to discover and eliminate counterfeiters. So instead of two third parties (CB + CC company), cash leaves only one (CB) in our threat model. CB also adds a risk of debasement of currency, so if you receive 0.10% of total currency today, tomorrow it may turn out to be just 0.09%. You are essentially paying a rent on money with little assurances of stability of that rent. Also note a somewhat hidden cost of tax-subsidized minting and law enforcement to protect authenticity of the money.

Lets scroll back a few hundred years to the age of silver and gold coins. “Cash” was more decentralized: gold is gold no matter what face is printed on it. But why have faces on gold coins at all? Elementary, Watson: because it’s a huge pain in the arse to verify the coin on the spot. So central mints were used to provide hard-to-counterfeit stamps that allow quicker verification of coin validity. Mints were still a source of debasement risk, but at least some independent verification was more possible and debasement could not have been done overnight (as the saying goes, Rome was not debased in one day).

So even precious metal coins are not better than paper cash (if they were, paper would never take off in the first place): they seem to be decentralized, but related costs are so high, that to make them useful we still need centralized authorities built around them.

Is it the kind of cash Satoshi attempted to turn into electronic form? Lets read [bitcoin.pdf](https://bitcoin.org/bitcoin.pdf) from the *very beginning*:

> A purely **peer-to-peer** version of electronic cash would allow online payments to be sent directly from one party to another **without going through a financial institution**.

Note that the Mint (or Central Bank) involved in coinage and printing paper bills is as much a financial institution as your bank or Visa.

If one is to create a truly decentralized bearer instrument, one must make *both issuance and authenticity checks* decentralized, not simply the transfer mechanism. And the only workable way that we know so far is to collectively (as a civilization) continuously build a proof-of-work chain of transfers authenticated via public key cryptography.

Folks who focus on payments without discussing issuance and corresponding holding costs (risks of debasement) are like grasshoppers who spend before saving, so when winter comes they all go to ants begging for the share of what the ants saved. This has happened all the time in the history: first, ants abstain from unnecessary spending in order to save some food for later, then ants are forced to abstain even more by all the stupid and hungry grasshoppers who come to take their savings. A truly decentralized cash would prevent the most badass grasshoppers issuing and debasing their own currency and asymmetric security of public key cryptography allows all ants, no matter how poor or rich, have equally cheap protection against even the strongest of grasshoppers.

But lets get back to our “original vision of Bitcoin”. We now clearly see that it is not fair to compare Bitcoin’s performance to performance of Visa electronic payments (large throughput, but a lot of trusted third parties and risks of reversal and censorship) or even paper bills or minted coins.

So how does Bitcoin compare to a fully decentralized gold bullion then, the best known decentralized money before Bitcoin? How many transactions a day can the naked chunks of gold settle around the world? How quick is each payment verification? How do costs scale with different amounts of payments, from the smallest to the largest? We will leave answering these questions as an exercise to the reader and jump right to the conclusion:

**Decentralized physical cash sucks in all ways imaginable compared to Bitcoin.** Bitcoin is faster, cheaper and safer than any other forms of decentralized cash that ever existed.

In addition, if you take Bitcoin and build payment layers on top of it by relaxing some underlying security requirements, you will still get better electronic cash than the paper cash today: faster, easier to verify, better protected against debasement etc etc.

Satoshi was building a basis layer for electronic cash by eliminating trusted third parties as a requirement. He succeeded. Everything else is simply an optimization. If some optimizations relax security requirements of Bitcoin (e.g. need some level of centralization), then they do not belong to Bitcoin, but to additional layers around Bitcoin.

Bitcoin is designed to be free from intervention as in “fuck you”.

***

Discuss: [Reddit](https://www.reddit.com/r/Bitcoin/comments/4m0cec/original_vision_of_bitcoin/), [HN](https://news.ycombinator.com/item?id=11813011).

***

{% include signup.md %}
