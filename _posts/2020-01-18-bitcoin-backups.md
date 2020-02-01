---
title: "Bitcoin Backups"
permalink: "/bitcoin-backups" 

author: _6102

tags:
  - _6102
  - 2020 Q1
  - Money Production
  - Money
  - Scarcity
  - Simple
  - Supply and Demand


excerpt: 6102 on money production. Posted January 1, 2020?

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin Backups](https://medium.com/@6102bitcoin/bitcoin-backups-e708028d8e4b)
### By [6102](https://twitter.com/6102bitcoin)
### Posted January 18, 2020

_A simple (worst case) evaluation of MultiSig wallet backups by_[_ 6102bitcoin_](https://twitter.com/6102bitcoin)

Consider a bitcoin wallet with a total of **n** keys, of which **m** are required to spend. **X** backups are made per key. When making bitcoin backups for this wallet there are three important things to consider;

## **1\. Number of backups**

We wish to minimize the number of backups required, predominantly because placing backups in a secure location can be time consuming, and checking backups are in place increases at least linearly with the number of backups required. The total number of backups required is equal to **nX**.

## **2\. Risk of Theft**

A thief can steal the bitcoin with access **m** backups (_in the worst case scenario_). Let this be the** ‘theft tolerance’ **of the setup**.**

With regard to the risk of theft, unless you are under targeted attack the **theft tolerance **of your backups is critical, rather than the % of keys the thief must access.

_Note: Users who may be under targeted attack may prefer to evaluate the percentage of keys which must be accessed by the thief rather than the number of keys._

## **3\. Risk of Inability to Recover**

Losing access to a minimum of **X(n-m+1)-1** backups does not impinge on the ability to recover the bitcoin. Let this be the **‘minimum backup redundancy’**. Losing more than this number of backups could potentially make recovering the bitcoin impossible.

With regard to **minimum backup redundancy** the % of keys that can be lost is considered more important than the actual number of keys.

## Tabulated Results

With this in mind we present an overview table of different m-of-n wallet configurations with different numbers of backups per key (**X**).

![](/assets/images/2020/m1/6102-6.png)

## Redundancy (%) vs Total Backups

![](/assets/images/2020/m1/6102-7.png)

When comparing the redundancy in terms of % backups you can afford to loose vs the total number of backups required to place it is striking how limited the redundancy of a 3of3 scheme is, even with 9 backups of each key.

If course, this is because we have assumed that that the ‘worst case scenario’ unfolds (e.g. for a 3of3 every one of the keys lost is the same key) which is very unlikely. This is done to be prudent, however future work could incorporate the statistical likelihood of these events, rather than assuming worst case scenarios.

**[Note: You MUST have access to all public keys with multisig.](https://twitter.com/kallerosenbaum/status/993193566343135234?s=19)**

***

{% include signup.md %}