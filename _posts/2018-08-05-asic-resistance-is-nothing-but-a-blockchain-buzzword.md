---
title: "ASIC Resistance is Nothing but a Blockchain Buzzword"
permalink: "/asic-resistance-is-nothing-but-a-blockchain-buzzword"

author: stopanddecrypt

tags:
  - StopAndDecrypt
  - 2018 Q3
  - Mining
  - Money
  - Privacy

excerpt: ASIC Resistance is Nothing but a Blockchain Buzzword. Posted August 5, 2018.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [ASIC Resistance is Nothing but a Blockchain Buzzword](https://hackernoon.com/asic-resistance-is-nothing-but-a-blockchain-buzzword-b91d3d770366)
### By StopAndDecrypt
### Posted August 5, 2018



![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword3.jpg)

### And Changing Bitcoin’s Proof-of-Work is a Futile Endeavor

#### Introduction

In the wake of the recent and most _(in)_significant push to change Bitcoin’s Proof-of-Work, I thought it would be a good opportunity to score some more brownie points from the community by laying it to rest. I’m going to discuss the broader topic of hardware specialization *(“ASIC Resistance”)*, the technical and logical flaws in trying to resist specialized hardware, some history around this, and then I’ll touch on what I hope to be a short lived *(and fishy)* motion for a Proof-of-Work algorithm change that nobody wants besides two and a half people.

Since the inception of the first alternative-cryptocurrency there has been a need for them to differentiate themselves from Bitcoin, or else it becomes obvious to the bystander *(those your coin is appealing to)* that it’s just a copy. They’re an alternative for a *reason*, you don’t want them to think it’s just a copy because then they dismiss it for what it really is…*a copy*.

##### What’s [Derp-Coin](https://hackernoon.com/thats-not-bitcoin-that-s-bcash-f730f0d0a837?ref=hackernoon.com)?

*Oh it’s just like Bitcoin, we copied it.*

##### Why would I use it if everyone else is using Bitcoin?

*It has a better name?*

That’s definitely not a good reason, so we need to replace that really bad reply with something better. Something that seems noteworthy or convincing, not just a new appearance. I won’t be explaining all of these, but here’s some of the common ones that are used:

* Faster confirmation times *(Litecoin)*
* Larger blocks *(*[*BCash*](https://hackernoon.com/thats-not-bitcoin-that-s-bcash-f730f0d0a837?ref=hackernoon.com)*)*
* Environmentally friendly *(Ethereum*)
* Better privacy *(Monero)*
* **ASIC Resistant**

#### So what is ASIC Resistance?

*It’s mining* ***you*** *can do, how does that sound? Does it sound* ***good****? It’s mining designed to stop people from having an “****unfair share****” of the hashpower, so you can join in on the fun and make some money too. Furthermore, it will keep our blockchain “****more decentralized****”, we know you don’t know what that really means but it’s going to work, we promise.*

It’s all nonsense and the reason why is pretty straightforward, but to cover all angles I’m going to give you the whole rundown.

#### Index

##### **1:** [**General Overview**](https://medium.com/@StopAndDecrypt/b91d3d770366?ref=hackernoon.com#4e3b)

* **Hashing & Mining:** Hash the block, check the hash like a lottery ticket
* **General Purpose Processing:** Your computers CPU is general purpose
* **Application Specific Processing:** An **AS**IC is one variant of this
* **Intentional Complexity:** Unintentional Consequences

##### **2:** [**Specialization Resistance Strategies**](https://medium.com/@StopAndDecrypt/b91d3d770366?ref=hackernoon.com#d7ae)

* **Different…But The Same:** Alternative but equitable algorithms
* **Memory Intensive Algorithms:** Uses different parts of a computer
* **External Oracles:** Periodically changed by the developers/community
* **Programmed Alternation:** Periodically changed by the code

##### 3: [**Where It All Began, And Why It’s Still Around**](https://medium.com/@StopAndDecrypt/b91d3d770366?ref=hackernoon.com#e520)

* **A Blast From The Past:** A little bit of history
* **When Will It End?:** A Gri[m/n] future

##### 4: [Late Stage Mining Requires Low Barriers-To-Entry](https://medium.com/@StopAndDecrypt/b91d3d770366?ref=hackernoon.com#fdd6)

* **Major League Mining:** The End Game
* **No Lemons?:** No Lemonade

##### 5: [Changing Bitcoin’s PoW Solves Nothing](https://medium.com/@StopAndDecrypt/b91d3d770366?ref=hackernoon.com#83d9)

* **Temporary Relief For Never Ending False Alarms**
* **Hard-Forks Intrinsically Lack Consensus** *(with few exceptions)*

##### 6: Conclusion

#### Hashing, Mining, and Pocketknives vs. Scissors

##### Hashing & Mining

Hashing is the act of scrambling data. You take anything you want, put it into a box, and out comes random 0’s and 1’s. There’s a few functions this provides, but generally it let’s you keep the input a secret while sharing the output. Hashing *algorithms* are a specific set of instructions used to generate a hash. They could be as simple as multiplying by 5 and then dividing by 2. The caveat here is this is completely reversible. You just multiply by 2 then divide by 5, and computers can do this guesswork extremely fast. If you want the input to remain a secret you need something stronger and irreversible. We could add more steps, but it’s the *kind* of steps that matter. Remember those number pattern recognition tests in high school?

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword4.jpg)

Computers are also really good at those, no matter how complex you make them. If you’re going to standardize a hashing algorithm for everyone to use you need to do *more* if you want the inputs to remain a secret. Making a process irreversible requires taking the numbers out of the realm of math and “playing” with them…a lot. Which brings us to Bitcoin’s hashing algorithm, the [SHA256](https://en.wikipedia.org/wiki/SHA-2?ref=hackernoon.com) hashing algorithm. There’s a lot of material out there that explains what this is but I’d rather leave that up to you and skip straight to demonstrating it.

Go to [this website](https://www.movable-type.co.uk/scripts/sha256.html?ref=hackernoon.com) and enter the following, you’ll see the outputs are the same.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword5.jpg)

[https://www.movable-type.co.uk/scripts/sha256.html](https://www.movable-type.co.uk/scripts/sha256.html?ref=hackernoon.com)

See how the outputs are all different? Now that you get the gist, keep adding random values after `**blockdata**`until the output hash begins with `**aaa**.` That’s all mining is. It’s just guesswork via trial and error. You can find more extensive detail on what I described above in this [video](https://www.youtube.com/watch?v=bBC-nXj3Ng4&ref=hackernoon.com) and you can watch someone perform the SHA256 algorithm by hand [here](https://www.youtube.com/watch?v=y3dqhixzGVo&ref=hackernoon.com).

##### **General Purpose Processing**

Running SHA256 on a string of data is a very simple process for a computer. The CPU in the computer you’re reading this from can do it because CPU’s are built like a multitool pocketknife, capable of performing a lot of different kinds of requests. Try and imagine each of these blue dots as a 0 or 1, and the entire machine is a CPU:

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword6.gif)

Taking the block data and hashing it doesn’t require all that machinery, only specific parts. Your CPU can do it, but the rest of that space and energy is wasted, leaving a lot of room for improvement. So let’s create something more *specific*.

##### Application Specific Processing

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword7.gif)

ASIC stands for Application Specific Integrated Circuit. It’s a *type* of hardware specialization, but it’s not the only kind. This is one of the causes for confusion on this subject because it’s a common misunderstanding. It’s similar to calling all Electronic music “Techno”. Techno is just a single genre of Electronic music, and ASICs are just a single *kind* of hardware specialization.

Similarly, ASIC Resistance is just a single *kind* of **Hardware Specialization Resistance**, so from here on out I won’t be using the ASIC misnomer, I’ll be addressing it for what it is. Please ignore the title of this article, it was only meant to lure you in with your own misunderstandings.

I’m inclined to believe that after reading up to this point and seeing the picture below you’ll get the idea. Application specific hardware is designed to do one thing, and one thing well. When you get rid of all the useless bells and whistles of a CPU, you end up with much more efficient and specialized hardware.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword8.gif)

##### Intentional Complexity

Complexity is the essence of The Resistance, but it doesn't always come in the same form. In contrast to a simple algorithm like the one above, the general goal of specialization resistance is to make it difficult to design a piece of hardware so that people are forced to use CPU’s or GPU’s.

Logic is as follows:

1. If it’s hard to specialize, it can’t be or won’t be worth specializing, forcing mining to be done on generic hardware.
2. Acquiring hoards of generic hardware will be more expensive for miners looking to expand their venture.
3. If mining operations expand slower, smaller ventures won’t be outcompeted, and people at home can play along as well.
4. This will keep mining *decentralized*.

Drawing from the .gif I used above, if SHA256 only required that small aspect of the CPU’s computational abilities, then a specialization resistant algorithm would look something like this:

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword9.gif)

The issue with this, and with the logic above, is that at some point if your coin is successful enough it *will* be worth designing specialized hardware for it. Then you end up in a situation where the production supply for that specialized hardware is very centralized, but more on that later.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword10.gif)

.

#### 2: Specialization Resistance Strategies

Without getting into the technical mumbo-jumbo I’d like to go over the different types of resistance strategies that are commonly advertised.

##### Different…But The Same

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword11.gif)

