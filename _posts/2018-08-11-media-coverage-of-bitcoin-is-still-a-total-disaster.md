---
title: "Media Coverage of Bitcoin Is Still a Total Disaster"
permalink: "/media-coverage-of-bitcoin-is-still-a-total-disaster" 

tags:
  - Nic Carter
  - CY18 Q3

excerpt: NIc Carter looks at 

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      read_time: true
      comments: false
      share: true
      related: false
---

# [Media Coverage of Bitcoin Is Still a Total Disaster](https://medium.com/s/story/media-coverage-of-bitcoin-is-still-a-total-disaster-7d0d34d98971)
## A recent Washington Post article shows how journalists get cryptocurrency wrong
### [Nic Carter](https://medium.com/@nic__carter)
### August 11, 2018

I 'm fed up with journalists who are either ignorant or unwilling to learn about cryptocurrency holding forth on its perceived weaknesses. Recently, the _Washington Post_ published a piece entitled "[Bitcoin is still a disaster](https://www.washingtonpost.com/business/2018/08/10/bitcoin-is-still-total-disaster/?utm_term=.24611791b51a)" by economic affairs reporter Matt O'Brien, which I feel relies on mistaken assumptions to paint a misleading picture of the world. Today, I'd like to engage with some of the claims made in the piece, and show how O'Brien — among many others — get it wrong.

## Claim: Currencies are meant to be stable

_"There's one thing a currency is supposed to do that bitcoin never has. That's maintain a stable value."_

This assumes that bitcoin is a currency, and that the definition of currency is normative ("x should do y") as opposed to descriptive ("things of type x have the qualities y and z"). I'd classify Bitcoin the protocol as a complete monetary system, and bitcoin the unit of value as a commodity money, which has the potential to become a gold-like reserve currency. Commodities fluctuate — that's what they do.

Additionally, currency isn't meant to maintain a stable value. Monetary policy is used for a variety of macroeconomic objectives, including targeting GDP growth, unemployment rates, inflation, trade balances, and more. If stability was the objective, the Federal Reserve Board would target zero percent inflation rather than the two percent that it currently does. Am I moving the goalposts? It's matter of figuring out how bitcoin is used, and what it was intended for. I'm not sure [bitcoin creator] Satoshi Nakamoto ever defined bitcoin as a currency. He defines it as a system for electronic transactions, a peer-to-peer version of electronic cash, and an electronic payment system. He envisions bitcoin as a protocol and a bearer digital unit of value.

The interpretation of bitcoin as a currency is mostly inferred by outsiders imposing a particular view upon the protocol. Unburdened by priors, a neutral analyst would probably describe it as something similar to gold. In fact, Satoshi described PoW (proof-of-work) with a reference to gold mining, and later discussed bitcoin as analogous to a scarce, inert, infinitely portable metal which might develop a monetary premium. He clearly saw it as a gold-like commodity which would recapture those same properties in the digital realm, and I think this the most fitting interpretation of the system.

## Claim: Bitcoin was designed with volatility in mind

_"Why has bitcoin's price been so up-and-down? Well, part of it is that it was designed that way."_

This is an odd rewrite of history, or more charitably, a very strange interpretation of bitcoin's purpose. The [impossible trinity](https://en.wikipedia.org/wiki/Impossible_trinity) tells that it's impossible to have free capital flow, sovereign monetary policy, and a fixed exchange rate all at the same time. Bitcoin was designed with sovereign monetary policy and a free flow of capital. No one underwrites or backs bitcoin, so it cannot be pegged to a real-world basket of goods. That's the same with gold. Both have emergent monetary premia. This can't be planned for — it just so happened that way. Needless to say, Satoshi didn't design bitcoin to be unstable, he wanted to solve the problem of double spends with digital cash such that it didn't rely on a single validator. Its volatility is an emergent property, not a design objective.

## Claim: Validating transactions is the source of its computational overhead

