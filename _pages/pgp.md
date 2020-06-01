---
permalink: /pgp1/
title: "PGP 101"
classes: wide
author_profile: true
---

## Let's PGP!
You're ready to level up your cypherpunk skills. It's time to learn how to use cryptography via PGP to send messages and sign files!

![could you give us some privacy for, like, one second?](https://media0.giphy.com/media/3otPoyXM2G9VRgROnK/giphy.gif?cid=ecf05e477d673bb37b8a248e46d14c623ee60f3220b4d493&rid=giphy.gif)

## What is PGP

According to our friends at Wikipedia, [PGP (Pretty Good Privacy)](https://en.wikipedia.org/wiki/Pretty_Good_Privacy) is an encryption program that provides cryptographic privacy and authentication for data communication. PGP is used for signing, encrypting, and decrypting texts, e-mails, files, directories, and whole disk partitions and to increase the security of e-mail communications. 

PGP allows you to send a messages in privacy. Basically, the recipient will only be ably to read it if  you intend for them to read it.

This is accomplished via the creation of a pair of keys:

1. Private Key - your secret key that's used to sign messages and files. **DO NOT SHARE** your private key. 
2. Public Key - you publicly available key where users can send you specific messages or files. Senders use your specific public key in order to make messages **ONLY** viewable by you. You can also sign a message and display publicly and viewers can use your public key to verify you wrote the message.

Besides sending an encrypted or private message, you can also **sign files**. By sigining a file, viewers will be able to verify that it has not been tampered with since it was signed. Perhaps you wanted to release a journal about Bitcoin and you want readers to verify that you were the author... you could use PGP to accomplish this. Readers could verify with your signature and rest assured that the journal has not been tampered with since it was published. 

## How to get started?
Be fearless. The only way to learn is to get in some reps!

Download the software and watch the tutorial at the links below. The video was extremely helpful. It walked me through everything to get started.

[PGP Software](https://www.gpg4win.org/index.html){: .btn .btn--warning}
[PGP Tutorial](https://youtu.be/CEADq-B8KtI){: .btn .btn--warning}


Once you are setup with Kleopatra, import my public key and send me a message!

[WORDS Public Key](https://raw.githubusercontent.com/bitcoinwords/bitcoinwords.github.io/master/assets/public-key/WORDS-public-key.txt){: .btn .btn--warning}

When you are ready, consider uploading your public key to your website or to a keyserver. 

I use this keyserver:
[keys.openpgp.org/](keys.openpgp.org){: .btn .btn--warning}