This one’s the easiest of the bunch because it explains itself. Some algorithms use the same “parts” of a CPU/GPU as SHA256, offering no real difference in computational difficulty, or cost to manufacture. Some other algorithms use multiple parts of the CPU, some of which may be more costly to create specific hardware for, but again this falls short in the end. The only real purpose of these is to say “they don’t make ASICS for these” so you can feel fine using your computer at home. That’s great and all…until your coin starts becoming valuable and a company does decide to make dedicated hardware. Litecoin tried this, and now they have specialized mining hardware.

The following article does a wonderful job elaborating on this and other stuff I’m discussing here:

[**The State of Cryptocurrency Mining**_For those new to the blog, I am the lead developer of Sia, a blockchain based cloud storage platform. About a year ago…_blog.sia.tech](https://blog.sia.tech/the-state-of-cryptocurrency-mining-538004a37f9b?ref=hackernoon.com)

##### Memory Intensive Algorithms

I don’t think this deserve its own section but it’s so commonly thrown around I need to mention it, else someone may comment saying “You only talked about CPU’s what about things that use different parts of the computer..like RAM?”

Motherboards connect different kinds of hardware together, yes, so not all kinds of computing take place within the CPU. Some algorithms are designed to require [more RAM](https://downloadmoreram.com/?ref=hackernoon.com) to generate more hashes. All this does is prevent graphic cards from being used to mine. It does not prevent anyone from coming along and making dedicated hardware for it, and that’s where it falls short. At best it’s useful as an emergency hard-fork algorithm because no one has made dedicated hardware for this kind yet. It falls short of utility in almost all other cases. The in-development coin [Grin](https://github.com/mimblewimble/grin/blob/master/doc/pow/pow.md?ref=hackernoon.com), making use of Mimblewimble privacy technology, uses this kind of algorithm, and companies will develop hardware if it ever becomes a viable cryptocurrency *(or perceived and valued as such)*.

##### External Oracle

This is effectively “same, but different”, except there’s more than one algorithm, and they change at the leisure of the developers and/or the community. These can be planned ahead of time in intervals, where the new algorithm isn’t decided until the last moment, or it could just be spur of the moment whenever “they” feel like mining centralization has become “worrying”.

Monero is like this. Having started with a typical resistant algorithm, Bitmain ended up developing specialized hardware for it anyway, so “they” decided to spontaneously fork and change the algorithm. This is of course, *fine*, but the most important distinction here is *this is not decentralized*, at all, whatsoever, no matter what anyone tries to tell you. Anyone can be bought, blackmailed, or worse, and any sort of “voting” mechanism can and will be gamed if the coin becomes valuable enough. Furthermore, this can’t go on forever. The network can’t keep shutting down old nodes just to hard-fork to a new algorithm. You need a robust and immutable set of code moving forward so infrastructure can be built on top of the network that won’t get disabled by some spontaneous hard-fork out of desperation.

##### Programmed Alternation

This one takes the selection process and automates it. It doesn’t matter how it automates it, all you need to know is that there’s a set of algorithms it cycles through. All of these algorithms can have specialized hardware designed for it, and again, the only thing preventing this from happening is the price of the coin. If it becomes valuable enough, it will happen. There’s also the likelihood of general purpose hashing units being developed that are semi-specialized, which can immediately destroy the initial intent of the alternation without having full-blown specialized hardware developed for it yet. Ravencoin aims to do this by alternating between 16 different algorithms. Like all the other methods described above, the end result is just a system that is **more difficult** to specialize, **not impossible**.

#### 3: Where It All Began, And Why It’s Still Around

##### A Blast From The Past

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword12.jpg)

[https://bitcointalk.org/index.php?topic=45667.0](https://bitcointalk.org/index.php?topic=45667.0&ref=hackernoon.com)

> Intended to be the First, the Best, and remain so into the future.

Well…it *was* the first one. **Tenebrix**. If you’ve heard of it you probably don’t need to even read this section. The premise was simple, mining is getting harder and it’s *unfair* to those without expensive graphics cards, so let’s make something that *resists* against this.

A lot of people like to toss around the word “scam” in this ecosystem, but I think it can be a bit off-putting because nobody had a clue back then and if anybody tries to tell you otherwise, well, make your own judgment. I was mining Litecoin in 2013 *(made like $20)*. I’m not a scammer, and neither was Charlie when he announced it only 15 days after Tenebrix announced theirs. It was just an interesting concept at a time when nobody knew where any of this was going to go.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword13.jpg)

Of course the issue here is not any particular coin, but how this trend ended up playing out. While one project may have been created out of genuine interest, others were certainly scams, then there was everything in between. This *gradient of legitimacy*, along with the exponential growth of this space, is important because it helps people understand why we are still seeing this concept of resistance continue to propagate today. If there is no hard line between what is a scam and what isn’t, then there’s no way to definitively move forward and away from the confusion. Some of these coins are still around, with Litecoin being the perfect example. Litecoin’s “success” is not because of its PoW algorithm, but rather because of how closely it’s managed to mirror Bitcoin, from its development process down to its community and their ideology. This image below was meant to mock another one that floated around, but there’s some truth to it if you look closely *(except LTC did have 150 premined coins, which amounted to literally nothing until very recently)*:

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword14.jpg)

