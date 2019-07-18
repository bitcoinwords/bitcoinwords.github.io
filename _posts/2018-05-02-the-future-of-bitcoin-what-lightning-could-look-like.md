---
title: "The Future of Bitcoin: What Lightning Could Look Like"
permalink: "/the-future-of-bitcoin-what-lightning-could-look-like" 

author: aaronvanwirdum

tags:
  - Aaron van Wirdum
  - CY18 Q2

excerpt: enter excerpt here

defaults:
  - scope:
      type: posts
---

# The Future of Bitcoin: What Lightning Could Look Like
### By [Aaron van Wirdum](https://twitter.com/aaronvanw)
### Posted May 2, 2018

After [years of conceptualization and development](https://bitcoinmagazine.com/articles/history-lightning-brainstorm-beta/), the first Lightning implementations [are now in beta](https://bitcoinmagazine.com/articles/lightnings-first-implementation-now-beta-developers-raise-25m/). As a result, more nodes are appearing online every day, a growing number of users are opening channels with one another, and some merchants even started to accept Lightning payments.

But of course, these are still the very early days of [the](https://bitcoinmagazine.com/articles/understanding-the-lightning-network-part-building-a-bidirectional-payment-channel-1464710791/) [Lightning](https://bitcoinmagazine.com/articles/understanding-the-lightning-network-part-creating-the-network-1465326903/) [Network](https://bitcoinmagazine.com/articles/understanding-the-lightning-network-part-completing-the-puzzle-and-closing-the-channel-1466178980/). While the main implementations are usable and some wallets and other applications are available, Bitcoin's overlay payment network is projected to improve over the next few years in areas ranging from network architecture to security and usability, and more.

These are some of the more important Lightning projects currently in development.

## Dual-Funded Channels

The Lightning Network consists of a series of payment channels. Each payment channel exists between two users, allowing funds to be sent back and forth between them.

However, in this early stage of development, payment channels can only be funded by one of the two parties. The funding party must first make a transaction to his counterparty; only then can that counterparty return a payment within the same payment channel.

The [Lightning Network white paper](https://lightning.network/lightning-network-paper.pdf), however, proposed dual-funded channels, for which a [specification proposal](https://github.com/lightningnetwork/lightning-rfc/pull/184) has now also been made by [ACINQ](https://acinq.co/), the company behind [eclair](https://github.com/ACINQ/eclair). As the name suggests, dual-funded channels will let both users partly fund a payment channel by each depositing some bitcoin. This should bring more flexibility to the Lightning user experience, as users can immediately send as well as receive payment after having opened a channel.

## Submarine Swaps

In order to make a Lightning payment, users must deposit funds in a Lightning channel. Once in a channel, these funds cannot be sent to regular (on-chain) Bitcoin addresses (unless the channel is first closed). This means that bitcoin in a Lightning channel is somewhat separated from bitcoin in a regular wallet, not unlike how money in a checking account is somewhat separated from money in a savings account.

But there are solutions to make switching between Lightning and on-chain payments more seamless.

One solution is [Submarine Swaps](https://submarineswaps.org/). Developed by Alex Bosworth (but conceptualized by [Lightning Labs](https://lightning.engineering/) CTO Olaoluwa Osuntokun even [before that](https://twitter.com/roasbeef/status/964608261830750208)), Submarine Swaps essentially let users send Lightning payments to a middleman on the Lightning Network; that middleman will send a corresponding amount of bitcoin to a regular (on-chain) Bitcoin address. It also works the other way around: users can send regular on-chain payments to the middleman; that middleman will then send a corresponding amount of bitcoin to a receiving Lightning node on the Lightning Network.

Importantly, with Submarine Swaps, this conversion is done "atomically." Using a trick that is already embedded in the Lightning Network, the Lightning payment and the on-chain payment can effectively be linked to each other. This makes it impossible for the middleman to steal funds by not forwarding the payment. (In agreement with the users, he could charge a small fee for his service.)

## Splicing

Another solution to make the Lightning user experience more seamless is called "splicing." In essence, splicing would let a user "top up" funds in an existing Lightning channel, or "drain" funds from it, potentially while keeping the channel open.

The idea is simple. Any Lightning channel starts with an opening transaction, which ensures that both users consent to moving the funds in the channel. The rest of the Lightning channel consists of a series of subsequent transactions exchanged between the users, which aren't usually broadcast to the Bitcoin network. The funds in the opening transaction don't move until the channel is closed.

When "splicing in," users take the opening transaction to instead send funds to a replacement opening transaction, which includes more bitcoin, from one or both users. Once this new opening transaction confirms on the blockchain, the channel is topped up. Until the new opening transaction is confirmed, the two users can simply update both the old and the new channel at the same time to avoid any "channel downtime."

Conversely, when they "splice out," users take the opening transaction to send funds to a regular (on-chain) address, and potentially keep some of it in the channel using the same trick. This way, users can make on-chain transactions straight out of a Lightning channel.

## Eltoo

Each time a new payment is made, Lightning channels between users are updated to reflect their mutual balances. The trick used to accomplish this currently includes a penalty for users who try to cheat by broadcasting an older balance (presumably because that older balance would pay them more). Cheating users can lose all the funds they have in a channel.

The problem is that the broadcasting of old balances is not always a cheating attempt. There are a number of scenarios in which users can accidentally broadcast an older balance; for example, because of a software bug or a backup gone wrong. In such scenarios, a complete loss of channel funds is quite a heavy punishment.

First published on April 30, 2018, [eltoo](https://blockstream.com/eltoo.pdf) is the newest proposal featured in this article. Developed by Blockstream's [c-lightning](https://github.com/ElementsProject/lightning) development team — Dr. Christian Decker and Rusty Russell — and Lightning Labs' Osuntokun, eltoo updates a channel by building a chain of time-locked transactions, where each transaction spends funds from the previous one to reflect the latest channel balance.

If one user broadcasts an older transaction (representing an older channel balance), her counterparty has some time to broadcast the latest transaction (representing the latest channel balance).

A solution like this could work today, but it isn't practical in cases of failure. It would require that the entire chain of transactions be broadcast and recorded on the Bitcoin blockchain, more or less defeating the purpose of the Lightning Network. Decker therefore [proposed](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2018-April/015908.html) a soft-fork change to the Bitcoin protocol to introduce a type of hierarchy in these types of transactions: any newer transaction can override any older transaction without requiring that all transactions in the entire chain be broadcast.

If this soft fork is adopted and activated on the Bitcoin network, Lightning users could create channels in both the current style and by using eltoo, depending on what they prefer.

## Compact Client-Side Block Filtering

While the Lightning Network is a second-layer protocol, the Bitcoin blockchain itself is still relevant for Lightning users for security purposes. Specifically, Lightning users must keep an eye on the blockchain to see if specific transactions are included. This can be resource intensive, in particular for mobile users.

A solution for this is called Simplified Payment Verification (SPV) and was described in the Bitcoin white paper. Current SPV wallets use a trick called "[Bloom filters](https://en.wikipedia.org/wiki/Bloom_filter) " to find out whether any relevant transactions happened.

Unfortunately, Bloom filters are rather privacy-unfriendly, as wallets essentially reveal all of their addresses to nodes on the Bitcoin network. They also have some scaling and usability issues, as each individual SPV wallet takes up resources from at least one full Bitcoin node.

To tackle these issues, Lightning Labs' Osuntokun and Alex Akselrod, along with [Coinbase](https://www.coinbase.com/) developer Jim Posen, [designed](https://github.com/bitcoin/bips/blob/master/bip-0157.mediawiki) a new solution called "compact client-side block filtering," which they are implementing in the [Neutrino](https://github.com/lightninglabs/neutrino) wallet.

Compact client-side block filtering essentially inverts the trick that current SPV wallets use. Instead of wallets requesting transactions relevant to them by creating and sending out a Bloom filter to full nodes, full nodes create a filter for all Neutrino wallets. The Neutrino wallet then uses this filter to establish that the relevant transaction did not happen — which is really all that users need to know to be sure they are not being cheated. (If the filter produces a match, Neutrino fetches the relevant block to see if the match really concerns the exact transaction instead of a false positive.)

Interestingly, while this trick was designed with the Lightning experience in mind, it could be utilized to benefit regular light wallets as well.

## Watchtowers

To avoid being cheated, Lightning users must keep track of potential on-chain transactions that could be relevant to them.

While compact client-side block filtering should make things much easier, users do need to "check in" once in a while to make sure they're not being cheated. If they forget to check, it creates a security risk.

"Watchtowers" are a potential solution that can be traced back to the Lightning Network white paper and has since been [improved](https://diyhpl.us/wiki/transcripts/scalingbitcoin/milan/unlinkable-outsourced-channel-monitoring/) by Lightning Network white paper co-author and [lit](https://www.media.mit.edu/projects/lit/overview/) developer Tadge Dryja and others. As the name suggests, Watchtowers could let users outsource blockchain monitoring to third parties.

Current Watchtower designs are not set in stone but would roughly work like this. Whenever users update a channel, they send a small data package to a Watchtower. The first part of this package is a "hint" of a transaction they should look out for, as if it were a piece of a puzzle. This hint alone doesn't reveal anything about the content of the transaction that the Watchtower must look out for; users don't give up any privacy in this sense.

However, if the relevant transaction shows up in the Bitcoin blockchain, the Watchtower can use the hint to recognize it. Then, with the transaction data on the blockchain itself, the Watchtower can use the second part of the package they've received to reconstruct the penalty transaction. This penalty transaction sends all funds in the channel to the user that is being cheated. (Or in the case of eltoo, it just broadcasts the correct channel balance.) The penalty transaction can also be designed to let the Watchtower claim part of the funds as a reward, as an incentive to do its job.

Users can outsource channel monitoring to multiple Watchtowers. Even if one fails, another might not, limiting the risk for Lightning users to the point where it's arguably negligible.

## Atomic Multi-Path Payments

What makes the Lightning Network a <i>network</i> is that the payment channels between users are interconnected. Users can pay across payment channels, through peers on the network that act as "middlemen," to users they don't have a direct channel open with.

However, right now a single payment must be routed over a single route. If one user wants to pay 5 mBTC to another, not only must he have 5 mBTC in a single channel, all the middlemen on the route must also have 5 mBTC ready in a channel to forward. The bigger a payment is, the smaller the odds of this being the case.

Atomic Multi-Path Payments (AMPs) could go a long way of solving this limitation. First proposed by Lightning Labs' Osuntokun and Conner Fromknecht, the idea is simple: Larger payments can be "cut up" into smaller pieces, all of which have their own route from the payer to the payee, through different middlemen.

A challenge to realize this solution is that Lightning payments can fail, which would in this case mean that a payment is made partially. Partial payments can easily be a bigger problem than no payment at all, however: a merchant won't be satisfied with a partial payment, while a customer won't be happy spending any money for nothing.

The solution to this problem is that AMPs use an extension to the [hash time-locked contracts](https://bitcoinmagazine.com/articles/understanding-the-lightning-network-part-creating-the-network-1465326903/), which are already used along Lightning routes and involve passing secret data along a network. Using a trick similar to the one used by deterministic wallets (which generate multiple Bitcoin addresses from a single seed), the smaller pieces of a larger payment can only be redeemed by the payee if all of them are: if some secret data doesn't make it through the route whole, the entire payment fails.

## Atomic Swaps

The Lightning Network is designed as a scaling layer for Bitcoin. But since many altcoins are software forks of Bitcoin's codebase(s), it's often not difficult to create similar scaling layers for these altcoins. Already, a small Litecoin Lightning Network exists, and more Lightning Networks are likely to follow.

Interestingly, these networks don't need to remain separated in the future.

Using a fundamental building block of the Lightning Network called "atomic swaps" (first [proposed](https://bitcointalk.org/index.php?topic=193281.msg2224949#msg2224949) by Tier Nolan and [realized](https://bitcoinmagazine.com/articles/lightning-network-now-supports-transactions-across-blockchains/) on Lightning by Lightning Labs' Fromknecht), payment channels can be linked across different blockchains. In other words, a user can send bitcoin, and as long as a node on the network is willing to make the exchange, another user can receive the payment as litecoin.

Of course, this also means that users can send such payments to themselves: they can send bitcoin and receive litecoin. In effect, the Lightning Network could establish a network of trustless cryptocurrency exchanges.
<i>For more information on this topic, see: "[Atomic Swaps: How the Lightning Network Extends to Altcoins](https://bitcoinmagazine.com/articles/atomic-swaps-how-the-lightning-network-extends-to-altcoins-1484157052/)."</i>

## Channel Factories

The main benefit of the Lightning Network is arguably its potential to vastly increase the upper limit of bitcoin transactions without burdening the Bitcoin network. As long as two users both have funds in their channel, they can pay each other a virtually unlimited number of times, while only requiring two on-chain transactions: one to open a payment channel and one to close it.

Still, two transactions per payment channel could add up if Bitcoin and the Lightning Network gain more adoption over time.

A proposal by [ETH Zurich](https://www.ethz.ch/en.html) researchers Christian Decker (also of Blockstream), Roger Wattenhofer and Conrad Burchert called "Channel Factories" could further decrease the average number of on-chain transactions required per payment channel, perhaps significantly.

Loosely based on an earlier Lightning-like proposal by Decker and Wattenhofer from 2015, Channel Factories are a type of payment channel that can exist among many users. Meanwhile, like any payment channel, a Channel Factory only ever requires two on-chain transactions. (If [Schnorr signatures](https://bitcoinmagazine.com/articles/the-power-of-schnorr-the-signature-algorithm-to-increase-bitcoin-s-scale-and-privacy-1460642496/) are implemented on Bitcoin, these transactions could be quite compact, even if it involves many users.)

The Channel Factories can, in turn, act sort of like "sub-channels" for the Lightning Network. Participants within a Channel Factory can open and close a virtually unlimited number of Lightning channels with each other, without requiring any additional on-chain transactions. By doing so, they could, in theory, bring the number of required on-chain transactions for the Lightning Network down by a magnitude.
<i>For more information on this topic, see: "[This New Scaling Layer Could Make Payment Channels Ten Times More Effective](https://bitcoinmagazine.com/articles/new-scaling-layer-could-make-payment-channels-ten-times-more-effective/)".</i><i>Thanks to Blockstream developer Christian Decker, Lightning Labs developer Conner Fromknecht, ACINQ CEO Pierre-Marie Padiou and others for information and feedback.</i>
