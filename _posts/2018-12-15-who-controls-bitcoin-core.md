---
title: "Who controls Bitcoin Core?"
permalink: "/who-controls-bitcoin-core" 

tags:
  - CY18 Q4
  - Jameson Lopp

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

# Who Controls Bitcoin Core?
### By [Jameson Lopp](https://medium.com/@lopp)
### Posted December 15, 2018

The question of who controls the ability to merge code changes into [Bitcoin Core](https://bitcoincore.org)'s [GitHub repository](https://github.com/bitcoin/bitcoin) tends to come up on a recurring basis. This has been cited as a "central point of control" of the Bitcoin protocol by various parties over the years, but I argue that the question itself is a red herring that stems from an authoritarian perspective — this model does not apply to Bitcoin. It's certainly not obvious to a layman as to why that is the case, thus the goal of this article is to explain how Bitcoin Core operates and, at a higher level, how the Bitcoin protocol itself evolves.

### The History of Bitcoin Core

Bitcoin Core is a [focal point](https://en.wikipedia.org/wiki/Focal_point_%28game_theory%29) for development of the Bitcoin protocol rather than a point of command and control. If it ceased to exist for any reason, a new focal point would emerge — the technical communications platform upon which it's based (currently the GitHub repository) is a matter of convenience rather than one of definition / project integrity. In fact, we have already seen Bitcoin's focal point for development change platforms and even names!

* In early 2009 the source code for the Bitcoin project was [simply a .rar file](http://www.metzdowd.com/pipermail/cryptography/2009-January/014994.html) hosted on SourceForge. Early developers would actually exchange code patches with Satoshi [via email](https://online.wsj.com/public/resources/documents/finneynakamotoemails.pdf).
* On October 30 2009, Sirius ([Martti Malmi](https://medium.com/@mmalmi)) [created a subversion repository](https://sourceforge.net/p/bitcoin/code/1/) for the Bitcoin project on SourceForge
* In 2011, the [Bitcoin project migrated](https://sourceforge.net/p/bitcoin/code/252) from SourceForge to [GitHub](https://github.com/bitcoin/bitcoin/commit/ca40e581ebcdc85dba15c1e873f5e5aedda45b77)
* In 2014 the Bitcoin project [was renamed to Bitcoin Core](https://github.com/bitcoin/bitcoin/pull/3408)

### Trust No One

While there are a handful of GitHub "maintainer" accounts at the organization level that have the ability to merge code into the master branch, this is more of a janitorial function than a position of power. If anyone could merge into master it would very quickly turn into a "too many cooks in the kitchen" scenario. Bitcoin Core follows principles of least privilege that any power bestowed to individuals is easily subverted if it is abused.

![Peter Todd tweet](/assets/images/cy18/cy18q4m12/lopp-1.png){: .align-center}

From an adversarial perspective, GitHub can not be trusted. Any number of GitHub employees could use their administrative privileges to inject code into the repository without consent from the maintainers. But it's unlikely that a GitHub attacker would also be able to compromise the PGP key of a Bitcoin Core maintainer.

Rather than base the integrity of the code off of GitHub accounts, Bitcoin Core has a continuous integration system that performs checks of trusted PGP keys that must sign every merge commit. While these keys are tied to known identities, it's still not safe to assume that it will always be the case — a key could be compromised and we wouldn't know unless the original key owner notified the other maintainers. As such, the commit keys do not provide perfect security either, they just make it more difficult for an attacker to inject arbitrary code.

### The Keys to the Kingdom

At time of writing, [these are the trusted PGP fingerprints](https://github.com/bitcoin/bitcoin/blob/master/contrib/verify-commits/trusted-keys):

> 71A3B16735405025D447E8F274810B012346C9A6
> 133EAC179436F14A5CF1B794860FEB804E669320
> 32EE5C4C3FA15CCADB46ABE529D4BCB6416F53EC
> B8B3F1C0E58C15DB6A81D30C3648A882F4316B9B
> CA03882CB1FC067B5D3ACFE4D300116E1C875A3D

These keys are registered to:

> Wladimir J. van der Laan <[laanwj@protonmail.com](mailto:laanwj@protonmail.com)>
> Pieter Wuille <[pieter.wuille@gmail.com](mailto:pieter.wuille@gmail.com)>
> Jonas Schnelli <[dev@jonasschnelli.ch](mailto:dev@jonasschnelli.ch)>
> Marco Falke <[marco.falke@tum.de](mailto:marco.falke@tum.de)>
> Samuel Dobson <[dobsonsa68@gmail.com](mailto:dobsonsa68@gmail.com)>

Does this mean that we are trusting these five people? Not quite. Keys are not a proof of identity — these keys could potentially fall into the hands of other people. What assurances do you really get if you run the verify-commits python script?

> python3 contrib/verify-commits/verify-commits.py
> Using verify-commits data from bitcoin/contrib/verify-commits
> All Tree-SHA512s matched up to 309bf16257b2395ce502017be627186b749ee749
> There is a valid path from "HEAD" to 82bcf405f6db1d55b684a1f63a4aabad376cdad7 where all commits are signed!

The [verify-commits](https://github.com/bitcoin/bitcoin/tree/master/contrib/verify-commits) script is an integrity check that any developer can run on their machine. When executed, it checks the PGP signature on every single merge commit since commit 82bcf405... in December 2015 — over 3,400 merges at time of writing. If the script completes successfully, it tells us that every line of code that has been changed since that point has passed through the Bitcoin Core development process and been "signed off" by someone with a maintainer key. While this is not a bulletproof guarantee that no one has injected malicious code (a maintainer could go rogue or have their keys stolen), it reduces the attack surface for doing so enormously. What are maintainers and how did they attain this role? We'll dig into that a bit later.

### Layered Security

The integrity of Bitcoin Core's code must not rely solely upon a handful of cryptographic keys, which is why there are a multitude of other checks in place. There are many layers of security here to provide defense in depth:

#### Pull Request Security

1. Anyone is free to propose code changes to improve the software by opening a pull request against the master branch on [bitcoin/bitcoin](https://github.com/bitcoin/bitcoin).
2. Developers review pull requests to ensure that they are not harmful. Anyone is free to review pull requests and provide feedback — there is no gatekeeper or entrance exam when it comes to contributing to Bitcoin Core. If a pull request gets to the point that there are no reasonable objections to it being merged, a maintainer makes the merge.
3. Core maintainers set [this pre-push hook](https://github.com/bitcoin/bitcoin/blob/master/contrib/verify-commits/pre-push-hook.sh) to ensure that they don't push unsigned commits into the repository.
4. Merge commits are optionally securely timestamped [via OpenTimestamps](https://github.com/bitcoin/bitcoin/blob/ebd786b72a2a15143d7ef4ea2229fef121bd8f12/contrib/devtools/README.md#create-and-verify-timestamps-of-merge-commits)
5. The [Travis Continuous Integration system](https://travis-ci.org/bitcoin/bitcoin) regularly runs [this script](https://github.com/bitcoin/bitcoin/blob/master/.travis/lint_06_script.sh) to check the integrity of the git tree (history) and to verify that all commits in the master branch were signed with one of the trusted PGP keys.
6. Anyone who wants to can run [this script](https://github.com/bitcoin/bitcoin/blob/master/contrib/verify-commits/verify-commits.py) to verify the PGP signatures on all of the merge commits going back to December 2015. I ran it while writing this article and it took 25 minutes to complete on my laptop.

#### Release Security

1. [Gitian](https://gitian.org/) deterministic build systems are run independently by multiple developers with the goal of creating identical binaries. If someone manages to create a build that doesn't match the builds of other developers, it's a sign that non-determinism was introduced and thus the final release isn't going to happen. If there is non-determinism, developers track down what went wrong, fix it, then build another release candidate. Once a deterministic build has succeeded then the developers sign the resulting binaries, guaranteeing that the binaries and tool chain were not tampered with and that the same source was used. This method removes the build and distribution process as a single point of failure. Anyone with the technical skills can run their own build system; the [instructions are here](https://github.com/bitcoin-core/docs/blob/master/gitian-building.md).
2. Once the Gitian builds have completed successfully and been signed off by the builders, a Bitcoin Core maintainer will PGP sign a message with the SHA256 hashes of each build. If you decide to run a prebuilt binary, you can check its hash after downloading and then verify the authenticity of the signed release message with the hashes. Instructions for doing so [can be found here](https://bitcoincore.org/en/download/).
3. All of the above is open source and auditable by anyone with the skills and desire to do so.
4. Finally, even after going through all of the above quality and integrity checks, code that is committed into Bitcoin Core and eventually rolled into a release is not deployed out onto the network of nodes by any centralized organization. Rather, each node operator must make a conscious decision to update the code they run. **Bitcoin Core deliberately does not include an auto-update feature, since it could potentially be used to make users run code that they didn't explicitly choose**.

Despite all of the technical security measures that are implemented by the Bitcoin Core project, none of them are perfect and any of them can theoretically be compromised. The last line of defense for the integrity of Bitcoin Core's code is the same as any other open source project — _constant vigilance_. The more eyes that are reviewing Bitcoin Core's code, the less likely that malicious or flawed code will make it into a release.

### Code Coverage

Bitcoin Core has a lot of testing code. There is an integration test suite that runs against every PR and an extended test suite that runs every night on master.

You can check the code coverage of the tests yourself by:

1. Cloning the Bitcoin Core GitHub repository
2. Installing the [required dependencies](https://github.com/bitcoin/bitcoin/tree/master/doc#building) for building from source
3. Running [these commands](https://github.com/bitcoin/bitcoin/blob/master/doc/developer-notes.md#compiling-for-test-coverage)
4. Viewing the report at ./total_coverage/index.html

Alternatively, you can view the coverage report Marco Falke [hosts here](https://drahtbot.github.io/reports/coverage/bitcoin/bitcoin/master/total.coverage/index.html).

![Code Coverage Report](/assets/images/cy18/cy18q4m12/lopp-2.png){: .align-center}*Code Coverage Report*

Having such a high level of test coverage means that there is a higher level of certainty that the code functions as intended.

Testing is a big deal when it comes to consensus critical software. For particularly complex changes, developers sometimes perform painstaking mutation testing — that is, they test the tests by purposely breaking the code and seeing if the tests fail as expected. Greg Maxwell gave some insight into this process when he discussed the 0.15 release:

> "The test is the test of the software, but what's the test of the test? The software. To test the test, you must break the software." — Greg Maxwell

<iframe width="560" height="315" src="https://www.youtube.com/embed/nSRoEeqYtJA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Free Market Competition

BitMEX wrote a great article about the ecosystem of Bitcoin implementations. There are over a dozen different Bitcoin compatible implementations, and even more "competing network" implementations. This is the freedom of open source — anyone who is dissatisfied with the efforts of the Bitcoin Core project is free to start their own project. They can do so from scratch or they can fork the Core software.

[**Competing with Bitcoin Core** _Abstract: We examine the power and dynamics of the "Bitcoin Core" software project and we draw distinctions between the..._blog.bitmex.com](https://blog.bitmex.com/bitcoin-cores-competition/ "https://blog.bitmex.com/bitcoin-cores-competition/")

At time of writing, 96% of reachable Bitcoin nodes are running some version of Bitcoin Core. Why is this the case? How can Bitcoin Core have near-monopoly status over the network of nodes if the effort required to switch to another software implementation is minimal? After all, many other implementations provide RPC APIs that are compatible with, or at least highly similar to Bitcoin Core.

I believe that this is a result of Bitcoin Core being a focal point for development. It has orders of magnitude more developer time and talent backing it, which means that the code produced by the Bitcoin Core project tends to be the most performant, robust, and secure. Node operators don't want to run the second best software when it comes to managing money. Also, given that this is consensus software and the Bitcoin protocol does not — and arguably can not — have a formal specification because no one has the authority to write one, it's somewhat safer to use the focal point implementation because you're more likely to be bug-for-bug compatible with most of the rest of the network. In this sense, the code of the development focal point is the closest thing to a specification that exists.

### Who Are the Core Developers?

People who are unfamiliar with the [Bitcoin Core development process](https://github.com/bitcoin/bitcoin/blob/master/CONTRIBUTING.md) may look at the project from the outside and consider Core to be a monolithic entity. This is far from the case! There are frequent disagreements between Core contributors and even [the most](https://github.com/bitcoin/bitcoin/pulls?utf8=%E2%9C%93&q=is%3Aclosed+is%3Aunmerged+is%3Apr+author%3Alaanwj) [prolific contributors](https://github.com/bitcoin/bitcoin/pulls?utf8=%E2%9C%93&q=is%3Aclosed+is%3Aunmerged+is%3Apr+author%3Asipa+) have written plenty of code that has never been merged into the project. If you read the guidelines for contributing you may note that they are fairly loose — the process could be best described as "[rough consensus](https://tools.ietf.org/html/rfc7282)."

> Maintainers will take into consideration if a patch is in line with the general principles of the project; meets the minimum standards for inclusion; and will judge the general consensus of contributors.

Who are the Bitcoin Core maintainers? They are contributors who have built up sufficient social capital within the project by making quality contributions over a period of time. When the existing group of maintainers believes that it would be prudent to extend the role to a contributor who has exhibited competence, reliability, and motivation in a certain area, they can grant commit access to that person's GitHub account. The lead maintainer role is for someone who has oversight over all aspects of the project and is responsible for coordinating releases. It has been voluntarily passed along over the years:

* [S](https://sourceforge.net/p/bitcoin/code/165)atoshi Nakamoto: 1/3/09 -[2/23/11](https://sourceforge.net/p/bitcoin/mailman/message/27102906/)
* [Gavin Andresen](https://medium.com/@gavinandresen):[2/23/11](https://sourceforge.net/p/bitcoin/mailman/message/27102906/) -[4/7/14](https://bitcoinfoundation.org/bitcoin-core-maintainer-wladimir-van-der-laan/)
* [Wladimir](https://medium.com/@orionwl) van der Laan:[4/7/14](https://bitcoinfoundation.org/bitcoin-core-maintainer-wladimir-van-der-laan/) — present

Acting as a Bitcoin Core maintainer is often referred to as janitorial work because maintainers don't actually have the power to make decisions that run contrary to the consensus of contributors or of the users. However, the role can be quite taxing due to the extra attention from the ecosystem at large. For example, Gregory Maxwell gave up his maintainer role in 2017 [for personal reasons](https://www.reddit.com/r/Bitcoin/comments/3x7mrr/gmaxwell_unullc_no_longer_a_bitcoin_committer_on/cy29vkx/), likely due to the public pressure he experienced during the scaling debate. Wladimir wrote a thoughtful post about the stress of being a Core maintainer and why it was appropriate to remove Gavin's commit access, which upset a lot of people.

[**Dazed and confused, but trying to continue** _I'm happy with the job I'm doing, happy to work with a few very smart people on an extremely interesting project..._laanwj.github.io](https://laanwj.github.io/2016/05/06/hostility-scams-and-moving-forward.html "https://laanwj.github.io/2016/05/06/hostility-scams-and-moving-forward.html")

Similarly, when [Jeff Garzik](https://medium.com/@jgarzik) was removed from the GitHub organization, he and others were upset about it, but he [had not contributed to Core in two years](https://www.reddit.com/r/Bitcoin/comments/6uec40/jeff_garzik_has_been_removed_from_the_bitcoin/). Leaving his GitHub account with write access to the repository was providing no benefit to the project — it was only creating a security risk and violated the principle of least privilege to which Wladimir referred in his post.

Others may look at Core and believe it to be a technocracy or ivory tower that makes it difficult for new entrants to join. But if you speak to contributors, you'll find that's not the case. While only [a dozen people](https://bitcointalk.org/index.php?topic=1774750.0) have had commit access over the years, hundreds of developers have made contributions. I myself have made a few small contributions; while I don't consider myself a "Core developer" I _technically_ am one. No one can stop you from contributing!

One of the most difficult things for people to wrap their mind around seems to be that the focal point for Bitcoin development is **not** simply the structure that is defined by the Bitcoin Core GitHub account. While Bitcoin Core has some structure (it uses centralized communications channels in order to coordinate), the project itself is not subject to being controlled by any of its participants — even those who have escalated privileges on the GitHub repository. While it is _technically_ possible for a maintainer-organized coup to hijack the GitHub repository, censor dissenting developers, and perhaps even maintain the brand name of "Bitcoin Core," the result would be that Bitcoin Core would stop being the development focal point. Developers who disagreed with the actions of the maintainers would simply fork the code and shift their work to a different repository over which the Bitcoin Core maintainers had no administrative privileges.

Even absent a "coup" per se, if a controversial change did somehow make it into Core, some developers would fork the software, remove the controversial change, and make it available for users. You could argue that this is exactly what happened when Amaury Sechet forked Bitcoin Core and removed the Segregated Witness functionality to create Bitcoin ABC. Alternatively, if Core rejects proposed changes that some people want, developers can fork it and add those changes. This has happened many times, such as when:

* [Mike Hearn](https://medium.com/@octskyward) forked Core to create Bitcoin XT
* [Andrew Stone](https://medium.com/@g.andrew.stone) forked Core to create Bitcoin Unlimited
* [Jeff Garzik](https://medium.com/@jgarzik) forked Core to create BTC1

Forking the code is easy. Shifting the focal point of Bitcoin development is hard — you must convince contributors that their time is better spent contributing to a different project.

It's also hard to convince many people that users do not blindly follow Bitcoin Core's changes — this may be a self reinforcing belief, because if users don't participate in the consensus process by staying aware of their options, they are ceding some of their power to developers. However, the power of the users was exercised during the UASF (User Activated Soft Fork) movement of 2017. An anonymous Bitcoin developer using the pseudonym [shaolinfry](https://medium.com/@shaolinfry) proposed [BIP 148](https://github.com/bitcoin/bips/blob/master/bip-0148.mediawiki), which would force miners to activate Segregated Witness functionality at a block height that would occur near August 1. However, BIP 148 proved to be too controversial to be adopted by Bitcoin Core, so shaolinfry forked Core and made "[Bitcoin UASF](https://github.com/UASF/bitcoin)" software available. This software implementation [gained a nontrivial amount of traction](https://www.uasf.co/) and [seemed to create sufficient pressure](https://hackernoon.com/bip-148-uasf-first-year-anniversary-a-new-system-of-governance-223907ec298b) to convince miners to adopt [BIP 91](https://github.com/bitcoin/bips/blob/master/bip-0091.mediawiki) to activate the fork before the BIP 148 deadline.

In my opinion the best Bitcoin Core contributors are those who practice [extreme ownership](https://www.youtube.com/watch?v=ljqra3BcqWM). Case in point — while [John Newbery](https://medium.com/@jfnewbery) did not write the code that contained this particular consensus bug, he feels responsible for not preventing it from being merged via careful review and for not finding it later while writing test cases.

We are all Satoshi.

Visualization of Bitcoin Core development

### Contributing to Bitcoin Core

It can feel daunting to start contributing to Core, though there are plenty of resources available to help aspiring developers. The guidelines for contributing [can be found here](https://bitcoincore.org/en/faq/contributing-code/) though you may wish to start off with [Jimmy Song](https://medium.com/@jimmysong)'s gentle introduction:

[**A Gentle Introduction to Bitcoin Core Development** _If you're a developer and you own any Bitcoin at all, contributing to Bitcoin Core can be one of the best things you..._bitcointechtalk.com](https://bitcointechtalk.com/a-gentle-introduction-to-bitcoin-core-development-fdc95eaee6b8 "https://bitcointechtalk.com/a-gentle-introduction-to-bitcoin-core-development-fdc95eaee6b8")

Core developer [Eric Lombrozo](https://medium.com/@elombrozo) also penned a piece about understanding how changes take place within the Core repository:

[**The Bitcoin Core Merge Process** _A major point of confusion, especially among people who have not worked a lot on free open source software development..._medium.com](https://medium.com/@elombrozo/the-bitcoin-core-merge-process-74687a09d81d "https://medium.com/@elombrozo/the-bitcoin-core-merge-process-74687a09d81d")

[Alex B.](https://medium.com/@bergealex4) wrote an excellent article about the philosophy behind Bitcoin development — anyone who wants to become a serious contributor can save themselves a lot of time by reading this.

[**The Tao Of Bitcoin Development** _Over the last few years, the buzz generated by Bitcoin's scaling debate has drawn unprecedented attention towards the..._medium.com](https://medium.com/@bergealex4/the-tao-of-bitcoin-development-ff093c6155cd "https://medium.com/@bergealex4/the-tao-of-bitcoin-development-ff093c6155cd")

A specific example may be helpful — while writing this article I encountered difficulties while trying to run the verify-commits.py script on my machine in order to audit the integrity of the GitHub commit history. In order to save future developers from having to deal with these issues, I [opened a pull request to improve the documentation](https://github.com/bitcoin/bitcoin/pull/14809). As you can see from the PR history, 4 different developers chimed in with suggestions for how I could improve my pull request. This ranged from using different wiki markup to a simplified bash command to a new parameter that could be used in the verify-commits.py script. I agreed that all of the suggestions made sense, so I incorporated them into my code and pushed an updated version for my pull request. At that point, the developers who were participating in the review acknowledged that they found the PR to be acceptable, and maintainer [Marco Falke](https://github.com/MarcoFalke) tagged it for inclusion in the 0.18 release. After several more days went by with no objections from developers, the code was merged into Core by maintainer Samuel Dobson.

### Who Controls Bitcoin?

As I've [argued extensively](http://www.coindesk.com/nobody-understands-bitcoin-thats-ok/) over the years, it's practically impossible to fully comprehend Bitcoin as a system. The definition (control) of Bitcoin the protocol is like the definition of a language. Languages emerge spontaneously; the consensus over the meaning of words is organic rather than dictated by dictionaries. Much as dictionaries describe the phenomenon of a language rather than define it, so do Bitcoin implementations describe the language of Bitcoin with code. No one is forced to agree with the definition of a given word in a dictionary, neither are they forced to agree with code in a given Bitcoin implementation by running it.

Languages are not governed by democracy and neither is Bitcoin; while you may hear people make references to miners, nodes, developers, or users "voting" there is no such mechanism that can enable a majority vote of any kind to coerce a minority of dissenters into accepting changes with which they disagree. Bitcoin is anarchy — without rulers, but not without rules. The rules are defined and enforced by individual participants on the network .

While changes to the Bitcoin protocol itself are usually made via the [Bitcoin Improvement Proposal](https://github.com/bitcoin/bips/blob/master/README.mediawiki) process, even this is only a recommended best practice and no one can be forced to follow it. It is merely a more formalized way of trying to guide a change through a process of peer review and consensus building.

As difficult as this is to explain and understand, it is a crucial aspect to Bitcoin's antifragility — if there was a single point of control, it would also be a single point of failure that would be exploited by powerful entities that are threatened by Bitcoin's success. Ultimately, each node operator governs themselves by ensuring that no one else on the network is breaking the rules to which they agree. [This security model](http://www.coindesk.com/bitcoins-security-model-deep-dive/) is the foundation for Bitcoin's bottom-up governance.


How self governance results in emergent consensus.

No one controls Bitcoin.

No one controls the focal point for Bitcoin development.


Thanks to [John Newbery](https://medium.com/@jfnewbery?source=post_page).
