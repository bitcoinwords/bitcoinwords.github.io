---
title: "Over 75% of Bitcoin’s On–Chain Volume Doesn’t Change Hands"
permalink: "/over-75-percent-of-bitcoins-on-chain-volume-doesnt"

author: rafaelschultzekraft

tags:
  - Rafael Schultze-Kraft
  - CY20 Q1
  - Metrics
  - Economics
  - On-Chain Metrics
  - Volume


excerpt: Rafael Schultze-Kraft looks at volume on-chain and explains why he thinks Bitcoin is not changing hands. Posted February 13, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Over 75% of Bitcoin’s On–Chain Volume Doesn’t Change Hands](https://medium.com/@neocortex/over-75-of-bitcoins-on-chain-volume-doesn-t-change-hands-920b09cb7111)
### By [Rafael Schultze-Kraft](https://twitter.com/n3ocortex)
### Posted February 13, 2020


## Assessing Bitcoin’s True Transfer Volume

_This article was originally published on _[_Glassnode Insights_](https://insights.glassnode.com/true-bitcoin-volume/)_._

Even though blockchain data is publicly accessible, it is a non–trivial challenge to make sense of it in a meaningful way.

**On–chain data is without a doubt highly valuable — but in its raw form it’s just not good enough.**

It contains a substantial amount of noise, and careful preprocessing and contextualisation is required in order to distil useful information from it.

Consider **on–chain transaction volume**: _Figure 1_ shows Bitcoin’s raw daily on–chain transaction volume (USD value) for 2019.

![](/assets/images/2020/m2/rs1.png)
*Figure 1 — Raw Bitcoin daily on–chain transaction volume for 2019.*

On August 21st an enormous spike occurred, leading to a recorded on–chain volume of over $250 billion USD in a single day.

Without context, this might seem like a significant event.

However, this volume was simply caused by [Bitcoin “change”](https://en.bitcoin.it/wiki/Change), associated to a crypto exchange creating new cold wallets and reshuffling their funds internally — no actual Bitcoins were transferred between different participants in the network.

Therefore, if we are interested in assessing the **value of bitcoin that is actually being transferred across different holders**, proper processing and sophisticated methods need to be applied to the raw blockchain data.

### Change–Adjusted Volume

Adjusting for (obvious) change is a commonly applied heuristic to obtain a more accurate measure for on–chain volume.

This adjustment is applicable to transactions in which the sending address is present in both the inputs and the outputs of the transaction, i.e. a transaction output returns Satoshis back to an address of the sender (see _Figure 2 _for an example).

![](/assets/images/2020/m2/rs2.png)
*Figure 2 — Example of obvious change. An address with a balance of ~119,646 BTC sends 1,300 BTC to another address. The remaining amount is returned to the sending address. Source: [blockchain.com](https://www.blockchain.com/btc/tx/28b81d72d814e50ec989ab9caeed59778285f76ba835c0e7ba80a947888aa767)*

The change is considered “obvious” because the sender is re–using an existing sending address within the same transaction to receive the bitcoin change in return.

_Figure 3 _shows the daily change–adjusted on–chain volume for 2019.

![](/assets/images/2020/m2/rs3.png)
*Figure 3 — Raw and change–adjusted Bitcoin daily on–chain transaction volume for 2019.*

Note how the volume spike vanishes, and in addition change–adjusted volume is consistently lower compared to the raw volume.

In fact, within the denoted time period above, the daily **change–adjusted volume is, on average, 43% lower**.

> A live chart comparing raw and change–adjusted Bitcoin volume can be found on Glassnode Studio [**here**](https://studio.glassnode.com/compare?a=BTC&a=BTC&e=aggregated&m=transactions.TransfersVolumeAdjustedSum&m=transactions.TransfersVolumeSum&s=1485784856&sameAxis=true&scl=lin&scl=lin&u=1580392856&zoom=1095).

### Beyond Change: Adjusting by Entities

The problem with the above heuristic is that it doesn’t go far enough. There are other cases in which on–chain bitcoin volume does not represent actual transfer of Bitcoin between different holders.

For one, a single user can send bitcoin between different addresses that he/she controls. Furthermore, many wallets nowadays send change back to the spender using newly created addresses instead of re–using an existing one.

At Glassnode we use more advanced techniques and heuristics in order to estimate an upper bound for the “true” on–chain volume of Bitcoin — **volume that actually changes hands.**

To do so, we employ what we coin **entity–adjustment **and refine this methodology by accounting for so–called **relay addresses** as well.

### Entity–Adjustment

[In our previous article](https://medium.com/glassnode-insights/how-many-entities-hold-bitcoin-e945ecc5d0a1) we introduced the concept of “entities” in the Bitcoin network: Clusters of addresses that are controlled by the same entity.

Entity–adjustment therefore makes use of this knowledge and discards volume moved between addresses that belong to the same entity cluster (“in–house volume”). This is volume that does not represent value transferred between distinct users in the network. Because one address belongs to a single entity, this adjustment entails, by definition, the aforementioned change–adjustment as well. (_Note: We ignore multisig addresses in this analysis)._

![](/assets/images/2020/m2/rs4.png)
*Figure 4 — Schematic example of entity-adjusted on-chain volume: Only volume that is moved into or out of an entity is counted (green). Transaction volume within addresses of the same entity (“in-house” transactions) are discarded (red).*

Consider the example transaction in _Figure 2_ above: While it contains obvious change, our algorithms actually detect that all input and output addresses are controlled by the same entity — therefore the whole transaction does not contribute to the true BTC transfer volume _at all_.

Moreover, this implies that this transaction is discarded in the computation of entity–adjusted transaction **counts**, since it is a transaction that only transfers BTC internally.

### Relay–Adjustment

In addition to adjusting for entities, we take into account so–called “relay addresses” as well. Relay addresses are addresses whose sole purpose is to forward (relay) funds to a subsequent address. Hence, the volume of relay addresses is usually double–counted: once moving into and once moving out of the relay address.

Through the identification of addresses with this behaviour, we are able to remove this added of noise in volume aggregates. To do so, we discard all outputs that are spent by relay addresses.

![](/assets/images/2020/m2/rs5.png)
*Figure 5 — Schematic example of relay addresses: In order to prevent double-counting on-chain volume, only transactions going into the relay addresses are considered. Outputs spent by relay addresses are discarded.*

Technically, we define relay addresses as addresses whose _mean spent output lifespan is less than 1 hour_, and whose current _balance is zero (excluding UTXOs which were created within the last hour)._

_Figures 6–8_ show the difference between between our entity–adjusted volume (incl. relay–adjustment), change–adjusted volume, and raw volume for the the years 2016, 2017–2018, and 2019, respectively.

![](/assets/images/2020/m2/rs6.png)
*Figure 6 — Daily Bitcoin on–chain transaction volume for 2016.*

![](/assets/images/2020/m2/rs7.png)
*Figure 7— Daily Bitcoin on–chain transaction volume for 2017–2018.*

![](/assets/images/2020/m2/rs8.png)
*Figure 8— Daily Bitcoin on–chain transaction volume for 2019.*

The results speak for themselves, and the differences are compelling.

The 2016 data illustrates the removal of significant volume spikes that are not accounted for by change–adjusted volume only. Similarly, volume during the bull market in 2017 shows substantial discrepancies (5x) between entity–adjusted and raw/change–adjusted Bitcoin volume.

Over the period from 2016–2019 the daily on–chain transaction volume using our entity–adjusted methodology has been

*   **75.5% **lower than the raw volume and
*   **63%** lower than change–adjusted volume.

**This means that less than 25% of Bitcoin volume that is recorded on–chain represents actual value transfers between network participants.**

> **Our entity–adjusted metrics show that the true Bitcoin on–chain volume is on average only 25% of the raw volume recorded on the blockchain.**

For a complete picture,_ Figure 9_ shows the ratio between raw volume and entity–adjusted (as well as change–adjusted) over time. The entity–adjusted ratio has been relatively stable fluctuating around 0.25 since 2016.

![](/assets/images/2020/m2/rs9.png)
*Figure 9 — Ratio of entity-adjusted/change-adjusted and raw Bitcoin on-chain volume.*

_Figure 10_ depicts the monthly difference between raw and entity–adjusted (as well as change–adjusted) volume in USD. It shows that on a monthly basis our entity–adjusted volume is up to a compelling **$875 billion** and **$629 billion** lower compared to the raw volume and the change–adjusted volume, respectively.

![](/assets/images/2020/m2/rs10.png)
*Figure 10 — Monthly difference between raw and entity-adjusted/change-adjusted volume in USD.*

### Conclusion

The data and analyses presented here are in no way intended to lessen Bitcoin’s value proposition and should not be interpreted as such.

The purpose of this work is merely to signify that advanced methods are required to meaningfully make sense of on–chain data. In order to accurately understand the underlying state of the Bitcoin network and its events it is essential to contextualise and scrutinize this data properly.

Note the in the present work we exclusively refer to bitcoin moved on the blockchain. We don’t account for BTC that is bought or sold on exchanges. Technically, on a network level, those bitcoin are still controlled by the same entity — the exchange itself.

In Bitcoin’s economy the implications of moving funds within the same entity, and actually transferring ownership of bitcoin (and therefore value) across network participants, are very different — they represent very different things in terms of economic activity.

Any investor, trader, and researcher aiming to properly understand value and wealth transfers in Bitcoin’s economy should be undoubtedly making use of these fundamental differences drawn from on–chain volume.

***

All metrics presented in this work are live on [Glassnode Studio](http://studio.glassnode.com/) as of today:

*   [**Entity–adjusted Volume (Total)**](https://studio.glassnode.com/metrics?a=BTC&m=transactions.TransfersVolumeEntityAdjustedSum)
*   [**Entity–adjusted Volume (Mean)**](https://studio.glassnode.com/metrics?a=BTC&m=transactions.TransfersVolumeEntityAdjustedMean)
*   [**Entity–adjusted Volume (Median)**](https://studio.glassnode.com/metrics?a=BTC&m=transactions.TransfersVolumeEntityAdjustedMedian)
*   [**Entity–adjusted Transaction Count**](https://studio.glassnode.com/metrics?a=BTC&m=transactions.EntityAdjustedCount)

For change–adjusted volume visit:

*   [**Change–adjusted Volume (Total)**](https://studio.glassnode.com/metrics?a=BTC&m=transactions.TransfersVolumeAdjustedSum)
*   [**Change–adjusted Volume (Mean)**](https://studio.glassnode.com/metrics?a=BTC&m=transactions.TransfersVolumeAdjustedMean)
*   [**Change–adjusted Volume (Median)**](https://studio.glassnode.com/metrics?a=BTC&m=transactions.TransfersVolumeAdjustedMedian)

![](https://miro.medium.com/max/60/0*GZviMKo-c7O2v4sS.png?q=20)

![](https://miro.medium.com/max/450/0*GZviMKo-c7O2v4sS.png)

*   Follow us and reach out on [Twitter](https://twitter.com/glassnode)
*   For on–chain metrics and activity graphs, visit [Glassnode Studio](https://studio.glassnode.com/)
*   For automated alerts on core on–chain metrics and activity on exchanges, visit our [Glassnode Alerts Twitter](https://twitter.com/glassnodealerts)

_Disclaimer: This report does not provide any investment advice. All data is provided for information purposes only. No investment decision shall be based on the information provided here and you are solely responsible for your own investment decisions._

***

{% include signup.md %}
