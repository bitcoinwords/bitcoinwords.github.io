---
title: "Summary update on Bitcoin transaction malleability adjustments"
permalink: "/summary-update-on-bitcoin-transaction-malleability-adjustments"

author: konradsgraf

tags:
  - Konrad S. Graf
  - 2014 Q1
  - Politics
  - Technology
  - Security

excerpt: Summary update on Bitcoin transaction malleability adjustments. Posted February 14, 2014.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Summary update on Bitcoin transaction malleability adjustments](http://konrad-graf.squarespace.com/blog1/2014/2/14/summary-update-on-bitcoin-transaction-malleability-adjustmen.html)
### By [Konrad S. Graf](https://www.konradsgraf.com/)
### Posted February 14, 2014

POST HEADER

POST BODY

Here is a quick summary of the current state of the response to transaction-malleability attacks on some exchanges, based on what I have gathered mainly from Github, Reddit, and Twitter discussions. One note on terminology at the outset, transaction-*ID* malleability would probably make this easier to understand for the general public at first glance—the substantive *content* of transactions cannot be alterned at all through this issue.

The MtGox exchange was still hardest hit in its particular implementation, but more importantly, it is mainly suffering in addition due to a general lack of market confidence in its business and solvency, which has built up over a very long period. The “price” it currently displays is not really a “Bitcoin price,” but mainly a market risk assessment of the likely state of the exchange’s own solvency. The current issue and MtGox’s response have come as a “last straw” for the market’s view of this company. This business-specific factor has also amplified the wider public impression of how significant the actual general technical issue itself is (this is typical for Bitcoin news, but still).

That said, MtGox’s infamous Monday press release blaming the Bitcoin protocol for its own woes was not *entirely* fanciful after all, and some wider adjustments are being made to tighten up this issue at some other exchanges and even in the reference implementation itself. These code adjustments in response to transaction ID malliators (those taking advantage of the situation to reissue transactions with altered transaction IDs) are taking shape and are in the process of being approved and implemented.

What we are apparently getting is a new “normalized transaction ID” field in transactions. This reflects the substantive content of the transaction itself and is therefore immune to the malliation to which the standard ID is subject prior to confirmation. To clarify for those who have not followed this closely, this issue has never had any direct effect on the content of transactions, that is, on who gets what. The exploit is only a way to fool some wallets into not seeing that a confirmed transaction has in fact been confirmed.

The work underway is precisely to fix these particular implementations so that they correctly perceive that confirmed transactions actually have appeared on the blockchain. These implementations had been relying on the initial standard transaction ID for this function. Not everyone understood that during a window after initial submission to the network and before confirmation, a transaction could be copied and the copy reissued with an altered transaction ID by changing the *format* of the signature.

Reference wallet features to make use of this new normalised ID are well in process. These include detecting copies of the “same” (in terms of hard content) transactions with differing standard transaction IDs. This is called “Walletconflict detection.” “Conflicted” transactions, that is, versions of a transaction that did not confirm due to ID malleation, are to be reported as “confirmations: -1 and category: ‘conflicted.’” This status is based on detection of multiple transactions with the same (new) normalised transaction ID as one another (only one such transaction can ever be confirmed, but this new feature brings any *ID-malleation* attempts to the ‘attention’ of the wallet software by showing all malleated and non-malleated versions that carry the same content).

The Bitstamp exchange announced Friday morning (in Europe) that its system adjustment, built with support from core developers, had passed internal testing and that it is likely to resume withdrawals later in the day.

There is more to be done to support more complex and as yet rarely used Bitcoin features in terms of the standard transaction ID issue, as this ID is what is used in inputs to future transactions. This is complex, because the malleability of the standard ID could also have positive uses in the future in facilitating certain types of complex transactions. The current adjustments with the addition of the normalized transaction ID and related code should be a sufficient immediate adaptation to the issue.

POST FOOTER

/post

/content-wrapper

***

{% include signup.md %}
