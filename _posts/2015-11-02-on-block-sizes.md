---
title: "On block sizes"
permalink: "/on-block-sizes"

author: mikehearn

tags:
  - Mike Hearn
  - 2015 Q4
  - Mining
  - Scaling
  - Governance

excerpt: On block sizes. Posted November 2, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [On block sizes](https://medium.com/@octskyward/on-block-sizes-e047bc9f830)
### By Mike Hearn
### Posted November 2, 2015

[这是文章的中文翻译。](https://medium.com/@octskyward/%E6%AF%94%E7%89%B9%E5%B8%81%E5%8C%BA%E5%9D%97%E5%A4%A7%E5%B0%8F%E7%9A%84%E9%97%AE%E9%A2%98-a4a25d30485f#.g7o9tzpnd)

The Bitcoin block size issue is currently deadlocked, with nothing happening. Nor is anything going to happen: unlike what the community has been led to believe, the Bitcoin Core maintainers are not going to give the community a block size increase regardless of how many people want one.

In this article I will cover the current status of BIP 100, why Bitcoin Core is not going to raise the block size limit, the recent admission that Core doesn’t actually use consensus to make decisions, and why the conference in December isn’t going to change anything.

#### BIP 100

About 60% of the hash power is currently voting for BIP 100. Whilst I understand why miners like the idea, here’s the current status:

* BIP 100 is not implemented.
* Jeff has not been working on it. He has been working on different projects (a little virtual machine called Moxiebox and also changing database layers). BIP 100 is “in the queue”.
* Even if someone does implement it, the code won’t be accepted into Core: the two Bitcoin Core maintainers who have the final say have not stated any support for it, and they don’t seem to believe in miner voting anyway.

#### Core is against miner voting

At the Scaling Bitcoin conference in Montreal discussion of actual proposals was forbidden, but nonetheless there was an “illegal discussion” held in a corridor. [According to a summary](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-September/011031.html) it concluded almost nothing, but one thing apparently everyone agreed on was this:

```
- Hard fork method:  Leaning towards "if (timestamp > X)" flag day hard fork Y months in the future.  Set high bit in version, resulting in a negative number, to more cleanly fork away.  "miner advisement" - miners, as they've done recently, signal non-binding (Bitcoin Core does not examine the value) engineering readiness for a hard fork via coinbase moniker. Some fork cancellation method is useful, if unsuccessful after Z time elapses.
```

Translated into English, this states that — unlike BIP 100 or BIP 101 — there would be *no miner voting at all*, not even on readiness to trigger the change.

Instead, miners would merely “advise” their opinions and the Bitcoin Core maintainers would then examine the advice and decide whether to ignore it or not. The fork would then happen on their chosen date regardless of how many miners had upgraded or whether there was any community support for it. As there’s no vote, some sort of (unspecified but presumably centralised) method would be created by which the Bitcoin Core maintainers can cancel the fork.

It’s very surprising that after criticising myself and Gavin for suggesting “only” 75% voting support for making a change, the one thing the handful of Bitcoin Core devs at the conference could agree on was that *if* the block size changed, the level of miner support for the change should be *entirely irrelevant*.

All this doesn’t matter much though, because:

#### Core won’t raise the limit

There’s a widespread belief in the Bitcoin community that all Bitcoin developers want the block size to rise and all that’s required is enough time for them to reach consensus about the best way to do it. These beliefs probably come from the fact that the community has repeatedly been told that by people involved in development.

Both beliefs are entirely wrong.

When you boil away the noise, there are only 5 people in the world who can make changes to the Bitcoin Core source code:

* Gavin Andresen
* Jeff Garzik
* Wladimir van der Laan (the official maintainer, the man who does releases)
* Gregory Maxwell (Blockstream)
* Pieter Wuille (Blockstream)

Of those, three (Gavin, Jeff, Pieter) won’t make changes that upset the other two. This means that in practice those two men control the Core repository: Wladimir van der Laan and Gregory Maxwell.

Wladimir van der Laan (the maintainer) put himself down early on as “weakly against”. In fact, here is what he [thinks about the block size issue](http://coinjournal.net/who-asked-wlad-what-does-bitcoins-lead-developer-say-about-scaling-debate-exclusive/) after months of debate:

> Yes, [my position remains the same]. If we’ve learned anything from the 2008 subprime bubble crisis it should be that nothing ever keeps growing exponentially, and assuming so can be hazardous …. Changing the rules in a decentralized consensus system is a very difficult problem and
>
> I don’t think we’ll resolve it any time soon
>
> .

Remember, this is the man who effectively runs Bitcoin, due to Core’s monopoly status amongst miners. He believes that technological progress isn’t going to keep going because in 2008 a lot of banks made bad loans to American homeowners.

There is illogical in the extreme: computer speeds have nothing to do with subprime lending practices. The financial crisis wasn’t caused by exponential growth.

So in case you are waiting for Core to make a move, remember this: there cannot be any code added to a Core release without Wladimir being satisfied with it. And he believes that *any change to the block size* *at all* simply can’t happen “any time soon”.

What does Maxwell think about a block size increase? He contradicts himself regularly; claiming he wants an increase but simultaneously stating he thinks it shouldn’t happen. So far, Maxwell has clearly stated support for *zero*block size proposals*.*Judge people by their actions rather than their words: when Gavin and I asked him to put a specific counterproposal on the table he answered with [the Lightning Network](https://medium.com/@octskyward/the-capacity-cliff-586d1bf7715e) (and 1mb blocks forever).

I think Bitcoin Core isn’t going to let the blockchain grow into the future. Not now, not in December, not ever. The two people who can push the button for adding code to Core won’t allow it.

#### Conflicts of interest

Many of the Bitcoin Core developers have been hired by Blockstream, a company that recently announced a [private, subscription-based side chain called Liquid](http://www.coindesk.com/blockstream-commercial-sidechain-bitcoin-exchanges/). It’s intended to connect Bitcoin exchanges together.

This is a problem because it means the developers the Bitcoin community are trusting to shepherd the block chain are **strongly** incentivised to ensure it works poorly and never improves. So it’s unsurprising that Blockstream’s official position is that the block chain should hardly change, even for simple, obvious upgrades like bigger block sizes.

Here’s a list of Bitcoin Core developers [that have been hired by Blockstream](https://blockstream.com/team/):

* Gregory Maxwell (has commit access)
* Matt Corallo
* Jorge Timon
* Mark Friedenbach (who posts as maaku)
* Patrick Strateman (who posts as phantomcircuit)
* Warren Togami
* Adam Back
* Pieter Wuille (has commit access)

#### Developer consensus is a lie

But perhaps despite that, you still think that Core will do something if some sort of agreement amongst developers is reached. Undoubtably you have read this claim many times already, along with the related claim that changes can’t happen if they’re ‘controversial’.

Both claims are untrue.

Core makes changes when the guys with commit access decides to do so, not when everyone agrees ….. and Maxwell [recently admitted it](http://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-October/011397.html) during a debate in which people were disagreeing with a change to the Bitcoin protocol rules that he wanted to see happen:

```
> [thomas zander] The point is that Bitcoin Core claims to have > a consensus mechanism and sticks to "no change" on not > reaching a consensus. And that rule is the reason why > bigger blocks were blocked for years.[gmaxwell] You're repeating Mike's claims there-- not anyone elses.
```

This statement is incredible: he flatly denies that a block size increase is waiting for agreement …. and then says that’s something I made up!

Fact check: In May, [Gregory Maxwell himself said](http://www.mail-archive.com/bitcoin-development@lists.sourceforge.net/msg07462.html) *“Hardfork changes should only be made if they’re almost completely uncontroversial”*. He was replying to an email from Matt Corallo (another Blockstream employee), in which [Matt said](http://www.mail-archive.com/bitcoin-development@lists.sourceforge.net/msg07451.html):

> “a consensus in this kind of technical community should be a basic requirement for any serious commitment to blocksize increase.”

In May, Pieter Wuille (one of the other 5 people who can commit changes to the code) said [*“I don’t think we can do a hard fork that is controversial in nature”*](http://www.mail-archive.com/bitcoin-development@lists.sourceforge.net/msg07466.html)*.*In August he again said, *“Bitcoin’s consensus rules are a consensus system, not a democracy. Find a solution that everyone agrees on, or don’t.”*

Adam Back (president of Blockstream and Maxwell’s boss) [told IEEE Spectrum magazine](http://spectrum.ieee.org/tech-talk/computing/networks/the-bitcoin-for-is-a-coup), *“Everybody should be in agreement and we should try to do this in concert.”*

Most critically, van der Laan — the maintainer of Core — [said in June](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-June/008775.html):

> …. anything that is controversial needs to be considered really carefully. If I suddenly start making changes to the consensus code without full agreement, by all means take away my commit privileges

The claim that Core demands full agreement**to change the consensus code wasn’t made by me, it was made **by the guy who runs the project.**

So why did Gregory suddenly spin 180 degrees like that?

Simple: suddenly a change he wanted had become controversial. People were disagreeing with him, so the need for agreement had to go. What better way to do it *than claiming it had never existed at all*?

By the way, undoubtably someone will claim that there are two classes of changes (soft and hard) and only the hard type needs full agreement. Don’t be fooled by this type of evasion: the same people commit changes to the code in the same way for any kind of change. Defining a technical category of change that has a single thing in it (block sizes) and then claiming everyone must agree *only for that kind of change*is just another way of telling the community to shut up about block sizes.

#### Why December won’t change anything

In talking with miners and companies, one thing I’m hearing repeatedly is “we will wait for the second conference in December. If there’s no progress by then, we’ll switch to BIP 101”.

It seems that many, many people in the community believe that there is a commitment to have a solution by December. At the first conference, [Gavin was explicitly promised there would be progress](https://www.reddit.com/r/Bitcoin/comments/3mo3ft/several_blocksize_bips_have_now_been_discussed_at/cvhl1m6?context=3):

> I’m giving Greg/Pieter/wlad a couple weeks to do what they said they’d do in Montreal — work on a solution everybody is unhappy with but everybody can live with.

If you haven’t been convinced by what you saw above already, consider the Montreal conference was over a month ago. Nothing has happened: the topic isn’t even mentioned in their weekly meetings. Only five weeks remain until the conference in Hong Kong. **Five weeks** for them to meet their promise of finding a solution “everyone can live with” … if they start tomorrow.

Here’s a bold prediction: they’re going to show up at the conference having violated the promise they made to Gavin. They will show up with nothing.

I keep being asked if I’m planning on going to Hong Kong. I’m not planning to and neither is Gavin. If the Bitcoin Core and Blockstream guys need two conferences and 10 months to decide how to change a single number that’s their problem: Gavin, myself and others were able to debate, choose, test, review and ship a specific proposal months ago.

#### Conclusion

The Bitcoin community is scared. I get that. Fighting and conflict is always scary; and miners with big investments worry that a controversial change could drop the price and cause them to lose money.

But every Bitcoin user, miner and investor faces a stark choice:

* Bitcoin Core: a project run by two men who have shown clear opposition to the block chain having a future. One of them works for a company that makes more money the worse the block chain gets: conflicts of interest don’t get more extreme than that.
* Bitcoin XT: a project run by two men who already shipped a compromise solution that reflects the demands of miners, users and companies.

Decentralisation comes not from some nebulous developer process that’s ignored the moment it goes against what Blockstream wants. It comes from people’s ability to be informed and then choose software that matches their beliefs. As it always did.

***

{% include signup.md %}
