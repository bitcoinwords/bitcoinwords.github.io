---
title: "Lightning at the End of the Tunnel"
permalink: "/lightning-at-the-end-of-the-tunnel" 

tags:
  - Roy Sheinfeld
  - CY19 Q2

excerpt: Roy Sheinfeld reviews the road ahead for Lightning adoption. Posted May 14, 2019.

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


# Lightning at the End of the Tunnel
## Overcoming Bitcoin's UX Challenges
### By [Roy Sheinfeld](https://medium.com/@kingonly)
### Posted May 14, 2019

![](/assets/images/cy19/cy19q2m5/rs-1.png){: .align-center}
(Sources: [pixabay](https://pixabay.com/photos/tunnel-light-hope-mystical-black-3915169/) & [publicdomainpictures.net](https://www.publicdomainpictures.net/en/view-image.php?image=171437&picture=lightning-display))

The Lightning Network is laying the ground for bitcoin to take the next giant leap in its evolution. Instead of just being an asset for HODLers', bitcoin now has the speed and economy to become a universal currency. We stand before the threshold of mass adoption.

The only thing holding bitcoin back is the UX. Raw technical possibility is not the same thing as an attractive, engaging, useful experience for all users.

But UX is a small term that hides great complexity. It implies many issues for which there are many solutions, each with advantages and disadvantages that different users will value in different ways.

For all their differences, we can assume that all users want at least one thing: simple functionality. Any viable solution must do its job simply and efficiently, so the complex technology has to operate seamlessly in the background. Perhaps the best measure of a UX is the gap between the utility it delivers and the complexity it manages to hide.

Here we take a look at the various challenges that remain in implementing the Lightning Network as a global payment solution for bitcoin and the different ways existing and impending technologies can overcome them.

### Challenge #1: Zero Configuration

If the primary UX goal is to spare users complexity, the right amount of effort they should have to devote to configuration is zero, none, nada.

#### Autopilot

Lightning Labs has developed the [autopilot](https://blog.lightning.engineering/announcement/2019/04/23/mainnet-app.html) feature to reduce the difficulty of configuring a Lightning Network wallet. Autopilot scans the network to determine which routing nodes are actively managing their channels' liquidity and recommends them to users.

The idea is to connect new users with the most active routing nodes on the assumption that they will provide the best service. Just like a 24-hour ATM usually provides a better UX than a 6-hour bank teller, active routing nodes should provide users more connectivity and payment flexibility — other things being equal.

That's a good start, but plenty of complexity remains. For one thing, users need to fund their own channels. Second, if a user funds a channel herself, she can send those funds down the channel, but she won't be able to receive funds until she has made some transfers. Third, users will have to fund a number of channels for adequate connectivity.

#### Lightning Service Providers (LSPs)

LSPs are basically network hubs. Just like ISPs, they make it easier for users to connect to the network.

In the language of autopilot, an LSP is just a routing node that recommends itself. As an active partner in its users' payment channels, the hub can spare users some further configuration hassles. For example, [Breez](https://breez.technology) funds users' channels with inbound liquidity, letting them receive bitcoin over the network immediately. Bitrefill's [Thor](https://www.bitrefill.com/thor-lightning-network-channels/?hl=en) service works similarly. LSPs are one big step closer to zero-configuration.

Centralization is not a concern with LSPs because a number of them exist already (with many more to come), so users can connect to several. In fact, Breez will soon allow users to select an LSP of their choice, minimizing configuration while preserving decentralization and user autonomy.

![](/assets/images/cy19/cy19q2m5/rs-2.png){: .align-center}
A good LSP is like a concierge service for your Lightning Network transactions. (Source: [Wikimedia](https://commons.wikimedia.org/wiki/File:Valet.jpg))

### Challenge #2: A Single Balance

The Lightning Network is a second layer on top of the bitcoin mainnet, and users have to dedicate bitcoin to their payment channels exclusively if they want to use the network. A satoshi cannot be on the mainnet and the Lightning Network simultaneously.

The separation of funds between on-chain and off-chain balances complicates the user experience in two ways:

1. Managing two balances for one currency is just unnecessary complexity.
2. The off-chain balance is typically spread across multiple payment channels, which limits how much users can spend in any single transaction (at least without AMP — see below).

Therefore, in terms of UX, the technical separation between users' on-chain coins and off-chain funds on the Lightning Network is part of the complexity that must disappear into the background. The technology to perform this illusion already exists, and improvements are on the way.

#### Submarine Swaps

[Submarine Swaps](https://blockonomi.com/submarine-swaps/) transfer funds between the base-layer chain and the second-layer Lightning Network through (paid) intermediaries — importantly — without trust. In effect, Submarine Swaps can bridge users' on-chain and off-chain balances.

Breez uses Submarine Swaps to move on-chain bitcoin directly to the user's Lightning node without the need to send the funds to a local bitcoin wallet first. As a result, users only see and manage their Lightning balance without a need to manage a separate on-chain balance.

#### Automatic Rebalancing

Another characteristic of the Lightning Network that could force users to deal with multiple balances is the dispersal of their funds across multiple channels. If a user's funds are split equally across five payment channels, making a payment above 20% of her total balance presents a challenge. She needs to find a way to reallocate those funds to the desired payment channel.

Currently, automatic rebalancing is probably the best way to work around this obstacle. In effect, a user reallocates her bitcoin by paying herself funds from the channels with excess capacity into the one that needs topping up. Ideally, rebalancing occurs in the background to hide the seams between the channels from the user. Automatic rebalancing can give users access to all their funds for any transaction.

#### Atomic Multipath Payments (AMPs)

As a means to achieve a single balance, AMPs will — once released — produce the same result as automatic rebalancing, but they do so more efficiently. AMPs split a payment into several smaller pieces that take different routes before being reconstituted in the recipient's wallet. The protocol ensures that the transfer can only be registered as successful if all the pieces do indeed arrive at their common destination, which prevents confusion and fraud.

AMPs overcome the dispersal of funds across channels by routing bitcoin from multiple channels to the single desired recipient, without prior local rebalancing. It's like having your friends meet at the restaurant instead of having all of them meet at your house before going to the restaurant. Again, this function can be automated, letting the user forget about how many coins are on which channel.

![](/assets/images/cy19/cy19q2m5/rs-3.png){: .align-center}
AMPs: Many paths from peer to peer. (Source: [Jurgen Appello](https://www.flickr.com/photos/jurgenappelo/5201869924))

### Challenge #3: Inbound Capacity

The funds in a payment channel are split between the two nodes at either end: some are local, and some are remote. If the remote balance depletes to zero, the local user will no longer be able to receive payments. If, say, a retailer receives far more payments than he makes, his customers will eventually lose the ability to pay because all the funds on the channel will _already_ be on the retailer's side. A few solutions exist to preserve the two-way functionality of payment channels.

#### Connecting to LSPs

Since "the inbound-capacity problem" depends on how funds are split between a user's local balance and the remote balance at the other end, LSPs can help by actively managing the balance at their own end. For example, [Breez](https://breez.technology/) funds users' channels as soon as they open, giving them the ability to receive funds immediately, and it manages their inbound capacity automatically. Other examples of LSPs that provide inbound liquidity include [LNBig.com](https://lnbig.com/#/) and Bitrefill's [Thor](https://www.bitrefill.com/thor-lightning-network-channels/?hl=en).

#### Dual-Funded Channels

As it stands, one party opens a channel, and the user on the other end cannot use the channel until the first initiates a transaction. However, there is a promising proposal to introduce [dual-funded channels](https://gist.github.com/bretton/53bc511b6fdafef31951199dd25bbf88). Two users would open a dual-funded channel together with starting balances at each end, giving both sides inbound and outbound capacity right away.

#### Loop Out

Using Lightning Labs' Loop feature, users can also remove funds from their local balance and move the coins to another wallet, onto the chain, or into cold storage. Removing these funds locally gives the user on the other end the chance to top up and transfer more.

Looping out solves the inbound-capacity problem, but it's far from a UX panacea. Before they can loop funds out, users need a functional bitcoin wallet (so long, single balance). Looping also requires channels to be pre-funded. The less experience a user has, the greater these obstacles will appear.

### Challenge #4: Effortless Payments

Transferring fiat can be so smooth that the sender doesn't even notice. That's the whole idea behind direct debit ... and pickpockets.

To send digital funds from one device to another, data needs to flow between them. Scanning QR codes is one way many wallets use to transfer data between devices. It works, and most people with a smartphone have had to do this at least a few times, so the inconvenience is perhaps bearable.

"Bearable inconvenience," though, is a hallmark of a UX in need of improvement. Even under optimal conditions, with good lighting and no jostling, QR codes are annoying. In low light or a rocking bus, though, trying to scan a QR code is as much fun as reading braille printed on sandpaper. There has to be a better way than QR. (And no, copy/paste is not a better way.)

![](/assets/images/cy19/cy19q2m5/rs-4.png){: .align-center}
"I know you're hungry, but there'll be no pizza until I can get the QR to work!" (Source: [wikimedia](https://commons.wikimedia.org/wiki/File:Dakar_car_2007.jpg))

#### Links

Links are nothing more than addresses for data. They are easy to use, and they can be transmitted in any text-based medium, like email or text message. As a means to transfer payment information between devices, links are the wheel that QR codes never needed to reinvent. With links, payment execution is a smooth, effortless process. [Breez's Connect-to-Pay](https://twitter.com/Breez_Tech/status/1090356173054926848) is a great way to see this solution at work.

Sending a Lightning payment can be as easy as sending a text message, and receiving a payment is as easy as reading one. It's like Venmo, but with bitcoin, and like DropBit, but off-chain.

#### Near-Field Communication (NFC)

NFC is very convenient for payments at short range. It also facilitates different hardware, giving users the option of using cards or their mobile devices. For face-to-face payments — and [>90% of retail purchases](https://retailnext.net/en/blog/brick-and-mortar-vs-online-retail/) are still in bricks-and-mortar stores — the UX of a well conceived NFC transfer is hard to beat.

### Challenge #5: Instantaneous Payments

A fiat wire transfer can take a couple of days, a domestic transfer or card payment takes seconds, and passing cash from one hand to another is instantaneous. Lightning has to beat fiat at its best, but two processes in the Lightning Network can present users with delays:

1. initially opening a user's channel, which has to be recorded on the chain;
2. keeping that channel's state current with the bitcoin chain and updating the Lightning Network graph.

The good news is that the first delay can be reduced to minutes and the second can be eliminated entirely.

#### LSPs

A new payment channel has to be posted to the chain. That means a delay of at least 10 minutes before a user can start sending and receiving payments over the Lightning Network. Compared to acquiring a new credit card — or even signing up for a fiat payment service like PayPal — 10 minutes is not bad at all.

Easing the on-boarding process and reducing the amount of time new users have to wait before being able to make their first payment is another area where LSPs shine. For example, by paying higher fees they can accelerate the process of posting users' payment channels to the bitcoin blockchain and minimize the initial on-boarding delay.

Bitrefill's [Thor Turbo](https://www.bitrefill.com/thor-turbo-channels/) channels even give users 500K-5,000K Satoshis of outbound liquidity immediately — for a price. But since Thor Turbo channels open even before on-chain confirmation, they can only _send_ payments initially, and they do so without bitcoin's underlying benefits.

#### Background Sync

Any bitcoin wallet worthy of the name needs to stay in sync with the mainnet. Otherwise, anything could happen with the users' funds. And syncing needs to happen in the background, or the lag when opening the app will be a frustrating experience.

Different syncing solutions demand [different amounts of trust](https://medium.com/breez-technology/the-only-thing-better-than-minimal-trust-is-none-at-all-34456f650332) from the users, depending on how much control over their money and their data they have to sacrifice. Low-trust solutions let users maintain control over their money and their data.

Neutrino (BIP 157) provides the raw, low-trust technology, but if Neutrino has to re-sync every time users open the app, they'll have to wait. So a UX-sensitive implementation has to hide [Neutrino's constant updates](https://bitcoinmagazine.com/articles/neutrino-privacy-preserving-light-wallet-protocol/) in the background. To give users even more control, Breez syncs Neutrino over a node of the users' own choosing. No other Lightning Network app gives users more privacy or control.

#### Trampoline Payments

At the moment, a user's light client has to download the network graph and calculate the best route from among all possible routes. As the network grows, we'll need a more efficient way to route payments than downloading the complete graph.

Trampoline payments would drastically reduce the amount of data and computation required by routing a payment first to a known [trampoline node](https://bitcointechweekly.com/front/outsourcing-route-computation-with-trampoline-payments/), which would then either pass it on to the recipient or to the next trampoline node, and so on until the payment reaches its recipient. Instead of having to survey the whole graph, a light client only needs to know a few trampoline nodes, and the rest takes care of itself.

### Challenge #6: Topping Up Naturally

Wallets empty. All wallets, whether physical or virtual, leather and digital alike. It's one of life's tragedies. To remain useful, they need occasional topping up. While there's no way around the need for topping up, there are different ways to realize it.

#### Fiat ↔︎ Lightning Interoperability

As long as fiat dominates the currency markets, everyone will need a way to convert the value of their fiat into bitcoin on the Lightning Network. For the time being, exchanges are the inevitable solution.

Exchanges, however, are not all equal. They can do users a great service by offering conversion directly from fiat into Lightning, bypassing the intervening step of a bitcoin wallet. Breez cooperates with [FastBitcoins](https://blog.fastbitcoins.com/new-fastbitcoins-com-partnerships-to-increase-bitcoin-access-for-all/) to give users a safe, easy, in-app means to acquire the bitcoin they need with the fiat they have.

#### Submarine Swaps

Since Submarine Swaps allow users to move funds back and forth between the bitcoin mainnet the Lightning Network, they're a convenient way to let users keep their wallets full of bitcoin. And with some canny design, the users won't even know they're doing it.

### Challenge #7: Enabling Large Transactions

In order to transfer over a payment channel, a user has to commit funds to it. Since there is no overdraft, no transfer can exceed the amount of funds on the respective payment channel — in theory. Practically speaking, transaction size and channel capacity are two different measures, but the general rule applies that a user cannot shift more beads on [a given abacus wire](https://medium.com/breez-technology/understanding-lightning-network-using-an-abacus-daad8dc4cf4b) than the wire holds.

In practice, users will likely have their funds distributed across a number of payment channels. But a user might want to combine those amounts to transfer a large sum over a single channel. Users need to be able to shift their beads from one wire to another at will. Ideally, they would be able to ignore the underlying channel architecture entirely and just pay — pay whomever, whenever, and as much as they like.

#### AMPs

A corollary of AMPs providing users with a single balance (see above) is that they could tap funds from all of a user's various channels to enable whatever transfer the user wants.

![](/assets/images/cy19/cy19q2m5/rs-5.png){: .align-center}
Wrong AMP, right idea. (Source: [maxpixel](https://www.maxpixel.net/Guitar-Amplifier-Amplifier-Marshall-Amp-Dsl40c-3577257))

#### Wumbo Channels

Appropriately enough for a new technology, payment channels are limited to a maximum of 0.167 BTC as a security feature. [Wumbo channels](https://www.coindesk.com/this-spongebob-themed-tech-proves-that-bitcoins-lightning-is-advancing) are one method proposed to relax that limit.

What's wumbo? [Patrick](https://youtu.be/--hsVknT1c0) explains it best. It's the opposite of "mini." If the two nodes at either end of the channel agree to remove the limit, they create a wumbo channel. And thus begins the science and art of wumbology.

#### Splicing

Splicing — especially combined with AMPs — could remove limits on channel capacity from users' consciousness entirely. With splicing, a channel can be closed and a new channel can be opened, with funds being added or removed in the process, and _all in a single transaction_.

Channel capacity would remain a feature of the network, but it could be tailored to fit the current transaction. This feature would also effectively obscure any difference between the Lightning Network and the bitcoin main chain from a non-expert user's perspective.

![](/assets/images/cy19/cy19q2m5/rs-6.png){: .align-center}
See where the one ends and the other begins? Exactly. That's splicing. (Source: [Wikimedia](https://commons.wikimedia.org/wiki/File:Splice_%28PSF%29.png))

### Mass Adoption Wasn't Built in a Day (but maybe in a couple of decades??)

While fiat sets the UX standard bitcoin has to beat, it also has the benefit of centuries of practice. Bitcoin has come a long way in a short decade, and its inherent benefits mean that fiat's days are numbered. Mass adoption has been three quarters away for years, but there is finally Lightning at the end of the tunnel.

The biggest and last remaining obstacle impeding bitcoin's mass adoption is the UX. The Lightning Network is the second layer bitcoin has long needed, and the technologies we've outlined here give it the speed, economy, and intuitiveness that users need now. If habit is the only thing left that speaks in fiat's favor, bitcoin wins by default.
