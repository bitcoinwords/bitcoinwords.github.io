---
title: "The Physics of Brute Force"
permalink: "/the-physics-of-brute-force"

author: aarontoponce

tags:
  - Aaron Toponce
  - 2016 Q2
  - Mining
  - Technology
  - Security

excerpt: The Physics of Brute Force. Posted June 19, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Physics of Brute Force](https://pthree.org/2016/06/19/the-physics-of-brute-force)
### By Aaron Toponce
### Posted June 19, 2016

### Introduction

Recently, MyDataAngel [launched a Kickstarter project](https://www.kickstarter.com/projects/datagatekeeper/datagatekeeper-the-first-impenetrable-anti-hacking/) to sell a proprietary encryption algorithm and software with 512-bit and 768-bit symmetric keys. The motivation was that 128-bit and 256-bit symmetric keys just isn't strong enough, especially when AES and OpenSSL are older than your car (a common criticism they would mention in their vlogs). Back in 2009, Bruce Schneier blogged about [Crypteto having a 49,152-bit symmetric key](https://www.schneier.com/blog/archives/2009/09/the_doghouse_cr.html). As such, their crypto is 100% stronger, because their key is 100% bigger (than 4096-bit keys?). [Meganet](http://www.meganet.com/), which apparently still exists, has a 1 million-bit symmetric key!

It's hard to take these encryption products seriously, when there are no published papers on existing primitives, no security or cryptography experts on your team, and you're selling products with ridiculous key lengths (to be fair, 512-bit and 768-bit symmetric keys aren't really that ridiculous). Nevermind that your proprietary encryption algorithm is not peer-reviewed nor freely available to the public. Anyone can create a symmetric encryption algorithm that they themselves cannot break. The trick is releasing your algorithm for peer review, letting existing cryptography experts analyze the design, and still coming out on top with a strong algorithm (it wouldn't hurt if you analyzed existing algorithms and published papers yourself).

So with that, I want to talk a bit about the length of symmetric keys, and what it takes to brute force them. Bruce Schneier addressed this in his "Applied Cryptography" book through the laws of thermodynamics. Unfortunately, he got some of the constants wrong. Although the conclusion is basically the same, I'm going to give you the same argument, with updated constants, and we'll see if we come to the same conclusion.

### Counting Bits

Suppose you want to see how many bits you can flip in one day by counting in binary every second. Of course, when you start counting, you would start with "0", and your first second would flip your first bit to "1". Your second second would flip your second bit to "1" while also flipping your first bit back to "0". Your third second would flip the first bit back to "1", and so forth. Here is a simple GIF (pronounced with a hard "G") counting from 0 to 127, flipping bits each second.

![](/assets/images/2016/m6/aaron-toponce1.gif)

By the end of a 24-hour period, I would have hit 86,400 seconds, which is represented as a 17-bit number. In other words, every 24 hours, flipping 1 bit per second, I can flip every combination of bits in a 16-bit number.

![](/assets/images/2016/m6/aaron-toponce2.png)

By the end of a single year, we end up with a 25-bit number, which means flipping a single bit every second can flip every combination of 24-bits every year.

![](/assets/images/2016/m6/aaron-toponce3.png)

So, the obvious question is then this- what is the largest combination of bits that I can flip through to exhaustion? More importantly, how many computers would I need to do this work (what is this going to cost)?

### Some Basic Physics

One of the consequences of the [second law of thermodynamics](https://en.wikipedia.org/wiki/Second_law_of_thermodynamics), is that it requires energy to do a certain amount of work. This could be anything from lifting a box over your head, to walking, to even getting out of bed in the morning. This also includes computers and hard drives. When the computer wishes to store data on disk, energy is needed to do that work. This is expressed with the equation:

```
Energy = kT
```

Where "k" is Boltzmann's constant of 1.38064852×10<sup>−16</sup> ergs per Kelvin, and "T" is the temperature of the system. I'm going to use [ergs](https://en.wikipedia.org/wiki/Erg) as our unit, as we are speaking about work, and an "erg" is a unit of energy. Of course, a "[Kelvin](https://en.wikipedia.org/wiki/Kelvin)" is a unit of temperature, where 0 Kelvin is defined as a system devoid of energy; also known as "absolute zero".

It would make the most sense to get our computer as absolutely cool as possible to maximize our output while also minimizing our energy requirements. Current background radiation in outer space is about [2.72548 Kelvin](https://en.wikipedia.org/wiki/Cosmic_microwave_background). To run a computer cooler than that would require a heat pump, which means adding additional energy to the system than what is needed for our computation. So, we'll run this ideal computer at 2.72548 Kelvin.

As a result, this means that to flip a single bit with our ideal computer, it requires:

```
Energy = (1.38064852×10−16 ergs per Kelvin) * (2.72548 Kelvin) = 3.762929928*10-16 ergs
```

### Some Energy Sources

#### The Sun

Now that we know our energy requirement, [let's start looking at some energy sources](https://en.wikipedia.org/wiki/Orders_of_magnitude_%28energy%29). The total energy output from our star is about 1.2*10<sup>34</sup> Joules per year. Because one Joule is the same as 1*10<sup>7</sup> ergs, then the total annual energy output of the Sun is about 1.2*10<sup>41</sup> ergs. So, doing some basic math:

```
Bits flipped = (1.2*1041 ergs) / (3.762929928*10-16 ergs per bit) = 3.189004374*1056 bits
```

3.189004374*10<sup>56</sup> bits means I can flip every combination of bits in a 2<sup>187</sup>-bit number, if I could harness 100% of the solar energy output from the sun each year. Unfortunately, our Sun is a weak star.

#### A Supernova

A [supernova](https://en.wikipedia.org/wiki/Supernova) is calculated to release something around 10<sup>44</sup> Joules or 10<sup>51</sup> ergs of energy. Doing that math:

```
Bits flipped = (1051 ergs) / (3.762929928*10-16 ergs per bit) = 2.657503608*1066 bits
```

2.657503608*10<sup>66</sup> bits is approximately 2<sup>220</sup>-bits. Imagine flipping every bit in a 220-bit number in an orgy of computation.

#### A Hypernova

A [hypernova](https://en.wikipedia.org/wiki/Hypernova) is calculated to release something around 10<sup>46</sup> Joules or 10<sup>53</sup> ergs of energy. Doing that math:

```
Bits flipped = (1053 ergs) / (3.762929928*10-16 ergs per bit) = 2.657503608*1068 bits
```

2.657503608*10<sup>68</sup> bits is approximately 2<sup>227</sup>-bits. This is a computation orgy [turned up to 11](https://en.wikipedia.org/wiki/Up_to_eleven).

Of course, in all 3 cases, I would have to harness 100% of that energy into my ideal computer, to flip every combination of these bits. Never mind finding transportation to get me to that hypernova, the time taken in that travel (how many millions of light years away is it?), and the cost of the equipment to harness the released energy.

### Bitcoin Mining

As a comparative study, Bitcoin mining has almost surpassed [2 quintillion SHA-256 hashes *per second*](https://blockchain.info/charts/hash-rate?showDataPoints=false&timespan=&show_header=true&daysAverageString=7&scale=0&address=). If you don't think this is significant, it is. That's processing all of a 60-bit number (all 2<sup>60</sup> bits) every second, or an 85-bit number (all 2<sup>85</sup> bits) every year. This is hard evidence, right now, of a large scale 256-bit brute force computing project, and it's barely flipping all the bits in an 85-bit number every year. The hash rate would have to double (4 quintillion SHA-256 hashes every second) to surpass flipping all the bits in an 86-bit number every year.

Further, we do not have any evidence of any clustered supercomputing project that comes close to that processing rate. It can be argued that the rate of Bitcoin mining is the upper limits of what any group of well-funded organizations could afford (I think it's fair to argue several well-funded organizations are likely Bitcoin mining). To produce a valid conspiracy theory to counteract that claim, you would need to show evidence of organizations that have their own semiconductor chip manufacturing, that has outpaced ARM, AMD, Intel and every other chip maker on the market, by several orders of magnitude.

Regardless, we showed the amount of energy needed anyway to flip every bit in a 256-bit number, and the laws of thermodynamics strongly imply that it's just not physically possible.

### Asymmetric Cryptography

Things change when dealing with asymmetric cryptography. Now, instead of creating a secret 256-bit number, you're using mathematics, such as prime number factorization or elliptic curve equations. This changes things drammatically when dealing with key lengths, because even though we assume some mathematical problems are easy to calculate, but hard to reverse, we need to deal with exceptionally large numbers to give us the security margins necessary to prove that hardness.

As such, it because less of a concern about energy, and more a concern about time. Of course, key length is important up to a point. We just showed with the second law of thermodynamics, that brute forcing your way from 0 to 2<sup>256</sup> is just physically impossible. However, finding the prime factors of that 256-bit number is a much easier task, does not require as much energy, and can be done by only calculating no more than half of the square root amount of numbers (in this case, 2<sup>127</sup>, assuming we're only testing prime numbers).

As such, we need to deal with prime factors that are difficult to find. It turns out that it's not enough to just have a 512-bit private key to prevent the Bad Guys from finding your prime factors. This is largely because there are efficient algorithms for calculating and testing prime numbers. So, it must also be expensive to calculate and find those primes. Currently, [best practice seems to be generating 2 1024-bit prime factors to produce a 2048-bit private RSA key](https://www.keylength.com/en/compare/).

![](/assets/images/2016/m6/aaron-toponce4.png)

### Fixed-length Collision-resistant Hashing

Fixed-length collision-resistant hashing puts a different twist on brute force searching. The largest problem comes from the [Birthday Attack](https://en.wikipedia.org/wiki/Birthday_attack). This states that if you have approximately the square root of 2 times 365 people in the room (about 23 people), the chances that *any two people* share the same birthday is 50%. Notice that this comes from any two people in the room. This means that you haven't singled out 1 person, and the odds that the other 22 people in the room have that same birthday is 50%. This isn't a pre-collision search. This is a blind search. You ask the first person what their birthday is, and compare it with the other 22 people in the room. Then you ask the second person what their birthday is, and compare it with the remaining 21 people in the room. And so on and so forth. After working through all 23 people comparing everyone's birthday to everyone else's birthday, the odds you found a match between two random people is 50%.

Why is this important? Suppose you are processing data with SHA-1 (160-bit output). You only need to calculate 2<sup>80</sup> SHA-1 hashes before your odds of finding a duplicate hash out of the currently calculated hashes reaches 50%. As we just learned with Bitcoin, this is practical within one year with a large orchestrated effort. Turns out, SHA-1 is weaker that that (we only need to calculate 2<sup>64</sup> hashes for a 50% probability), which is why the cryptographic community has been pushing so hard to get everyone and everything away from SHA-1.

Now you may understand why 384-bit and 512-bit (and more up to 1024-bit) cryptographically secure fixed-length collision-resistant hashing functions exist. Due to the Birthday Attack, we can make mince meat of our work.

### Conclusion

As clearly demonstrated, the second law of thermodynamics provides a clear upper bound on what can be found with brute force searches. Of course, brute force searches are the least effective way to find the private keys you're looking for, and indeed, there are more efficient ways to get to the data. However, if you provide a proprietary encryption algorithm with a closed-source implementation, that uses ridiculously long private keys, then it seems clear that you don't understand the physics behind brute force. If you can't grasp the simple concept of these upper bounds, why would I want to trust you and your product in other areas of security and data confidentiality?

Quantum computing does give us some far more efficient algorithms that classical computing cannot achieve, but even then, 256-bits still remains outside of the practical realm of mythical quantum computing when brute force searching.

As I've stated many times before- trust the math.

***

{% include signup.md %}
