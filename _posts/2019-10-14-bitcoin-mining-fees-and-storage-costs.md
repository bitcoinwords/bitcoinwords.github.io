---
title: "Bitcoin Mining Fees and Storage Costs"
permalink: "/bitcoin-mining-fees-and-storage-costs"

author: tamasblummer

tags:
  - Tamas Blummer
  - 2019 Q4
  - Mining
  - Fees
  - Security Budget

excerpt: Tamas makes the case for miners requiring certain fee threshold in order to include transactions in their blocks. Posted October 14, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [What fee would be fair?](https://medium.com/@tamas.blummer/what-fee-would-be-fair-953272c19935)
### By [Tamas Blummer](https://medium.com/@tamas.blummer)
### Posted October 14, 2019

**The driver of fees is scarcity of block space. There is an other scarce resource we should also price in, the use of UTXO.**

Bitcoin transaction fees rise if block space is scarce thereby take into account current use of a scarce resource, the block space. This is all fine but is not fully aligned with the costs implied by a transaction.

A transaction spends inputs and creates some new outputs. The new outputs become member of the UTXO set, the actual coins of bitcoin, and the spent inputs that were earlier outputs are deleted from the UTXO set.

The UTXO set is huge and ever increasing. It is not as big as the block chain but is still gigabytes with increasing trend. While the block chain can be pruned in a full node, the UTXO can not as it is the ultimate guard against double spending a coin.

Every transaction validation looks up the UTXO set and this operation is takes longer as the set grows. An output that is in the UTXO set increases processing time for all subsequent queries of the set until it is finally deleted because spent.

This means a transaction that spends an UTXO that was long standing is the final opportunity to charge for the term of its UTXO use and that is what we should do.

I suggest that miner impose a minimum fee to transactions that is not only taking into account the byte-size of the transaction but is also increasing with the age of the inputs. This does not have to be net increase of fees, but transactions that spend recently acquired coins might be even cheaper than now.

There is no fork needed for this as miner are free to implement any transaction filter, rejecting transactions that do not meet their particular taste.

I urge them to consider implementing a requirement that makes required fee increasing with the sum of spent coin’s age as this aligns fees with actual costs that the owner of those outputs imposed to the network.

Some miner might ignore this suggestion, actually I am sure most will for now, since they are focused on short term revenue that is highest if picking highest fee-per-byte transactions. Some might however recognize with time that alignment of costs with actual resource use will lead to higher revenues on the long run as it sets the right incentives on UTXO use.

# [Who pays the miner?](https://medium.com/@tamas.blummer/who-pays-the-miner-6d90431afc96)
### By [Tamas Blummer](https://medium.com/@tamas.blummer)
### Posted October 14, 2019

**No doubt that miner work for profit, but who pays for it?**

A bitcoin’s rules allow that a miner who creates a valid continuation of the block chain includes a transaction that benefits the miner with new bitcoins aka. subsidy and with fees offered by transactions within the block.

The source of fees is explicit and clear. Every transaction within the block pays the difference of the sum its outputs and inputs to the miner of the block.

The source of new bitcoins is however not visible, they are just granted to miner out of nothing. New coins have significant value, where does that value come from?

## Thermodynamics of wealth

A source of value is capital inflow into the bitcoin economy. Someone who already possessed wealth in an other currency buys the new coins. We see fluctuations of bitcoin’s price as a consequence of capital in- and out-flows. Those movements are rather severe and thereby hiding the answer to our question.

What if capital inflow into the bitcoin economy is zero, who pays for new coins then? This is not unlikely, we get close to it during dull days and there are many days where capital flows out of bitcoin. Mining would not stop as a consequence of no inflows, but the wealth that new bitcoins represent would have to come from within the bitcoin economy. Why? Because wealth, just like energy, can not arise from nothing. In absence of an external source someone within the bitcoin economy have to get poorer so the miner gets more wealthy.

Before we answer who pays, let’s quantify the wealth increase of the miner. Mining is a costly business to run. A miner will have to pay for electricity, amortization, labor, research, financing etc. The miner will only become wealthier if bitcoins mined worth more than the sum of these costs. Therefore we need a source of wealth that equals to miner’s profit and not revenue.

A miner who is not profitable does not get wealthier and there is no need for capital inflow or anyone to become poorer to offset it.

Above arguments are easier to follow if one considers that all costs of a miner have to be paid for with bitcoins the miner produces. This remains true even if bitcoins have to be traded for fiat currency first.

The miner trades some bitcoins with those who supply electricity, labor etc. Those resources are consumed (destroyed) in course of the production and their loss cancels out the wealth of the spent coins that are now owned by the resource supplier (or someone who gave fiat for them on the way to supplier).

In contrast wealth represented by coins that the miner kept after paying for production resources represent wealth that is not offset by resource consumption.

## Dilution

Observe that number of bitcoins in circulation also might have increased in the process. This is the case until subsidy runs out.

If the miner was profitable then loss of resources consumed in production is less than the value represented by the new coins. This means the purchasing power of a single bitcoin must fall.

_Thereby all bitcoin holder jointly pay for the profit of the miner._

For illustration, let us assume that it costs 3400 USD to produce a bitcoin and the current market price for it is 8400 USD. This means the miner spends only 0.40476 bitcoin to produce a bitcoin.

At current schedule, miners altogether will mine 12.5\*6\*24=1800 bitcoins a day. 1,800 * (1-0.40476) = 1,0714 bitcoins represent wealth in excess of burned resources.

The purchasing power of bitcoin is diluted proportional to current coins in circulation with 1,0714 / 17.89 million that is with ca. 5 USD

## On the long run

Miners profit is constantly under pressure through new entrants and technology improvements, therefore profitability is expected to be low on the long run. Profit rate should still remain positive as no one assumes the associated operational risk for no return. Those who are not profitable will leave.

Consequently dilution will stay with us to some extent until there are new bitcoins available to mine.

Fees do not dilute purchasing power of holders as profits in them are paid by those who transact.

## Conclusion

New coins dilute purchasing power of bitcoin holders to the extent that their production is profitable. Profitability of miner and hence dilution is expected to be low on the long run, but is rather significant nowadays.


# [Bitcoin’s storage cost](https://medium.com/@tamas.blummer/bitcoins-storage-cost-38f17f46e782)
### By [Tamas Blummer](https://medium.com/@tamas.blummer)
### Posted October 13, 2019

**Storing wealth in bitcoin is not for free. That cost is traditionally called carry for other assets and is easily quantifiable for bitcoin and is ca. 2.1% p.a. nowadays, read why.**

## Fees

The most obvious cost of storing wealth in bitcoin is that it requires some fee to move it in and out of a wallet. The aggregate amount of fees visible on the block chain as it is the excess income of miner above the subsidy.

![](/assets/images/cy19/cy19m10/tb1.png)
*Total bitcoins paid as transaction fees*

These fees were paid by those who moved their coins, and were proportional to the byte-size of the moving transaction, not to the moved amount. Nevertheless they were explicit costs of storage billed for use of the ledger.

## Dilution

Miners also receive new bitcoins for their work in a predefined schedule.

![](/assets/images/cy19/cy19m10/tb2.png) 
*Total coins produced in million bitcoins*

New coins increase the supply of coins to market and would drive their value lower if there were not other factors that dominate price movements, namely:

## Capital inflow

Those who buy bitcoin for an other currency contribute to capital inflow into the bitcoin economy and those who sell drain its capital stock. The net effect of these in- and out-flows dominate price movements and hide the deterministic value decline dilution would cause.

## Cost of mining

Bitcoin mining implies significant costs. Miner cover production costs by selling at least a fraction of their production. They contribute to capital inflow only to the magnitude of costs that they cover by selling bitcoins. (This thereby assumes constant bitcoin price.)

Consequently miner’s profit that was kept in bitcoin decreases wealth of holder through its dilution. This is also obvious since where else could the value come from if not covered by new inflow?

Note that if competition drives miners profit margin to zero and they cover their costs at selling bitcoin for a constant price or by paying costs entirely in bitcoins, then their activity no longer dilutes wealth of holder. This is true in the limit and temporarily at some points in bitcoin’s history but not in general.

We can observe changes to miners’ profit margin through changes of mining difficulty. If bitcoin current market price is not sufficient to sustain production then miner will turn off some devices to save electricity, which will be observable as drops in difficulty. This is certainly an imprecise measurement as it gives us a hint when miner with worst equipment and higher energy prices give up. Industry leader are likely still profitable and even cheer the shakeout of competition that will give them higher market share as price recovers.

## Mining cost estimate

The most recent example where mining difficulty recovered from a longer downturn was in January 2019 at a bitcoin price of 3400 USD. I suggest to assume this as the most recent estimate of bitcoin mining costs for a unit.

## Storage cost estimate

Using this mining cost estimate and current bitcoin price of 8400 USD we can assume a current mining profitability of at least 5000 USD / bitcoin produced.

This means that at current schedule of 12.5 bitcoins per block miners’ profit is ca. 9 million USD/day. This profit dilutes holders wealth at a daily rate of 9 million USD / 150.3 billion USD (market cap), that is ca. 2.1% pa.

Storage cost of wealth in bitcoin is therefore currently 2.1% annually plus transaction cost that is negligible for now. Storage cost will drop significantly with halving as that will cut into miners’ profitability.

This cost is hidden by more dominant price moves caused by short term capital in- and out-flows (speculation), but is nevertheless endured by investors, who should know about it.


***

{% include signup.md %}