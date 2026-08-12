---
title: "Bitcoin and Software Reliability"
permalink: "/bitcoin-and-software-reliability"

author: beautyon

tags:
  - Beautyon
  - 2017 Q2
  - Mining
  - Money
  - Technology

excerpt: Bitcoin and Software Reliability. Posted May 27, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin and Software Reliability](https://hackernoon.com/bitcoin-and-software-reliability-d681367a49b2)
### By Beautyon
### Posted May 27, 2017



![](/assets/images/2017/m5/bitcoin-and-software-reliability3.jpg)

A small group of disgruntled people who feel left out of Bitcoin’s meteoric rise complain that Bitcoin’s developers add new features to its basic tool kit “too slowly”, and that innovation on it has stagnated. It is not true that Bitcoin is stagnating. Bitcoin is the fundamental backbone of the missing infallible payments layer of the Internet. In order for it to be infallible and totally reliable, there is only one possible approach to maintaining and extending the software that governs it.

The mindset and approach needed is not many quick iterations and “break things” mentality; instead, what is needed is the thinking behind super high uptime software, where methodical, slow, evidence-based improvement cycles are employed, and where features are added only when it is proven that stability, compatibility and integrity are absolutely guaranteed.

This is not a new approach in software. Mission-critical systems and applications where life and death are at stake opt for vendors who are very conservative and focussed on stability and reliability.

[**INTEGRITY Real-time Operating System**_The flagship of Green Hills Software operating systems, the INTEGRITY RTOS&, is built around a partitioning…_www.ghs.com](http://www.ghs.com/products/rtos/integrity.html?ref=hackernoon.com#max)

These systems have [uptimes](https://en.wikipedia.org/wiki/Uptime?ref=hackernoon.com) (the amount of time a system is available without interruption) measured in years. [Visa’s recent downtime](https://twitter.com/RyanDippmann/status/1003547928642777088?s=20&ref=hackernoon.com) shows they are not running systems built to this high and exacting standard, and Bitcoin shows that it *is* built to this standard, with its uninterrupted, infallible and continuous service measured in years.

![](/assets/images/2017/m5/bitcoin-and-software-reliability4.jpg)

Bitcoin isn’t an operating system, but the principles of fault tolerance and careful extension apply nonetheless. The “To the Moon” meme provides a useful context. NASA’s software fault tolerance requirements are very strict. When astronauts are involved, their lives are at stake. “Break stuff” in that context means “Kill People”. The software simply ***must*** *work every time*, no compromise, no guesswork, no exceptions. There are no “do overs” or roll-backs. Guaranteed performance is possible in software, because everything about the systems, including the hardware, can be known in advance and thoroughly tested.

High fault tolerance software development has been going on for decades. It is a very well understood discipline, and the practices, methods and mentality are also established and known to work. This is why regular satellite launches work exactly as expected every time. People take them for granted, but there is a culture behind the processes that make regular flawless space launches possible that needs to be applied to Bitcoin, if it is to serve everyone as is hoped. It is not unreasonable to expect Bitcoin to never have an error in its operation. This expectation is already understood to be achievable in Air Traffic Control systems, where once again, lives are at stake.

![](/assets/images/2017/m5/bitcoin-and-software-reliability5.jpg)

[https://shemesh.larc.nasa.gov/fm/fm-atm.html](https://shemesh.larc.nasa.gov/fm/fm-atm.html?ref=hackernoon.com)

With Bitcoin, lives and money are at stake. Interruption of its service can cause a cascade of losses and unintended consequences for potentially millions of people and billions of fiat dollars. If it is possible to build a Bitcoin that cannot fail, that should be the goal, and no compromise should be acceptable. It is also clearly possible that a distributed Bitcoin with that characteristic can exist. Bitcoin can be absolutely fault free and distributed at the same time; in fact, any centralization of Bitcoin into data centres increases the probability of critical faults. For certain, there is a math function to describe this. Can you write it out? The exam question would be something along the lines of,

*“If Bitcoin is run from a single data centre and that data centre goes off-line, Bitcoin goes down. If Bitcoin is in two data centres and one of them goes off-line, Bitcoin stays up. Describe a function that explains this, showing the number of data centres in relation to the probability of Bitcoin going down, where going down means Bitcoin is totally inoperable. Extra marks for providing a graph of the function.”*

Bitcoin is not a social network or chat app. It is a mission-critical software project that has greater integrity than any financial software project in history, in both senses of the word “integrity”. It never goes down, is always available, and is absolutely predictable. All other projects next to it pale in comparison. It is a solid foundation to build against — more solid, in fact, than the operating systems used to build the services that take advantage of it.

The vast majority of tool builders are not held to the standards that NASA and Mission-Critical, High Availability systems are held to; it is a special discipline that most people are unaware of. Participants who are not even software developers at all have *no clue* about this specialist field, let alone the expert field of software that isn’t life or death fault tolerant itself; that field is two times removed from them, and is not a part of their thinking at all.

![](/assets/images/2017/m5/bitcoin-and-software-reliability6.jpg)

[Cherenkov Radiation](https://en.wikipedia.org/wiki/Cherenkov_radiation?ref=hackernoon.com) in a Nuclear Reactor. TOXIC!

The more you look at what Bitcoin has achieved, how specialised its disciplines and requirements are, the number of things outside the software realm that constrain its operation (like the speed of light) the more you’re astonished that it has even happened, and the more you want to stay as far away as you can possibly get from its inner workings…if you are sane. This doesn’t mean that you can’t build on Bitcoin as an ordinary developer; on the contrary, its APIs are easy to understand and build against. What you cannot do, however, is enter the “radiation zone” where unseen problems can literally irradiate and kill you. The speed of light is a perfect example.

There is an upper limit to the block size beyond which the Bitcoin network cannot stay in sync. Because it takes time for data to move across the network, the speed of light is a limiting factor. You can’t have blocks of a size that are beyond that limit, *and* have Bitcoin as a distributed network. The obvious question is, *“what is that magic block size number?”.* It is certainly a function of the fastest possible network transmission speed, which is very much slower than the speed of light in air. Normal fibre optic cable transmits light at one third the speed of light, which suggests another exam question,

*“Calculate the largest theoretical block size the Bitcoin network can manage and maintain a distributed peer structure if it were running on a perfect fibre optic network where the connections between all nodes run at half the speed of light, over a geographic area the size of the Earth. Any node on the network must be a maximum of one microsecond behind any other node at any time during normal Bitcoin operation.”*

This is the sort of question big blockers don’t ask and don’t have the math to answer. New [ultra-thin photonic-bandgap rim, mode division multiplexing fibre optic cable](https://www.extremetech.com/computing/151498-researchers-create-fiber-network-that-operates-at-99-7-speed-of-light-smashes-speed-and-latency-records?ref=hackernoon.com) can transmit light at 99.7% of c, but it will take decades to replace all the “slow” fibre optic cable globally. For now, Bitcoin *must* operate within the constraints we have today. This matter of speed constraints is a question High-Frequency Traders have already posed, and found a solution to; [put everything in one data centre](http://www.datacenterknowledge.com/archives/2010/12/14/speed-of-light-constrains-high-speed-traders?ref=hackernoon.com):

![](/assets/images/2017/m5/bitcoin-and-software-reliability7.jpg)

This means that traders who are competing against each other buy rack space in specialist data centres where their [*boxen*](https://www.urbandictionary.com/define.php?term=boxen&ref=hackernoon.com) can execute trades with the equipment of other traders. This is not acceptable for Bitcoin, obviously, because it exists outside of the State and its regulations. High-speed trading data centres are all “compliant” and regulated. Bitcoin is not regulable. It can never exist in a data centre without losing its *force of nature* characteristic. This is not to say that Bitcoin is in opposition to anything; the rain, wind and snow are not in opposition to crops, roads or your vacation; they simply **are**, just as Bitcoin **is**. Putting Bitcoin in a data centre is like trying to put lightning in a [Leyden Jar](https://en.wikipedia.org/wiki/Leyden_jar?ref=hackernoon.com). It isn’t lightning any more, but *static electricity*.

Decades from now, when fibre optic cable runs at near-lightspeed it may be possible to increase the block size, and do other things that take advantage of the inevitable improvements in hardware and software. Certainly, as Bitcoin unleashes the forces of the free market, these innovations will come faster than they would have under the fiat currency fueled State. For now, however, Bitcoin must exist inside the constraints imposed by today’s technology. And it will be enough to change everything.

If you like the content and feel so obliged to send some love via BTC donations you can do so at the address below:↴

![](/assets/images/2017/m5/bitcoin-and-software-reliability8.jpg)

***

{% include signup.md %}
