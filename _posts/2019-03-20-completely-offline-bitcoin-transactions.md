---
title: "Completely Offline Bitcoin Transactions"
permalink: "/completely-offline-bitcoin-transactions"

author: grubles

tags:
  - grubles
  - 2019 Q1
  - Technology
  - Markets
  - Adoption

excerpt: Completely Offline Bitcoin Transactions. Posted March 20, 2019.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [Completely Offline Bitcoin Transactions](https://medium.com/hackernoon/completely-offline-bitcoin-transactions-4e58324637bd)
### By grubles
### Posted March 20, 2019

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions1.jpg)

With the advent of Blockstream Satellite and widely broadcasted, passively-receivable Bitcoin data, a new era of Bitcoin adoption can occur. Areas without access to fast broadband connections can now trustlessly verify Bitcoin blocks and transactions, and receive BTC discreetly with common cheap hardware. With the Satellite API, those same areas can now receive arbitrary data — current market data, private messages, and data from exciting new use cases not thought of yet. All free. The broadcasts are free and the software is free with code available for auditing and improvement by the community.

For the first time, most of the planet’s population can receive bitcoin using *their own fully validating nodes*without expensive data plans. But how do they send bitcoin? There are a few cheap and accessible ways to do so. Transactions can be broadcasted via SMS, by mesh networking devices, and even sneakernet (simply transporting the signed raw transaction data on a flash drive or printed QR code).

GoTenna sells a simple to use mesh networking device, which along with a piece of software called TxTenna can broadcast Bitcoin transactions to a local mesh network of GoTennas. [There is also growing interest and work being done on LoRaWAN](https://twitter.com/tulipan81/status/1058729901874917376) — a similar mesh networking technology.

With this hardware setup, anyone can send and receive bitcoin without an internet connection. It’s resistant to network outages and can also maintain uptime through power outages since all of the hardware is run off batteries. The hardware can of course be run off of gasoline generators or solar panels if the power outage is longer lasting.

***

In this tutorial we will be using the following:

**Hardware:**

* Blockstream Satellite Receiver
* GoTenna Mesh
* Android device (I used a cheap $30 Coolpad)
* A hardware wallet (optional)

**Software:**

* Linux (Ubuntu 18.04 used here)
* Electrum Personal Server
* Electrum Wallet
* `qrencode` (simply `sudo apt install qrencode`) to generate QR codes
* [TxTenna smartphone app](https://github.com/MuleTools/txTenna)

## Going Offline 🛰

To start, a Blockstream Satellite Receiver is required for passively receiving Bitcoin data without an internet connection. There is comprehensive documentation [here](https://github.com/Blockstream/satellite), along with the guide I wrote a couple years ago:

### Building Your Own Bitcoin Satellite Node

#### A layman’s guide

##### hackernoon.com

***

### Electrum

Once the satellite receiver is setup, you can begin to install Electrum Personal Server and Electrum Wallet:

### chris-belcher/electrum-personal-server

#### Maximally lightweight electrum server for a single user - chris-belcher/electrum-personal-server

##### github.com

### spesmilo/electrum

#### Electrum; Bitcoin thin client. Contribute to spesmilo/electrum development by creating an account on GitHub.

##### github.com

***

## Initializing a Hardware Wallet

If you want to use a hardware wallet, Electrum supports most of the popular offerings: Trezor, Ledger, Coldcard, and possibly even OpenDIME.

For this tutorial / demo, I used a Trezor Model T.

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions2.jpg)

*My aptly named Trezor*

Trezor’s blog has a great tutorial for initializing a hardware wallet here:

[https://blog.trezor.io/using-trezor-with-electrum-v3-a0b9bcffe26e](https://blog.trezor.io/using-trezor-with-electrum-v3-a0b9bcffe26e)

***

Now you should have a completely off-the-grid Bitcoin node and wallet; capable of receiving BTC and validating blocks. 🛰

***

## Outbound Transaction Broadcasting

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions3.jpg)

Now we want to spend some of our BTC. With available tools and software, we can broadcast a signed raw transaction via a local mesh network.

GoTennas have a range of up to 4 miles depending on your local geography and “density” — forested areas or urban areas with buildings will reduce the range of the GoTenna. There *are* ways to modify the GoTenna to attach external antennas for longer range communications. Note that you can broadcast transactions multiple times if you don’t succeed the first time. You could also always save the raw transaction onto your mobile device and carry it to a location where you’re within range, or fall back to broadcasting via SMS.

Combining GoTenna hardware with a piece of software called TxTenna enables Bitcoin transaction broadcasting and relaying without cellular network nor WiFi connectivity. TxTenna also supports transaction relay via SMS.

Simply download the TxTenna app on your Android smartphone using Google Play or other means, and pair your GoTenna with Bluetooth.

***

### Signing Bitcoin Transactions Prior To Broadcasting

Using Electrum Wallet, Bitcoin transactions can be signed with a hardware wallet device and saved locally to be converted into a QR code. To do so, sign the Bitcoin transaction with Electrum like you normally would, but don’t broadcast it with Electrum.

This transaction is spending BTC to an address broadcasted globally via Blockstream Satellite by the anonymous “[Post Soviet](https://twitter.com/notgrubles/status/1088902367188267008)”:

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions4.png)

*Transaction ready to be signed by a hardware wallet*

### Sign the transaction.

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions5.jpg)

*Confirm sending*

Once signed, you can click “Copy” at the bottom left of the Electrum UI to copy the raw transaction hex in order to generate a QR code.

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions6.png)

*Click “Copy”*

Now generate a QR code with the following command:

```
$ qrencode <paste raw tx data here> -o signedtx.png
```

Then display it with your GUI:

`$ display signedtx.png`

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions7.png)

Now you’re set to scan the QR code with the TxTenna app and broadcast it to your local mesh network where it will eventually make its way to the TxTenna API endpoint.

Scan the QR code with TxTenna and broadcast it via GoTenna Mesh:

The transaction is now broadcasted to the mesh network!

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions8.jpg)

Once the transaction is included in a block, your offline satnode will display the transaction in Electrum Wallet.

![](/assets/images/2019/m3/completely-offline-bitcoin-transactions9.png)

*Confirmed!*

### To clarify what just happened:

I run a Blockstream Satellite Receiver which receives Bitcoin data and arbitrary data broadcasted by the Satellite API. [An anonymous person in some undisclosed location broadcasted a journal and BTC address.](https://bitcoinist.com/bitcoin-blockstream-satellite-message/)

Using their BTC address, I generated an offline transaction with my satnode, signed it with a hardware wallet, and finally broadcasted it outbound to my local mesh network. The transaction was included in a block, beamed down from space, and my satnode verified the data. Electrum Wallet displayed the transaction as confirmed!

No expensive internet subscription required. 🏄‍♂️

Thanks for reading!

-grubles

***

{% include signup.md %}