[https://twitter.com/StopAndDecrypt/status/1015988742841163776](https://twitter.com/StopAndDecrypt/status/1015988742841163776?ref=hackernoon.com)

This is a testament to the gradient of legitimacy, which Bitcoin maximalists tend to outright dismiss in favor of Bitcoin’s “immaculate conception”. It’s fine to think like that, [and I’m one of them](https://twitter.com/StopAndDecrypt/status/1001625618113552386?ref=hackernoon.com)…but I wasn't *always* one of them. Like most people, there’s an eventual realization that occurs, and like most most people, there are things that hold us back from making that mental switch. If you took all of these people and plotted them we’d get another gradient, a *gradient of mindset*. You can’t expect everyone to instantly change their minds at the same time, and so long as there exists a subset of people that think there is utility in alternative algorithms then the idea is going to propagate, especially to the new waves of people entering this space. This doesn’t make the entire group of people that support them scammers, although there are many scammers that exist among them.

And boy do they scam…

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword15.jpg)

[https://web.archive.org/web/20140209050500/https://bitcointalk.org/index.php?topic=421615.0](https://bitcointalk.org/index.php?topic=421615.0&ref=hackernoon.com)

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword16.jpg)

[https://bitcointalk.org/index.php?topic=999886.0](https://bitcointalk.org/index.php?topic=999886.0&ref=hackernoon.com)

DASH *(formerly DarkCoin)* fanboys will deny the issue with this, but it’s partly why they re-branded, with the other reason being they are no longer pretending to be a privacy coin *(dark = private)*. You can see these scams are multi-faceted, in that they use a “CPU only” algorithm as a one of many selling points to get people interested, but they then go and pre/insta-mine *millions* of coins without having to worry about competition before releasing it to everyone else. BitcoinTalk is *littered* with sketchy coin launches just like this, so it makes sense to see one of them become a “major” altcoin. It doesn’t make it any more legitimate than the others, but most people just don’t know better.

##### When Will It End?

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword17.jpg)

[https://techcrunch.com/2017/06/08/how-ethereum-became-the-platform-of-choice-for-icod-digital-assets/](https://techcrunch.com/2017/06/08/how-ethereum-became-the-platform-of-choice-for-icod-digital-assets/?ref=hackernoon.com)

Cryptocurrencies are not disappearing any time soon, and it’s likely there will always be minority chains that try to achieve the spotlight. While I can’t predict when the trend will subside, the amount of coins in existence doubled over the last year alone. A good portion of them are ICOs, but *(within the context of this article)* more notably is the introduction of new blockchain security methods. The most known of the bunch is Proof-of-Stake, but then there’s _Delegated-_PoS, Proof-of-Storage, Proof-of-Authority, Proof-of-Work *w/Masternodes*, Proof-of-Endorsement *(??)*, and Directed Acyclic Graphs …

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword18.jpg)

[https://www.coindesk.com/10-years-wont-blockchains/](https://www.coindesk.com/10-years-wont-blockchains/?ref=hackernoon.com)

The list keeps growing, and the waves of blockchain hype are slowly moving away from Proof-of-Work, particularly because it’s portrayed as a waste of energy *(more on that below)*, yet there are still are new coins in development that market themselves as ASIC resistant. As mentioned already, Ravencoin launched recently and it advertises itself as resistant by having the protocol switch between 16 different algorithms. Then there’s Grin, which is in development, that actually goes about this in a very interesting way. It’s not trying to be resistant, it’s just trying to be new by using a memory intensive PoW algorithm that will be easy to mass manufacture in the future to avoid GPU farms coming in instantly and dominating the network, allowing it to grow organically the way Bitcoin did. While I don’t think altcoins will disappear entirely anytime soon, the outlook for most of them medium-term is grim. I find it unlikely that ASIC resistance will continue to be a major selling point in the future, but likely that the hype-death cycle of altcoins will continue via other means of attraction.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword19.jpg)

[https://woobull.com/data-visualisation-118-coins-plotted-over-time-this-is-why-hodl-alt-coin-indexes-dont-work/](https://woobull.com/data-visualisation-118-coins-plotted-over-time-this-is-why-hodl-alt-coin-indexes-dont-work/?ref=hackernoon.com)

#### 4: Late Stage Mining Requires Low Barriers-To-Entry

In the first two sections I alluded to the underlying issue with trying to resist specialized hardware, and I’d hope the following conclusion has already been made: **You can’t stop it**. Instead of endlessly trying to stop something you can’t, an alternative approach would be to look at the situation rationally and find a new way to think about it.

As the title of this section suggests, I want to discuss the importance of having a low barrier-to-entry into the mining market, particularly in the “end game” scenario where a blockchain has become massively adopted. Ultimately this is the only thing that matters, because what’s the point in creating a temporarily semi-useful blockchain with no positive outlook to its future because only a few select entities can create the required hardware?

##### Major League Mining

Mining in its current state is chaotic, dirty, *sort of* disruptable, and there are too many blockchains to go around. Verge was 51% attacked, and it won’t be the last. Hashpower security *(in the form of energy expenditure)* is slowly starting to prove its necessity. Everyone has their opinion, but many refuse to think 50 or 100 years into the future when it becomes fundamentally important to have a **good** Proof-of-Work algorithm. If they do consider the future, they reference what we see today and claim it’ll have the same issues but worse. Putting the mining *skeptics* aside who prefer alternative options *(like Proof-of-Stake)*, the *pro*-mining critics typically point at geographical & manufacturer centralization as growing concerns and will toss around fast-and-loose solutions, like arbitrarily changing the Proof-of-Work to something “better”.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword20.jpg)

[https://twitter.com/CobraBitcoin/status/1014185328054239234](https://twitter.com/CobraBitcoin/status/1014185328054239234?ref=hackernoon.com)

Bitmain doesn’t have a monopoly on mining. They have a large stake in hashpower, but it’s not a monopoly. And, they’re losing more of that stake every day to more energy efficient hardware like Halong’s new DragonMint T1, and other manufacturers that are starting to produce their own ASICs outside of China, like the Japanese Internet giant [GMO](https://www.gmo.jp/en/?ref=hackernoon.com). I wouldn’t be surprised if others are engaging in this development in private as well, just like Halong was until the announcement, so you shouldn’t be either.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword21.jpg)

[https://twitter.com/KryptykHex/status/1016019655767547904](https://twitter.com/KryptykHex/status/1016019655767547904?ref=hackernoon.com)

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword22.jpg)

[https://twitter.com/KryptykHex/status/1014283645132115970](https://twitter.com/KryptykHex/status/1014283645132115970?ref=hackernoon.com)

Minings intrinsic properties imply a never-ending race to be the most energy efficient and the end result will be mining on renewable energy, which will encourage farms to grow outside of China and in close proximity of those renewable resources. We’re already seeing this migration play out without renewable energy in locations where it’s just cheaper to cool off the hardware by being located in a colder climate. It becomes even easier to do this when you can get the hardware manufactured locally, or even do it yourself. So let’s take a step back and think, which is more difficult to manufacture? An advanced piece of hardware like a modern central processing unit, or a very specific and simple to produce chip that performs a very basic hashing algorithm?

If you don’t think renewable energy is going to dominate in the future, then you should just check out this [publication by the International Energy Agency](https://www.iea.org/publications/renewables2017/?ref=hackernoon.com). I’ll just let some of the data do the talking but add in that in just 2017 alone, renewable energy **additions** were 40 times the amount of energy Bitcoin mining used in the same year. We’re going to be in such a surplus of energy that latency *(transporting it)* will become the energy supply bottleneck as demand grows. Do you think these power companies are going to standby and just let all the extra energy production go to waste? They’re going to be producing **clean** energy at rates faster than they can export it, so where do you think all of that is going to eventually go?

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword23.jpg)

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword24.jpg)

##### Headline: Lemonade Stand Startups Crippled By New Regulations

Probably the last headline you want to see as a Lemonade Stand entrepreneur when you wake up in the morning. In preparation for this day, you created a list of things that could potentially effect your new Lemonade business:

* Tariffs on Lemon imports *(costly to import Lemons from other countries)*
* Lemon farming has new regulations *(reducing supply, increasing costs)*
* Lemon DNA patents are created *(others can’t farm those kinds of lemons)*
* Major Lemon farm burns down *(reducing supply, increasing costs)*

Wouldn’t it be nice if you could just grow Lemons in your own backyard? Or rent your neighbors yard to grow Lemons for just this season, and rent then someone else’s yard next season if they have better rates? Would you have this freedom if only a limited set of your neighbors had the right kind of soil that could grow Lemon trees? Hopefully you see where I’m going with this.

When it comes to designing and fabricating hardware to process the PoW algorithm being used in Bitcoin, the last thing you want to see is 50 different companies trying to get the same single fabrication company to create hardware for them. Anyone can do research, but development ends with mass production, even if it’s just a single production run. The more complicated the hardware design is that you need created, the less likely you are to find a variety of chip manufacturers that can do this for you, and the ones ones that do exist may be production bottlenecked, or in some sort of binding contract.

Do you know why mining originally centralized in China? China has less regulations on hardware design, happened to have cheaper electricity *(or it was easier to fraudulently get cheaper electricity)*, and the hardware was relatively easy to produce. Fundamentally though, it was because of the cheap electricity where they wanted to set up mining facility, and a low cost *(distance)* to transport from the manufacturer to the mining facility.

As renewable energy starts becoming more prominent, what do you think is a better scenario over the long term?

1. Complicated hardware designs that only a select few manufacturers can produce, and mining centralizes in distance around these locations.
2. Simple hardware designs that many manufacturers can produce, and mining facilities can be reasonably spread out among the globe wherever it’s convenient to use renewable energy sources.

This kind of necessary diversity/distribution/decentralization in hardware production is promoted by a Proof-of-Work algorithm that is *the opposite* of complicated, *the opposite* of resistant, and *not* prone to getting changed.

We went over how new startups are coming online and expanding at this very moment, and that there will be more to come, but what would happen if they were stopped in their tracks?

What would happen if you have, let’s say, 10 manufacturers, but only 2 of them have been producing long enough to see a profit, and then suddenly all of their hardware is rendered obsolete?

Would they all be able to come back from that loss?

I’d bet 8 of them won’t, so what’s the point in crippling all of them except the largest ones who can recover from it and just start making new hardware?

10 manufacturers versus 2, which sounds more decentralized?

If you were a startup that was looking into mining, but you made no initial investment yet, what would you do after such a thing occurred?

Would you be more likely, or less likely to keep moving forward knowing that one day all your equipment will become obsolete?

Do you really want people being scared or hesitant to invest into mining?

How would this not result in monopolization of the mining ecosystem?

Why, again, do you think a Proof-of-Work change would help the ecosystem?

#### 5: Changing Bitcoin’s PoW Solves Nothing

Now that I’ve successfully lured you this far into my ramblings, let’s go over some recent talks about trying to change Bitcoin’s Proof-of-Work, and why it Will-Never-Work. If you don’t know the difference between hard/soft-forks, [here’s a primer](https://medium.com/@alpalpalp/chain-splits-and-resolutions-d3398bddf4ab?ref=hackernoon.com) that should be enough for this section.

##### **Temporary Relief For Never Ending False Alarms**

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword25.jpg)

This isn’t an attack on Luke, it’s just that Luke is the most vocal developer that is pushing for a change, and openly makes it clear that it would have to change again at some point in the future “until a better solution is found”. This directly implies that Bitcoin doesn’t work *as is*, which I fundamentally disagree with for all the reasons I’ve spoken about up until this point. Bitcoin PoW change advocates are only temporary relieved by their own solution and have nothing to offer that brings finality to the never ending PoW change dilemma their logic puts themselves in. Fortunately Bitcoin’s security is **not** dependent on our ability to hard-fork the PoW, and its security only grows as more hashpower comes online. This is effectively the External Oracle variant from the 2nd section, where the network’s security is completely dependent on the communities ability to come to consensus and change the PoW when we all “feel like it’s necessary”. Remember that thing about gradients of people? Yeah…Then we need to come to full consensus every time we fork the PoW?

##### Hard-Forks Intrinsically Lack Consensus (with few exceptions)

Below are excerpts of two bitcoin-dev mailing list emails from [Anthony Towns](https://twitter.com/ajtowns?ref=hackernoon.com). The emails discuss upgrading Bitcoin’s signature scheme from ECDSA to Schnorr. This upgrade, like most to follow, is set to be a soft-fork *(one of the benefits of the Segwit soft-fork)* that allows all the old functionality to continue existing, while providing the option and incentive to switch to using the new feature. This allows the network of nodes to undergo a sort of plastic upgrade, so that your node continues to function *(and not get kicked off)* even if you don’t upgrade. Additionally, it’s a **trivial** upgrade, because it **doesn’t break any of the underlying incentives** the network assumes. The suggestion below is to include within the soft-fork a 5 year “timer” at which point the network will hard-fork in the upgrade that we would have *(by then)* already had for 5 years. The hard-fork would then remove additional complexity in the code that was required with the soft-fork to keep the network together.

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword26.jpg)

[https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-May/015951.html](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-May/015951.html?ref=hackernoon.com)

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword27.jpg)

[https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-March/015838.html](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-March/015838.html?ref=hackernoon.com)

The logic surrounding this hard-fork proposal is actually quite reasonable. The soft-fork upgrade isn’t expected to be contentious in the slightest, it doesn’t break anything, doesn’t cut your own node off the network, and it only adds in a new feature. The hard-fork that is being proposed tacked on to the end of it makes a single assumption: That within 5 years, most people will have upgraded already anyway. I polled Twitter a while back and these were the anecdotal results:

I firmly consider this to be an extremely reasonable hard-fork *(as far as hard-forks go)* but I would **never** support it with results like these. If it’s split 50/50 for such a non-contestable change just because it includes a hard-fork, can you imagine ever reaching consensus on a Proof-of-Work hard-fork with an assortment of drawbacks and unknowns that may negatively affect Bitcoin’s network incentives as a result?

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword29.jpg)

[https://twitter.com/LukeDashjr/status/1019579851043475456](https://twitter.com/LukeDashjr/status/1019579851043475456?ref=hackernoon.com)

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword30.jpg)

[https://twitter.com/LukeDashjr/status/1019737295581261824](https://twitter.com/LukeDashjr/status/1019737295581261824?ref=hackernoon.com)

Unless Bitcoin’s immediate & obvious death is the only alternative, hard-forks are likely to always be contestable, and as such will **always lack consensus**. I don’t agree with the need for a PoW change, most people I engage with don’t agree that one is necessary, and there’s really only a a select few, if not a single Core developer who’s been pushing for it. I think it’s great that people think differently in this space, but consensus is never going to arrive on this subject, primarily because it solves nothing and only resets the board.

#### 6: Conclusion

To wrap things up, let’s briefly summarize my arguments:

1. Hardware specialization resistance is futile.
2. The “success” of altcoins are not reliant on resistance.
3. Proof-of-Work algorithms need to be easy to manufacture.
4. New altcoins are swimming upstream and must apply 1, 2, and 3.
5. Changing a coins Proof-of-Work does nothing for it long term.
6. Mining will be running on 100% clean energy in the future.
7. Bitcoin mining is not ideally decentralized yet, but it’s certainly improving.
8. Hard-forks require predominant consensus, if not impending doom.
9. Bitcoin will never change its PoW unless a life threatening vulnerability is found, because the current PoW ***works.***

[**StopAndDecrypt (@StopAndDecrypt) | Twitter**_The latest Tweets from StopAndDecrypt (@StopAndDecrypt). Full-Stack Social Engineer. somewhere routing around you_twitter.com](https://twitter.com/StopAndDecrypt?ref=hackernoon.com)

![](/assets/images/2018/m8/asic-resistance-is-nothing-but-a-blockchain-buzzword31.jpg)

still image for the url

***

{% include signup.md %}
