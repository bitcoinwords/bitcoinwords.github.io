---
title: "Decentralizing Bitcoin's Last Mile With Mobile Mesh Networks"
permalink: "/decentralizing-bitcoins-last-mile-with-mobile-mesh-networks" 

author: richardmyers

tags:
  - Richard Myers
  - CU19 Q2
  - Technology
  - Mesh Networks
  - Decentralization

excerpt: Richard Myers explains the power of mobile mesh networks and how to further decentralize the Bitcoin network. Posted May 29, 2019.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

# [Decentralizing Bitcoin's Last Mile With Mobile Mesh Networks](https://coincenter.org/entry/decentralizing-bitcoin-s-last-mile-with-mobile-mesh-networks)
## How you can use Bitcoin without relying on centralized Internet Service Providers
### By [Richard Myers](https://twitter.com/remyers_)
### Posted May 29, 2019

![](/assets/images/cy19/cy19q2m5/rm-1.png){: .align-center}

_The "Expert Views" series of publications allows legal and technical practitioners in the cryptocurrency space to share their insight and opinions on cutting edge policy questions. The views expressed here are those of the author and not necessarily those of Coin Center._ Bitcoin has been designed to be resilient against not just technological attacks, but also political ones. Cryptography, incentives and decentralization are all tools used to give the Bitcoin network a high level of resiliency. Here I will discuss how communication decentralization is important for Bitcoin's resiliency and how this feature can be enhanced with alternative last-mile communication technologies such as mobile mesh networks.

Centralized communication systems are prone to failure in the case of natural (or man made) disasters. For example, Hurricane Sandy downed one-third of all communication infrastructure in a 10-state area back in 2012. After a natural disaster, centralized systems are slow to recover.

Puerto Rico struggled for many months after Hurricane María when 80% of landlines became inoperative. Marginalized communities and places with failing or nonexistent infrastructure are also not well served by centralized providers.

Modern economies increasingly rely on electronic payments and suffer when communication systems are unavailable. This is true not just for Bitcoin, but also for Visa and Mastercard. Where Bitcoin is unique is in its goal of also being resilient against deliberate state-level financial censorship and surveillance.

Network decentralization gives Bitcoin protection against censorship on a global scale, but local Internet Service Providers (ISPs) are in a position where they can unilaterally monitor and block users of the Bitcoin protocol. Examples of politically motivated internet censorship and surveillance from China to Turkey are easy to find. It is not hard to imagine regimes applying these techniques to people using Bitcoin. Even in the United States, Edward Snowden revealed that the NSA had a program in 2013 to intensely track Bitcoin users.

Within any particular location, users must access the Bitcoin network using ISPs and mobile carriers which are dominated by regional and national monopolies. ISPs like Comcast have been shown to throttle and block the popular decentralized file sharing protocol BitTorrent. When the IRS requested Coinbase's user records in 2016, they also requested detailed IP logs of their users that could be matched up with ISP IP logs. Anti-piracy groups like Prenda Law have previously used IP address information obtained from ISPs to target BitTorrent users for legal harassment. Someday, Bitcoin users could be targeted in a similar way. It's much easier for a government or powerful corporation to pressure a single monopoly with huge infrastructure investments to surveil and censor people in an automated fashion than it is to try to target citizens individually. Software privacy tools alone are not enough. Before Snowden revealed himself, he built a personal map of open WiFi hotspots that were not near his home in Hawaii. He understood that even using Tor did not eliminate the risk that came from using an internet access point somehow connected to his true identity.

Centralized ISPs are the single point of failure for all of these attacks; either from direct censorship or meta-data logging. Even sending a chat message to someone a few feet away involves data traveling to a distant base station and through centralized servers. Mobile phones are technically capable of forming decentralized mobile mesh networks, but current spectrum license holders have no economic incentive to allow it. Instead, peer-to-peer connectivity is limited to a few dozen feet of Bluetooth range which has limited practical utility in the real world.

Fortunately, alternatives to centralized ISP networks are starting to appear. Local mesh radio networks, satellites, and long-range radio have all been proposed as ways to enable decentralized peer-to-peer communication—both for Bitcoin transactions and for resilient communication generally.

