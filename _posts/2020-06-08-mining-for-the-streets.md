---
title: "Mining for the Streets"
permalink: "/mining-for-the-streets"

author: diverterbtc

tags:
  - Diverter "No ID" BTC
  - 2020 Q2
  - Mining
  - Home brew
  - DIY
  - Mining Calculator
  - Mining Profitability
  - KYC
  - No KYC
  - Fungible
  - Antminer
  - Whatsminer

excerpt: Diverter "No ID" BTC shares a really fantastic report about the realities of mining in 2020. Posted June 8, 2020.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Mining for the Streets](https://keybase.pub/diverterbtc/)
### By [Diverter "No ID" BTC](https://twitter.com/DiverterNoKYC)
### Posted June 8, 2020

[**Download**](https://diverterbtc.keybase.pub/Mining%20for%20the%20Streets%20(4)%20(1).pdf?dl=1) the orignal *Mining in the Streets*  report PDF.
{: .notice--info}

![rig in a box](/assets/images/2020/m6/d1.png){: .align-center}

*Simple Guide for Acquiring Bitcoin Without KYC/AML Using ASIC Mining*

## Introduction
For years the narrative that has been pushed regarding Bitcoin mining is that it’s a fool’s game, better left to the professional mining farms and big players due to shrinking profitability. This guide aims to show that this is overly simplistic and narrow-minded in its view. In fact, as ways to acquire BTC without going through the dangerous KYC/AML verification process shrink, mining becomes more and more intriguing for the average user. By having the ability to create an account with no real verification required, you can simply hook up ASIC miners, plug them into a mining pool, and begin receiving payouts for your provided hashpower directly into your personally controlled Bitcoin wallet without providing any KYC/AML identifying data to be scraped.

![genesis mining miners in a rack](/assets/images/2020/m6/d2.png){: .align-center}

## The Skinny on Mining in 2020

We are all aware of the perils of attempting to mine Bitcoin profitably. Between the new hardware that is incrementally released so that you never seem to have the newest version, to the huge mining farms that pop up and fire tons of hash at the chain. It is very important to understand the difference that proper hardware plays in this calculation.

For a solo, or as I like to call it “Garage Band Miner”, it is imperative that the miner purchased be relevant for some time to come. What the home miner wants to keep in mind is to be able to recoup the funds paid to purchase the machine (ROI), and have the machine then still be able to run, and preferably still be producing BTC near or above profitability levels if possible.

It is here I must stress the marked difference in mentality to be taken when entering into this task-- Home mining is not a business model . The most profitable Bitcoin miner on the market today, even with free electricity, will net you ~\$10 per day in USD profit at current BTC prices, and cost upward of \$3,000 USD to obtain. If BTC price were to quadruple overnight, that profitability would likewise go up if the hashrate remained the same. As we know, however, that won’t be the case. At $100k BTC everyone that has ever owned a miner will have it fired back up, which then causes a difficulty increase, and profitability stabilizes. What most don’t understand is the dynamic ability of the difficulty adjustment makes mining a near perfect mechanism for balancing the market.

So if you plan to begin Bitcoin mining as a business, I sincerely hope you have millions of dollars to get started. If you plan to begin mining as a way to acquire BTC without KYC/AML regulations, and to help maintain the security of the network that you have time and value invested in at the same time, the barrier to entry is much lower. **Knowing the difference between these two is paramount to having a good experience with Bitcon mining.**

![genesis mining miners in a rack](/assets/images/2020/m6/d2.png){: .align-center}

## Infrastructure Needs

During mining, electricity is expended and miners rewarded with BTC in the event that a block is “found”. <strong><u>Thus, the first critical need for mining is an energy source.</u></strong> This available energy source is also one of the considerations needed when buying your miner.

**Most miners require 220 volts (V) electricity to operate at maximum efficiency**. There are some miners that, with a proper firmware upgrade, may be able to operate at 110V and achieve normal hash power, but that requires some technical knowledge of the miner, and generally uses a higher number of watts (W) to generate. Some S9's, for example, may be able to run on 110V, but in the 6.25 BTC subsidy epoch, these miners are generally less profitable at \$0.04/kWh than an S17 at \$0.07/kWh. Having said that, *if in a situation where electricity is essentially free*, they can be useful and have a very low barrier to entry. S9's can be purchased for <$50 now due to their limits.

*In the US, many residential buildings are not equipped with 220V outlets*, but rather use the standard 110V. There are exceptions of course, but for the most part 110V outlets is what you will see. If you wanted to run a larger miner in these conditions, my advice would be to **have a licensed electrician install the 220V outlet and be done with it**. The price tag on this usually runs around $200-300, depending. I advise against the DIY attitude in this matter, for safety reasons; but understand it can be and is done by some users. I'm sure guides can be found for such things, but as I don't recommend I won't be linking.

*A 110V-220V converter will not supply the miner with the necessary efficiency in most cases.*

- Know your electricity infrastructure beforehand . Visit here for specifications of various Bitmain Antminers to understand the electrical requirements (Volts & Amps).
- The second critical infrastructure requirement is steady internet access and ethernet connection. You need ethernet cable connection on each miner, if running more than one. The good thing is ethernet cable can be run for a good deal of distance, so miners do not necessarily need to be in close proximity to the router.
- In addition, these miners are very loud machines, often reaching decibel (db) levels between 60-90db. To set a miner up in the bedroom of your apartment would be like having a conversation while standing near a jet engine. Intolerable. There are ways to mitigate much of the noise, which we will discuss later.
- The final infrastructure piece to keep in mind is the heat generated by the miners. If you have ever been in a dedicated server room, you know that the heat given off by a running computer chip is immense. ASIC miners are no different, and most miners come equipped with intake and exhaust fans designed to help feed air over the working chips to keep them cooled. So, a miner set up in your bedroom will sound like a jet engine and have your entire room feeling like a sauna in short order. This is unacceptable for most.

<strong><u>Infrastructure requirements likely the largest barrier to entry. Make sure you have them covered before buying a miner. If these requirements are not able to be overcome or are economically infeasible, it may be necessary to look into hosting options.</u></strong>

## Miners, Miners Everywhere

<strong><u>Your choice of miners depends on your infrastructure abilities and electricity costs</u></strong>. I generally recommend buying new, as longevity of operation is key to achieving ROI, and a miner you buy second-hand may have been run in excessive heat for extended periods, run in especially dusty, humid, or oxidized areas, or otherwise generally abused. The last thing you need is to spend your sats on a piece of equipment that runs for a week then leaves you with a nice looking conversation piece, or just shows up DOA.

*However, some of Bitmain's S17 line have had a litany of issues, and repair or return from Bitmain is expensive in shipping alone, nevermind the fact that many people claim to have received back either the same miner they sent in or an equally bad machine.*

I can only speak to my personal experience, which is with the S17 PRO 50Th/s model. I absolutely love them. *There is a Telegram group for the growing number of dissatisfied customers of the S17 line, linked [here](https://t.me/Bitmainminers).*

It is worth bearing in mind many factors come into play, such as different facilities and temperatures, setups, etc. From what I have been able to gather, there are far less complaints with PRO model Antminers in general, and I haven't noticed any for the particular 50T model I run. **Several complaints seem to come from the S17+ models**. *Point being, buying a slightly used S17 model from a reputable dealer known to put accurate grades on equipment is probably not a terrible idea for the time being*. This can at least let you know it shouldn't arrive dead and likely runs without issue.

Hopefully Bitmain rights the ship with the S19 model; but if they don't, **MicroBT** will continue to take market share as long as they produce even decent quality miners.

*For a single, Garage Band Miner, there is one miner on the market today that I can confidently recommend*. That miner is the **Bitmain Antminer S17 PRO 50Th/s edition**.

You will note there are several versions of the S17 model, which as mentioned before, Bitmain strategically releases with slightly higher hash rate on each successive miner in an effort to FOMO you into buying new again. If you are paying attention though, as with anything, you find the signal in the noise. <strong><u>This machine runs on 220V electricity, and will net you a true average of ~51.5th/s at a power consumption of ~2000W</u></strong>.

This is remarkably efficient. For comparison, the soldier of SHA-256 mining, the Antminer S9, nets the miner 13.5Th/s at power consumption ranging from 1150W-1400W. **So the 50T model provides nearly 4x the hashing power on less than 2xthe power consumption**.

That isn’t even the most beautiful part of the S17 for the home miner. This version has several settings:

- **Normal--50Th/s @ 1945W**
- **Turbo--Listed up to 62Th/s @ 2250W, actually averages around 57Th/s daily**
- **Low--36Th/s @ 1296W**

For those times when BTC rises sharply in price and the difficulty adjustment hasn’t recalibrated yet so you throw every hash you have at it--**Turbo**. To make it through those brutal “crypto winter” bear markets, or for those with high energy costs--**Low**.

The specific numbers for the S17 PRO 50Th/s model can be found [here](https://support.bitmain.com/hc/en-us/articles/360021167174-S17-Pro-Specifications). The efficiency of this miner, coupled with a reasonable price, make it an excellent choice in my opinion. MicroBT Whatsminer M20 and M30 lines have come out swinging back against Bitmain dominance. They generally run a bit higher on energy consumption, but overall Joules/Terahash efficiency remains competitive if not better than Antminer.

The average price for electricity is measured in kilowatts per hour (kWh), and in the US the average is ~$0.13/kWh. *At Bitcoin prices below \$10,000 USD, this makes mining unprofitable at "normal" difficulty and hashrate levels*. But that's precisely the problem with the blanket claims often seen regarding the "cost of production" for BTC. The cost of production is dynamic, and varies depending on a variety of factors, including electricity cost, hash rate (which then determines difficulty settings), the amount of transactions producing miner fees, and more. **It is virtually impossible to apply some blanket number to say "Bitcoin mining is profitable above \$X.xx"**.

However, we can use mining profitability calculators, of which there are several, to help determine what things look like in reality. I will use [cryptomining.tools](https://cryptomining.tools/calculator) which is a site by [Scott Offord](https://twitter.com/offordscott) a Bitcoin mining proponent for many years. So, what does profitability actually look like with the S17 PRO 50th/s model?

Below are the results on today’s metrics of price, network hashrate, and difficulty, in
normal mode, in USD amounts per day <strong><u>NOT including mining fees</u></strong> (Subsidy=6.25 BTC):

| Electricity | Earned | Cost | Profit |
|:--------|:-------:|:--------:|-------:|
| .07/kWh | $4.36   | $3.28   | $1.08 |
| .09/kWh | $4.36   | $4.22   | $0.14 |
| 11/kWh | $4.36   | $5.16   | $-0.80 |
| 13/kWh | $4.36   | $6.10   | $-1.74 |


You would mine around .000453 BTC per day, equivalent to around \$4.36 If your electricity cost is \$0.09/kWh, you would pay around \$4.22 USD per day to run the miner. What does that really mean? It is the equivalent of going into CashApp with \$4.36 andbuying the .000453 BTC, except when you back out of the app you aren’t broke--you still have \$0.14 remaining. **So while BTC price is \$9,625, you will have paid an exchange rate of \$9,315**. <u>**_You bought at ~3% discount_**</u>.

Looked at another way, you essentially have set up an account on Swan Bitcoin and requested to purchase \$30 of Bitcoin per week in their "Savings" plan. You've obtained .003171 BTC at a cost of \$29.54. You pay your electric bill in USD, you receive BTC. **This is, for all intents and purposes, Dollar Cost Average (DCA) buying**. <u>**_This way though, you have avoided the KYC databases_**</u>.

This may seem like too rosy a picture to paint, so let's look at it from more of a "worst case" type scenario. Difficulty has historically risen in Bitcoin, and in my opinion, is likely to do so for the foreseeable future. The all time high difficulty to this point was ~16.55T. Difficulty rises when more hashpower joins the network, resulting in blocks being mined on average less than 10 minutes apart over a period of 2016 blocks. Conversely, difficulty drops if hash leaves and blocks take longer than the 10 minute target. 

Let's assume then that difficulty will be at least as high as 16.55T, and sticking with the worst case let's assume there are no transaction fees to be awarded. Using instead only the subsidy of 6.25 BTC per block and electricity cost of \$0.13/kWh on the mining calculator again we can find what price Bitcoin needs to be in order for the S17 PRO 50Th/s model to be at least break-even. Quick glance might lead you to believe we need all time high prices to breakeven if we're at all time high difficulty and only half the subsidy amount as the last 4 years; but you'd be wrong.

We find that we see break even levels--essentially buying KYC-free at spot market value in a DCA manner--~\$16,225. However, leaving all variables the same but switching the S17 PRO 50Th/s model over to "Low" power mode efficiency, we find that BTC price only need reach \$14,785 to see breakeven. In such a case, the miner would be mining extremely close to the USD equivalent amount of BTC used in the earlier example of \$30/week, since low power at 16.55T difficulty mines ~.001897 BTC @ \$14,785, or ~\$28.05.

Lots of numbers, lots of "what-ifs", and plenty of opportunity to lose the signal in the noise. So let me get you back on solid ground.

## Where Do I Even Begin

You may have heard of the cutthroat, competitive, and secretive nature of mining--and it's not entirely untrue *if* you are speaking about large mining companies or even pools. However, you'll find the community of miners much more receptive and willing to help, as long as you are willing to help yourself.

*If you come in expecting to be spoon-fed every little thing to do, have your million questions answered now, or with some sort of idea that you don't have to earn your stripes then you will indeed likely have a rough journey.*

Outside that, it's fun and exciting to help others further their Bitcoin journey, and miners are no different. These are bitcoiners, many of them have been for several years. They are also business people, with little desire to waste time and effort on, well, assholes. So don't be one.

In trying to stay off KYC databases, you also want to avoid having your name and information stored with a company such as Bitmain, much like you wouldn't want your info to be held by Coinbase, for example. Luckily, there is a thriving peer-to-peer (P2P) market setup you can leverage to obtain a miner (or 4😉) without having to hand over too much information to do so.

I feel it's important here to note the distinction between non-KYC and anonymous.

<u>**_Buying something without doing full KYC does not necessarily mean remaining fully anonymous. In my opinion, the most important thing is to keep your name, photo ID, date of birth, social security number, and bank account information off an easily requested database of users, such as one necessarily held by the most used Bitcoin exchanges today._**</u>

Often these exchanges are favored for their convenience and ease of use. I'll skip the whole no KYC only spiel, and assume if you are still reading it's because you understand why it is important.

**When dealing in P2P type markets, the trade-off for being able to maintain pseudonymity or not having to do KYC is that the possibility of fraud can dramatically increase**. There are ways to mitigate these risks, such as the use of reputation systems and requiring vendors, but not buyers, to complete some sort of verification that may be leveraged against them in the case of fraudulent activity. Such is the case with my favorite--and recommended--market for buying a new generation ASIC Bitcoin miner.

I recommend Hardware Market on Telegram, which can be found [here](https://t.me/HardwareMarket). I encourage all to read the pinned message in order to best avoid being scammed.

<strong><i>* I do not recommend buying a miner from ANYONE if they are not verified on Hardware Market *</i></strong>

*There is a command that can be given as **!toprep** which reveals a list of verified sellers .*

You can likely also simply scroll through until you find the list as requested by another, so we don't spam the chat. This means they have undergone KYC essentially, and their info will be handed over to proper authorities in the case of any scam behavior. They have reputation scores to help show the most reputable based on the number of successful interactions and the *quality* of those interactions.

Ads get posted by different sellers and/or the companies they work for, and the miners are listed as new/used, often with grades. They denote whether shipping is included or not, where shipped from, there is often video evidence of the miners hashing, etc. In addition, the group is very well moderated by respectable members of the community and I have witnessed some disputes be worked out and resolutions amenable to all parties be reached in the end. Everything does not always go perfectly, but this group and its verified members do a wonderful job of doing the best they can to operate smoothly and efficiently.

I recommend this group because it is easiest to branch off into individual companies or sellers from there, since it acts as a sort of central hub. **I do not recommend Ebay for buying miners**, as the setup is not good from a privacy standpoint, and you run a very real risk of receiving a seriously beat up miner. Example of dust filled Ebay miner shown below.

![dusty miner](/assets/images/2020/m6/d4.png){: .align-center}

As a quick example, I will pick on Kaboomracks for a bit. Their marketplace can be found [here](https://t.me/kaboomracks) and the pinned message outlines why they feel buyers should consider them. You will often see them place ads similar to this:

**81 qty Antminer S17 Pro 50T for Sale**

**Used in Excellent Condition, A**

**$1299 each all-in which includes domestic shipping includes built-in Bitmain APW9 power supplies no minimum order size ships from Ohio, United States  Contact Sales: [t.me/kaboomracksNick](t.me/kaboomracksNick) 🍕#kb00737 #used #sha256 #usa June 2nd, 2020 Miners for Sale → [t.me/kaboomracks](t.me/kaboomracks) 🔆🔆**

It is advised to scroll for ads for miners you would like to buy, rather than post a "Want
To Buy" (WTB) ad in Hardware Market. The reason is simple--scams.

*Posting a WTB order is open season for scammers to DM with very similar looking profiles to verified sellers*

If you send your BTC to these scammers there is no customer service recourse to be pursued. If you scroll for ads until you see one you like, you can click on the links in the ad or the poster themselves to open up a chat that you know is with the correct person. This is because every ad posted in Hardware Market must only be done by verified sellers, and any ad attempted to be posted by an unverified seller is quickly removed, and the poster receives a warning. After 3 warnings, they are banned. Can also click the name of the verified seller directly from the !toprep list.These are the tradeoffs of working around regulations, and it's on us to make them work.

Say you wanted to buy one of the 81 S17 PRO 50Th/s miners at an all-in (shipping to your door in US, in this case) price of \$1,299. Kaboomracks accepts BTC as payment, so you do not have to give over your banking information or reveal your account at all. They will ask of you (as most all sellers will for their own records) some very basic, vanilla information such as your "Name" and "Company Name"or the like. **There is no need for them to verify this generic information, so no need to panic and reveal everything about yourself**. There is no "selfie" to submit, no singular honeypot to be mired in. As for the shipping address, this is where your personal threat modeling comes even more into play.

<p style="color:red;">KYC free != Anonymous</p>

If State agents try hard enough in situations such as these, it is likely one may be deanonymized using a shipping address. If that is a concern, I leave it on your own research to find ways of setting up P.O. Boxes or having them set up in different names, or having it delivered somewhere other than your home address. *<u>In my opinion, it is very likely enough to keep name, DOB, SSN, bank info, and photo ID off an exchange database</u>*. Only supplying a shipping address provides a certain amount of deniability, requiring far more work than sending a single subpoena to an exchange and rounding up 1 million users at once. That part is on you to decide, I advise not making it too difficult, and instead aiming to keep the lowest hanging fruit out of Big Brother's face. **If you have concerns about these things, have a frank conversation with the verified seller about your issues**. As I said, dealing with fellow bitcoiners generally makes explaining these things much easier than telling Joe Schmoe why you value your privacy. These guys get it.

Once you order and receive the miner, and have verified it is the miner you ordered in the
condition advertised, you and the seller will post a final message in a chat group specifically used to increase/decrease reputation. The seller will claim to make a deal with your Telegram username, you will reply to that message with a simple "Confirmed", and that's that. You are now ready to mine on.

## Hello? Is This Thing On?

Now the fun begins. Let's assume you are mining at home. Let's also assume you have a significant other (though I feel like many in this space need only pull a plug and deflate theirs) and are interested in both mining and keeping the spouse. The other assumptions being made are that you have 220V 20A power outlet and a router to connect ethernet to the miner.

**<i><u>Many new gen miners have two (2) plug in needs for 220V power cords.</u></i>**

![dusty miner](/assets/images/2020/m6/d5.png){: .align-center}

They have built-in Power Supply Units (PSU) but need two cords plugged in to operate, not just one, as you can see from the picture on this page. **Further, it is important to note these miners rarely, if ever, come with power cords that are compatible with US power outlets**. I suggest universal adapters, which can be bought for a few dollars usually on Ebay or Amazon to ensure you have the right gear when the miner arrives. Generally compatible power cords and multi-outlet extension cords are found in Hydrofarms equipment pages, if not able to simply find them in Hardware Market or related channels themselves. They have the CN style outlets, and sell for around \$15-25, example of where to start [here](https://www.amazon.com/Hydrofarm-Extension-Cord-240v-ft/dp/B0055F66ZS) . 

If you don't have a sufficient amount of CAT-5 ethernet to extend from the router to miner placement, might want to go ahead and pick some up as well. The rest of the supplies needed will really depend on your personal placement of the miner.

![dusty miner](/assets/images/2020/m6/d6.png){: .align-center}

Do you have a room that can be kept cool enough to allow your miner to operate? **The cooler you are able to keep your miner, the quieter it will be**. It needs to be above freezing to prevent issues, but if you are able to provide cool enough air for the intake fans to blow over the miner, and able to relieve the exhaust heat as well, the fans don't have to work nearly as hard to keep it cool, and thus move slower and quieter. One way to help mitigate the noise through heat reduction is through the use of 3d printed duct shrouds that can be applied to the outside of exhaust (or intake) fans, attaching flexible ducting, and directing the heated air to a different area. This may sound difficult, but it's actually quite easy. Sellers on Ebay like the one [here](https://www.ebay.com/itm/Antminer-DR5-S11-S15-T15-S17-T17-Z9-Z11-6-Double-fan-duct-Shroud-eBit-10-2-also/303149608185?_trkparms=aid%3D1110002%26algo%3DSPLICE.SOI%26ao%3D1%26asc%3D225080%26meid%3D6810d7a9d73d43af960de05dd895c2af%26pid%3D100891%26rk%3D1%26rkt%3D6%26sd%3D303185937067%26itm%3D303149608185%26pmt%3D0%26noa%3D1%26pg%3D2332490%26algv%3DSellersOtherItemsV2%26brand%3DAntminer&_trksid=p2332490.c100891.m5206) offer these shrouds for cheap prices, and they are well made. Will need a bit of cleanup of the rough strands before applying, but work great. 

![dusty miner](/assets/images/2020/m6/d7.png){: .align-center}

<u>**_Whatsminer and Antminer may not be compatible, so be sure to check on your miner's specifications before ordering_**</u>. Usually either be 120mm or 140mm, but check each miner before ordering. Flexible ducting can be picked up or ordered for around $10-20 online or at Wal-Mart, takes nothing more than a screwdriver to mount it all, *mounts right on the miner using existing screws and holes, no scary drilling or extra parts to worry over*.

Depending on your situation, you may need to go even a step further. Might want to keep your miner(s) "on ice" to try and keep sound low and the spouse happiest. Insert the cooler as a possible sound barrier.

![dusty miner](/assets/images/2020/m6/d8.png){: .align-center}

There are some sellers on Ebay offering pre-built coolers, generally they have been custom fitted for S9 miners, so only have a single intake and outake. This can likely translate pretty easily to Whatsminer single-tube ASIC's, or may require some modifications to work for Antminer double-tube miners. *To DIY the entire thing is not a very difficult or costly endeavor, so if going with a cooler, I say just go for it*. Can grab a normal, 38-48 quart cooler from Walmart for \$20-35 in most areas. It is helpful to have a small, hand-held drill with a circular bit, but even to buy all from scratch--cooler, drill, bits, ducting, and don't forget some soundproofing foam--still very likely looking at less than $100-150 and less than a days work to put all together. Not bad to maintain a happy home. Doing this all yourself works fine, it doesn't have to be perfect. **It's a very simple concept; cool air in, hot air out**. The further you can easily get the hot air out, the better. Remember, we're talking about a miner or two, not a farm.

There's no investigation coming into the massive electricity use of your home, no heat signature changing dramatically, and no need for professional installation help. It can look as crude as you like. *If it gets cool in and hot out, **mission accomplished***.

![dusty miner](/assets/images/2020/m6/d9.png){: .align-center}

Once you have your setup in place, you will need to use ethernet to connect from router to miner. You will need a computer on the same internet connection in order to be sure to find the IP address of the miner. It is a simple process to configure the miner, takes only a couple steps, and is detailed here as well as any of several YouTube video guides. Very "n00b" friendly setup overall. If you do run into problems, again there are several places to reach out to fellow miners for help, including on Keybase .

## Pool Selection

Mining pools are ways for many miners from geo-diverse locations to "pool together" their hash rate in an effort to increase chances of winning a block. I won't spend much time on pool types, as it's easy to understand and a personal choice as to which pool you want to trust with your hash.

<strong>I will say this--<u>mining pools have gone and do go broke, and there is a chance you do not receive payout for hash if that happens.</u></strong>

Usually this happens if an FPPS type pool hits an unlucky streak and does not have the Bitcoin required to pay out. Pools such as Slush, running a different type of pool where miners are only paid if/when a block is found, run less risk of going bust. *However, if no blocks found, no BTC earned*, unlike FPPS pools like Poolin for example, where contributing miners get paid from the pool coffers *regardless of the number of blocks found*. There are tradeoffs to each, and it is fiercely competitive. Find more opinions about this subject [here](https://t.me/MinersPoolParty) and learn about different pool types [here](https://medium.com/luxor/mining-pool-payment-methods-pps-vs-pplns-ac699f44149f).


## Hosting Services

Now we reach a portion with which I am a bit unfamiliar, but I realize may be a necessity for many would-be miners. As a result of too high electricity or simply infeasible infrastructure abilities, hosting services are becoming more widely used and viable options.

My advice concerning hosting boils down pretty simply to this: <strong><em><u>Don't skimp on cost at the expense of reputation.</u></em></strong> If it costs a cent or two more in kWh to host,  but is with a reputable host that is far less likely to "take the money and run", pay the little extra.

Again, we are in a highly unregulated market, which many of us ask for. That means responsibility is transferred more to ourselves to police bad actors and make good decisions. That said, to think you'll get out of Bitcoin without ever having been scammed is likely a foolish dream. Keep the amount low, learn, and spread the knowledge to others.

I'm going to give a bit of info relayed to me by an outstanding <em>(and criminally underfollowed)</em> bitcoiner in [CrazyK](https://twitter.com/Crazyk_031). You may have seen his amazing luck in winning a brand new MicroBT Whatsminer M30S 88Th/s a short time ago. His situation did not allow for him to mine at home, and so he explored hosting options with [Blockware](https://www.blockwaresolutions.com/). They offer hosting services for new gen miners, as well as the sale/host package deal, for which they offer better kWh cost deals.

CrazyK reached out to Blockware about hosting a single M30S and they were able to accommodate him. The electricity cost was quoted at \$0.067/kWh, and would likely be lower if more miners were hosted or if the miners were bought from Blockware themselves. **Blockware does not actually provide the hosting**. Another company does that, and there is a fairly lengthy, and rather one-sided, contract involved. **_This is going to be necessary for hosting, since you are empowering a trusted 3rd party with control of your machine and hash._** Luckily for all, CrazyK is planning to do a more detailed write-up on his overall experience, especially regarding hosting. I'm looking forward to that myself. I'll leave many details to him, and paint with a broader brush here instead. There are one-time setup fees, and then ongoing monthly electricity cost, which must be paid in full upfront. The electricity cost then, using M30S specs and the $\0.067/kWh rate, is ~\$180/month. _So the recurring cost for this contract, which is for one year, is that \$180 upfront monthly._

*   **_Using current network stats, the M30S in an FPPS pool should mine an average of ~.023929 BTC/month, which at current exchange rate is ~\$230. This means someone hosting a single M30S at these rates is essentially DCA "stacking sats" at a rate of $57.50/week auto buy, at an exchange rate of 1 BTC=\$7,522. Instead of paying an extra fee on top of spot market value to auto-DCA, you can do it at a hefty discount._**

Sounds too good to be true? It kinda is, seeing as not everyone gets a free machine which is valued at over $2,000 dropped at their door for free (I'm not at all jealous) But the bigger point is the fact that his experience has been pleasant to this point, and hosting is an actual, viable option if you can't or don't want to go through the trouble of hosting your own machine. Can find out about hosting services using Scott Offord's [cryptomining.tools](https://cryptomining.tools/directory) site. 

A couple of parting shots about hosting single or small numbers of miners: Some hosting services don't like taking single customers, so check around. _Get a knowledge of how miners work and the fluctuation in hashrate before you get involved_, in order to keep from being the guy that emails to his hosting service 4 times a week asking why their 88Th/s machine is only showing up as 75Th/s when they just checked it. Can watch an actual S17 PRO 50Th/s model running on Poolin (one of mine) [here](http://www.poolin.com/my/9075026/btc?read_token=wowa8FoQWUPyRSGgIjljEOJPvmKNiCInMAYzbKgxhwemNgGOAHbuX6Fqx7yEevl3). 

**As with anything, do not see magic dollar signs and rush into something without understanding all costs involved.** That is a sure way to end up disillusioned and "mad at Bitcoin". Tradeoffs and incentives matter more than most people understand, it pays to learn as much as you can before making any moves.    

## Are We There Yet?!?!?

Let me bottom line this thing for you. **Bitcoin mining is _NOT_ a get rich quick scheme**. 

In fact, I would argue that beginning mining for yourself requires the _most_ bullish sentiment of all. To mine, you must put forward a not-so-insignificant amount of upfront money, be it BTC or USD, with the expectation that you will recoup those expenses at some point in the future--much like buying bitcoin. The difference being, you can't just wake up on a Thursday having 'lost faith', jump on CashApp and sell all your BTC for USD, turn and walk away. 

**Investing in mining equipment, infrastructure, and even hosting contracts means it's virtually impossible to just walk away.** It is the ultimate test of time preference. If your initial miner purchase takes 2-3 years to make a ROI and be truly profitable, is it worth it? Why not just buy bitcoin and hold it instead? Wouldn't you end up coming out better that way? This [report](https://www.blockwaresolutions.com/research-and-publications/mining-bitcoin-vs-buy-amp-hold-bitcoin-which-is-the-optimal-strategy-to-capture-the-long-term-opportunity) throws a big wrench in that argument. Past performance is not indicative of future returns, of course. 

We are in the beginnings of a new deployment cycle, with the M30S/M30S+(+) and S17/ S19 PRO hitting the street now. Their life cycles are still TBD--so the gamble persists. Twitter leaders would have us follow the Stock-to-Flow model predictions, with varying targets between \$55,000-288,000 per 1 BTC within the next 2 years. If so, mining profitability likely sees a spike, newcomers FOMO in chasing a dream, and (by then) 'seasoned' vets have piled sats up regularly the whole time. In addition, the fact you've been able to avoid full KYC compliance sets you up for the ability to avoid something else as well--capital gains taxes. 

**If buying through 3rd party centralized exchanges that are willing and in most cases obligated to turn over the holdings and tax liabilities of users, defunding the government becomes much harder.** If looking to cash out from years of HODL'ing when BTC hits $288k, you must understand how much bigger (and thus how much more important and scrutinized by government) Bitcoin will be. **How much more interested in holders identity and tax liabilities will the State likely be?** How willing, and more importantly how **_able_**, are you to resist attempts to compel disclosure and pay huge taxes on those gains? 

Will the % of gains lost to taxes be more or less than the premium you may have paid to acquire those BTC in a non-KYC fashion? And if not so much interested in gains, but more so in taking power from the State, how much are you able to contribute to the security and decentralization of the Bitcoin network? What kind of future do you see for Bitcoin and bitcoiners in an adversarial environment? 

_The time to strike is upon us_, immediately post-halving coinciding with new miner life cycles beginning and chips perhaps approaching uncertainty principle levels. Each bitcoiner must decide for themselves the depth of their interest in BTC; just be sure you're actually doing that. 

**Don't fall victim to the narrative pushers that would have you believe mining is "too hard", "too expensive", or "better left to the big players".** Sounds an awful lot like the same thing bankers and governments tell the masses about fiat money and economics now, doesn't it? Don't let me influence you--that's not my job. I just want the knowledge to be out there for anyone to pursue for themselves. And I certainly don't want the DM's from people that spent too much on a shitty miner and now hate Bitcoin and the asshole that inspired them to buy! 

![dusty miner](/assets/images/2020/m6/d10.png){: .align-center}

**_I do want adversarial thinkers, narrative challengers, and fighters._** This Bitcoin thing was founded and secured by such minds, and it's my opinion if Bitcoin continues to succeed, it will be because of the next wave of these minds and their contributions; both in software and code they push _and_ in security and hardware run by users. Click the links, find some resources, and decide for yourself. Help is out here in the form of guides and personal interaction if you know where to look. I hope I have at least provided a bit of illumination for those paths. 

**_Stay adversarial, frens._**

## Additional Links

- [Mining Calculator](https://whattomine.com/coins/1-btc-sha-256?hr=110000.0&p=3250)
- [Difficulty Calculation Site](https://diff.cryptothis.com/)
- [Twitter Profile](https://twitter.com/DiverterNoKYC)
- [Keybase Profile](https://keybase.io/DiverterBTC/chat)
- [Telegram](https://t.me/DiverterBTC)

***

{% include signup.md %}