_"[...] the problem [with a decentralized network] was that the only way to do that would be for every member of that network to keep a record of every bitcoin transaction there had ever been — that way they knew who had bitcoin to spend — which would require_a lot _of computing power."_

This is a common misconception. PoW and mining ensures that the network deterministically converges to a shared history, without any subjectivity or off-chain coordination. The fact that the minted units have value means that miners are incentivized to behave appropriately in the short and medium term. And the fact that those units are worth $x means that miners will pay anything up to $x to obtain them. This is the source of the large quantities of computing power allocated to the network — the combination of efficient mining hardware and large amounts of value at stake.

The validation and record-keeping is behavior conducted by full nodes, not miners. The cost of maintaining the bitcoin data store is an externality pushed onto full nodes through bandwidth and storage costs. This is NOT the job of miners. This is a basic distinction lost on many.

## Claim: Bitcoin's volatility is unnatural

_"But even this inbuilt volatility doesn't fully explain why bitcoin has been on such a roller-coaster ride. Something else must be going on, and that something is plain-old manipulation."_

Volatility isn't inbuilt, it's a feature of every non-pegged economic asset. The _Post_ should keep its fragilista-thinking to itself.

> Does the Post have any proof that markets are not long-term efficient? If so, they have a Nobel prize in economics to collect.

_Plain old manipulation_? You really mean to tell me you think a $100 billion network was manipulated into existence? Is it so difficult to accept that bitcoin provides a differentiated, useful service to millions of people worldwide, and that's why it has value? Does the _Post_ have any proof that markets are not long-term efficient? If so, they have a Nobel prize in economics to collect.

_"[...] what seems to still be happening in 2018 with various pump-and-dump schemes."_

Don't conflate bitcoin with random worthless altcoins. There is a lot of PND [pump-and-dump] in this industry, but it is infeasible in the extreme to PND bitcoin. If you're part of a PND group, you target alts in the $50–$300 million range, not bitcoin.

## Claim: Bitcoin is only used as a currency due to the wealth effect

_"The first is that what makes bitcoin work as a way to transfer things — the expectation that its price will keep rising."_

That's not what makes it work. It works as a way to transfer things because it's a pretty good distributed clearinghouse for value. If bitcoin were stagnant at $1000 for the next ten years, it would remain a good way to transfer things.

During the 18-month bear market that began in January 2014, people still used bitcoin. In fact, usage grew consistently the entire time.

