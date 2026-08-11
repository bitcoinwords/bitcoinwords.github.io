---
title: "My Thoughts On Your Thoughts"
permalink: "/my-thoughts-on-your-thoughts"

author: thepiratewhocantbenamed

tags:
  - The Pirate Who Can't Be Named
  - 2017 Q2
  - Mining
  - Economics
  - Politics

excerpt: My Thoughts On Your Thoughts. Posted June 28, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [My Thoughts On Your Thoughts](https://medium.com/@thepiratewhocantbenamed/my-thoughts-on-your-thoughts-17474d800dda)
### By The Pirate Who Can't Be Named
### Posted June 28, 2017

![](/assets/images/2017/m6/my-thoughts-on-your-thoughts1.png)

*Disclaimer: I am writing this in form to Erik Voorhees, but this is for everyone to read.*

The fact that this sits at the top of the page above your written thoughts is the epitome of irony Erik. Hopefully you will see why as I break down what I see in your thoughts.

Firstly, you start off by quoting Sergio Lerner on his proposal. He himself explicitly acknowledges that the disagreements over current proposals are entirely political and not technical in nature. He also portrays the nature of a blocksize increase somewhat inaccurately. It is neither standard nor something done before. I’m assuming what he meant to do, and by extension what you did in quoting him, was to equivocate previous historical raises of a soft limit that is entirely separate from the hard limit enforced by consensus code to a complete change of the enforced hard limit that will for a fact partition the network in a way that is permanent. **That has never been done before, and comes with systemic risks that individuals such as yourself trivialize at every opportunity.** Continuing to frame things in such an intellectually dishonest way is what is inflaming the current stalemate. It is literally what started it in the first place.

##### Status Quo: The Threat of a Hostage

You go on to say that Bitcoin is important. Yes, I agree completely with this statement. It is **very** important. I don’t think you understand why it is important though. You go on to say in further irony, that Bitcoin must be extended as an offer of “*refuge from tyranny*” and not forced upon them. You go on to create a nostalgic image of the past, when everyone just got along, implying things should be like that. That things have to be like that for Bitcoin to work, to be valuable. Nothing could be further from the truth. If Bitcoin required everyone to just get along to work, it will never work globally unless spontaneous global utopia springs upon us from the ether(not that ether). Disagreement is almost universal, you will never get everyone to agree on everything.

You even attempt to paint the false image of two honest participants in a debate with two honest interpretations of the point of debate. This is false in the sense of oversimplifying things into a dichotomy, and false in the sense of painting all participants as equally honest when that is not the case at all.

> “Just that little innocuous thing that is the specific way a data structure is formatted
>
> has profound implications on the economics, incentives, and scalability of the system.”

The data that is put into the blockchain is an externalization of cost onto every validating user. Miners are paid for this, but not businesses validating, self-validating users, or anyone else running a node.*This is a tragedy of the commons.* So many people in this space, a large number of them advocating for very reckless blocksize increases(and do not try to continue this false dichotomy by responding that I am implying here all supporters of larger blocks fall into this category, I am not), completely refuse to acknowledge this dynamic. I am willing to bet even you refuse to really acknowledge the truly nuanced nature of this and the many intricate ways seemingly disconnected aspects of this system feed into the problem.

The block size is consistently paraded around as the central point of scaling, the scaling problem, the scaling bottleneck, etc. Anyone doing this is demonstrating a complete lack of understanding of the realities and nuances of Bitcoin scaling and what its problems are. The blocksize is only related to scaling issues in a tertiary way. It is what acts as a throttle to the growth of the Unspent Transaction Output(UTXO) set. The UTXO set is the central point of Bitcoin scaling, it is the real bottleneck. **It is completely impossible for any fully validating Bitcoin node, whether they are miners or not, to function without the entire UTXO set.** It is impossible to validate any transaction at all without checking that it is validly in the UTXO set. The only way to guarantee an output is validly in the UTXO set with 100% certainty, *trustlessly*, is to have derived the UTXO set yourself by processing the entire historical chain. I might also add, **there is no upper limit of any kind on the size of the UTXO set.** The only limitation exists indirectly through the blocksize, which places an upper bounds on how fast it can grow. It can shrink as well, but historically it has increased in size.

![](/assets/images/2017/m6/my-thoughts-on-your-thoughts2.png)

*Historical UTXO set growth from statoshi.info*

It seems common sense that this is a result of more people buying Bitcoin, and it being of a finite supply, they are broken up into more and more outputs of smaller denominations. This is entirely unavoidable. Taken to an extreme though, it easily gets into the Petabytes, or dozens of Petabytes. The worst case is that every Satoshi is its own output, which would be somewhere around 574 Petabytes(~350 bytes * 16.4 million[mined coins] * 100 million[satoshis in a bitcoin]. Why is this always ignored? Why are people given platitudes of “just this one bump in blocksize isn’t too much” while you wave away all the other implications of that? The blocksize isn’t what is going to impede people from validating, or raise the cost of operating a node to the breaking point at the end of the day. Its going to be the UTXO set. But ultimately most people in this space just sweep this under the rug, gripe about the blocksize, and ignore any longer term thinking on scalability.

As you yourself said, “There is clearly a problem and we need to fix it.” The problem is I think you fail to grasp the nature of the problem, let alone the nature of the solutions.

##### The Hollow Understanding

The entire parallel section to this in your piece is literally one giant straw man. Everyone involved, especially the developers, understands that Bitcoin is not merely a technical thing. We understand that very well. I think it is you who fails to grasp the nuanced and complicated way in which the social, economic, and technical aspects are intertwined.

Take the basic structure of a transaction for instance. Inputs and Outputs. Just the fact that the signature of an input is inherently a part of that Input structure has profound implications for the scaling of Bitcoin. Fees are a direct result of the datasize of a transaction, and because of the size of signatures relative to every other part of a transaction, that has a direct economic effect on the fee cost of certain transactions, and an effect on the incentives for users regarding the UTXO set. Fees are larger for transactions with more inputs, thereby both incentivizing users not to spend many small inputs while simultaneously creating more by breaking up few larger ones because that is cheaper in terms of fees. *Really think about that.*

That has a very serious systemic effect. Users over time cannot avoid winding up with multiple scattered unspent outputs as a consequence of transacting, which results in compounding fee costs. Businesses can’t avoid it period. This encourages users to bloat the UTXO set until they no longer can, because they are economically penalized for doing the opposite. This also imposes a cost of transacting heavily skewed in disfavor of businesses accepting payments at any scale from customers frequently.

***Just that little innocuous thing that is the specific way a data structure is formatted*** ***has profound implications on the economics, incentives, and scalability of the system.***But you throw the spotlight on the blocksize. You carve up the field of debate into a false dichotomy. You build up ridiculous straw men that wildly misrepresent what other people are saying and arguing. You then have an argument with this imaginary straw man, and then write pieces such as the one I am responding to reinforcing all of your ridiculously oversimplified arguments. All the while completely dismissing the nuances that render your simple arguments void. *All the while ignoring the realities of scaling this system.*

Then you run around advocating we loosen the limits on UTXO set growth while displaying a complete lack of appreciation on any level of that being a scaling concern, while completely dismissing and trivializing the upgrades both ready to go live right now and in the pipeline that work to address some of the most fundamental exacerbating factors to this scaling issue. You are so fixated on the blocksize you do not appreciate the gravity of how it affects the much more important scaling issue of the UTXO set. You dismiss all the compounding problems you worsen in attempts to put together a nice public perception for the Fiscal Quarter.

![](/assets/images/2017/m6/my-thoughts-on-your-thoughts3.png)

*Look at how BU bills itself as a “solution to scalability” while addressing none of what I just highlighted, on an ICO page none-the-less.*

##### The Cost of Bullshit

Let me break down the current roadmap that is being fought tooth and nail with nonsense:

* *Segregated Witness*: Begins a restructuring of transaction format to correct the imbalances mentioned above, solves the case of transaction malleability impeding functional payment channel systems, and introduces the witness discount to begin counteracting the skewed fees regarding UTXO condensing versus fragmenting and the resulting misalignment of incentives.
* *Schnorr Signatures*: Introduces a new signature scheme with the mathematical properties needed to implement things like *Aggregate Signatures*. This brings the the discount introduced with Segwit more into line with the actual data being externalized onto the network. It allows one signature regardless of number of inputs. This scales to help users, businesses, CoinJoins, or anything where the signers can interact or a single signer needs to make multiple signatures. Oh, it also comes with a huge privacy benefit because now multisig is indistinguishable from regular addresses, therefore making channel openings and closings and CoinJoins look just like regular transactions.
* *MAST(Merkelized Abstract Syntax Tree)*: A system to allow more complicated smart contracts to be packaged into merkle trees, allowing coins to be encumbered to much more complicated scripts that only require the parts being executed to be submitted to the Bitcoin network. This takes more complex contracts and drastically lessens the amount of data they externalize onto the network in order to be processed.
* *Lightning Network*: Creates a decentralized top-layer that allows users to transact without each individual transaction having an immediate effect on the state and size of the UTXO set. If implemented with an onion-routing protocol for payments as intended, it also maintains a high degree of privacy for payments while moving to a mode of transacting much more efficient with UTXO creation/destruction. It also helps the issue of validation by removing the need for other nodes to validate anything but the opening and closing of a channel, giving much more room for transaction throughput without externalizing everything onto the commons of validating nodes.

Look what all of that does in totality. It corrects the economic misalignment of user incentives relating to growth of the UTXO set while in the same swoop solving transaction malleability by restructuring transactions to provide better functionality to payment channel systems. It also makes upgrading Bitcoin’s script easier, and makes many other things such as chaining transactions safer. Schnorr Signatures then gives a more efficient signature algorithm, which in turn lays the foundations for Aggregate Signatures to close the gap in terms of data externalities versus its fee price that is introduced with Segwit. *As another benefit it comes with sorely need privacy improvements*. MAST then reintroduces more powerful scripting capability while also greatly reducing the data externalities of more complex scripts. To really drop the cherry on top, Lightning Network introduces a way for users to *transact with much more efficiency regarding UTXO creation while maintaining privacy*.

Is your trivialization of all of this just shellshock from too much winning? Is your desire to continually push courses of action that worsen the problems I’ve highlighted before correcting the agitating factors some attempt to counteract all the winning?

The entire position being argued by Sergio’s proposal and the New York Agreement is to the effect of “Let’s take one step forward, then two steps back.” And I’m willing to bet many people pushing in that direction don’t even realize that. People of this mindset are literally trying to present making one problem worse as a solution to another problem that is both not as important as it’s made to seem and is presented in a false light regarding its interplay with other problems. *This kind of intellectually dishonest interaction is the root of Bitcoin’s problems.*

##### Unity and Segwit2X

Segwit2x will never create Unity. I don’t say this to agitate, or divide, I say this as a conclusion reached through observation and assessment. It does not address real problems. What it does do is worsen critical ones while trying to hide it by treating the symptoms. It also injects the precedent of *admittedly* entirely political compromise into the process of upgrading and defining the protocol. That is not okay.

You erroneously made the assertion that developers and people such as myself do not appreciate the social or economic aspects of Bitcoin, I have demonstrated that to be false. I will remind you of the reason for the carefully designed synchronicity between the technical, the social, and the economic: **immutability**. Not just of the blockchain itself, *but of the rules that define its validity*. If you cannot verify the rules you agreed to are being followed, then you are forced to trust the people that do. You are also forced to just follow the rules those people enforce with no say or recourse.

![](/assets/images/2017/m6/my-thoughts-on-your-thoughts1.png)

*Remember this?*

Whether people like it or not, the cost of validating is intrinsically tied to whether or not users can utilize Bitcoin without trusting anyone else. Without relying on third parties that can choose to act as gatekeepers. When I am confronted with the types of ultimatums, arguments, emotionally manipulative pleas(such as the ones in your article trying to stoke fear of a contentious hardfork while at the same time advocating for one) from people who seemingly fail to grasp the true complexities and nature of Bitcoin’s scaling issues, **I see it as people attempting to take control of my money**.

I will never accept that. I will never compromise that. That’s not because of tribalism, or “blindness” to the non-technical aspects of Bitcoin. That is because I am here for a ***trustless immutable money***. If that is what you are here for, there is no need for compromises, just patience.

The higher the cost of running a validating node gets, the higher the total percentage of Bitcoin users forced to use Bitcoin as a trusted system gets. And the less people decide what the rules of that system are. The further we go in that direction, the more Bitcoin’s immutability in all senses gets weaker. You will never get unity until the people refusing to acknowledge the gravity of that reality, refusing to acknowledge the complexity of the issues that stand to accelerate that process, wake up and acknowledge it. *Unity comes from open collaboration, not dictating terms to win disproportionate favor in a compromise.*

***

{% include signup.md %}
