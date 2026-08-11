---
title: "A take on Bitcoin’s Gini coefficient"
permalink: "/a-take-on-bitcoins-gini-coefficient"

author: tamasblummer

tags:
  - Tamas Blummer
  - 2019 Q2
  - Privacy
  - Lightning

excerpt: A take on Bitcoin’s Gini coefficient. Posted June 5, 2019.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [A take on Bitcoin’s Gini coefficient](https://medium.com/@tamas.blummer/a-take-on-bitcoins-gini-coefficient-3a353e02075d)
### By Tamas Blummer
### Posted June 5, 2019

*Gini coefficient is the popular measure of inequality, that I attempt to estimate for Bitcoin, with a simple approach.*

Bitcoins exist technically as unspent transaction outputs (aka. UTXO) which may be spent by their pseudo anonymous owner. The value of UTXOs vary widely. They are the actual coins of the system. As of now, there are UTXOs of a few satoshis and some with many thousands of Bitcoins.

We could use the value distribution of the UTXO set to estimate Gini coefficient, but that would only be meaningful, if every Bitcoin holder would own exactly one of them. This is certainly not the case.

We could group UTXOs by addresses, but this approach is known to be futile since most wallets nowadays do not reuse addresses.

We could work out some elaborate heuristics to cluster Bitcoins, as do companies analyzing the Bitcoin blockchain. The more external data is joined with the blockchain data the more precise a clustering would be. The downside of this approach that it is proprietary and relies on data not widely available or even secret.

Even with near perfect clustering based on elaborate research and lots of exogenous information, the amounts grouped may not represent holdings of individuals. The biggest heaps of Bitcoins are likely in hot and cold wallets of exchanges that represent wealth of many users. *Although as you know: “Not your keys means not your Bitcoins”. But this is an other topic.*

The approach I took instead is based only on blockchain transactions, more precisely some special but very common forms:

* A transaction with a single output (aggregation) puts those coins very likely under the control of a single owner. This assumption will hold less often with growth of the Lightning Network.
* A transaction with two outputs is very likely a payment. Whoever did that was apparently in control of the total input value. Mixing transactions that obfuscate ownership have very likely more than two outputs.

Finally I make the assumption that one makes transactions of above types in proportion of one’s wealth. Wealthy people also do small payments out of small inputs, but poor can not command large inputs. The distribution of these transaction’s aggregate input values therefore leads to an underestimation of the Gini coefficient of Bitcoin wealth.

I used a moving window of 1 million transactions of above types to calculate below Gini coefficients:

![](/assets/images/2019/m6/a-take-on-bitcoins-gini-coefficient1.png)

*Gini coefficient of last 1 million Bitcoin payments and aggregations*

The calculated Gini coefficients show rather serious inequality, more than in any [real-world countr](https://en.wikipedia.org/wiki/List_of_countries_by_distribution_of_wealth)y, and it is an underestimation.

I am not interested in discussing implications or desired levels of inequality, just attempt to deliver measurements here.

***

{% include signup.md %}