In 2014, the Kryptoradio project pioneered transmitting Bitcoin data using a terrestrial digital television transmitter in Finland. The trial lasted 2 months and reached ~5 million people, or about 95% of all Finns. For the first time, you could validate transactions without an internet connection. But this system still relied on regionally centralized broadcast infrastructure.

In 2017, Blockstream started satellite-based Bitcoin transaction broadcasts that now cover virtually the entire world's population. This enables decentralized transaction verification in countries that might ban Bitcoin and also enables Bitcoin use in locations without reliable or affordable internet. But this system only receives transaction information from the Bitcoin network. How can an offline user add a new transaction to the ledger?

At Scaling Bitcoin 2017, Nick Szabo and Elaine Ou from Global Financial Access proposed transmitting transactions using low-cost digital shortwave radio. Their system uses long-range skywave transmissions to route around censorship and across borders. Their proposed system is semi-mobile for use in censored countries and supports two-way communication over hundreds of miles. This is a promising technology but requires further development before it can be widely deployed.

The goTenna Mesh radio powers the world's first consumer mobile mesh network. It's focused on relaying short-burst data over great distances, in a totally decentralized, off-grid manner: no cell, WiFi, or satellites required.

In a mobile peer-to-peer mesh network, devices communicate directly with each other if they are within range, or relay from device to device to device if the destination is further away.

All of this happens automatically with no centralized routing or infrastructure needed. Bitcoin nodes communicate using a similar flat peer-to-peer network without any special nodes that coordinate their connections. Unfortunately, the Bitcoin peer-to-peer network is only a virtual overlay on a physical internet that is dependent on centralized ISPs and mobile carriers. Unlike nodes in a mobile mesh network, nodes connected to centralized networks have a fixed location or identity that can be targeted for censorship and surveillance.

Privacy activists from the Samourai Wallet team were inspired by Blockstream's satellite project to create an open-source initiative called Mule Tools to support similar alternative communication projects. In 2018, goTenna collaborated with Samourai Wallet to create the open-source TxTenna App for Android phones. With TxTenna, you can send signed Bitcoin transactions over the goTenna Mesh network directly from an offline mobile phone. This enables people to broadcast Bitcoin transactions in a decentralized way, without depending on local ISPs. The goTenna Mesh network enhances financial privacy by removing any physical link between a person and their bitcoin. TxTenna can also route around local censorship by using gateways to reach distant, uncensored internet connections.

## How does it work?

From an offline phone, Samourai Wallet creates a signed Bitcoin transaction. The signed transaction is sent automatically to the TxTenna App. TxTenna broadcasts the transaction to nearby goTenna Mesh nodes. They relay the transaction data from node to node until it reaches a mesh node running TxTenna with uncensored internet access, which can send the transaction to the Bitcoin network.

A Python-based version of TxTenna has also been made for computers and Internet-of-Things devices, enabling them to broadcast signed Bitcoin transactions or act as an internet gateway between the goTenna Mesh network and the Bitcoin network. The goTenna Mesh radio can also be combined with a Blockstream Satellite receiver to create an off-grid system that combines the best off-grid features of both. Such a system can both receive Bitcoin blockchain updates from the Blockstream Satellite receiver and broadcast signed Bitcoin transactions over the goTenna Mesh network without any direct internet connectivity.

## Conclusion

In time, we expect low-cost gateway devices will support multiple alternative communication modalities. These will include mobile mesh, satellite, long-range High Frequency Radio, WiFi, and mobile phone networks. In the case of an ISP failure, natural disaster or political oppression, Bitcoin transactions will simply fail over to an alternative network. In this way, transactions on the Bitcoin network can be made even more unstoppable.
_Richard Myers is a decentralized applications engineer at [goTenna](https://gotenna.com/), co-founder of Bytabit AB, and has been interested in both the technology and political implications of bitcoin for many years. Richard is passionate about tools that empower decentralized societies. Follow him on Twitter at [@remyers_](https://twitter.com/remyers_)_
