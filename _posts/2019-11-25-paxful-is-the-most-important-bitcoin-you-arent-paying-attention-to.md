---
title: "Paxful is the Most Important Bitcoin Company You Aren’t Paying Attention to."
permalink: "/paxful-is-the-most-important-bitcoin-you-arent-paying-attention-to" 

author: mattahlborg

tags:
  - Matt Ahlborg
  - CY19 Q4
  - Paxful
  - International Money Transfers
  - Money
  - Economics

excerpt: Matt Ahlborg shares how Paxful is delivering money services in places you'd never expect. Posted November 25, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Paxful is the Most Important Bitcoin Company You Aren’t Paying Attention to.](https://medium.com/dlabvc/paxful-is-the-most-important-bitcoin-company-you-arent-paying-attention-to-4e699db0c5ca)
### By [Matt Ahlborg](https://twitter.com/MattAhlborg)
### Posted November 25, 2019

If cryptocurrency is the Wild West of money, then Paxful is [Deadwood, South Dakota](https://en.wikipedia.org/wiki/Deadwood,_South_Dakota#History). Settled, errr, founded in 2015, [Paxful](https://paxful.com/) has slowly but surely grown into a pillar of Bitcoin trading ecosystem. In total, Paxful now employs over 200 people in four offices around the world and oversees the trading of approximately $25 million dollars worth of Bitcoin every week. And while most cryptocurrency exchanges out San Francisco way are far from their highs reached during the bubble of 2017, Paxful has seen a consistent uptrend for its entire existence.

![](/assets/images/cy19/cy19m11/ma1.png)
*Take note of the two Y axes.*

Paxful, like LocalBitcoins, is an online peer to peer (P2P) over the counter (OTC) exchange where peers interface with the advertisements of other peers offering to trade for Bitcoin using online wallets like Paypal, gift cards, domestic bank transfers, and others.

As is the case with most P2P OTC exchange models, Paxful does not custody the fiat or fiat-like wallets, accounts, or instruments (gift cards, for example) used as counterparty to these trades and instead acts as a supervising authority over peers who use these wallets, accounts, or instruments to trade amongst themselves. As such, Paxful does not need to officially connect to the banking or regulatory infrastructure of many of the countries which it operates in. Because of this model, **Paxful is able to onboard financially disconnected citizens of developing countries on a level that non-P2P OTC exchanges like Coinbase simply cannot.** As of this writing, Paxful services trades in more than 70 currencies around the world and has made much of its traction in geographic regions that many bigger exchanges have not.

![](/assets/images/cy19/cy19m11/ma2.png)

As shown above, US Dollar denominated transactions are by far the most popular on the platform. However, two thirds of that US Dollar volume is actually attributable to USD denominated gift card trading which, as I will show later in the article, is very international in its nature.

![](/assets/images/cy19/cy19m11/ma3.png)

Online wallets are services like Paypal, Skrill, Zelle, etc. Digital currencies are things like Litecoin, Bitcoin Cash, etc.

So what is the deal with gift card trading then and how does it all work?

## The Gift Card Trading Ecosystem

> “**Gift cards can be seen as a sort of stablecoin** **which are available for purchase on nearly every street corner in the world**.”

Gift cards are a massive market and constitute [billions in sales every year](https://www.giftcards.com/gift-card-statistics). And unlike Bitcoin, gift cards are ubiquitous at nearly every gas station, convenience store, and grocery store. Aside from being an easy, last minute gift on the way to birthday or holiday party, they also have a few other attributes which make them useful in other respects:

![](/assets/images/cy19/cy19m11/ma4.png)

1.  You can quickly and easily purchase them with cash,
2.  They hold a stable value,
3.  The redemption codes on the card can be digitally transferred with a simple picture,
4.  It is not illegal to sell your gift card to another person.

In effect, **gift cards can be seen as a sort of stablecoin** **which are available for purchase on nearly every street corner in the world**. Additionally, as you will find out later in the article, the people using these gift cards as stablecoins often don’t even need to know what a stablecoin is or how cryptocurrency works.

## So which cards are being brought to Paxful for selling?

![](/assets/images/cy19/cy19m11/ma5.png)
*Use the legend on the right to filter out cards and adjust the date range.*

Itunes gift cards were the first gift card to come to prominence on the platform. Amazon gift cards and Steam Wallet gift cards have now taken the lead. More recently, a large variety of cards have become popular.

## How much are the cards selling for?

Amazon gift cards are currently the most popular gift card brand on the platform. They most frequently sell for around 64 cents on the dollar (that is, a $100 card fetches around $64 in Bitcoin). As shown in the distribution below, Amazon gift cards cards can fetch a variety of prices:

![](/assets/images/cy19/cy19m11/ma6.png)

The price distribution for these cards comes from a variety of factors which effect the [chargeback fraud risk](https://en.wikipedia.org/wiki/Chargeback_fraud) that the buyer of the card takes on when purchasing the card. These factors include:

*   Whether the redemption code comes from a physical card or a digital gift card,
*   The amount of dollars on the card ($25, $50, $100, $200, etc),
*   Whether the card is accompanied by a receipt and whether the receipt confirms the card was bought with cash (cards bought with cash have the lowest probability of a chargeback event to the card buyer),
*   The reputation of the account selling it.

Additionally, each brand of card garners a different price on the platform. Below are the trade price distributions of the top ten cards by volume:

![](/assets/images/cy19/cy19m11/ma7.png)

The final price for a given brand of card tends to be a function of:

*   The types of items which can be bought with the card,
*   The liquidity of that brand of card on Paxful (less common cards tend to sell for lower prices),
*   The terms of service related to the redemption of each card (some cards have stricter redemption policies than others, affecting their fungibility).

At the end of the day, the price of every card on Paxful is determined by the collective amount that the people buying the cards are willing to pay. The chart below shows that the average price of a given brand of gift card even changes over time:

![](/assets/images/cy19/cy19m11/ma8.png)

## So who are the people bringing these gift cards to Paxful to sell?

This is one of the most difficult questions I’ve tried to answer in the course of my research. The reasons for trading a gift card are many and include the selling of unwanted spare gift cards \[Appendix 1\], online freelancers cashing in their earned gift cards \[Appendix 2\], and yes, even fraud and/or money laundering activity \[Appendix 3\]. Based on what I’ve learned up to now, I am not confident that any one of these use cases accounts for the majority of volume. Rather, I would guess that each may account for some minority portion of the volume.

Of the gift card sellers that I spoke with (as well as those who are buying gift cards from the sellers), **the cited reason for a large amount of the trades is actually remittance**. That is, immigrants in the USA are using gift cards and Bitcoin to transfer value back to their home country. For the next few paragraphs I will explore how this “gift card remittance” process works and then evaluate the data and price points to determine whether or not it could plausibly account for a sizable amount of the volume on Paxful.

Gift Card Remittance on Paxful
------------------------------

> **“The entire remittance process can be completed in 20–30 minutes with the end result of local Nigerian currency arriving to the family member’s bank account.”**

When you go to Paxful and see advertisements looking to purchase gift cards, gift card buyer advertisements show all sorts of requirements and restrictions on the types of cards they are willing to buy. A large chunk of these advertisements demand the gift card be:

1.  A Physical Gift Card,
2.  Accompanied by Receipt,
3.  Shows that the card was paid in cash on the receipt,
4.  Purchased in the last 24–48 hours

![](/assets/images/cy19/cy19m11/ma9.png)

For Amazon gift cards, these advertisements match the 63–83 cent price range constituting the right side of the bell curve on the Amazon gift card distribution above. **What this means is that a large amount of the cards being sold on Paxful are purchased with the specific intent to bring them there to be sold at a substantial discount.**

![](/assets/images/cy19/cy19m11/ma10.png)

In speaking with the traders who act as counterparty to those who bring these cash-bought gift cards and receipts, they tell me that the majority of the cards are coming from Nigerians or other West Africans and that their IP address according to Paxful’s trading dashboard confirms this. The interesting twist however is that the receipts of these cards show that they were purchased at various convenience stores and gas stations in the USA, often times mere hours before they were uploaded to Paxful.

So what is happening here then? What I discovered is that (mostly Nigerian) immigrants in the USA are purchasing gift cards in the USA, taking a picture of the card and receipt, and then immediately sending those pictures to their family and friends in Nigeria using Whatsapp. Those on the receiving end of the gift card pictures in Nigeria are the ones who then upload the pictures to Paxful. These Nigerians in Nigeria use the gift cards to trade for Bitcoin, and they then turn around and complete a second trade which sells that recently acquired Bitcoin for Nigerian currency through a bank transfer. The whole process is described in the diagram below:

![](/assets/images/cy19/cy19m11/ma11.png)
![](/assets/images/cy19/cy19m11/ma12.png)

While this process may seem complicated, Nigerians who engage in these trades tell me that **the entire process can be completed in 20–30 minutes with the end result being that local Nigerian currency arrives to the family member’s Nigerian bank account.**

Additionally, neither the person sending the money nor the person receiving money needs to stand in line at a remittance counter in either country and the person who sends the money does not even need to know what Bitcoin is or what Paxful is. They just need to know to purchase a gift card, take a picture of it, and send it to their family or friend in Nigeria.

So why is it mostly Nigerian immigrants then? Again, the issue is perplexing, but here is my best attempt at reasoning:

Nigeria’s currency, the Naira, has been subject to varying degrees of manipulation and capital controls in recent years and has had a parallel black market rate for some time. In circumstances like these, standard remittance companies like Western Union **have to play by the rules of the local government and honor whatever exchange rate is deemed appropriate** **there** (instead of the black market rate). When going outside of official channels to remit (using gift cards and Bitcoin for example), remitters are able to sell for the more favorable black market rate instead of the official rate and thus receive more Nairas per dollar sent in comparison to Western Union. Another factor at play here is that during the bull run of 2017, Bitcoin buying options across Africa were very limited and caused a premium on the price of Bitcoin there, again creating favorable circumstances for people who hold Bitcoin (those who are selling gift cards). Together, these factors may have conflated to create an environment in 2017–18 such that **Nigerian immigrants in the US could actually take a 30% loss on the value of their gift card while still achieving more Nairas delivered to their families than any other traditional remittance channels offered.**

If you look at the chart below, you can see how Nigerians were able to sell Bitcoin for tens of percent above the official exchange rate during much of 2017–2018 as Nigeria imposed various sweeping measures in an attempt to control the value of its currency.

![](/assets/images/cy19/cy19m11/ma13.png)

However, since that fortuitous time in 2017–18 the situation seems to have changed and that premium appears to have evaporated. More recently, the government of Nigeria has allowed the official exchange rate to float closer to the black market rate and, correspondingly, remittance companies like Western Union have been able to honor exchanges rates at or close to the black market rate as well.

If we compare the two potential remittance methods as it would play out in the present day, a crisp $100 bill brought to Western Union would yield (after all fees) **32,208 Naira available for pick-up at a Western Union location in Nigeria.** If on the other hand you chose to use the gift card remittance method made possible by Paxful, **you would need to get 88.5 cents on the dollar for your gift card in Bitcoin to get as many Nairas as Western Union would offer** (see Appendix 4 for a full breakdown and calculation). In looking at the “_Top 10 Gift Cards by Volume Histogram”_ again, you can see that no gift cards on Paxful are able to fetch 88.5 cents on the dollar. This would imply that gift card remittance is no longer economically viable and that any such continued remittance using gift cards would involve factors other than sheer cost, namely convenience and speed.

![](/assets/images/cy19/cy19m11/ma14.png)
*Annotations indicate the implied “convenience cost” of using gift cards instead of Western Union.*

In the course of my research I purchased several Amazon gift cards on Paxful for 65 cents on the dollar, and the Nigerian counterparties I spoke to cited remittance as the reason. This means that they were receiving 26% less Nairas than the Western Union method. If we are to believe their account then we need to ask ourselves why this use case has continued to play out despite the costs.

In my estimation, the ingrained habit, convenience, and speed of using Paxful for remittance may have caused this use case to persist even though cheaper options may have re-emerged. In other words, old habits die hard and convenience trumps efficiency. The Nigerians I spoken with seemed to indicate as much as well.

In addition to convenience and speed, I’ve also come up with other reasons as to why gift cards may be the superior remittance method for some:

*   Some Nigerians do not live near a Western Union and it appears that Western Union is currently not doing bank transfers to Nigerian bank accounts \[Appendix 5\]. This means that the only way to receive money via Western Union in Nigeria is to travel to a remittance counter there. Gift card remittance on Paxful however allows for near-instant bank transfers and so the entire remittance process could be done from the phone of the Nigerian family member in the comfort of their home.
*   Gift card remittance (including the final bank transfer step) works 24/7 whereas Western Union only works during business hours of Nigerian Banks (all Western Union locations are inside of banks in Nigeria).
*   Another factor may be that undocumented and/or underbanked immigrants in the US may not have or be willing to provide the necessary documents to conduct official remittance.
*   While losing this much value to conduct remittance seems crazy, consider the irrational success of [payday lending](https://en.wikipedia.org/wiki/Payday_loan) where a significant percentage of customers are ‘regulars’ and perpetually lose money on the majority of their paychecks over the course of years. Human behavior isn’t always rational.
*   Nigerians that I’ve spoke with tell me that in reality, they use a hybrid of traditional remittance and Paxful to meet their needs. Larger transfers of hundreds of dollars tend to go through Western Union or informal [Hawala networks](https://www.investopedia.com/terms/h/hawala.asp) whereas smaller, quicker transfers covering unexpected costs at home fall to Paxful.

If you still cannot get past the idea of an immigrant willing to turn $100 into as little as $65 worth of Nigerian currency in a single remittance transaction (26% less than Western Union), then we must acknowledge another possible (and previously documented \[Appendix 3\]) use case playing out here which is that the gift cards being brought to Paxful are coming from nefarious activity, namely West African cyber crime and the associated money laundering that goes with it.

On a related note, it was [reported](https://guardian.ng/news/u-s-massive-fraud-backlash-as-western-union-denies-transfers-to-nigeria/) in August of this year that Western Union locations in Texas (home of over 40,000 Nigerian-born immigrants) blocked the sending of money to Nigeria on the heels of a major cybercrime operation in the US which resulted in the arrest of nearly 80 Nigerian nationals. In moments like these, Paxful and Bitcoin are likely answering the call for these disenfranchised communities.

![](/assets/images/cy19/cy19m11/ma15.png)

In addition to this single observation of a service outage, based on my reading of the subject over the last few years, Western Union transfers to Nigeria have been unreliable on a few occasions as the company struggles to deal with both the ramifications of anti-cybercrime policy in the USA as well as capital control mandates forced upon them by the Central Bank of Nigeria.

To summarize my thoughts on the viability and prevalence of “gift card remittance” on Paxful, I have definitely observed it happening but I also want to qualify my opinion in saying that the jury is still out in terms of how prevalent it is in comparison to other use cases.

## Who in Nigeria needs to trade their Naira for Bitcoin?

Looking back on the “_gift card remittance_” flow chart from earlier in the article, we have yet to touch upon the potential reasons people in Nigeria would want to give away their Naira to acquire Bitcoin. What is Bitcoin offering them?

![](/assets/images/cy19/cy19m11/ma16.png)

As mentioned before, Nigeria has enacted a number of capital control measures on its citizens and residents. One flavor of these controls allows only permissioned and registered individuals and entities to exchange local Naira for foreign currency. **I believe that a good amount of the people who are acquiring Bitcoin in Nigeria are ones who are _not_ permissioned to trade for foreign currency and who still desire to gain access to it.** These people fall into two groups:

The first group would be local Nigerians who seek to purchase goods on the international market and who use Bitcoin to do so. This use case has been anectdotally confirmed by Paxful CEO Ray Youssef’s customer interactions [where he learned](https://open.spotify.com/episode/1pcJ984vqlOEN1DBLGSflc?context=spotify%3Ashow%3A5fGtjPQt92RF9ygxz2A5iq&si=sVaOmvlJSWmxk3wBrYSVjw) that a group of Nigerians were using Bitcoin to purchase, ship, and sell flood-damaged automobiles from the US in Nigeria after the Central Bank of Nigeria clamped down on foreign currency exchange in 2016. I also heard something of this nature several times in the course of my interviews but it instead involved Nigerians purchasing Chinese goods from Chinese vendors who accepted Bitcoin.

The second group of people who seem to have a need for Bitcoin in Nigeria are Chinese nationals. In this scenario, the Chinese people conducting business in Nigeria are filling their bank accounts with Naira but have little recourse in repatriating the value of that Naira back to China due to the aforementioned foreign exchange controls.

In such a scenario, the Chinese national in Nigeria would conduct a P2P OTC transfer on Paxful to trade the Naira in their bank accounts for Bitcoin which they could then use to enter into a second trade to convert their Bitcoin to Yuan in their Chinese bank account. Also, an added bonus here is that Bitcoin now trades slightly below global spot against the Naira and so the transaction is likely also a nice arbitrage opportunity for them \[Appendix 6\].

![](/assets/images/cy19/cy19m11/ma17.png)
*Chinese national in Nigeria using Bitcoin to perform a capital flight and/or remittance maneuver*

## The other side of the trade: Who is buying these discounted Gift Cards and why?

While theoretically anyone could benefit from buying discount gift cards on Paxful for their own personal use, because buying gift cards on Paxful requires a fair amount of risk management, the majority of the discount card purchasing is actually attributable to a smaller group of professionals who perform what is known as [dropshipping](https://www.abetterlemonadestand.com/what-is-drop-shipping/).

![](/assets/images/cy19/cy19m11/ma18.png)
*Paxful user who has bought millions of dollars worth of Amazon gift cards*

Dropshipping, put simply, is where a business sells items which they do not have in their current inventory. That is, a business will post an advertisement for a particular item online and wait for a customer to come along and buy it. Once the customer elects to buy the item, the dropshipper will purchase the item directly from a supplier and have it shipped directly to the customer. In the context of Paxful and gift card trading, the most simple manifestation of dropshipping is shown in the diagram below:

![](/assets/images/cy19/cy19m11/ma19.png)

Dropshipping comes in many flavors, however, and can be conducted from any place in the world and to any place in the world. More sophisticated forms on dropshipping involve intermediate warehouses called shipping forwarders and play out on a global scale like this:

![](/assets/images/cy19/cy19m11/ma20.png)

Based on interviews I’ve done with people familiar, dropshipping done with Bitcoin-traded gift cards may primarily be conducted by (1) Americans dropshipping domestically, (2) Asians with American connections/accounts shipping to Asia, and (3) Nigerians with American connections/accounts shipping to West Africa. It isn’t exclusively these groups, however, and the model can be done by anyone anywhere.

In light of this dropshipping revelation, it is now clear why certain cards on Paxful are more popular than others. In general, the most popular and voluminous gift cards tend to be ones which can be redeemed for small and shippable items or which are wholly digital (Steam Wallet, iTunes, etc) and therefore globally redeemable. Additionally, I suspect that many of the goods involved in dropshipping are ones which have limited availability in various countries for reasons relating to import tariffs and protectionism.

Dropshipping as a business ranges in sophistication and is talked about at length on a variety of [online forums](https://www.aspkin.com/forums/) where people strategize how to hide from and/or not upset the terms of service of Amazon or others as well as the best logistics practices, and so on.

Conclusion:
===========

Paxful is truly a showcase of the interesting, beautiful, novel, and bizarre ways that Bitcoin is manifesting itself into our world. While I’ve focused primarily on gift card trading across the United States, Nigeria, and China corridors, there are many other stories playing out on Paxful as well. I tried my best to use a mixture of both qualitative and quantitative data to bring a full and accurate picture forward, but there are still many stones left unturned. Furthermore, it was a real challenge to get many of these market participants to speak with me because their activity often times fell into a legal grey area and/or were a form of proprietary knowledge and so at the end of the day I feel like what I’ve uncovered is only a small representation of the true diversity and scale of these activities. I will also be very eager to learn new lessons from some of my more informed readers regarding the topics that I’ve covered. :)

In the next two days I will be **releasing the Paxful data to my website,** [**UsefulTulips.org**](https://www.usefultulips.org/)**,** with daily updating charts and paired with other data layers for the public to study for themselves. If you enjoyed reading this article please follow me on [Twitter](https://twitter.com/MattAhlborg) where I regularly post pithy data observations and trends relating to utility use of cryptocurrency around the world. Also feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/mattahlborg/) if you wish to chat there.

And if you would like to contribute to the project, please do so!

3DT599SqPhDakzL4cJ3tnbFTKxVBk3fwvo

## Appendix:

1.  Americans have tens of billions of dollars in spare gift cards laying around the house. It is a certainty that some of these gift cards are making their way to Paxful for sale. However, there are many other places on the internet where you can sell gift cards at a greater convenience and get a better price so I would think that **Paxful is not the first choice for most regular Americans selling spare cards and probably does not constitute the majority of the volume there.**
2.  It is quite common for a freelancer from a developing country to accept gift cards as a form of payment. This isn’t because they want the gift cards, rather, it is because it is often times the most convenient and easy way for people in other countries to pay  them. Services like Paypal would generally be the first choice for freelancing, but Paypal is not available or heavily restricted in many countries and this includes most of West Africa. In these instances, gift cards are often times the next best thing. In addition to paying professional-level freelancers, there any many websites which use gift cards to pay for what I call **digital micro-services**. These micro-services are related to websites like mechanical turk, swagbucks, surveymonkey, and dozens of others which pay out hundreds of millions of dollars in gift cards every year to earners in developing countries. The interesting thing about freelancing and digital-microservices using gift cards as payment is that **the freelancer receiving these gift cards is fully aware of the fact that they are not spendable in their own country and they instead treat them as fungible stores of value which they can take to places like Paxful to redeem for cash and eventually local currency.**
3.  A [report](https://www.agari.com/cyber-intelligence-research/whitepapers/scarlet-widow-bec-scams.pdf) published earlier this year showed that Nigerian based romance scammers were using Paxful to cash out gift cards sourced from their victims. Additionally, it’s also seems possible that Paxful is a tool used in the vast world of [credit card fraud](https://www.investopedia.com/terms/c/carding.asp).

4.
![](/assets/images/cy19/cy19m11/ma21.png)

5.
![](/assets/images/cy19/cy19m11/ma22.png)

6\. Despite the logic of this activity and hearing of it second-hand from Nigerians, I wasn’t able to get testimony from a Chinese person in Nigeria who could confirm this.

* * *

Thanks to my research sponsor [**dlab**](https://dlab.vc/), several employees at Paxful for interviews, [**Reggie Adaka**](https://twitter.com/ozomediacrypto), LocalBitcoins and forex trader of Nigerian origin residing in the UK, [**Eduardo Gomez**](https://twitter.com/Codiox), Head of Support at Purse.io, Venezuelan-born LocalBitcoins trader, and sovereign individual, **several Nigerian gift card sellers including Victor Oluwasegun**, **several gift card buyers/drop shippers**, and [**Nick Plante**](https://www.nickplante.com/) for reviewing my grammar and overall readability.

Also thanks to my data analysis volunteer [**Boaz Sobrado**](https://twitter.com/sobradob). We are looking for some front end help with the website so if interested please contact me.

**Conflict of interest disclosure:**

Paxful has discussed paying me to research and write future articles.
![](/assets/images/cy19/cy19m11/ma23.png)

***

{% include signup.md %}
