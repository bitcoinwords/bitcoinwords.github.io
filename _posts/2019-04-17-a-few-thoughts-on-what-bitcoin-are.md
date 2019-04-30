---
title: "A few thoughts on what bitcoins are"
permalink: "/a-few-thoughts-on-what-bitcoin-are" 

tags:
  - Joe Kendzicky
  - CY19 Q2

excerpt: enter excerpt here

defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: false
      share: true
      related: false
---

# [A few thoughts on what bitcoins are](https://afterthoughts.substack.com/p/a-few-thoughts-on-what-bitcoins-are)
### By [Joe Kendzicky](https://twitter.com/jkendzicky)
### Posted April 17, 2019

There is no such thing as a bitcoin.

Even crazier, there is no "money" in the Bitcoin protocol; no BTC token, no virtual commodity, no accounts, no balances.  All that exists is an accounting ledger.

When someone says "I have 5 bitcoins", the classic image that comes to mind are shiny-looking digital tokens housed inside some digital wallet; like a dollar tucked away inside a leather purse. When sending bitcoin to a recipient, most believe that this virtual token departs from the program on their screen, traverses across the network at the speed of light, and lands in the possession of their recipient.

The truth is, bitcoins as a noun don't even exist.

The assets of value people lust after are actually called UTXOs (unspent transaction output). Bitcoin can essentially be boiled down to a game where people compete for the right to scratch their name inside some digital ledger. The unique feature about this ledger space is that it is scarce, so there exists a limited number of people who can write their name inside of it.

Entitlement to this space is represented by virtual contracts known as UTXOs. We can think of this concept like a land title- it grants the owner legal right to a fixed plot of earth. What's important to note about Bitcoin is that the total ledger space never changes; it sits there stagnant, like a parcel of land that never moves. So, when Bitcoin users broadcast transactions, they aren't actually changing the ledger space itself. Instead, they are changing the _claims_ to this space, by tearing up old UTXO contracts and drafting new ones that reassign it to a different owner.

![](/assets/images/cy19/cy19q2m4/kend-1.png){: .align-center}

So where do _bitcoins_ (lower case b) come into play? By providing us with a novel measuring unit to numerically "weigh" any UTXO in question. We can think of bitcoins like an acre, inch or pound.

![](/assets/images/cy19/cy19q2m4/kend-2.png){: .align-center}

_Bittrex [UTXO](https://blockchair.com/bitcoin/transaction/4be8c8135f5185b135f3c03131a2875a00a857a492e12eb4966e2873173f4ee4) transferred on March 31, 2019. The collective value of these bytes, specifically the ones outlined in blue, are worth ~$640M. Arguably, this string of characters is the single most valuable asset in the world._ 

We can say that a UTXO's value is a function of the ledger space it offers title to. But where does the ledger space derive _its_ value? Why would anyone want it? It provides no "utility" in the manner we traditionally think of productive assets. Its only functionality is an ability to claim portions of meaningless digital "real estate".

Turns out this digital real estate provides a tremendous amount of utility in the context of digital scarcity.
**Bitcoin's inherent value is the fact that it cannot be inflated.** Doesn't seem like much to the naked eye, but when we start experimenting, we quickly realize anything virtual is trivially replicated. 1's and 0's can be copied and pasted an infinite amount of times. If we can't introduce scarcity, a decentralized e-currency becomes an impossible feat.

Bitcoin's model is beautiful because proof-of-work, the mechanism by which all nodes update the ledger, bridges the virtual world and meatspace in sci-fi fashion. Validators using specialized computer hardware compete against one another in a game where they brute force cryptographic puzzles. These machines consume an enormous amount of capital (electricity and hardware) in the process. Some constitute this energy expenditure as wasteful; I would argue that it is transformative.

There is an unforgeable costliness associated with this structure as the destroyed resources embed themselves into the protocol, generating security and assurance. **This is what separates the authentic chain from an imposter.** I can trivially copy the bitcoin codebase, but I cannot copy the energy expended towards validating previous blocks.

In a way, we are "uploading" scarcity from the physical world to the digital realm. This allows us to numerically quantify the total Bitcoin network security in $ figures, and represents how much an attacker would need to spend to reorder the ledger. The larger this value is, the greater the assurances that the network provides, creating a reflexive feedback loop leading to more demand. Currently, we obsess over this security so greatly that we literally burn billions of dollars' worth of natural resources in order to protect it. Think about how wild this is for a moment- and we do all this for possession of some virtual real estate inside a meaningless ledger (that itself doesn't even really exist)!

So sure, you can try and secure money, produce, diplomas or Pokemon cards with your latest "efficient" or "eco-friendly" consensus algorithm. But these blockchains are only as strong as the opportunity cost of inputs forgone.

Like a cheap Chinese import, cost savings on the frontend reveal themselves on the backend; in our case, equally marginalized security. Owning bitcoins, in short, means possessing provably scarce lines of monetized code, tethered to billions of dollars in unrecoverable physical capital, all done as an effort to generate strong assurance.
_Joe researches cryptographic protocols and is on twitter at [@JKendzicky](https://twitter.com/jkendzicky?lang=en)_
