---
title: "It must be done… but is not a panacea"
permalink: "/it-must-be-done-but-is-not-a-panacea"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2015 Q2
  - Scaling
  - Lightning
  - Game Theory

excerpt: It must be done… but is not a panacea. Posted May 5, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [It must be done… but is not a panacea](http://gavinandresen.ninja/it-must-be-done-but-is-not-a-panacea)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted May 5, 2015

There are two related arguments I hear against raising the maximum block size:

> There is no need to raise the maximum block size because the Lightning Network / Sidechains / Impulse / Factom solves the scaling problem.
>
> If the maximum block size is raised, there will be little incentive for other scaling solutions to emerge

The first is easy to address: if any of the other proposed scaling solutions were tested, practical and already rolling out onto the network and being supported by all the various Bitcoin wallets then, indeed, there would be no hurry to schedule a maximum block size increase.

Unfortunately, they’re not; read [Mike Hearn’s blog post](https://medium.com/@octskyward/the-capacity-cliff-586d1bf7715e) for details. We are years away from a time when we can confidently tell a wallet developer “use **this** solution to give your users very-high-volume, very-low-cost, very-low-minimum-payment instant transactions.”

The second is also easy to address. The “layer 2” services that are being built on top of the blockchain are absolutely necessary to get nearly instant real-time payments, micropayments and high volume machine-to-machine payments, to pick just three examples. The ten-minute settlement time of blocks on the network is not fast enough for those problems, and it will be the ten minute block interval that drives development of those off-chain innovations more than the total number of transactions supported.

Scheduling an increase to the maximum block size now is a short-term, “kick the can down the road” fix. It is ugly, [but necessary](http://gavinandresen.ninja/why-increasing-the-max-block-size-is-urgent).

***

{% include signup.md %}
