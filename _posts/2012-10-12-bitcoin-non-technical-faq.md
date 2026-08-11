---
title: "Bitcoin Non-Technical FAQ"
permalink: "/bitcoin-non-technical-faq"

author: olegandreev

tags:
  - Oleg Andreev
  - 2012 Q4
  - Education
  - Technology

excerpt: Bitcoin Non-Technical FAQ. Posted October 12, 2012.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin Non-Technical FAQ](https://blog.oleganza.com/post/32725987418/bitcoin-non-technical-faq)
### By [Oleg Andreev](https://twitter.com/oleganza)
### Posted October 12, 2012

### [Bitcoin Non-Technical FAQ](https://blog.oleganza.com/post/32725987418/bitcoin-non-technical-faq)

Bitcoin is a peer-to-peer digital currency. It does not depend on any particular organization or person and it is not backed by any commodity like gold or silver. Bitcoin is a name for both: the currency and the protocol of storage and exchange. Just like dollars or gold, Bitcoin does not have much direct use value. It is valued subjectively according to one’s ability to exchange it for goods.

This FAQ complements the bigger Bitcoin FAQ: [https://en.bitcoin.it/wiki/FAQ](https://en.bitcoin.it/wiki/FAQ) You may start here and then proceed with Bitcoin Wiki for more details.

If you have already heard of Bitcoin mining and exchange, or you would like to know more about it, see below “Who is interested in Bitcoin?”.

##### Why is it any good?

Bitcoin is designed to be a faster, cheaper and a more secure currency. It is fast because verification of transfers is completely automated and does not involve human supervision. Security is achieved by having every participant do the verification himself using well-known cryptographic methods. Bitcoin is designed to prevent double-spending, stealing and creating money out of nothing. The original software source code is open and available to everyone for review and improvement.

##### How does it work?

Bitcoins do not exist as distinct items of information. They only appear as records in a global transaction history that is stored and synchronized between all participating computers. Transactions are grouped into *blocks* that are cryptographically signed in such a way that they are computationally hard to produce. Such scheme guarantees that no one can revert a transaction or double-spend bitcoins.

To own and spend bitcoins each participant only needs an address and a corresponding secret key. This key allows to send bitcoins from that address. To receive bitcoins a key is not needed; you only need to give the sender your address.

A person may have unlimited addresses and keys. A collection of keys is called a *wallet*.

Keys are used to *sign* new transactions in order to verify the ownership of the address. Then every client in the network can verify that the signature is valid and that the entire chain of transactions is done by actual holders of their keys. Therefore, one may steal bitcoins only by stealing secret keys.

##### Who creates bitcoins?

Bitcoins are not created upfront and distributed to some privileged persons. Instead, they are given as a reward to anyone for verifying and securing transactions. Transactions are secured by being put into *blocks* that are computationally expensive to generate. People who create blocks are called *miners*.

The reward for creating a block is contained in the first transaction that sends 25 BTC from nowhere to any address chosen by the creator of the block (reward was 50 BTC before December 2012).

The reward is halved approximately every 4 years until a total of 21 million bitcoins are generated around the year 2140. More than 10 million bitcoins are available already. Every participating computer checks that the reward is generated at a constant speed and has a correct value. See the chart here:

##### Is 21 million enough?

The minimum amount of bitcoins to be transferred is 0.00000001 BTC. This gives more than 2000 trillion of smallest units. If everybody finds it useful in the future, the format can be changed to allow even smaller values.

##### Is Bitcoin printed out of thin air?

No. Bitcoins are not printed, they are *earned*. In a way, all 21 million bitcoins already exist. You may earn them through an exchange or by validating and securing transactions. The rate at which new blocks are created is kept more-or-less stable by the protocol, so everybody can accurately account for money supply changes.

##### Why bitcoins are created this way?

The supply is designed to be constant in order to avoid undermining the value of Bitcoin in favor of less inflationary instruments (e.g. physical gold). At the same time, bitcoins are introduced gradually to motivate early adopters to create a secure and efficient network.

##### Who is interested in bitcoins?

There are normally three reasons why people get interested in bitcoins:

1. Mining.
2. Speculative exchange with other currencies and liquid assets.
3. “Regular” use in exchange for goods and services.

An “average” person can safely ignore the first two reasons.

Mining, the process of creating blocks of transactions, was possible on a home computer some time ago, but now it is profitable only using a custom-designed hardware. Bitcoin network adjusts the difficulty of mining to keep the rate of block creation constant (6 blocks per hour). As more people are throwing their resources into mining, the process becomes more expensive.

Speculation on currency exchange is also very competitive and does not significantly differ from any stock market.

Therefore, this FAQ focuses on the third reason: using Bitcoin in exchange for goods and services.

##### Who accepts bitcoins?

Bitcoin is a very young currency launched in 2009, but it already covers a surprisingly wide variety of goods and services. You can pay for personal services, buy digital and physical goods: books, games, movies, etc. So far you cannot buy groceries, but some coffee shops and restaurants already accept bitcoins.

There are wallet apps for computers and smartphones. There are different ways to buy bitcoins offline in physical form. Several companies develop processing services and debit cards. Right now Bitcoin is not always convenient or easy to use, but the trend is very strong towards more and better services.

See a list of places where one can buy, earn or spend bitcoins:

##### How do I use Bitcoin?

You need a software or a web service in order to manage your wallet and make transactions. A wallet is a collection of private keys (like passwords, but much longer), it does not contain any bitcoins itself. Each Bitcoin address has a corresponding private key that allows you to send money from that address. Addresses and keys are free to create and anyone can have as much of them as they want. To increase privacy, it is recommended to use a new address for each transaction. Popular Bitcoin software does that for you automatically.

##### How does Bitcoin protect against fraud?

Unlike Visa, MasterCard or PayPal, all Bitcoin transactions are final and cannot be reversed. Chargeback thus can only be performed through the good will of the seller. On the other hand, Bitcoin transactions do not only express transfer of funds, but they can also express complex contractual agreements. For instance, one can create a transaction between a seller, a buyer and a mediator. If the seller and the buyer agree on a transaction, the mediator cannot cancel it. But if there is a conflict, then the mediator may side with either buyer or seller to decide who receives the money. In this way Bitcoin provides a much stronger protection against fraud without a requirement to trust the mediator. This idea may be extended to a larger amount of participants to facilitate collective fund raising or insurance.

##### Is it legal?

See the discussion here:

Bitcoin is certainly in a “grey area”. So far no attempt has been made to penalize bitcoin users. However, certain activities that are illegal with other currencies (fraud, money laundering, illegal purchases, etc.) are illegal with Bitcoin as well. Since some central banks may see Bitcoin as a competitor that undermines their control over money supply, one may expect laws affecting Bitcoin in the future.

##### Can somebody shut Bitcoin down?

Bitcoin requires access to the internet and a special software to create and verify transactions. To stop people from using Bitcoin, one would have to suppress communication channels. Bitcoin is facing the same risk as any other internet protocol: being filtered or denied by the internet service providers. However, there is no single organization to shut down to cause major disturbances in the network. For example, if a popular currency exchange is closed, one can always use another exchange service or even trade in person. In a sense, Bitcoin is as difficult to shut down as BitTorrent.

##### Is Bitcoin backed by nothing?

The value of Bitcoin (and all the other goods for that matter) is purely subjective and depends on each individual valuation. Of course, the valuations may be aggregated and averaged, but they all stand on a shaky ground of each individual’s *decision* to buy or abstain from buying. The same applies to dollars, gold, oil and groceries.

There is no objective value of Bitcoin, but there are several common reasons why people use it. First, every day Bitcoin proves itself as a robust registry of money ownership: nobody can revert transactions, freeze accounts or take somebody else’s money. Second, it provides better privacy than modern banking. Third, there is no risk that some day the amount of bitcoins has suddenly increased and your savings have lost their value.

##### Is it fair that early adopters obtained bitcoins easier and became rich?

Yes. Early adopters took the risk of spending their time and energy on a project, which turned out to be useful for the people who joined later. The more confidence people have in the network, the more they are willing to invest in it, thus increasing the Bitcoin price.

##### Is it another Ponzi scheme?

No. Bitcoin does not promise any dividends. There is no central issuer and anyone who generates bitcoins makes the process more expensive for himself and the other miners, but at the same time increases reliability of Bitcoin for everyone.

Just like any other currency or stock, Bitcoin is also subject to speculative bubbles and bursts. Part of its value is based on the willingness of the users to spend and receive, while the other part is based on the anticipation of an increase or decrease of such willingness. If that anticipation grows too much, Bitcoin may quickly gain in value until no one will want to buy it anymore. Then the people will sell until the price goes down to a “normal” level. These speculative spikes will get smaller as the market grows and each individual share of bitcoins decreases.

##### Isn’t it stupid to generate money by burning electricity?

Some people are spending their energy printing metal coins with sophisticated patterns to make forgery more difficult. This activity is useless only if nobody wants to buy or use these coins.

Transactions are secured by putting them into blocks that are computationally expensive to generate. One has to spend time and electricity to verify and secure transactions to prevent double spending and illegitimate creation of money. Bitcoins are supplied as a reward to those who spend their resources to keep the network secure while it is young and growing. Money is not added because some amount of electricity is spent. It is electricity that is spent because people are demanding that much security and quality from the network. Automatically adjusted difficulty ensures that the amount of power to be spent is determined by the current demand in bitcoins, no more no less.

##### Why would the people generate blocks when the reward becomes very small?

By design, every transaction may include a fee for it to be included in a block. Right now this fee is usually zero for big enough transactions and insignificantly small for small transactions (in order to prevent spam). When the reward gets smaller, these fees will become the main motivation for generating blocks.

Blocks appear at a constant rate (6 blocks per hour) and every block has a limited size (1 Mb). Today the typical block size is 50-200 Kb. When the rate of transactions increases, they will start competing for a place in a block. This will in turn increase the average fee. The protocol may be changed in the future to allow bigger blocks.

##### Do I need to constantly waste electricity to use Bitcoin?

If you are not generating blocks, you will not spend much electricity. To store bitcoins you only need a wallet with secret keys. To transfer bitcoins you need an application that synchronizes transactions with the rest of the network. To do both you may use an app for your computer or a mobile phone, or a web service.

##### Do I need to be online to receive payments?

No. The payment is sent by relaying a signed transaction to the network. All you need to do is to give another person one of your addresses to send bitcoins to. To verify the payment, you can check the transaction status on or using a similar service. Digital signature is required only for spending bitcoins, not receiving them.

##### Do escrow services undermine the benefits of decentralization?

Even if you use a debit card with an escrow service that holds your keys, you will still benefit from the more competitive and non-inflationary nature of bitcoins. You may keep most of your savings on your personal computer, or transfer them easily and at low cost to any escrow in any country. Every escrow service in the world will need to compete with each other and with those who hold bitcoins by themselves.

##### How fast are the transactions?

Transactions are secured by being included in a block. Blocks are generated approximately every 10 minutes. Including the time to propagate a transaction through the network, today it usually takes about 15 minutes to verify inclusion in a block. For better security, one can wait until more blocks are added after the block with the transaction.

##### How transactions are secured?

Transactions are grouped into blocks and each block contains the signature of the previous block, thus making up a *chain* of blocks.

The security of the system is based on computational difficulty to generate blocks parallel to the main chain. The more blocks are created after the block containing your transaction, the harder it is to fork the chain and make the transaction invalid. Therefore, no transaction is *100% confirmed*. Instead, there is a *confirmation number* — a number of blocks built after the transaction. Zero confirmations means that the transaction is not yet included in any block (*unconfirmed*). One confirmation means that the transaction is included in one block and there are no more blocks after it yet.

Today for small transactions one or two confirmations (10-20 minutes) are considered enough. For bigger transactions it is recommended to wait for at least six confirmations (1 hour). One known exception is 120 confirmations required by the protocol for the use of generated bitcoins. This is because *miners* (those who create blocks) have the most of computing power in the network and must have extra incentive to play fairly and generate blocks in the main chain without attempting to double-spend their rewards.

##### What is the main chain?

Each block has a cryptographically signed reference to the previous block (*parent*). This way blocks form a chain. It is perfectly possible to have two blocks referencing the same parent block (the chain is *forked*). In this case we can think of two parallel chains diverging at some point. The *main chain* is by definition a chain of blocks with the maximum total difficulty.

##### What happens when the chain is forked?

Whenever miners accidentally generate parallel blocks, only one of these blocks is considered to be a part of the main chain. If later more blocks are added to some other block, then that block and all blocks after it will become part of the main chain.

The reward for the block and transaction fees are valid only for the blocks in the main chain. This motivates the miners to build on top of the main chain and avoid creation of parallel blocks. Otherwise, it is simply a waste of time and electricity if the block becomes abandoned by the network.

##### What happens to the transactions in the abandoned blocks?

The transactions that are not in the main chain are not lost. All valid blocks (including the abandoned ones) are distributed among participants in the network.

When it is evident that some block will never again become a part of the main chain, a miner will interpret transactions in that block as unconfirmed and will include them in his new block. This means that now they collect the fees from these transactions while the owner of the abandoned block does not receive the 50 BTC reward or the transaction fees.

For the person who made the transaction this means an extra delay in the transaction confirmation (typically 10-20 minutes).

##### Is Bitcoin anonymous?

Bitcoin is not anonymous, but rather pseudonymous. All transactions, addresses and amounts are visible to everyone. But every address is just a random number and is not associated with an identity unless deliberately revealed by its owner. If one reveals that they are an owner of a particular address, then everyone will be able to see the chain of transactions involving that address. Addresses are free to create and it is recommended to create a new address for each transaction. This makes it hard to track how many bitcoins one has or where they are sent to or received from.

To further increase privacy one may use “laundering” servers. The servers randomly exchange bitcoins between all their users in order to make it more difficult to trace their source. In the jurisdictions that prohibit laundering money, some people use online casinos as a plausible way to clear the trace of money at the expense of about 10% of the amount lost in gambling. But if you are not doing anything illegal, the usual level of anonymity provided by changing addresses should be enough.

##### What do miners do exactly?

Miners create blocks. To create a block one needs to create a file containing unconfirmed transactions (that are not yet included in any other block), add a timestamp, a reference to the latest block and a transaction sending 50 bitcoins from nowhere to any address. Then, the miner needs to compute a signature for the block (which is basically a very long number). This signature is called *hash* and the process of computing is called *hashing*.

Computing a single hash takes very little time. But to make a valid block, the value of its hash must be smaller than some target number. The hash function is designed to be hard to reverse. That is, you cannot easily find some file contents that will produce the desired hash. You must alternate the contents of the given file and hash it again and again until you get a certain number. In the case of Bitcoin, there is a field in a file called “nonce” which contains any number. Miners increment that number each time they compute a hash until they find a hash small enough to be accepted by other clients. This may take a lot of computing resource depending on how small is the target hash value. The smaller the value, the smaller the probability of finding a valid hash.

There is no guarantee that you need to spend a certain amount of time to find a hash. You may find it quickly or not find it at all. But in average, the small enough value of block hash takes time to create. This constitutes a protection against creation of a parallel chain: to fork the chain you will need to spend more resources than the people who created the original blocks.

##### What are the parameters of the network?

Here are some parameters of the Bitcoin chain. They may be different for alternative currencies based on the Bitcoin software (like Namecoin).

1. The minimum amount of bitcoins is 0.00000001 BTC.
2. Blocks are created every 10 minutes.
3. Block size is limited to 1 Mb.
4. Difficulty is adjusted every 2016 blocks (approx. every two weeks)
5. Initial reward for a block is 50 BTC.
6. Reward is halved every 210 000 blocks (approx. four years).

Points #5 and #6 imply that the total number of bitcoins will not exceed 21 million.

##### Why is the minimum amount 0.00000001 BTC?

It is a limitation of a transaction format (amount is a 64-bit number). This can be changed in the future if people will need to send smaller amounts.

##### Why are blocks created every 10 minutes?

The 10 minute interval is designed to give enough time for the new blocks to propagate to other miners and allow them to start computation from a new point as soon as possible. If the interval was too short, miners would frequently create new blocks with the same parent block, which would lead to a waste of electricity, a waste of network bandwidth and delays in transaction confirmations. If it was too long, a transaction would take longer to get confirmed.

##### Why is the block size limited to 1 Mb?

The block size is limited to make a smoother propagation through the network, the same reason why the 10 minute interval was chosen. If the blocks were allowed to be 100 Mb in size, they would be transferred slower, potentially leading to many abandoned blocks and a decrease in the overall efficiency.

Today a typical size of a block is 50-200 Kb which makes a lot of room for growth. In the future it is possible to increase block size when the networks get faster. Decreasing time interval would not change much because the security of transactions depends on the actual time, not the number of blocks.

##### Why is the difficulty adjusted every two weeks?

The difficulty of mining is adjusted every 2016 blocks (approx. every two weeks). This gives miners enough time to adjust their hardware, but at the same time prevents the blocks to be created too quickly as the total computational power grows.

##### Why is the initial reward 50 BTC?

Initial reward of 50 BTC is purely arbitrary. If it were 500 BTC, then it would not change anything in the market structure, just change the nominal prices by a factor of 10.

##### Why is the total number of bitcoins limited?

According to the Austrian theory of money, any money supply is “good” in a sense that any differences in money supply are purely nominal. If everyone suddenly wakes up with twice as much money in their wallet, it would not change anything in the world since the money has almost no direct use value. What matters are the relative differences in amounts.

If Bitcoin allowed unlimited mining, it would allow perpetual shift of wealth from productive uses to miners. As a limited commodity, Bitcoin itself does not encourage any particular type of work. By being neutral, it appeals more to non-miners, than it would be otherwise.

##### Why is the reward decreasing?

Mining rewards are decreasing (instead of being constant) to motivate earlier miners to secure the network while it is young and more vulnerable.

The reward is changed every 210 000 blocks (about four years) to ensure an optimal growth of the network. If the interval was too short, all the bitcoins would have been generated too quickly before a wide network could be created. If the interval was too long, then it would have effectively decreased the reward of the early adopters making the network more vulnerable.

##### How can the protocol be changed?

The protocol is a list of rules that every client must follow in order to validate transactions and have their transactions validated by others. Hence, if you change the rules for yourself, other clients will simply reject your transactions and you probably will not be able to accept theirs. This makes it hard to change the protocol.

If there is a change that a vast majority of clients will find useful, then it is possible to publicly agree that starting with the block number X, new rules will apply. This will give a certain amount of time to everyone to update the software.

##### I have more questions

Please send your questions and comments here: oleganza@gmail.com

Twitter: @oleganza

##### Discussion on Hacker News

##### Donation

If you like this FAQ, you may donate 0.1 BTC on this address: 1TipsuQ7CSqfQsjA9KU5jarSB1AnrVLLo.

***

{% include signup.md %}
