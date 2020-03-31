---
title: "Bitcoin Core Contributor Challenges"
permalink: "/bitcoin-core-contribution-challenges"

author: jamesonlopp

tags:
  - Jameson Lopp
  - CY20 Q1
  - Technology
  - Core
  - Bitcoin Core
  - PR
  - Pull Requests
  - Development

excerpt: Jameson Lopp examines Bitcoin Core developers activity. Posted March 14, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin Core Contributor Challenges](https://blog.lopp.net/bitcoin-core-contributor-challenges/)
### By [Jameson Lopp](https://twitter.com/lopp)
### Posted March 14, 2020

![Bitcoin Core Contributor Challenges](/assets/images/2020/m3/jl1.png)

Bitcoin Core is an open source project that is the schelling point for development of the Bitcoin protocol; it is often referred to as the "reference implementation" because it is by far the most mature Bitcoin software with more contributors and activity than any other implementation by far. While it has changed names and even platforms several times, it is the original organization started by Satoshi Nakamoto.

![](/assets/images/2020/m3/jl2.png)

But Bitcoin Core isn't like most open source projects. It's mission critical software than is relied upon by many individuals and enterprises in what has grown to be a $100+ billion network. Bitcoin Core is not developed in the same manner as your average consumer software; it's more akin to aerospace engineering. The stakes are high and tolerance for even the most minor failure is incredibly low due to the potential for catastrophe. If you speak to Core contributors who have been participating for many years, they tend to agree that the quality control of code review and testing has increased enormously over the past decade. As such, the bar has been raised for anyone who wishes to have their code merged into the repository. 

If you wish to better understand the dynamics of how Core operates as an organization, check out [Who Controls Bitcoin Core](https://blog.lopp.net/who-controls-bitcoin-core-/)? I also have several guides about contributing to Bitcoin Core [linked in my educational resources](https://www.lopp.net/bitcoin-information/technical-resources.html).

## Pull Request Stats
Note that in late 2011 the Bitcoin project migrated from SourceForge to Github - for simplicity I'm ignoring any rejected PRs that occurred during the SourceForge era. It's not clear to me if it's even possible to find them. At time of writing, Bitcoin Core has:

*   337 [open PRs](https://github.com/bitcoin/bitcoin/pulls?q=is%3Apr+is%3Aopen)
*   8,431 [closed merged PRs](https://github.com/bitcoin/bitcoin/pulls?q=is%3Apr+is%3Aclosed+is%3Amerged+)
*   4,014 closed [unmerged PRs](https://github.com/bitcoin/bitcoin/pulls?q=is%3Apr+is%3Aclosed+is%3Aunmerged+)

Thus 32% of pull requests end up being abandoned / rejected (or re-proposed differently.)

## Merged Pull Request Stats
Thankfully it's quite simple to query git to aggregate stats for the code that made it into the repository.

> $ git log --no-merges --all --pretty=tformat: --numstat | awk '{inserted+=$1; deleted+=$2; delta+=$1-$2; ratio=deleted/inserted} END {printf "Commit stats:\\n- Lines added (total):  %s\\n- Lines deleted (total):  %s\\n- Total lines (delta):  %s\\n- Add./Del. ratio (1:n):  1 : %s\\n", inserted, deleted, delta, ratio }' -

Based upon all historical commits (excluding merge commits):

*   Lines added (total):  2,167,565
*   Lines deleted (total):  1,483,481
*   Total lines (delta):  684,084
*   Added / Deleted ratio (1:n):  1 : 0.6844

## Unmerged Pull Request Stats
But now we need to figure out how many PRs have been closed without being merged! 

We've already determined that there are a little over 4,000 unmerged PRs at time of writing. But how many lines of code would these PRs have changed if merged? GitHub [has an API for that](https://developer.github.com/v4/object/pullrequest/), though perhaps there's a library that can help us use it more easily! Let's give [PyGithub](https://github.com/PyGithub/PyGithub) a shot... 

After a bit of trial and error, here's what I came up with: [https://gist.github.com/jlopp/5aa87ed33e97ad58f54ace65e9b0ece3](https://gist.github.com/jlopp/5aa87ed33e97ad58f54ace65e9b0ece3) 

Unfortunately, while Github's UI allows us to filter out merged pull requests, it appears the API does not. So we need to iterate over all 12,000+ PRs to count the lines of code from the unmerged ones. It turns out that Github limits API calls to 5,000 per hour, so this operation requires us to throttle the script to spread itself out across 2+ hours.

### The Results
After iterating all rejected pull requests from Bitcoin Core we find that there were: 
* 9,011,209 total rejected added lines of code 
* 6,279,435 total rejected deleted lines of code 

That's 15,290,644 rejected lines of code changed vs 3,651,046 accepted! 

Which means that as of time of writing, only 19% of proposed changed lines of code have been accepted into Bitcoin Core.

## Top Contributor Stats
What if we drill down a bit more to the individual level? Clearly some contributors are better than others at navigating the (often arduous) process of seeing a proposal through to completion. 

* _Wladimir van der Laan - 88% PR merge rate_ 737 merged PRs 104 unmerged PRs 
* _Pieter Wuille - 87% PR merge rate_ 600 merged PRs 90 unmerged PRs 
* _Marco Falke - 85% PR merge rate_ 733 merged PRs 133 unmerged PRs 
* _Matt Corallo - 77% PR merge rate_ 290 merged PRs 88 unmerged PRs 

What about notable contributors who have stopped contributing after scaling contention? 

_Jeff Garzik - 58% PR merge rate_ 88 merged 63 unmerged 
_Mike Hearn - 57% PR merge rate_ 8 merged 6 unmerged 
_Gavin Andresen - 80% PR merge rate_ 180 merged 43 unmerged 

Gavin's stats are high but I wondered if that was due to his early involvement and if there was a noticeable trend leading toward his departure. It turns out there is indeed:

> 2012: 91% PR merge rate (49 out of 54 PRs) 
> 2013: 86% PR merge rate (60 out of 70 PRs) 
> 2014: 81% PR merge rate (29 out of 36 PRs) 
> 2015: 59% PR merge rate (10 out of 17 PRs) 
> 2016: 0% PR merge rate  (0 out of 5 PRs)

Did Gavin become a worse programmer over the years? That seems pretty unlikely. Rather, I suspect that this is evidence of Bitcoin Core's quality standards increasing in rigor.

Takeaways
---------

*   Bitcoin Core has high standards; a significant portion of code changes are abandoned or rejected.
*   There's evidence that supports the theory that code standards have increased over the life of the project.
*   It appears that a PR rejection rate of under 70% is a sign that a contributor will get frustrated and stop contributing.

There's certainly opportunity to dig further into this phenomenon, but I think this is a good start!

***

{% include signup.md %}