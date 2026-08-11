---
title: "Batching Mental Transaction Costs"
permalink: "/batching-mental-transaction-costs"

author: elaineou

tags:
  - Elaine Ou
  - 2018 Q1
  - Economics
  - Transaction Costs

excerpt: Batching Mental Transaction Costs. Posted March 2, 2018.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Batching Mental Transaction Costs](https://elaineou.com/2018/03/02/batching-mental-transaction-costs/)
### By [Elaine Ou](https://twitter.com/elaineou)
### Posted March 2, 2018

![](/assets/images/2018/m3/batching-mental-transaction-costs1.jpg)

There’s a popular American pastime that involves flinging dollar bills at scantily clad dancers. Canada, Europe, and the UK lack small-denomination banknotes, so strip club patrons have limited ability to express appreciation for their performers. Customers can either pelt the dancers with coins, which is rude; or shower them with large bills, which is extravagant. The transaction costs are unnecessarily high, and onstage tipping is rare.

In Australia, the smallest banknote is a five. While living in Sydney, I discovered (not from personal experience!) that gentlemen’s clubs sell fake banknotes for guests to use as tips. The dancers exchange the fake dollars for real money at the end of the night.

![](/assets/images/2018/m3/batching-mental-transaction-costs2.png)

*Fake dollars for sale at a gentlemen’s club in Sydney. Why did they model their money after USD instead of Aussie banknotes? Also, I bet the US $2 bill would have much wider adoption if the note featured a pole dancer instead of Thomas Jefferson. He already has the nickel! How bout some diversity, come on.*

How terribly exploitative! Instead of peer-to-peer payments, the house intermediates every transaction with self-issued fiat. It probably even takes a cut.

But… maybe it’s not so bad. I endured many a childhood birthday party at Chuck E. Cheese, where parents would hand each kid a stack of tokens and set them loose. Tokens could be used to pay for rides and games and candy, and were functionally equivalent to a quarter.

We already have quarters. Why did Chuck E. Cheese go through the hassle of minting its own coinage when it could have simply installed a laundromat change machine?

![](/assets/images/2018/m3/batching-mental-transaction-costs3.jpg)

*Chuck E. Cheese tokens come in a jumbo plastic cup, just like a real casino.*

Chuck E. Cheese and Aussie strip clubs employ the same brilliant strategy of **batching mental transactions**. Every monetary exchange incurs a cognitive cost, if from nothing more than the conscious decision to spend money. The overhead is nominal for most standard transactions, but relatively massive compared to a micropayment.

By forcing customers to make a large upfront commitment, these establishments avoid imposing a cognitive load on every subsequent exchange.

Casinos employ the same strategy with poker chips and slot tokens: Gamblers wager more freely with play money they’ve already bought. Sure they can cash out, but that’s an additional transaction cost.

People have been failing to effectuate micropayments since the [early days of the internet](https://www.w3.org/ECommerce/Micropayments/). A machine-payable web, where you pay for the content you consume, or pay-per-byte internet protocols – these sound like great ways to finely optimize the allocation of resources. But no matter what fancy new technology is employed – [Digicash](https://cyber.harvard.edu/fallsem98/final_papers/Worden.html)! [Millicent](https://www.w3.org/Conferences/WWW4/Papers/246/)! [FirstVirtual](https://www.wired.com/1998/04/the-bankrupt-promise-of-micropayments/)! [CyberCash](https://web.archive.org/web/19970611050302/http://www.netbill.com/netbill/press_release.html)! Blockchain! – [**micropayments never cease to be a bad idea**](http://nakamotoinstitute.org/static/docs/micropayments-and-mental-transaction-costs.pdf).

And now the Bitcoin Lightning Network. With instant transactions and exceptionally low fees, [This Time is Different](https://www.coindesk.com/blockstream-launches-micropayments-processing-system-for-bitcoin-apps/).

Maybe. A user funds a Lightning channel with the intention of fully spending its contents (it is a hot wallet after all, and costs money to cash out). In these early days, each channel has limited utility. If a channel commitment represents a one-way payment for a certain set of services, then it functions more like a subscription fee than a series of microtransactions. Like buying a stack of tokens at Chuck E. Cheese.

This model isnt great for Lightning-as-a-liquidity-provider, but it does bode well for Lightning-as-enabler-of-micropayments. Who knows.

![](/assets/images/2018/m3/batching-mental-transaction-costs4.png)

*Virtual tipping. A great application for Lightning.*

**See Also:**
 [The Transaction Costs of Tokenizing Everything](https://elaineou.com/2017/10/14/the-transaction-costs-of-tokenizing-everything/)

<strong>Note:</strong> A common defense of micropayments is the example of energy bills. Every time I flip a light switch, I’m technically agreeing to a microtransaction! The reason why my head hasn’t exploded from the cognitive load is because energy is fungible: A kilowatt-hour is a kilowatt-hour and PG&E is unlikely to rip me off with second-rate joules. On the other hand, if I agree to pay fifty cents to read an article on the internet, who knows what I’m gonna get. My local utilities company offers consumers the <a href="https://www.pge.com/en_US/residential/solar-and-vehicles/options/solar/solar-choice/rate-calculator.page" rel="noopener noreferrer" target="_blank">choice</a> of green energy (as opposed to dirty regular energy, blechh!) for an extra charge. Does green energy feel different when I open the fridge? I wonder how that’s working out for them.

***

{% include signup.md %}
