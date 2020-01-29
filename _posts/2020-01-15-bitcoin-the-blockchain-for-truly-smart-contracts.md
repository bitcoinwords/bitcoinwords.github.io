---
title: "Bitcoin: The Blockchain for Truly Smart Contracts"
permalink: "/bitcoin-the-blockchain-for-truly-smart-contracts" 

author: connerbrown

tags:
  - Conner Brown
  - 2020 Q1
  - Finance
  - Smart Contracts
  - Technology
  - Blockchain
  - Startup
  - Lightning Network
  - Lightning

excerpt: Conner Brown explains why Bitcoin is paving the way for smart contractswith lightning network. Posted January 15, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin: The Blockchain for Truly Smart Contracts](https://medium.com/@Conner_/bitcoin-the-blockchain-for-truly-smart-contracts-f7100b73da01)
### By [Conner Brown](https://twitter.com/_ConnerBrown_)
### Posted January 15, 2020

![](/assets/images/2020/m1/cb1.png)

Smart contracts sound enticing. The allure of cutting out attorneys, endless paperwork, and exorbitant legal fees is what drew me into learning about cryptocurrency in the first place. Unfortunately, my dreams were shortly crushed. It was clear that reality didn’t live up to the advertising hype and “smart contracting platforms” had fundamental problems with the nature of contracts.

Many have encountered these problems and decided smart contracts are something that can never work, I disagree. In fact, Bitcoin has made the proper design choices to make smart contracts possible where others have failed.

In this essay, I will cover the basics of contracts, explain the problems with naive “smart contracting platforms”, and finally show how Bitcoin is keeping the dream of smart contracts alive.

## Part One: Contract Basics

First, let’s cover the basics of a contract. A contract is _an enforceable agreement between consenting parties_. Here is an example:

**Alice agrees with Bob to purchase $1000 dollars of coffee beans from him per month for the next 3 years. Alice will pay Bob on the first of each month.**

The contract is the agreement between the two parties (Alice and Bob) for the transaction (coffee beans for dollars) and can be digital, written, or even verbal.

The key difference between a contract and a mere promise is that a contract can be enforced by a third party. This third party is often an agent of the law, such as a judge, but can also include private arbitrators, mutual friends, mob bosses, etc. In the event of a_ breach_ (i.e. Alice misses a payment), the injured party can take the contract and evidence to their enforcement authority who will use their abilities to make the injured party whole under the terms of the contract.

Contracts are a necessary part of a functioning economy as they allow individuals to rely on actions of others. Therefore, an entrepreneur can operate a business knowing that the components needed for their product will arrive on schedule. This forms the basis of predictable trading, planning, and specialization. In this sense, contracts are socially scalable as they “overcome shortcomings in human minds . . . that limit who or how many can successfully participate.” ¹ As more people can rely on the efforts of others without trusting them personally, the entire network of possible economic interaction grows exponentially.

The key feature that makes contracts socially scalable is that **a contract can be entered and executed without supervision.** A merchant may engage in thousands of trades and contracts with others and never need to see a judge to resolve the conflict.

On the contrary, imagine a world where every contract you entered into (i.e. every time you sat down at a restaurant or purchased something from amazon) there had to be a third party overseeing the entire transaction to ensure that everything went according to plan. That would be ridiculous. Transaction costs would be so high that no one would ever use contracts in the first place. The beauty of contracts is not that a third party is present at all times, but that **there can be a third party if needed. **That fallback option is sufficient to generate trust between strangers.

With contracts, we improve the division of labor and add reliability to our world, the cornerstones of economic progress, by replacing the element of trust with enforceable guarantees.

## Part Two: The Naive “Blockchain” Approach

Lately, there has been a lot of buzz around contracts. With the blockchain boom of the past decade, the meaning of the term “smart contract” has evolved in reference to the many distributed networks that have sprung up. For the purposes of this article, I will define a smart contract as the enforcement, verification, and performance of an agreement between two parties over a distributed protocol.

![](/assets/images/2020/m1/cb1.png)

If only it were this simple.

The stock image above represents the naive vision for smart contracts. The theory is that one can simply take real world contracts, “put them on the blockchain”, and somehow end up with an agreement that is more trustworthy. In this view, (1) there is a contract coded into the network, (2) data from the real world event is then processed by the network, and (3) lastly the network performs an action based on that information.

However, there are major problems with this approach.

### 1\. The Oracle Problem

If your smart contract system is based on information from the physical world, (i.e. title to land, the price of a good, or the delivery of an item) then it must rely on a service known as an oracle that can feed that information to the smart contract system. This is a problem because there is no objective way to know if the physical world corresponds to the internal databases. As a result, services require trusted third parties to supply the information for their contracts — defeating the purpose of using a decentralized network in the first place.

Additionally, problems arise when something happens with a piece of property, but the blockchain is not properly updated. For example, imagine you are storing land titles on a blockchain. What happens if the land is meant to be passed on to family members but the private keys to the land are lost or destroyed? In that scenario, there are two options. Either the ledger is immutable and title is permanently issued to the wrong person, or the ledger can be changed by a third party (i.e. government agent or customer support) to reflect what occurred.

The first scenario means over time the ledger will become increasingly incorrect, and the second demonstrates why a blockchain is unnecessary to begin with . Problems like these are fundamental to their respective networks and demonstrate why smart contracts are not suited for physical world property rights.

### 2\. The Inflexibility Problem

Contracts are never perfect manifestations of the drafters will. Often confusions and misunderstandings occur between parties when drafting. However, when drafting in a smart contract language, there is no room for error. Each word must be drafted from fully-defined computer terms which can be processed by the smart contract platform.

Jeremy Sklaroff explores this problem in a fantastic paper titled _Smart Contracts and the Cost of Inflexibility._² Smart contract platforms claim to reduce “inefficiency” by removing traditional language; however, Sklaroff demonstrates this removal unfavorably increases transaction costs. Hard coded contracts must be rigid and purely self-referential. This means that both parties must **fully and precisely define all expected and possible future states of the contract without traditional language. **The possibilities for even a simple contract of coffee bean delivery are dizzying.

It is also common when drafting contracts to reference conventions, customs, and terminology specific to a certain trade, significantly reducing the time required in drafting contract. These commonly understood substitutes would also not be recognized under a smart contract and would need to be entirely defined.

In sum, human activities require human constructs. Natural language has an interpretive richness and flexibility that cannot simply be replaced by computer logic.

### 3\. The Breach Problem

Contracts are often complex agreements with a variety of terms and requirements. Many times whether or not the terms of an agreement have been breached is up for debate. Bob may believe that he acted in accordance to the terms of the contract, however Alice may interpret things differently. For example, what happens if the coffee beans being delivered are the wrong size or type? Should this constitute a punishable breach or a negligible difference? Hopefully this would be negotiated ahead of time, but these problems are often difficult to anticipate.

To make matters worse, breaches are not always intentional or harmful. With standard contracts, a counterparty can give an explanation of their mistake and the injured party can choose take the case to the courthouse, or simply let it slide. This is because a technical violation is not always a detrimental violation.

To illustrate, let’s return to the contract between Alice and Bob. There may be a month where bob delivers the wrong type of coffee bean for Alice. He calls her ahead of time, informs of her of the mix-up, but tells her he’ll make up for it by giving her 25% off that order. Alice thinks this is a great idea. She will get a discount on this month’s delivery and can use these different coffee beans as a “limited time offer” in her store to boost sales.

Informal modifications like these are important and possible because they operate in the malleable world of human interaction. On the other hand, a trustless smart contract would simply see the wrong goods were delivered and penalize the offending party — a costly result that could have been avoided.

This lack of selective enforcement is another massive burden to smart contracts where the flexibility of standard contracts is a feature, not a bug.

### 4\. The Enforcement Problem

As mentioned above, the difference between a contract and a promise is that the third party to an agreement can enforce the terms of the contract. But what about a smart contract? If there is a smart contract for a delivery of coffee beans and Bob doesn’t deliver, who will enforce it? A blockchain is decentralized and has no jurisdiction or ability to affect physical objects, naturally this creates a problem with getting people to be good on their promises.

Defenders of blockchain enforcement generally take one of two positions. First, one might argue that the blockchain can’t enforce it, but it could be used as proof in a court of law. In that case however, you’re still falling back on the same state institutions to enforce the contract. A standard contract would have the same assurances and more privacy!

The alternative to this is a staking model. To use a smart contract, a user would need to post collateral that can be auctioned off in the event of the breach. This also brings its own problems — it’s expensive! Posting collateral for every contract brings its own opportunity costs, especially if dealing with multiple contracts on multiple services.

Neither of these solutions is appealing, and brings us back to the question of why use a blockchain for contracts in the first place?

### 5\. The Scalability Problem

As explained above, a key element of contracts is their ability to scale by providing third party monitoring on an _as needed basis_. However, smart contracting platforms such as Ethereum, Tron, and EOS, have decided to ignore this basic principle. By allowing users to upload contracts directly to the base layer, any contract that individuals create must be verified and constantly monitored by all other validators of the network.

Their results have been disappointing and predictable. Despite gaining little traction or active users, the major smart contracting platforms are already incredibly difficult to download, verify, and stay synced. [This timeless piece by StopAndDecrypt](https://hackernoon.com/the-ethereum-blockchain-size-has-exceeded-1tb-and-yes-its-an-issue-2b650b5f4f62) does a fantastic job exploring the implications of this design choice which applies to blockchains with expressive languages on the base layer such as Ethereum, Tron and EOS.⁴

Despite claiming to be innovative compared a simpler protocol like Bitcoin, complex base layer scripting is a step backwards. By requiring all validators to verify the entirety of every smart contract on these platforms, the inevitable result is centralization and falling right back into the realm of trusted third parties they claim to remove. Contracts simply don’t work that way.

## Part Four: A Judge Like No Other

![](/assets/images/2020/m1/cb2.png)

After seeing these problems, it is tempting to think they cannot be overcome. While most uses of the term “smart contracts” are merely fluff, we shouldn’t abandon the concept entirely. In fact, Bitcoin has already solved these problems with the Lightning Network.

The Lightning Network is a system of peer-to-peer payment channels that operate on top of the bitcoin protocol. A brief introduction to Lightning can be found [here](https://coincenter.org/entry/what-is-the-lightning-network).

In broad terms, a Lightning Network interaction works as follows. Two parties communicate with each other that they would like to enter into an agreement to open a payment channel. Both parties sign a commitment transaction which memorializes their mutual assent to the agreement and records it on the Bitcoin blockchain. Both parties abide by rules of the Lightning Network protocol, which form the boundaries of their cooperation. After transacting for a period of time, the parties can choose to terminate the contract by signing and publishing a final mutual transaction. In the event that one party tries to break the rules of the network and steal their counterpart’s funds, the injured party can publish proof to the bitcoin blockchain and prevent the theft.

These elements line up perfectly with traditional notions of contract, and overcome the problems listed above.

1.  **Terms:** The rules of the LN protocol itself are akin to the terms of a contract where both parties to the agreement must act accordingly.
2.  **Signing:** Publishing the commitment transaction is a way of signing and agreeing to the terms of the contract.
3.  **Breach:** The contract is breached if a party violates the terms of the lightning contract, and injured parties can essentially “have their day in court” by publishing cryptographic evidence to the base chain.
4.  **Enforcement: **Finally, the bitcoin protocol acts as a virtual judge, logically evaluating the evidence before it and transferring funds to the appropriate party.

The lightning network completely sidesteps the traditional pitfalls of smart contracts by isolating the contract system in a virtual closed loop. A smart contract on lightning lives and dies entirely in the digital realm. The oracle, enforcement, and breach problems only arise with dealing with the gray world of material objects and actions.

There is also a strong flexibility inherent in the network as the agreements are peer-to-peer like traditional contracts. Each set of partners chooses which terms they wish to be bound by. While there are generic lightning contracts, (i.e. the default build of Eclair or LND), these terms can be tweaked to fit the needs of the parties. For example, [Bitrefill recently opened](https://blog.bitrefill.com/the-first-1-btc-lightning-channel-is-live-on-mainnet-a7b30690d8a8) the first 1BTC channel by changing the default channel size limit. Contract flexibility will continue to improve as protocol upgrades such as Schnorr Signatures and SIGHASH_NOINPUT are implemented. [The eltoo proposal](https://blockstream.com/2018/04/30/en-eltoo-next-lightning/) is just one example.

With all this being said, perhaps the most important part of Lightning is its understanding of social scalability. As mentioned earlier, what makes contracts so powerful is that a judge _is not necessary for a transaction_, but only as a backup in the event of a breach. Other “smart contract platforms” such as Ethereum and Tron completely miss this fundamental insight of contracts. Instead, they opt for a model where the “judge” (i.e. the blockchain) sits over the shoulder and watches every single transaction as it occurs.

The design of the lightning network fully grasps this contracts concept. With lightning, millions of transactions can take place between two individuals without needing the judge at all. This provides two obvious benefits, reducing transaction costs with users of the network, and increasing the privacy of those entering into contracts. At this point, the size and growth of the network is somewhat unknown because many channels are private. However, in the event that something goes wrong, the benevolent bitcoin judge can step in, evaluate, and resolve the dispute.

Lastly, its important to note that the Lightning Network is only the first of many of such examples. [POWSWAP by Jeremy Rubin ](http://powswap.com/)offers a similar type of smart contract for hashrate derivatives, and[ Lot 49 by Richard Myers](https://globalmeshlabs.org/) for mesh network messaging. These innovative smart contracts are not being built on other chains because of their “expressiveness” or “turing-completeness”, quite the opposite. They chose bitcoin for its simplicity.

The blockchain space often touts complex base layer scripting as what is best for smart contracts — but they fail to recognize simplicity is crucial for smart contracts by forming the basis of predictable execution. In this light, bitcoin’s simplicity and security shines through.

Going forward, I expect the smart contracts with the most usage and value to be built in a similar way — leveraging bitcoin as their virtual judge of choice.

## Conclusion

Lightning is the first truly smart contract. By tackling the problems plaguing other networks, Lighting has prevailed as a shining example of what is possible on Bitcoin and paints a bright future for smart contract innovation on the network.

_I would like to thank _[_Bitcoin Lawyer_](https://twitter.com/Bitcoin_Lobby?lang=en)_, Jeremy Sklaroff, and Nick Szabo for their ideas, and the Cato Institute for hosting me to do this research._

References:

1.  Szabo, Nick. Money, Blockchains, and Social Scalability, 9 Feb. 2017, unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html.
2.  Sklaroff , Jeremy. “Smart Contracts and the Cost of Inflexibility .” _University of Pennsylvania Law Review _, vol. 166, 2018, pp. 263–303.
3.  Id. at 264.
4.  For more recent evidence of SAD’s concerns coming to fruition, I recommend[ this thread by Eric Wall](https://twitter.com/ercwl/status/1159940020331040770) documenting the herculean efforts to sync a full node on Ethereum.

***

{% include signup.md %}