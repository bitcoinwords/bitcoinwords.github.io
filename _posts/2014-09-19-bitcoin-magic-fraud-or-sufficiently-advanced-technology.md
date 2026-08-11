---
title: "Bitcoin: Magic, fraud, or 'sufficiently advanced technology'?"
permalink: "/bitcoin-magic-fraud-or-sufficiently-advanced-technology"

author: konradsgraf

tags:
  - Konrad S. Graf
  - 2014 Q3
  - Mining
  - Money
  - Technology

excerpt: Bitcoin: Magic, fraud, or 'sufficiently advanced technology'?. Posted September 19, 2014.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Bitcoin: Magic, fraud, or 'sufficiently advanced technology'?](http://konrad-graf.squarespace.com/blog1/2014/9/19/bitcoin-magic-fraud-or-sufficiently-advanced-technology.html)
### By [Konrad S. Graf](https://www.konradsgraf.com/)
### Posted September 19, 2014

POST HEADER

POST BODY

![](/assets/images/2014/m9/bitcoin-magic-fraud-or-sufficiently-advanced-technology1.webp)

Arthur C. Clarke’s third law famously states: “Any sufficiently advanced technology is indistinguishable from magic.” What Bitcoin makes possible can at first seem almost magical, or just impossible (and therefore most likely fraudulent or otherwise doomed). The following describes the basic technical elements behind Bitcoin and how it brings them together in new ways to make *seeming* magic possible in the real world.

Clarke’s second law states: “The only way of discovering the limits of the possible is to venture a little way past them into the impossible.” And this, we can see in retrospect, is basically what Bitcoin creator Satoshi Nakamoto did. Few at the time, even among top experts in relevant fields, thought it could really ever work.

It works.

One reason many people have a hard time understanding Bitcoin is that it uses several major streams of technology and method, each of which is quite recent in historical perspective. The main raw ingredients include: an open-source free software model, peer-to-peer networking, digital signatures, and hashing algorithms. The very first pioneering developments in each of these areas occurred almost entirely within the 1970s through the 1990s. Effectively no such things existed prior to about 40 years ago, a microsecond in historical time, but a geological age in digital-revolution time.

Some representative milestone beginnings in each area were: for open-source software, the GNU project (1983) and the Linux project (1991); for peer-to-peer networking, ARPANET (1979) and Napster (1999); for digital signatures, Diffie–Hellman theory (1976) and the first RSA test concept (1978); and for hashing algorithms, the earliest ideas (around 1953) and key advances from Merkle–Damgård (1979). Bitcoin combines some of the best later developments in each of these areas to make new things possible.

Since few people in the general population understand much about *any* of these essential components, understanding Bitcoin as an innovation that combines them in new and surprising ways, surprising even to experts *within* each of those specialized fields, is naturally a challenge without at least a little study. Not only do most people not understand how the Bitcoin puzzle fits together technically, they do not even understand *any of the puzzle pieces!*The intent here is not to enter into much detail on the content of any of these technical fields, but rather to provide just enough detail to achieve a quick increase in the general level of public understanding.

#### What Bitcoin is about in one word: Verification

It may help to focus to begin with not on the details of each field, but at *how* each part contributes strategically to Bitcoin’s central function. This is to create and maintain a single unforgeable record that shows the assignment of every bitcoin unit to addresses. This record is structured in the form of a linked chain of blocks of transactions. The Bitcoin protocol, network, and all of its parts maintain and update this blockchain in a way that anyone can verify. Bitcoin revises the Russian proverb, “doveryai, no proveryai,” “Trust, but verify,” to just “verify.”

If a single word could describe what the Bitcoin network does, it would be *verification*. For a borderless global currency, relying on trust would be the ultimate bad idea. Previous monetary systems have all let users down just where they had little alternative but to rely on *some* trusted third party.

First, the core Bitcoin software is open source and free. Anyone can use it, examine it, propose changes, or start a new branch under a different name. Indeed, a large number of Bitcoin variations with minor differences have already existed for some time. The open source approach can be especially good for security, because more sets of eyes are more likely to find weaknesses and see improvement paths.

Open source also tends to promote a natural-order meritocracy. Contributors who tend to display the best judgment also tend to have more of their contributions reflected over time. Unending forum discussions and controversies are a feature rather than a bug. They focus attention on problems—both real and imagined—which helps better assure that whatever is implemented has been looked at and tested from diverse angles.

Many computers worldwide run software that implements the Bitcoin protocol. A protocol is something roughly like a spoken language. Participants must speak *that*language and not some other, and they must speak it well enough to get their messages across and understand others. New protocols can be made up, but just as with making up new languages, it is usually rather unproductive. Such things only take off and become useful if enough others see a sufficient advantage to actually participate.

Second, as a peer-to-peer network, there is no center. Anyone can download core Bitcoin software and start a new node. This node will discover and start communicating with other nodes or “peers.” No node has any special authority or position. Each connects with at least eight peers, but sometimes many more. Some faster and always-on nodes relay more information and have more connections, but this conveys no special *status*. Any node can connect or drop out any time and join again later. A user does not have to run a full node just to use bitcoin for ordinary purposes.

It is common to say that Bitcoin is “decentralized” or doesn’t have a center. But then, Where is it? Thousands of active peering nodes are spread over most countries of the world and each one carries an up to date full copy of the entire blockchain.

*Some* nodes not only relay valid transactions and blocks, but *also* join the process of discovering and adding new blocks to the chain. Such “mining” activities both secure the final verification of transactions and assign first possession of new bitcoin to participating nodes as a reward. Understanding basically how mining works requires a look at the distinct functions of several different types of cryptography.

#### Bitcoin cryptography dehomogenized

Bitcoin relies on two different types of cryptography that few people understand. Both are counter-intuitive in what they make possible. When most people hear “cryptography,” they think of keeping data private and secure through encryption. File encryption can be used to help secure individual bitcoin wallet files, just as it can be used for the password protection of any other files. This is called symmetric key cryptography, which means the same key is used to encrypt and decrypt (AES256 is common in this role). Encryption may also be used for *securecommunication* among users *about* transactions, as with any other kind of secure traffic. This is called asymmetric key cryptography, which means a public key encrypts a message and its matching private key decrypts it at the other end.

However, all of this is peripheral. Nothing inside the core Bitcoin protocol and network is encrypted. Instead, two quite different types of cryptography are used. They are not for keeping secrets, but for making sure the truth is being told. Bitcoin is a robust global system of truth verification. It is in this sense the opposite of the “memory hole” from George Orwell’s *1984*; it is a remembering chain.

The first type of cryptography within Bitcoin is used to create a message digest, or informally a “hash.” Bitcoin uses hashing at many different levels (the most central one is an SHA256 hash run twice). The second type is used to create and verify digital signatures. This uses pairs of signing keys and verification keys (ECDSA secp256k1 for signatures).

#### The keys to the kingdom

Despite intuitive appearances to users, bitcoin wallets do not contain any bitcoin! They only contain pairs of keys and addresses that enable digital signatures and verifications. Wallet software searches the blockchain for references to the addresses it contains and uses all the related transaction history there to arrive at a live balance to show the user. Some of the *seemingly* magical things that one can do with bitcoin, such as store access to the same units in different places, result from the fact that the user only deals with keys while the actual bitcoin “exists,” so to speak, only in the context of the blockchain record, not in wallets. It is only multiple copies of *the keys* that can be stored in different places at the same time. Still, the effective possession of the coins, that is, the ability to make use of them, stays with whoever has the corresponding signing keys.

While software designers are working hard to put complex strings of numbers in the background of user interfaces and replace or supplement them with more intuitive usernames and so forth, our purpose here is precisely to touch on some technical details of how the system works, so here is a real example of a set of bitcoin keys. This is a real signing key (do not use!):

5JWJASjTYCS9N2niU8X9W8DNVVSYdRvYywNsEzhHJozErBqMC3H

From this, a unique verification (public) key is cryptographically generated (compressed version):

03F33DECCF1FCDEE4007A0B8C71F18A8C916974D1BA2D81F1639D95B1314515BFC

This verification key is then hashed into a public address to which bitcoin can be sent. In this case:

12ctspmoULfwmeva9aZCmLFMkEssZ5CM3x

Because this particular signing key has been made public, it has been rendered permanently insecure—sacrificed for the cause of Bitcoin education.

#### Making a hash of it

Hashing plays a role quite different from digital signatures. It proves that a message has not been altered. Running a hash of the same message always produces the same result. If a hash does not match a previous one, it is a warning that the current version of the message does not match the original.

To illustrate, here is a message from Murray Rothbard. He wrote in *Man, Economy, and State* that:

“It must be reiterated here that value scales do not exist in a void apart from the concrete choices of action.” —Murray Rothbard, 1962

And here is the SHA256 digest of this message and attribution (the same algorithm that Bitcoin uses):

68ea16d5ddbbd5c9129710e4c816bebe83c8cf7d52647416302d590290ce2ba8

Any message of any size can go into a hash function. The algorithm breaks it down, mixes the parts, and otherwise “digests” it, until it produces a fixed-length result called “a digest,” which for SHA256 takes the above form, but is in each case different in content.

There are some critical properties of a good hash algorithm. First, the same message always produces the same digest. Second, it only works in one direction. Nothing about the message that went in can be reconstructed from the digest that came out. Even the tiniest change produces a completely different digest, with no relationship between the change in input and the change in output. This is called “the avalanche effect.” Third, the chances of producing the same digest from an altered message are miniscule. This is called “collision resistance.” It is impossible to craft an *altered* message that produces the same digest as the original *un*altered message.

To demonstrate, here is the same quote without the two quotation marks.

It must be reiterated here that value scales do not exist in a void apart from the concrete choices of action. —Murray Rothbard, 1962

Which produces this digest:

0a7a163d989cf1987e1025d859ce797e060f939e2c9505b54b33fe25a9e860ff

Compare it with the previous digest:

68ea16d5ddbbd5c9129710e4c816bebe83c8cf7d52647416302d590290ce2ba8

The tiniest change in the message, removing the two quotation marks, produced a completely different digest that has no relationship whatsoever to the previous digest. In sum, a digest gives a quick *yes or no answer* to a single question: Is the message still exactly the same as it was before? If the message differs, the digest cannot indicate how or by how much, only that it either has changed at all or has not.

How could such a seemingly blunt instrument be useful? Bitcoin is one application in which hashing has proven very useful indeed. In Bitcoin, hashing is used in the lynchpin role of making it impossible to alter transactions and records once they have been recorded. Once the *hashes* are hashed together within the blockchain, record forgery anywhere is impossible.

#### Transactions and how miners compete to discover blocks

Wallet software is used to create transactions. These include the amount to be sent, sending and receiving addresses, and some other information, which is all hashed together. This hash is signed with any required signing keys to create a unique digital signature valid only for *this* transaction and no other. All of this is broadcast to the network as *un*encrypted, public information. What makes this possible is that the signature and the verification key do not reveal the signing key.

To keep someone from trying to spend the same unit twice and commit a kind of fraud called double-spending, nodes check new transactions against the blockchain and against other new transactions to make sure the same units are not being referenced more than once.

Each miner collects valid new transactions and incorporates them into a candidate in the competition to publish the next recognized block on the chain. Each miner hashes all the new transactions together. This produces *a single* hash (“mrkl_root”) that makes the records of every other transaction in a block interdependent.

Each hash for any candidate block differs from every other candidate block, not least because the miner includes his own unique mining address so he can collect the rewards if his candidate block does happen to become recognized as next in the chain.

Whose candidate block becomes the winner?

For the competing miners to recognize a block as the next valid one, the winning miner has to generate a certain hash of his candidate block’s header that meets a stringent condition. All of the other miners can immediately check this answer and recognize it as being correct or not.

However, even though it is a correct solution, it works only for the miner who found it *for his own block*. No one else can just take another’s correct answer and use it to promote his own candidate block as the real winner instead. This is why the correct answer can be freely published without being misappropriated by others. This unique qualifying hash is called a “proof of work.”

The nature and uses of message digests are counter-intuitive at first, but they are indispensable elements in what makes Bitcoin possible.

#### An example of a mined block

Here is an example of some key data from an actual block.

“hash”:”0000000000000000163440df04bc24eccb48a9d46c64dce3be979e2e6a35aa13”,

“prev_block”:”00000000000000001b84f85fca41040c558f26f5c225b430eaad05b7cc72668d”,

“mrkl_root”:”83d3359adae0a0e7d211d983ab3805dd05883353a1d84957823389f0cbbba1ad”,

“nonce”:3013750715,

The top line (“hash”) was the actual successful block header hash for this block. It starts with a large number of zeros because a winning hash has to be below the value set in the current difficulty level. The only way to find a winner is to keep trying over and over again.

This process is often described in the popular press as “solving a complex math problem,” but this is somewhat misleading. It is rather an extremely simple and brutally stupid task, one only computers could tolerate. The hash function must simply be run over and over millions and billions of times until a qualifying answer happens to finally be found somewhere on the network. The chances of a given miner finding such a hash for his own candidate block on any given try are miniscule, but somewhere in the network, one *is* found at a target average of about every 10 minutes. The winner collects the block reward—currently 25 new bitcoins—and any fees for included transactions.

#### How is the reward collected?

The candidate blocks are already set up in advance so that rewards are controlled by the winning miner’s own unique mining address. This is possible because the miner already included this address in his own unique candidate block *before* it became a winner. The reward address was *already incorporated* in the block data to begin with. Altering the reward address in any way would invalidate the winning hash and with it that entire candidate block.

In addition, a miner can only spend rewards from blocks that actually become part of the main chain, because only those blocks can be referenced in future transactions. This design fully specifies the initial control of all first appropriations of new bitcoins. Exactly *who* wins each next block is random. To raise the probability of winning, a miner can only try to contribute a greater share of the current total network hashing capacity in competition with all of the others trying to do the same.

As shown above with the Rothbard quote, a completely different hash comes out even after the slightest change to the message. This is why the protocol includes a place for a number that is started at zero and changed by one for each new hash try (“nonce”). Only this tiny alteration, even if the rest of the candidate block data is unchanged, generates a completely different hash each time in search of a winner. In the example above, it looks like this miner found a winning hash for this block at some point after the *three billionth* attempt (“nonce”:3013750715), and this was just for that one miner or mining pool, not including the similar parallel but unsuccessful attempts of all the other miners, and all this just for the competition for this one block.

The key point to understand is that*finding* a hash under the difficulty level is extremely competitive and difficult, but *verifying* afterwards that one has been found is trivial. The rest of the miners do so and move right along. They use the newly discovered hash of the previous block header (“prev_block”) as one of the inputs for their next crop of block candidates (which assures the vertical integrity of the single chain of blocks) and the race continues based on the remaining pool of unconfirmed transactions.

#### A powerful, self-financing, verification network

The Bitcoin mining network is, as of late September 2014, running at about 250 petahashes per second and rising at a logarithmic pace that will soon make this figure look small (rate tracked [here](https://blockchain.info/charts/hash-rate)). This means that about 250 quadrillion hashes are currently being tried across the network *every second* all the time. This is the world’s most powerful distributed computing network, by far, and has already been steadily extending this lead for quite some time.

Block rewards and transaction fees help promote the production and maintenance of this entire network in a decentralized way. Since block generation is random and distributed on average in proportion to hashing power contribution, it helps incentivize all contributors all the time. Many miners participate in cooperative mining pools so that at least some rewards arrive on a fairly regular basis.

The network is designed to be entirely self-financed by participants from the beginning indefinitely into the future. Early on, new coin rewards are larger and transaction-fee revenue smaller. Finally, only transaction-fee revenue is to remain, with a long and gradual transition phase built in.

If Bitcoin does remain successful over the longer term, by the time transaction-fee revenue predominates, there would likely be many orders of magnitude more transactions per block by which to multiply the average competitive fee per transaction.

This has been a summary look at a few of the key technical elements of Bitcoin. Hashing algorithms and digital signatures are especially counter-intuitive and relatively new inventions, but knowing what they make possible is essential for understanding how Bitcoin works. Each of Bitcoin’s major elements contribute to the central functions of verification, unforgeable record-keeping, and fraud prevention. These technical underpinnings and the functions they support sound about as far from the systematic deceptions of a fraud such as a Ponzi scheme as it would be possible to get.

## Adapted and revised from [*Bitcoin Decrypted Part II: Technical Aspects*](https://konrad-graf.squarespace.com/bitcoin-decrypted/) and cross-posted to[*actiontheory.liberty.me*](https://konrad-graf.squarespace.com/config/pages/actiontheory.liberty.me)*.*

POST FOOTER

/post

/content-wrapper

***

{% include signup.md %}
