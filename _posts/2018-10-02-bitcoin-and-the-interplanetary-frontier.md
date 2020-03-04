---
title: "Bitcoin and the Interplanetary Frontier"
permalink: "/bitcoin-and-the-interplanetary-frontier"

author: clarkmoody

tags:
  - Clark Moody
  - CY18 Q4
  - Space
  - Block Time
  - Economics
  - Galactic
  - Signal Latency
  - Transaction Speed
  - Layer 2
  - L2

excerpt: Clark Moody explores Bitcoin and space, how it would function in multiplanetary economics. Posted October 2, 2018.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin and the Interplanetary Frontier](https://bitcoin.clarkmoody.com/posts/bitcoin-interplanetary-frontier)
### By [Clark Moody](https://twitter.com/clarkmoody)
### Posted October 2, 2018

The Bitcoin rallying cry of “To the Moon!” anticipates massive price increases and never-ending bull markets. But have we considered what would happen if we sent Bitcoin literally to the Moon? This is the first of a series of articles discussing the future of economics, money, and Bitcoin as humanity pushes outward to the planets and to the stars. 

![Apollo moon landing with Bitcoin flag](/assets/images/cy18/cy18q4m10/cm1.png)

## Space Economics
Space-based economies differ significantly from their Earthbound counterparts in a few critical ways. But just as the laws of celestial mechanics govern the motion of the heavens, the laws of economics guide the financial interactions of humans, no matter their location. 

Thus far, human spaceflight has been dominated by government efforts, with resources allocated carefully by mission planners. In the Apollo days, a trip to the Moon offered the [same per diem](https://www.lrb.co.uk/v27/n17/steven-shapin/what-did-you-expect) to the astronauts as an overnight in a motel (with deductions for accommodations aboard the spaceship). We shouldn’t expect significant economic activity in space until larger groups of people must allocate resources themselves. This article addresses some of the limitations of space economics and the opportunities for Bitcoin as we establish a toehold in space.

### Mass Constraints
First and foremost, shipping costs to orbit are … astronomical. Recent efforts by our [favorite space entrepreneur](https://www.youtube.com/watch?v=A0FZIwabctw) are driving down costs, but rocket launches may continue to be prohibitively expensive for decades. Non-rocket space launch [systems](https://en.wikipedia.org/wiki/Non-rocket_spacelaunch) hope to bring costs way down, but for now getting off the Earth is an expensive undertaking. 

Immense launch costs partly explain the low population density of people in outer space. Humans are much less suited to spaceflight than computers. We require food, air, climate control, limited acceleration, and low radiation. So much mass and complexity comes with putting a person in space that it makes sense to send a robot instead and beam back pictures. However, once we have a more robust human presence in space, there will be commerce and economic calculation, so we can continue with our discussion. 

In the face of mass limitations, allocating precious payload capacity to physical money like paper or gold makes no sense. As a digital money, Bitcoin was practically invented to power offworld commerce. Information is massless, and computers and communication equipment required to process digital payments would be in place regardless, serving other purposes critical to the mission. Bitcoin imposes additional overhead for block download and processing.

### Orbital Mechanics

The scarcity of useful mass in space confines us to the most efficient orbits. This makes a trip to Mars feasible only every 26 months, though smart people are working on [cheaper routes](https://arxiv.org/pdf/1410.8856.pdf). Missions to the asteroids, Jupiter, and beyond require years of flight time barring the invention of alternate propulsion systems. 

![](/assets/images/cy18/cy18q4m10/cm2.png)

The long lead time turns the most trivial expenditure on Earth into an extreme luxury. Space settlements must depart with large numbers of replacement parts and spares for all critical systems, ingenious water recycling systems, and, eventually, some way to grow food. Once they arrive, the settlements must be able to produce goods with local resources, or they will rely forever on resupply missions from their Earth-side sponsor. Even Moon colonies, with their [3-day shipping time](https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/19630007117.pdf), require a rocket launch for supplies, and that takes planning. 

Introducing long time delays into a supply chain makes advanced economic planning even more difficult and important. Systematic distortions of human [time preference](https://mises.org/wire/how-interest-rates-affect-time-preference-%E2%80%94-and-vice-versa) brought on by depreciating fiat money kick off the boom-and-bust of the business cycle. For offworld colonies, a large economic shock could be fatal. To that end, the interest rate should be left free to fluctuate according to the supply and demand for money, providing the best information to entrepreneurs making decisions about the future. A sound money like Bitcoin ensures interest rates are not artificially lowered by an increased money supply.

### The Speed of Light Penalty

Information spreads no faster than light in vacuum, which means that a round-trip message between a space settlement and Earth will incur a minimum time penalty. The Moon is 384,400 kilometers away, and radio takes 1.28 seconds to travel that distance. Using the Internet with that latency would be possible but painful. With its eventual consistency and 10 minute block times, Bitcoin would work well enough on the Moon and in near-Earth space given adequate communication capacity. A lunar colony might even receive a new block before some nodes on Earth, due to long network propagation times through parts of the Internet. 

In contrast, Mars oscillates between 3.1 and 22 light-minutes away. At those distances, a new [delay-tolerant network architecture](https://tools.ietf.org/html/rfc4838#section-1) would be required to mitigate the lag. Mining Bitcoin on Mars would be unprofitable because of the propagation delay, assuming Earth maintains hash power dominance. The Martian miners would have a view of the blockchain up to 22 minutes out of date, so by the time their latest mined block reaches the majority of hash power on Earth, on average there would be four new blocks added to the chain. We can simulate mining on Mars today: simply mine on top of a block four deep in the blockchain. Extreme luck aside, the dominant mining planet will [remain dominant](https://bitcoin.stackexchange.com/a/34310) across the solar system. 

![](/assets/images/cy18/cy18q4m10/cm3.png)

That is not to say that Bitcoin could not be used far from Earth. On the contrary, confirmation time simply becomes part of transaction planning, and second-layer solutions fill in the gap for payments. While physical goods transport incurs the cost of rocket launch and orbital transit time, transacting in digital goods happens at the speed of light. Offworld settlers could charge Earthlings for interesting data, such as scientific experiments or [art inspired by the Moon](https://dearmoon.earth/). Bitcoin makes the exchange possible.

## Space Cash
Space settlements will be entirely dependent upon their Earth-based sponsors potentially for decades, meaning that an independent economy might not arise for generations. However, fledgeling economies and offworld societies will need money one day, and a [sound money](http://a.co/d/aawM6eN) would provide a stable bedrock for planning, investment, and growth. Bitcoin is the money that you [beam across the galaxy](https://youtu.be/z5PqbKiLp0s?t=133). 

Earth-orbiting colonies, space stations, and even Moon bases could operate on Bitcoin as surely as they will have access to the Internet. Wherever Bitcoin is used, verification of the blockchain is essential in order to prevent economic censorship of the settlement. Bitcoin nodes should ensure that more than one communication channel receives updates from Earth. Multiple independent node operators in each settlement improve the censorship resistance of the blockchain. Outgoing transactions should be transmitted over [multiple channels](http://mule.tools/) back to Earth to resist economic blockade of the settlement.

### Lightning for Payments
On-chain transactions require radio round trips and multiple confirmations before they can be trusted offworld. For payments far from Earth, the [Lightning Network](https://dev.lightning.community/resources/) comes into its own. Payment channels are established on-chain, but further transactions are off-chain and local. Your payment for the newest experimental Martian coffee will be instant, private, and cheap. 

A simple technical modification is required during channel setup to mitigate large time lags: adjust the time lock delta to account for a round trip to the blockchain. Martian settlers add 44 minutes, or 4 blocks. Colonists on Saturn’s moon Titan add 3 hours, or 18 blocks to the minimum time lock delta. Otherwise, payments will be local and instant while retaining all the properties of Lightning Network payments on Earth. 

What about interplanetary Lightning channels? Enabling faster payments between worlds would be icing on the cake, but with the [current protocol](https://github.com/lightningnetwork/lightning-rfc/blob/master/02-peer-protocol.md), Lightning may not be the best fit. Aside from the assumption that “transport is ordered and reliable,” node interactions are communication-heavy, with multiple round trips for certain operations. This is not to say that some other Layer 2 technology can’t fill the gap, or that Lightning could have a delay-tolerant mode. There will probably be secure bridges between Layer 2 networks, just as there are already [services that go between](https://submarineswaps.org/) on- and off-chain payments. Brilliant minds are refining and improving these protocols constantly, so there will probably be a solution to the time delay problem by the time we need interplanetary payments. 

Should Bitcoin be used for all planets in the system? Do we need MarsCoin and MoonBux? Will Bitcoin go with colonists on missions to other stars? Later essays will discuss the viability of multiple blockchains for interplanetary trade and further implications for interstellar expansion.

### The Interplanetary Frontier
![](/assets/images/cy18/cy18q4m19/cm0.png)

The frontier offers the promise of a fresh start, and the settler spirit fuels perseverance in the face of immense challenge. As we embark on the journey to the stars, we need all the help we can get. Since the money of space settlement will be digital, we must leave behind the printing presses. Let’s also leave behind the distortions of unsound money and fuel the space economy with Bitcoin.

***

{% include signup.md %}
