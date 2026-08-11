---
title: "An historical timeline of The Real Bitcoin (TRB) development, part i."
permalink: "/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i"

author: petedushenski

tags:
  - Pete Dushenski
  - 2015 Q4
  - Economics
  - Technology
  - History

excerpt: An historical timeline of The Real Bitcoin (TRB) development, part i.. Posted December 25, 2015.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [An historical timeline of The Real Bitcoin (TRB) development, part i.](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i)
### By [Pete Dushenski](http://www.contravex.com/)
### Posted December 25, 2015

On October 10, 2014, on the well-intentioned<sup>[i](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_0_6393)</sup> premise that more relay nodes would mean a healthier, more robust, and more reliable Bitcoin network, I whipped up a[little guide](https://contravex.com/2014/10/10/guide-to-setting-up-a-remote-bitcoin-node-for-20-per-year/) for setting up el cheapo AWeSque nodes. How easy, how simple, how innocent, no ?<sup>[ii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_1_6393)</sup>

At the time, the [Vessenes Phoundation](https://contravex.com/2014/04/07/analysis-annual-letter-from-bitcoin-fundation-chairman-vehehes/) was promoting their version of the Bitcoin reference code, which they called “0.9.x” or “Core,” but which was widely known to be at best a laughingstock and at worst a very marginal improvement on [webwallets](https://contravex.com/2015/01/22/the-problem-of-digital-identity-or-how-to-circumvent-blockchain-info-2fa-and-e-mail-authorisation/).<sup>[iii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_2_6393)</sup> But while the old Foundation’s jig was up and their puerile pretenders to the throne were literally [tripping over themselves](https://contravex.com/2015/02/11/the-economics-of-sinking-20-mb-gavincoin-blocks/) to lie to Bitcoin users in an attempt to subvert this world-eating little project, the emerging Republic calling #bitcoin-assets home lacked a reference implementation to call its own. Each individual member carefully guarded their homebrew concoctions with all the shrewdness of poker players in an old Western Saloon, leaving the hows and whys of each stack almost entirely unknown, even if [theories swirled](http://btcbase.org/log//?date=14-07-2015#1201358).

With this in mind, my $20 node guide<sup>[iv](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_3_6393)</sup> was never intended to be the final word on the matter, but rather a stop-gap measure that at the time seemed better than nothing, being predicated on the not-overly-ridiculous-sounding-notion that someone, somewhere in my WoT had a decent reference implementation (and that they’d be willing to share) that I could just plug in, press the big red LAUNCH button, watch the thing build in a flurry of lines whizzing across the terminal screen before kickin my feet up on the desk, breathing a sigh of satisfaction, and then deciding if I wanted to spend the next hour shoveling snow or reading poetry or something, all the while smugly content in the knowledge that I was supporting the Bitcoin network.<sup>[v](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_4_6393)</sup> Oh, the innocence of youth… and how dubious this all seems in hindsight !

Needless to say, this reference codebase thing wasn’t quite so simple.<sup>[vi](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_5_6393)</sup> Fast forward to today and we’re still here, still glued to our chairs as the since-established [Bitcoin Foundation](http://thebitcoin.foundation/) (the Real one) hacks away at Satoshi’s codebase, getting ever-closer yet paradoxically ever-further from their objective, all the while trying to hygienically remove as much stupidity / FOSS as possible while keeping the important bits ticking.

This is their story :

[October 21, 2014](http://btcbase.org/log/?date=21-10-2014#885539)[:](http://btcbase.org/log/?date=21-10-2014#885539) Bitcoin 0.5.3 selected by Mircea Popescu<sup>[vii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_6_6393)</sup>

After Ben Vulpes sifted through the history of Bitcoin’s development [from Satoshi to Phoundation](http://cascadianhacker.com/blog/2014/10/20_a-summary-of-changes-to-bitcoin-since-0321.html), the call was made to select a development branch upon which to base future efforts.<sup>[viii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_7_6393)</sup> The balance of considerations saw 0.5.3 selected, with cutting edge features like encrypted wallets (ooh! ahh!) being included and obvious prole-related nonsense like support for “click-to-pay” being eschewed. That the 0.5.3 branch was far from perfect was no mystery, but it was the tallest midget so to speak.

[October 22, 2014](http://thebitcoin.foundation/charter.html)[:](http://thebitcoin.foundation/charter.html) The (Real) Bitcoin Foundation established

In order to guide this process as formally and as professionally as possible, Mircea Popescu selected Shane Kinney<sup>[ix](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_8_6393)</sup> and Ben Vulpes<sup>[x](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_9_6393)</sup> as co-chairs and Juraj Variny<sup>[xi](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_10_6393)</sup> as treasurer for the newly formed (Real) Bitcoin Foundation, an organisation tasked with taking the 0.5.3 turd and polishing it into something resembling Anish Kapoor’s Cloud Gate in Chicago, except useable and meaningful.

While Mr. Kinney and Mr. Vulpes were tasked with guiding and moderating development of The Real Bitcoin (TRB), patch submissions have always been open to anyone in assbot’s L2 WoT. As you’ll see, this is an important consideration, not the least of which because it’s the opposite of the FOSS<sup>[xii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_11_6393)</sup> approach that rendered the reference software so mangled in the first place.

The Real Bitcoin Foundation’s charter is found [here](http://thebitcoin.foundation/charter.html).

[October 24, 2014 :](http://btcbase.org/log/?date=24-10-2014#894311) Qt excised by Stanislav Datskovskiy<sup>[xiii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_12_6393)</sup>

With “chicken,” the first scruffy feathers to be plucked from the frankly fetid corpse of 0.5.3 was Qt, which was the basis for the program’s Graphical User Interface (GUI). Qt uses C++ with signals and slots<sup>[xiv](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_13_6393)</sup> to provide a cross-platform application framework. ~~for, essentially, illiterate amateurs.~~<sup>[xv](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_14_6393)</sup>~~~~

As Qt introduced weight and complexity to the code, both mortal enemies of security and “[fits in head](http://search.bitcoin-assets.com/?q=fits+in+head),” philosophically as much as practically, Qt had to go. Bitcoin, after all, is for professionals and this first excision was telling of this fundamental reality. What remained after the excision of Qt could more properly be called “bitcoind” once again as it was accessible exclusively via the command line interface, as you do.

[October 25, 2014 :](http://btcbase.org/log/?date=25-10-2014#896151) UPNP excised by Ben Vulpes

With the “rm_rf_upnp” patch, Universal Plug and Play (UPnP) – which allows inter-device networking and communication but in doing so creates a security vulnerability – was plugged. The issue with UPnP centres around the “libupnp” library – that is, the Linux Software Development Kit (SDK) that provides “developers” with an Application Programming Interface (API) and open source code for building control points, devices, and bridges – and in which multiple buffer overflow vulnerabilities were widely recognised, even by the US Department of Homeland Security. (*N.B.* If something isn’t good enough for the enemy, it’s a pretty damn good bet that it won’t be good enough for the Republic.)

[October 28, 2014 :](http://btcbase.org/log/?date=28-10-2014#900326) HTTPS/SSL excised by Stanislav Datskovskiy

With the “https-snipsnip” patch, the vulnerability that exposed the Bitcoin network to Heartbleed via Public Key Infrastructure (PKI) was removed.<sup>[xvi](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_15_6393)</sup> OpenSSL is a cryptographic library that enables Secure Sockets Layer (SSL) or Transport Security Layer (TLS) encryption across the web. In theory, this is both a “cost-effective” and “industry approved” method of encrypted communication. In practice, however, the project was subverted sometime in 2012, if not sooner, and no amount of rubber-stamping could prevent the stench of roadkill from betraying the true state of the library, viz. unknowably large and impossible to trust.

Given that Mr. Datskovskiy is on the record as calling out this turd way back in 2013, it’s little wonder he was the one to pull the trigger here.<sup>[xvii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_16_6393)</sup>

[October 29, 2014 :](http://btcbase.org/log/?date=29-10-2014#901445) Win32 excised by Stanislav Datskovskiy

With the “goodbye-win32” patch, the swiss cheese mousetrap that is Microsoft’s Windows operating system was trimmed from the reference implementation. This should really require no further explanation other than fuck Bill Gates.

[October 30, 2015 :](http://btcbase.org/log/?date=30-10-2014#904199) Upgrade warning excised by Stanislav Datskovskiy

With the “turdmeister-alert-snip” patch, the old-fashioned, out-dated “upgrade needed” warning message from USGavin *et al.* was put on the chopping block.<sup>[xviii](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_17_6393)</sup> The idea being that The Real Bitcoin will eventually be whittled into a weaponised implement of such robustness that it would never need software updates,<sup>[xix](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#footnote_18_6393)</sup> certainly not those “recommended” by Central Command.

[December 19 2014 :](http://therealbitcoin.org/ml/btc-dev/2014-December/000024.html) DBD parameters set by Shane Kinney

With the “db_config” patch, the wedge issue at Block 252450 was overcome. The ram exhaustion wedge was apparently caused by less than ideal Berkeley DB (BDB) configuration settings. BDB is a relatively simple-to-use database management library that’s used to keep track of Bitcoin transactions.

[To be continued]

___ ___ ___

1. Yes, the road to hell is undeniably paved with good intentions and quadruply so when you have the good intentions of *others* in mind, with evil squaring further still [as a function of distance](https://contravex.com/2015/04/07/foreign-aid-assuaging-your-guilt-and-ruining-lives-since-forever/) between you and the intended recipient. So ya, mind your own fucking business ! Ya bunch of fucking wreckers… Oh, you “just wanted to” ? Shut up and get back in the kitchen. What is this, a democracy ? And no, I don’t give a shit if you fancy yourself “a guy who doesn’t *do* kitchens,” stop being such a sexist tard and find a worthwhile cock to suck already. You’re not getting any younger, you know.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_0_6393)
2. This was itself motivated by [an article](https://contravex.com/2014/10/07/how-a-bigger-blockchain-is-less-secure-and-why-block-size-aint-gonna-increase-any-time-soon/) I’d penned just a few days prior, specifically :  The biggest challenge ahead isn’t “[bringing Bitcoin to the people](https://contravex.com/2014/02/25/matters-of-bitcoin-merchant-adoption/)” or some such nonsense, it’s in maintaining a sufficient number of nodes to relay and verify transactions. This is challenging issue that has yet to be fully addressed. But hey, we need *something* to do in 2015 once all the derps are dead, y’know? Which was itself informed by a comment to this effect by [Mircea Popescu](http://btcbase.org/log/?date=07-10-2014#862048), which was itself informed by Gavin Andresen’s idiocy, which was itself informed by Gavin’s mother dropping him on the head as a child, etc., etc., *ad infinitum*. Little did I, or anyone else, suspect the magnitude of the task at the time… perhaps Alf notwithstanding.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_1_6393)
3. This open secret was due in no small part to the at-the-time-recent Heartbleed OpenSSL vulnerability that [Mike Hearn](https://contravex.com/2015/08/19/vox-populi-vox-dei-no-more/) surreptitiously inserted into version 0.9, only to have his efforts blown apart by Riku, Antti and Matti of Codenomicon (“independent” and “simultaneous” discovery of the bug by Google Security my ass !) But what was the big deal with Heartbleed and OpenSSL ? Well, we’re getting to that ![↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_2_6393)
4. Also at the time, $20 was about 0.05 BTC and would just barely cut the mustard. Today, even with BTC trading for about 30% on the exchanges, you’re looking at about 0.18 BTC to run a node. That being said, Bitcoin’s due for another bounce-and-resettle, so 0.05 BTC per year is likely a reasonable rate going forward, which means that, yes, if you can’t afford that, you can’t afford to be in Bitcoin. [↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_3_6393)
5. Why did I want to support the Bitcoin network in the first ? Why not just be a free-rider and coast off the accomplishments of others ? Well, my personal reasons were, and still are, two-fold : i) It’s in my rational self-interest to do so, and ii) If you can, you must, and I figured that I could.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_4_6393)
6. See [this conversation](http://btcbase.org/log/?date=10-10-2014#867670), which took place shortly after I tried and failed to follow my own recipe :  **mircea_popescu:** pete_d you really should know better than taking bitcoin “foundation” shit at face value yo.
 ***asciilifeform** read the published script, sees nothing to verify installation of particular known-hygienic classical ver. of bitcoind **pete_d:** This i know ! Any suggestions for how to remedy this ??
 **mircea_popescu:** Nothing good short of running some decent nodes.
  **pete_d:** And where might I find the scripts for this?
 **mircea_popescu:** For running a node you mean ? **pete_d:** 0.9.3 is obviously dirt but how would one go about installing 0.6.x on a VPS ?
 **mircea_popescu:** Well you get the code off the repository and compile it. Or if you trust anyone, you get a binary from them. **pete_d:** The instructions in my “guide” definitely need improvement. Currently point people towards latest bitcoind as per pankkake’s script.*
 **mircea_popescu:** Generally the people involved in Bitcoin to this level kinda have the history, and a complete file of historical versions and so on. I guess it’s an interesting question, “What’s the new guy to do”. Bunch of playing catchup it seems. **asciilifeform:** n00b, as in any serious business, must apprentice to another. Or make good friends with the nuts and bolts alone, for ages.
 ***pete_d** now accepting offers for binary of bitcoind 0.6.x for Contravex guide. **mircea_popescu:** But actually his is a legitimate request. I guess I’m adding this to the “wanted maintainer for eulora binaries” thing : wanted maintainer for bitcoin binaries. Anyone want to do a bunch of compiling and sign stuff ?  And so it began. Of course, since [the lathe dog](https://contravex.com/2015/11/20/alf-the-lathe-dog/) is a more notable player in this saga than I could ever hope to be (as you’ll readily observe from the sheer volume and quality of patches he’s thus far submitted to TRB development) his [open order](http://btcbase.org/log/?date=21-10-2014#885782) for a printed and bound volume of the 0.6-era source code is commonly regarded as the first cause in The Real Bitcoin’s development, even though it took place some 10 days *later*, and only after much collective stumbling around in the dark and pawing at the edges of the iceberg that is modern general purpose computing… But hey, we could point to specific causes and their causes and their causes all the way back to infinity and we’d just end up at that Douglas Adams line about the creation of the Universe and how it made a lot of people very angry and was widely regarded as a bad move. ___ ___ *You may recall pankkake as being he of “OMG YOU GUISE R A CULT” [fame](https://contravex.com/2014/11/04/lets-cut-to-the-chase-is-la-serenissima-a-cult/).[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_5_6393)
7. mircea_popescu is identified by PGP Fingerprint : 6160 E1CA C8A3 C529 66FD 7699 8A73 6F0E 2FB7 B452[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_6_6393)
8. Update : MP can be credited with his selection of the “no later than 0.6.x branch” as early as ~~[February 2014](http://btcbase.org/log/?date=13-02-2014#499837)~~ ~~[December 2013](http://trilema.com/2013/the-future-in-the-past/) (h/t to Alf!~~) [May 2013](http://btcbase.org/log/?date=02-05-2013#12053) (!).[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_7_6393)
9. mod6 is identified by PGP fingerprint : 027A 8D7C 0FB8 A166 4372 0F40 7217 05A8 B71E ADAF[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_8_6393)
10. ben_vulpes is identified by PGP fingerprint : 4F79 0794 2CA8 B89B 01E2 5A76 2AFA 1A9F D2D0 31DA[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_9_6393)
11. jurov is identified by PGP Fingerprint : BBB0 A999 5003 7551 F533 850A 677A BD62 D0AE E7D7[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_10_6393)
12. Free and Open Source Software.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_11_6393)
13. asciilifeform is identified by PGP fingerprint :1721 5D11 8B72 3950 7FAF ED98 B982 28A0 01AB FFC7.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_12_6393)
14. Signals and slots work a bit like a spreadsheet in that certain objects auto-update when other objects that they’re linked to are modified.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_13_6393)
15. A [little birdy](http://btcbase.org/log/?date=26-12-2015#1353513) tells me that Qt isn’t just for illiterates, but is unfortunately, “the ~only~ remaining working cross-platform native-widget graphic lib for cpp.”[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_14_6393)
16. The issue with PKI is that it requires “Certificate Authorities”, ie. third-parties who may or may not have your best interests at heart, and whose opinion of you may change over time. For obvious reasons, then, PKI is a political tool rather than a security tool and therefore has no place in [sane personal computers](http://www.loper-os.org/?p=278) any more than your national army does.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_15_6393)
17. From “[Don’t Blame the Mice](http://www.loper-os.org/?p=1299),” September 2013 :  Let’s go back to your kitchen. It is squeaky-clean, you say, because nowhere in your house do you make use of Microsoft’s miserable imitation of an operating system. Guess what, the mounds of garbage are still there, stinking brazenly; the mice leap, they play without fear, because virtually all of your cryptographic needs are serviced by some variant of OpenSSL. What a monstrous turd of a library! Have you read *and understood* it – any of it? Do you *personally* know a single living soul who has done so? Dare to contemplate the very idea of plowing through these megabytes of gnarly crapola.  [↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_16_6393)
18. “WARNING: Displayed transactions may not be correct! You may need to upgrade, or other nodes may need to upgrade” from out of the blue ? Pfff. No thank you. That being said, “InvalidChainFound: WARNING: Displayed transactions may not be correct! You may need to upgrade, or other nodes may need to upgrade.” is still in place as a warning in TRB.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_17_6393)
19. Even if hard drive updates are inevitable as the blockchain grows ever more voluminous.[↩](http://www.contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i#identifier_18_6393)

***

{% include signup.md %}
