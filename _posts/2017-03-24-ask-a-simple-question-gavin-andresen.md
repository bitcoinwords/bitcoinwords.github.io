---
title: "Ask a simple question... • Gavin Andresen"
permalink: "/ask-a-simple-question-gavin-andresen"

author: gavinandresen

tags:
  - Gavin Andresen
  - 2017 Q1
  - Politics
  - Technology
  - Security

excerpt: Ask a simple question... • Gavin Andresen. Posted March 24, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Ask a simple question... • Gavin Andresen](http://gavinandresen.ninja/ask-a-simple-question)
### By [Gavin Andresen](http://gavinandresen.ninja/)
### Posted March 24, 2017

## [Ask a simple question…](http://gavinandresen.ninja/ask-a-simple-question)

This is a conversation with Matt Corallo (Bitcoin Core contributor) that started on twitter and migrated into email:

**Matt Corallo** @TheBlueMatt - Mar 19
 Bitcoin Core does not want to and does not make decisions on Bitcoin’s consensus rules

**Gavin Andresen** @gavinandresen - Mar 23
 Might a small, well-tested patch that added a default-false option to disable block-size checks be accepted by Core?

**Matt Corallo**
 if it a) took HF risks seriously and had protections for then and b) had community consensus to do a HF, sure!

**Gavin Andresen**
 I’ll email you– if you really don’t want to dictate consensus rules, give your users a choice!

**Matt Corallo**
 cool. You may also want to check out some of the HF proposals at [https://bitcoinhardforkresearch.github.io](https://bitcoinhardforkresearch.github.io)

**From: Gavin**
 **To: Matt**
 **Subject: Expanding an idea from Twitter…**

> If Core really wants to avoid taking sides in the Great Scaling Debate, why not let users simply opt-out of block size-related checks?
>
> The idea would be “IF there is a hardfork, you can run with the -anyblocksize=true option to follow the most-work branch of the chain.”
>
> On twitter you say “if it took HF risks seriously” : it is paternalistic for you to decide risk/reward, and when you do you just make lots of people really upset.
>
> … and “had community consensus to do a HF” : again, you are just making lots of people really upset by taking sides in the debate– who are you to judge community consensus?
>
> I think a neutral statement from Core like “IF there is a hard fork over the block size, Core software is able to follow either branch” along with a trivial patch/option that, again, simply skips the validation checks for max base block size / max block sigops / max segwit block size if the option is set – would be a really good way of extricating the Core project from the insanity of the debate.
>
> (I haven’t looked at the code, but maintaining a 1MB max transaction size would mitigate any quadratic hashing attack-block concerns)

**From: Matt**

> I get the paternalistic view, I really do, but that is neither the intent, nor based on reality of peoples’ views. It is very much based on a misunderstanding of what roles developers are willing to play in the community. No one wants to be a decision maker, and that feature is a key differentiator of Bitcoin when compared to alternative systems.
>
> As I’ve said many times, if a reasonable hard fork is proposed which doesnt have massive risk and has real community backing, it will be released in some supported version or branch of Core (if nothing else, supported by me). What this doesn’t mean is a hard fork with no opt-in replay protection or with a webapp to select consensus rules or a commitment to 20GB blocks or a low-hashpower-commitment activation criteria.
>
> This also doesnt mean that I wont, personally, argue against it, but if there’s real community backing, I’m happy to maintain the code. I’m not “one to judge consensus”, that is for each individual to judge, and if they think it exists they can and should run the code for it, even if it doesn’t come from Core.
>
> Because any realistic hard fork is going to have more than just a simple block size rule relaxation (activation criteria, replay protection, n**2 sighash protection, additional commitments to block data, etc, etc, see Spoonnet for a reasonable example of likely fixes), such a change only serves to mislead users into thinking they are running something other than an SPV client (might as well just have an SPV mode..we’ll likely do one of these days..when someone gets around to it).
>
> I’m disappointed that you seem to have bought into the deliberate misunderstanding of the view of most devs in the community that a few very loud voices in the community have been touting for their own political gain. If you believe something other than Bitcoin Core has consensus, you can and should run it! This is both critical to Bitcoin’s success and a deeply held view by every serious developer I know. The view that developers are refusing to allow a consensus change that has real community backing is more than a little insulting, and only exists to create diviceness and attempt a negotiation with a group that can’t negotiate except as individuals who can, individually, advocate to the community for changes.

**From: Gavin**

> So… that’s a no?
>
> Would a command-line option to allow users to say ‘I want to go along with hashpower consensus when it comes to block size’ be unacceptable for some reason?
>
> No code related to a hard fork AT ALL, zero expression on what the max block size should or shouldn’t be…
>
> Also: would you be willing to make this conversation public?

**From: Matt**

> That is a “you know as well as I do that no one individual can or should make decisions about forks”. Have you seen [https://bitcoinhardforkresearch.github.io](https://bitcoinhardforkresearch.github.io) with recent proposed hard forks by Core contributors? I helped a ton early and contributed some to Johnson’s most recent one, but then I assume you saw the bitcoin-dev discussion and coindesk article about it. Sadly the community seems to have a much lower appetite for hard fork proposals these days, or at least has no interest in any of those proposals.
>
> If you want to follow hashpower, great! You’re an SPV Client, and there are many great SPV clients out there for people to run.
>
> As for making it public, oops…I already posted my response (with your name and original email omitted, of course).

***

{% include signup.md %}
