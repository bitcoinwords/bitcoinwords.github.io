---
title: "Supplemental Rebuttal to Angela Walch’s Views on Software Devs as Fiduciaries"
permalink: "/supplemental-rebuttal-to-angela-walchs-views-on-software-devs-as-fiduciaries" 

author: gtabrielshapiro

tags:
  - Gabriel Shapiro
  - 2020 Q1
  - Fiduciaries
  - Legal
  - Developers
  - Devs
  - Law
  - Cypherpunk
  - Voluntary
  - FOSS
  - Blockchain


excerpt: Gabriel Shapiro makes the case AGAINST devs as fiduciaries. Posted January 19, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Supplemental Rebuttal to Angela Walch’s Views on Software Devs as Fiduciaries](https://medium.com/@lex_node/supplemental-rebuttal-to-angela-walchs-views-on-software-devs-as-fiduciaries-f886f2b47ffd)
### By [Gabriel Shapiro](https://twitter.com/lex_node)
### Posted January 19, 2020

![](/assets/images/2020/m1/gs1.png)
*The Last Fiduciary, a film directed by Rian Johnson and starring Jerome W. Van Gorkom*

* * *

## **_Introduction_**

In various talks, tweets and [papers](https://papers.ssrn.com/sol3/cf_dev/AbsByAuth.cfm?per_id=1031367), Professor Angela Walch has popularized her view that blockchain protocol developers are or should be deemed fiduciaries of blockchain network participants.

Her views have been ably rebutted (and, in my opinion, conclusively refuted) [Blockchain Development and Fiduciary Duty](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3338270) by Raina S. Haque, Rodrigo Seira Silva-Herzog, Brent A. Plummer and Nelson Rosario.

Nevertheless, Angela Walch’s views on this topic have continued to receive unjustified and regrettable attention and credence. I therefore wish to supplement prior academic criticisms with some quick-and-dirty practical counterarguments in the hope that, when those are combined with the more detailed black-letter law and policy-based arguments set forth in [Blockchain Development and Fiduciary Duty](https://blog.goodaudience.com/blockchain-protocol-developers-are-not-fiduciaries-49bf436a20ca), people will stop having the slightest reason to take Angela Walch’s unfounded position on this topic seriously, instead treating it with the scorn it deserves.

* * *

## Unmodified Fiduciary Duties Barely Exist Today in Any Actual Commercial Relationship

Most of the case law on fiduciary duties comes from Delaware court opinions on how the members of the board of directors of a corporation owe fiduciary duties to the corporation’s stockholders.

Corporations are one of the few remaining state-chartered entity types that impose non-waivable default fiduciary duties on the managers of an entity-based enterprise. Most U.S. states allow the definitive agreements governing “un-corporations” like LLCs to completely eliminate all fiduciary duties that otherwise would be implied by the applicable statute governing such entities or the common law. And, in a majority of cases, the management and investors in such “un-corporations” do in fact opt to eliminate vague fiduciary duties in favor of no duties or very light and precisely defined contractual duties.

Even in the case of corporations, which continue to impose some non-waivable fiduciary duties, such duties have been whittled down to a bare minimum. As a result, corporate managements’ duties toward stockholders are effectively no longer fiduciary duties in the classic sense, but are a set of rather narrow and specific duties defined by carving back fiduciary duties through a complex web of D&O insurance and exculpation and indemnification arrangements agreed to by contract, which in turn are to be interpreted against a backdrop of robust and specific case law explaining how any fiduciary duties that remain play out in various scenarios. In effect, even in the context of corporations, the fact that fiduciary duties still nominally apply to managers is an accident of history or [path dependence](https://en.wikipedia.org/wiki/Path_dependence) — the actual duties assumed by actual corporate directors/officers are radically different from, and are far more narrow and predictable than, “fiduciary duties” in the classic sense.

To flesh this out a bit more: In response to a famous case called [**_Smith v. Van Gorkom_** 488 A.2d 858 (Del. 1985)](https://en.wikipedia.org/wiki/Smith_v._Van_Gorkom), where the Delaware Supreme Court held that members of the board of directors of a target corporation were liable for negotiating and approving an acquisition of the corporation in a grossly negligent manner and thus breaching their fiduciary duty of care, the Delaware legislature enacted Section 102(b)(7) of the Delaware General Corporation Law. 102(b)(7) allows a Delaware corporation to specify in its charter documents that breaches of the duty of care by directors are “exculpated” — which effectively eliminates fiduciary duties for all practical purposes. The DGCL also authorizes corporations to indemnify and insure directors against nearly all other breaches of fiduciary duties, except those that essentially involve conflicted self-dealing, fraud or crime — i.e., breaches of the duty of loyalty. Even some of those breaches may be insured against, if they resulted from good faith behavior.

Just as with un-corporations, as a practical matter, every corporation that receives competent legal advice in fact utilizes these protections and dramatically limits management’s fiduciary duties. Effectively then, directors’ and officers’ fiduciary duties are in practice limited to a duty not to do things like embezzlement that would likely be illegal even if fiduciary duties did not apply. Narrow exceptions exist in very well-defined conflict of interest scenarios that do not apply to blockchains — such as situations in which the directors are negotiating an acquisition of the corporation by a third party and the risk of breaches of the duty of loyalty due to conflicts is deemed so high that the directors face heightened, but still relatively well-defined, fiduciary duties. Even there, a result like that found in the _Van Gorkom _case is now impossible — directors in practice do not owe stockholders a fiduciary duty to negotiate a great deal. They merely must act in a loyal manner in negotiating the deal.

Of course, the above is a discussion of duties owed by management of a company to its investors. Angela Walch’s theory goes further than that, and would require software developers to have fiduciary duties to software users who typically will be using the software for free. In modern markets, technology companies do not owe fiduciary duties even to their PAYING software users — they usually owe a bare duty not to commit gross negligence (product torts) plus very narrowly defined contractual duties like a simple software warranty. _A fortiori_, the software developers who work for technology companies do not owe fiduciary duties — they don’t owe them to the technology company, to the technology company’s stockholders or to the paying software users. They are mere service providers owing, at most, light contractual duties to their employer.

The few areas where unmodified fiduciary duties still survive today in ordinary commerce are in situations of deeply personal, inherently obvious and highly regulated agency relationships like the relationship of an attorney or accountant to a client, or the relationship of a trustee to a beneficiary. These are about as dissimilar to the relationship between any software developer — not to mention a FOSS contributor — and the user of that software as day is to night.

* * *

## If We Wanted to Impose Duties On Devs, We Would Not Make Them Fiduciaries, But Rather Would Impose More Specific Duties

Again, note that even in the context of corporations, the fact that we still speak of “fiduciary duties” is essentially an example of path dependence. No one who wanted to reach the same result as we have in corporate law today would look at it and say: “Hmmm, you know what I think we should do? Create some big fuzzy vague default legal duties and then kill them in a death by a thousand cuts with a complex webwork of charter exculpation provisions, indemnification and advancement of expense arrangements, D&O insurance policies and as-applied legal doctrine spread out over hundreds of court opinions.” While law often evolves in that messy fashion and ends up in a reasonably good place _despite _the mess, no one designing a system of policy-driven incentives through regulation or contracts would ever proceed in such torturously convoluted path _on purpose_.

Thus, even assuming _arguendo _that we wanted software devs to wind up owing a similar set of duties to users as, say, the directors of a corporation owe to its stockholders, we would _never _try to get there by first imposing fiduciary duties and then carving them back. We would just impose the actual duties we want them to end up having. Those would _not _be fiduciary duties, but rather would be the kinds of duties directors and executive officers of corporations functionally have — narrow, reasonably well defined duties to avoid conflicted self-dealing, refrain from committing crimes in connection with their jobs, etc.

* * *

## If Fiduciary Duties Were Imposed On Devs, They Would Cope With Them The Same Way As In Other Industries, And Thus The Fiduciary Duties Would Effectively Become Contractual Duties Anyway

Furthermore, if fiduciary duties were imposed on devs in their raw state, then devs would respond in one of two ways: (1) stop doing the development, since it is now too liability prone and (in the case of FOSS devs) they are not paid, so the activity will have become un-economical; or (2) organizing themselves in ways that let them eliminate fiduciary duties as a matter of law. Modern law and commerce offers pretty much anyone numerous paths to contracting out of default nebulous duties. Developers could form an LLC and opt to eliminate all fiduciary duties under the LLC. Developers could insure themselves against the risks. Developers could build into the FOSS license provisions wherein users of the software waive all fiduciary duty claims. Etc. And, of course, they would do this. Thus, a proposal to impose fiduciary duties on devs only makes sense if one is also proposing to make all these possible, and perfectly legal, countermoves illegal. That would be a radical change to modern commerce and law that few people would support.

* * *

## Reductio Ad Absurdum #1 — FOSS Devs Should Not Have More Liability To Free Software Users Than The CEO Of Apple Inc. Has To Apple Stockholders

For the reasons discussed above, under Walch’s view a dev voluntarily contributing code to Bitcoin Core for free would have greater duties to an unknown user of Bitcoin who has never paid the dev in any way and who the dev is not in privity with and may not even know exists than Tim Cook, CEO of Apple Inc.., has to Apple Inc. stockholders, which is already way higher than the duties that the typical fund manager has to the funds’ LPs.

This result is absurd and untenable and constitutes a _reductio ad absurdum_ of Walch’s position.

* * *

## Reductio Ad Absurdum #2 — FOSS Devs Should Not Have More Liability To Free Software Users Than Apple Inc. Has To Paying Apple Software Users Or Apple Inc.’s Developers Have To Paying Apple Software Users

For the reasons discussed above, under Walch’s view a dev voluntarily contributing code to Bitcoin Core for free would have greater duties to an unknown user of Bitcoin who has never paid the dev in any way and who the dev is not in privity with and may not even know exists than:

(1) Apple Inc. has to paying Apple software users (minimal duties, basically just avoid committing product torts);

(2) the directors and executive officers have to paying Apple software users (no duties); or

(3) a paid coder at Apple has to paying Apple software users (no duties).

This result is absurd and untenable and constitutes a _reductio ad absurdum_ of Walch’s position.

* * *

## Conclusion

Walch’s work on “blockchain devs as fiduciaries” has led blockchain law scholarship down an absurd and meritless rabbit hole. Blockchain devs in general are not fiduciaries, and, even if one thought that as a matter of policy it were a good idea to impose legal duties on blockchain devs, fiduciary duties would not be the logical or natural vehicle for doing so. Angela Walch’s views on how to structure and regulate technology relationships absurdly hearken back to an old, pre-1960s view of corporate law and agency law where fiduciary duties were commonly used in commerce and still had force and meaning as such. This is no longer the case. In contemporary law and commerce vague fiduciary duty standards have, directly or in effect (depending on context) been superseded by precisely defined and usually very narrow contractual duty standards.

This is as it should be, and is consistent with the bedrock cypherpunk principle of those who work on blockchain — the principle of free entry and free exit in environments where social coordination has been scaled and traditional social trust and agency reduced and replaced by the precision of software, economics and game theory.

_Veritas in numeris!_

***

{% include signup.md %}