![](/assets/images/cy18/cy18q3m8/nc-1.png){: .align-center}
Price (solid red line) and transaction count (shaded red area) during the 2014–16 bear market. Image: [Coin Metrics](https://coinmetrics.io/charts/#assets=btc_log=false_roll=7_right=txCount_zoom=1377947972765.212,1473140404379.312_includeZero=true)

Bitcoin offers transactors a rival benefit; something they cannot find anywhere else. It's unique among cryptocurrencies, as it boasts the best reliability, uptime, dedicated track record, and protocol developer community. It's unique among monetary assets because it offers properties not instantiated by gold or the USD. There's a reason people choose bitcoin.

## Claim: Bitcoin's deflationary characteristics mean that no one uses it

_"Why spend $100 worth of bitcoin today if you think it's going to be worth $1,000 in a not-too-distant tomorrow? You wouldn't. And people aren't."_

Shameless plug: I urge you to consult my website [Coin Metrics](https://coinmetrics.io/), where we make this data free and available so anyone can use it. Conservatively, bitcoin saw $2.5 billion in on-chain transaction volume yesterday. That's omitting all the off-chain transactions that occur on Opendimes, on second-layer networks like Lightning, and internally at Xapo and at Coinbase.

![](/assets/images/cy18/cy18q3m8/nc-2.png){: .align-center}
Image: [Coin Metrics](https://coinmetrics.io/charts/#assets=btc_log=false_roll=7_left=adjustedTxVolume_zoom=1483221885644.5312,1533772800000)

In the last year, bitcoin routinely hosted the transfer of $2B worth of bitcoin a day, up to a peak of about $16B of bitcoin a day. That's a lot of fake transactions. The anticipated response to this from the skeptic is that on-chain volumes are just a clearinghouse for the multitude of exchanges worldwide, or simply a way for individuals to access the altcoin casino. The former is probably true; we have good evidence that bitcoin is mostly an [industrial network](https://medium.com/hasufl/an-analysis-of-batching-in-bitcoin-9bdf81a394e0) dominated by exchanges and power users rather than one that caters to end-users. Using the rough heuristic that industrial users tend to [batch transactions](https://p2sh.info/dashboard/db/batching?orgId=1), we can see that 30–40 percent of the network is industrialized in this manner.

There's nothing wrong with this. It simply means that bitcoin acts as a decentralized global settlement network for a number of endpoints that connect it to everyday economic systems, with which users transact at the individual level. This is pretty radical! A decentralized, neutral, untamperable central bank that settles flows on a continuous basis between a global network of smaller banks (exchanges, merchants, and custodians). What a concept.

As for the "bitcoin as an on-ramp to the altcoin casino view," if this were true, then bitcoin would have cratered along with altcoins as they fell 80–90 percent over the last six months. However, bitcoin has shown great strength against altcoins during the bear market. If you look at any index, bitcoin has regained dominance. This pokes holes in the story that it is only used for access to altcoin pump and dumps.

For context, here's the [Bletchley total market index](https://www.bletchleyindexes.com/) quoted in bitcoins since December. Ever since the contraction began in January, bitcoin has strengthened against the rest of the cryptoasset market.

![](/assets/images/cy18/cy18q3m8/nc-3.png){: .align-center}
Image: [Bletchley Indexes](https://www.bletchleyindexes.com/home)

You wouldn't expect this if bitcoin was only a vehicle for speculation on other cryptocurrencies. Clearly, there is demand for bitcoin in its own right.

## Claim: Bitcoin is illiquid and hence manipulated

_"This lack of liquidity makes it pretty easy for a few fraudsters to push the price up quite a bit."_

This isn't the case, and relies on a flawed reading of the Tether situation. Fundamentally, bitcoin is quite liquid. It has huge volumes on listed exchanges, and probably the same amount again on over-the-counter providers like Cumberland, Circle, Genesis, and Octagon.

![](/assets/images/cy18/cy18q3m8/nc-4.png){: .align-center}
Much illiquid. Very manipulation. Image: [Coin Metrics](https://coinmetrics.io/charts/#assets=btc_log=false_roll=7_left=exchangeVolume_zoom=1483221885644.5312,1533772800000)

Even if you subtract all Tether volume, and all volume from synthetic exchanges like BitMEX, and all swaps and futures volume from the CME and CBOE, you have robust volumes. The market for BTC → fiat (on the right in the chart below) is also quite liquid.

![](/assets/images/cy18/cy18q3m8/nc-5.png){: .align-center}
Image: [Nomics](https://nomics.com/assets/btc-bitcoin)

If you look at the market for fully-regulated futures exchanges, the picture is sunny.

![](/assets/images/cy18/cy18q3m8/nc-6.png){: .align-center}
CME daily volumes (contracts are for 5 BTC). Image: [CME Group](https://www.cmegroup.com/trading/equity-index/us-index/bitcoin_quotes_volume_voi.html#tradeDate=20180809)

Yesterday, 7077 contracts were traded at the CME — equivalent to $215 million. The liquidity picture is strong, and improving.

## Claim: Bearer assets are dangerous and illegal

_"There's a reason, after all, why bitcoin has attracted so many scammers: All its transactions are irreversible."_

You have to take the bad with the good. It's a digital bearer asset, which is completely new. Of course people want to scam with it — it's the best money ever invented. That USD is never used by scammers, right?

_"All of which is to say that if you steal a bitcoin, you get to keep a bitcoin."_

If you earn a bitcoin, you get to keep a bitcoin. If you mine a bitcoin, you get to keep a bitcoin. Strong property rights are a hell of a thing. This is just an incentive to build more secure wallet and custody software. We're halfway there already.

## Claim: Bitcoin still relies on a trusted set of intermediaries

_"Bitcoiners think all of this is worth it. That it's better to have a financial system that is clunkier, costlier and more vulnerable to attacks than it is to have to trust someone — or, more accurately, to_admit _that you have to trust someone."_

Using bitcoin doesn't rely on trust in an individual. If you run a node, use a hardware wallet or a well-concealed paper wallet, and maintain good opsec, you are pretty much set. Of course, to obtain your bitcoin, you may have to use Gemini/GDAX/Square. But no one is forcing you to hold your bitcoin on an exchange. It's only long-term storage on an exchange which requires significant trust in the institution. And bitcoiners universally, vociferously, encourage people _not_ _to do that_.

> Nothing backs bitcoin or pegs it to a basket of assets. That's the point. Bitcoin was designed specifically to avoid the influence of a single authority.

More broadly, bitcoin doesn't remove trust entirely. That's a straw man frequently knocked down by critics. Bitcoin reduces the need for trust in a single institution. Instead, you just have to trust that the code is well-vetted in the typical FOSS [free and open-source software] manner, that the economics that underscore mining continue to hold, and that discrete log problem is still hard. We have plenty of evidence that these things all hold, and will continue to hold. And we have plenty of evidence that, conversely, a single institution in control of the money supply will _always_ abuse its power. If you don't believe me, just check out [what's happening in Turkey](https://www.washingtonpost.com/business/could-turkeys-financial-crisis-have-a-snowball-effect-on-world-markets/2018/08/17/8fdccd88-a16b-11e8-93e3-24d1703d2a7a_story.html?utm_term=.b609c18a0b10) today. Seignorage is a drug — and it's pretty much impossible to kick the habit.

_"Bitcoin exchanges require some measure of [trust] whether they realize it or not."_

Centralized exchanges do. There exist non-custodial peer-to-peer exchanges, like [Hodl Hodl](https://hodlhodl.com/) and [Bisq](https://bisq.network/), for bitcoin. [LocalBitcoins](https://localbitcoins.com/) is another peer-to-peer exchange that places reduced reliance on a single intermediary. Even centralized exchanges can conduct periodic proofs of solvency, if users demand it. And, as with the rest of finance, if the brokerages/exchanges/clearinghouses are regulated under functional regimes, they are strongly incentivized not to run fractional reserves or lose user funds.

The broader point here is that relying on centralized exchanges is inevitable. Many people will trade off decentralization for convenience, and we can't stop that. We can demand that exchanges behave appropriately. There are many exchanges and custodians with long histories of robustness, resilience, and integrity. There is a market for exchanges, and the badly-run ones will fail.

## To sum up

The problem with this article is that the pundit in question has settled on a narrative — bitcoin is a poor economic system — and then searched for various datapoints that confirm his view. Bitcoin is volatile, yes. It is an emerging commodity-money that's becoming financialized and growing from a small tribe of enthusiasts to a global user base. Of course it's volatile. Growth is not linear. Only fragilistas demand it to be so.

Nothing backs bitcoin or pegs it to a basket of assets. That's the point. Bitcoin was designed specifically to avoid the influence of a single authority. Bitcoin is priced exactly where it ought to be — this is always true. Manipulation might work on a 15-minute time frame, but it's just implausible in the extreme that a $100 billion-plus asset class has been manipulated into existence.

Yes, bitcoin relies on exchanges to provide exit ramps for individuals that want to reduce their reliance on sovereign currencies. Sometimes those exchanges get hacked and fail. That is entirely natural. Bitcoin continues to chug along unaffected. It's extremely popular; its strong assurances and settlement guarantees grant it daily volumes in the billions. It is a single order of magnitude behind Visa's economic throughput — that's right, just one 10x away. The gap will probably be closed in the next year. It has an unmatched record of reliability, resilience, and resistance to cooption. For a nine-year-old, this is a pretty good track record. If it were a human, it would be midway through the fourth grade.

Pundits will continue to ignore this; not because they're incapable of reading the data, but because they don't want to. They are deeply afraid of the world that bitcoin threatens to bring about. They prefer a paternalistic, easy-money regime, where occupations like punditry are profitable. Bitcoin promises accountability and a hard money standard. It threatens the existence of bailouts, moral hazard, and fiat-inflationism. In Bitcoinland, the only way to acquire wealth is to work for it. Cronyism doesn't work, as the central bank of bitcoin is entirely indifferent to politics and lobbying. This offends the sensibilities of the partisans writing for the _Post._

Bottom line, the central premise of the article is wrong:

_"There's one thing a currency is supposed to do that bitcoin never has. That's maintain a stable value."_

Bitcoin isn't designed to have a stable value. That just quite frankly isn't what Satoshi set out to build, and that's not the system we have today. Artificial stability — shorting volatility — leaves you destined for a blowup. That is the fate of any non-fully-backed stablecoin. Bitcoin is designed to solve the double spend problem for digital cash, and to provide a predictable monetary policy. It does that very well, it has done that for the last nine and a half years, and it will continue doing that for the foreseeable future. Demanding low volatility on top of that is farcical, and betrays deep ignorance about the tradeoffs inherent in monetary systems, and the way that financial markets work more generally.

Bitcoin is still an emerging, youthful asset. It hasn't reached maturity. It has somewhere in the realm of 50–100 million holders/users; that's global penetration of a percentage point or two. The base layer still hasn't been nailed down, let alone the next layers up on the stack. Development is deliberate and careful, because this is money we're talking about, not a consumer app. Governance is hard to organize; consensus is difficult to obtain. The internet wasn't built in a day, and neither will the protocols for transmitting value trustlessly.

Since the market is constantly revising its expectations for bitcoin, amid a backdrop of growing, unsteady adoption, its exchange rate is volatile. No one is forcing you to hold it; it is totally opt-in. Bitcoin may not make sense for Westerners who live under somewhat credible monetary regimes, but it might be a good bet for an Iranian, a Venezuelan, a Turk, or anyone else who mistrusts their monetary authorities. Truthfully, mechanisms to bring bitcoin to these disempowered groups are still lacking or nonexistent. But they have the right to money that isn't controlled and minted by a hostile state. This is why bitcoiners work to make global access to this economic institution a reality.

Bitcoin's complexity doesn't acquit these pundits for getting simple facts about bitcoin blatantly wrong. And ultimately, their ignorance hurts their bottom line. Being amateurishly wrong about basic details of a system that is widely-understood undermines their integrity and makes readers question their work. The _Post_'s owner Jeff Bezos should understand this and demand more from his employees.

I f any of this resonates with you, and you want to learn about this novel economic system, here are some sources I recommend for a better understanding of bitcoin:

* [Coin Metrics](https://coinmetrics.io/): no-nonsense open data and charting platform informing users about the actual usage of cryptocurrencies (full disclosure: I am a Coin Metrics cofounder)
* [Bitcoin Visuals](https://bitcoinvisuals.com/): charts and visuals relating to bitcoin and the Lightning network
* Jameson Lopp's [list of Bitcoin resources](http://lopp.net/bitcoin.html)
* "[Bitcoin's Academic Pedigree](https://cacm.acm.org/magazines/2017/12/223058-bitcoins-academic-pedigree/fulltext)," Arvind Narayanan and Jeremy Clark
* [BitMEX research](https://blog.bitmex.com/category/research/?lang=en_us): long-form investigations into bitcoin economics, the Tether mystery, and market dynamics

_Thank you to_ [_hasufly_](https://medium.com/@hasufly) _and_ [_Larry Sukernik_](https://medium.com/@LarrySukernik) _for their feedback._
