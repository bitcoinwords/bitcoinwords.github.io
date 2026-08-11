---
title: "An historical timeline of The Real Bitcoin (TRB) development, part ii."
permalink: "/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii"

author: petedushenski

tags:
  - Pete Dushenski
  - 2016 Q1
  - Technology
  - Security
  - History

excerpt: An historical timeline of The Real Bitcoin (TRB) development, part ii.. Posted January 21, 2016.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [An historical timeline of The Real Bitcoin (TRB) development, part ii.](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii)
### By [Pete Dushenski](http://www.contravex.com/)
### Posted January 21, 2016

*See also : [part i](https://contravex.com/2015/12/25/an-historical-timeline-of-the-real-bitcoin-trb-development-part-i/)* *(and TRB co-chair Ben Vulpes’ [nulla part](http://cascadianhacker.com/blog/2015/05/02_a-brief-history-of-the-bitcoin-foundations-activity-from-102014-through-42015.html))*

[January 23, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-January/000029.html) Bump version by Ben Vulpes

With the “rev_bump” patch, the software version advertised to other nodes on the network was changed from 0.5.3 to 0.5.3.1 so as to more readily distinguish and more clearly identify TRB nodes from less thoughtfully maintained version. Though 0.5.3.1 was not to be the final word on version strings, it was under this banner that TRB would publish its first formal release on March 19, 2015.

[January 28, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-January/000033.html) Portatronic build by Stanislav Datskovskiy

With the “porta-tronic” patch, support was established for cross-compiling TRB on ARM CPUs, namely those found in the Pogoplug 4s acquired by several TMSR~ citizens with the aim of broader TRB node deployment.

Also included in this update was a build script that specified the OpenSSL, DBD, and Boost versions for the first time. While this script was initially designed for the Pogos with the idea that these nodes would be set-up once and “[poured into cement](http://btcbase.org/log//?date=05-11-2015#1316759),” it would go on to form the basis of Stator and Rotor for desktop (and possibly laptop) users, both of which were key developments in the establishment of a deterministic bitcoind, but these will be covered in more detail in part iii.

[January 30, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-January/000038.html) Orphan block limiting by Stanislav Datskovskiy

With the “orphanage-burner” patch, recurrent memory exhaustion crashes during initial sync were first addressed. The root of the issue was the “mapOrphanBlocks” data structure. In essence, during initial sync, transaction blocks would be accumulated from other hosts out of order, and such “orphan blocks,” with no where to call home, would simply accumulate in memory before ultimately exhausting it, thereby triggering the kernel to issue SIGKILL to TRB.<sup>[i](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_0_6423)</sup> This patch also sneakily updated the version from 0.5.3.1 to 0.5.3.2, despite much belabouring of the cardinal “[one change per patch](http://btcbase.org/log/?date=25-10-2014#896064)” rule.<sup>[ii](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_1_6423)</sup> This patch did much to address the memory footprint concerns during initial sync, but more would ultimately still be needed. More on which in a minute.

[February](http://therealbitcoin.org/ml/btc-dev/2015-February/000040.html)[2, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-February/000040.html) DNS Seeding excised by Stanislav Datskovskiy

With the “dnsseed_snipsnip” patch, the first of four patches aimed squarely at the Domain Name System (DNS) application layer,<sup>[iii](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_2_6423)</sup> four of the “trusted” nodes<sup>[iv](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_3_6423)</sup> from which an initial sync might be conducted were removed, reducing potential attack vectors from UnSavoury Garnishes and leaving the TRB operator free to point their machine in the seeding direction of their preference. Also affected by this patch were, as [Ben Vulpes](http://cascadianhacker.com/blog/2015/06/21_excising-dns-lookups-from-bitcoind-asciilifeforms-patches.html) points out, i) the removal of the “-nodnsseed” flag and the corresponding “SoftSetArg” call from init.cpp, ii) removal of ThreadDNSAddressSeed and ThreadDNSAddressSeed2 declaration and implementation, and iii) removal of ThreadDNSAddressSeed from StartNode.

The purpose of removing DNS references from TRB at the time was that, if DNS were activated, glibc<sup>[v](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_4_6423)</sup> would invoke libnss.<sup>[vi](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_5_6423)</sup> The biggest problem with libnss was that it couldn’t be statically linked because it’s configured for each machine individually, and without a static build, TRB couldn’t realise its goal of releasing a deterministic bitcoind for any reasonable Unix on any reasonable machine.

While removing DNS seeding was only the start of the complete DNS excision, glibc would ultimately be replaced by musl<sup>[vii](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_6_6423)</sup> in the July 27th publication of Rotor, which will be covered in part iii.

[March 6, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-March/000056.html) Static makefile by Shane Kinney **

With the “static-makefile” patch, the versions of OpenSSL, BDB and Boost were fixed at v1.0.1g, 4.8.30, and 1.52.0, respectively. The idea here being to give all TRB implementations a fixed starting point<sup>[viii](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_7_6423)</sup> from which to build as well as the specific tools known to work (and sufficiently trusted to do so). This patch therefore laid important groundwork for the cementing of Bitcoin on a Linux OS with either a x86_64 or x86_32 CPU architecture.<sup>[ix](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_8_6423)</sup> Then,<sup>[x](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_9_6423)</sup> as now,<sup>[xi](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_10_6423)</sup> you don’t build your house on sand. Capiche ?

The March 12th “[v0.0.2](http://therealbitcoin.org/ml/btc-dev/2015-March/000064.html)” update to this patch, also by Mr. Kinney, added a static libgcc, a library that the GNU Compiler Collection (GCC) uses during code generation. “More static is more better” isn’t a bad heuristic here.

[March 19, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-March/000069.html) 0.5.3.1-RELEASE published by Shane Kinney

The summation of all improvements to the reference client to date, The Real Bitcoin Foundation published its first formal release. A major milestone !

[April 2, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-April/000080.html) Integer ironing out by Stanislav Datskovskiy

With the “kills-integer-retardation” patch, the unsigned integer (uint)<sup>[xii](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_11_6423)</sup> width in the macros<sup>[xiii](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#footnote_12_6423)</sup> arguments were set precisely. This had the ultimate effect of creating defined uints more than once, but this was at least better than uints being undefined in several places simultaneously, as was the case prior to this patch. This was necessary, if not entirely satisfactory progress (at least according to Stan).

[May 4, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-May/000088.html) Orphan block excision by Stanislav Datskovskiy

In the “orphanage_thermonuke” patch, the large memory footprint was attacked from the angle of “orphan” or “bastard” block storage in memory during the initial sync process. In essence, rather than storing randomly received blocks from the randomly connected nodes (a process that was limited in the “orphanage_burner” patch), this patch forced TRB nodes to discard any block received whose direct antecedent was not part of the longest chain and ask the inputting node for all the blocks between the bastard and the at-the-time best-known height.

[May 28, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-May/000094.html)Orphan transaction excision by Stanislav Datskovskiy

With the “tx-orphanage_amputation” patch, as a follow-up to the previous patch and as a further measure towards reducing TRB’s memory footprint, orphan transactions that have not yet been incorporated into blocks are also discarded. This greatly sped up the sync process as the TRB node would thereafter focus its resources exclusively on processing blocks useful for establishing the correct longest chain, after which it could begin its function as a relay node if its owner so decided.

[June 17, 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-June/000098.html) DNS hard-coded seeds excised by Stanislav Datskovskiy

With the “zap_hardcoded_seeds” patch, as [Ben Vulpes](http://cascadianhacker.com/blog/2015/06/21_excising-dns-lookups-from-bitcoind-asciilifeforms-patches.html) points out, the pnSeeds array and fAddSeed were removed, preventing the hard-coded DNS seeds from being added to the mapAddresses data structure used to track trusted nodes. This was step two of four in completely eliminating DNS invocation in TRB.

[June 17 2015 :](http://therealbitcoin.org/ml/btc-dev/2015-June/000099.html)“showmyip.com” mechanism excised by Stanislav Datskovskiy

With the “zap_showmyip_crud” patch, as Ben Vulpes points out again, we saw the removal of GetMyExternalIP, GetMyExternalIP2 and GetMyExternalIP from ThreadGetMyExternalIP, all of which were dependent on a single centralised service (showmyip.com) for their operation and in turn the secure and effective operation of the entire network. If a bad actor were to gain access to that service, a service that is quite fittingly [no longer in operation](https://archive.is/MBsov), they could manipulate IP addresses and spoof good nodes into thinking that they were connecting to trusted nodes when in fact they were connecting to an alt-chain being broadcast by malicious nodes. This was clearly a weak link in the node identity chain and was therefore step three of four in completely eliminating DNS invocation in TRB.

[To be continued]

___ ___ ___

1. SIGKILL is a command issued by the Unix-based operating system to immediately cease operation of an application with no opportunity for user intervention. It’s highly, highly annoying when you’re trying to, y’know, actually run software because it forms the backbone of essential economic infrastructure.[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_0_6423)
2. Alas, this little tweak was not the end of the world.[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_1_6423)
3. DNS ~= [USG](http://btcbase.org/log//?date=11-01-2016#1366217).[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_2_6423)
4. Namely, bitseed.xf2.org, dnsseed.bluematt.me, dnsseed.bitcoin.dashjr.org, and seed.bitcoin.sipa.be – the latter two of which will be readily recognisable to the alert reader as belonging to Luke “[BFL is legit u guise](http://www.btcalpha.com/wot/user/luke-jr/)” Jr. and Pieter “[Dead Man Walking](http://trilema.com/2015/theres-a-one-bitcoin-reward-for-the-death-of-pieter-wuille-details-below/)” Wuille, respectively.[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_3_6423)
5. Any Unix-like operating system needs a C library: the library which defines the “system calls” and other basic facilities such as open, malloc, printf, exit… The GNU C Library is used as *the* C library in the GNU system and in GNU/Linux systems, as well as many other systems that use Linux as the kernel.  ~[GNU](https://www.gnu.org/software/libc/)[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_4_6423)
6. Network Security Services (NSS) is “a set of libraries designed to support cross-platform development of security-enabled client and server applications.”[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_5_6423)
7. You’re invited to compare musl with glibc, dietlibc, and Uclibc [for yourself](http://www.etalabs.net/compare_libcs.html).[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_6_6423)
8. Software updates in general, especially those necessitating hardware upgrades – as seen in the mainstream implementation of planned obsolescence in consumer electronics and “[apps](https://contravex.com/2015/06/29/audibles-app-is-another-symptom-of-the-update-upgrade-disease/),” which at this point even includes, sadly, [cars](https://contravex.com/2015/07/19/porscheflation-and-the-death-of-automotive-purity/)– are diseases that have no place in something as economically fundamental and politically important as Bitcoin, at least not any more than, say, the jeweler’s gold weighing scale or the dollar bills in your pocket. While it’s indeed the case that cash bills do receive the occasional facelift, this is typically on timescales in the order of decades, not ~~monthly~~ ~~weekly~~ *daily* as in “tech.” You wouldn’t plague your case with new “features,” “performance updates,” and “bug fixes,” would you ? Oh you would ? [↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_7_6423)
9. As [Stan](https://contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii/#comment-39383) points out in the comments below, ARM CPU architecture could also be added to this list, even if this avenue of the project is not in active deployment at the moment.[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_8_6423)
10. Matthew (7 : 26) : And the rain fell, and the floods came, and the winds blew and slammed against that house; and yet it did not fall, for it had been founded on the rock. Everyone who hears these words of Mine and does not act on them, will be like a foolish man who built his house on the sand.  [↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_9_6423)
11. [**mircea_popescu:**](http://btcbase.org/log/?date=02-01-2016#1359076) This is really the revolution Bitcoin brought about. People think it’s a major breakthrough in money, but that’s doubtful. It is however a string of major breakthroughs in systems theory.  [↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_10_6423)
12. Unsigned integers differ from signed integers in that the latter include a sign bit that allows for the expression of both positive and negative integers whereas the former lack such specification.[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_11_6423)
13. A macro is a single instruction that expands automatically into a set of instructions to perform a particular task.[↩](http://www.contravex.com/2016/01/21/an-historical-timeline-of-the-real-bitcoin-trb-development-part-ii#identifier_12_6423)

***

{% include signup.md %}
