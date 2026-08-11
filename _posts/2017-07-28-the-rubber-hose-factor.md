---
title: "The Rubber Hose Factor"
permalink: "/the-rubber-hose-factor"

author: elaineou

tags:
  - Elaine Ou
  - 2017 Q3
  - Security
  - Privacy
  - Custody

excerpt: The Rubber Hose Factor. Posted July 28, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [The Rubber Hose Factor](https://elaineou.com/2017/07/28/the-rubber-hose-factor/)
### By [Elaine Ou](https://twitter.com/elaineou)
### Posted July 28, 2017

[![](/assets/images/2017/m7/the-rubber-hose-factor1.png)

The strongest encryption in the world can be broken with a [rubber hose](https://en.wikipedia.org/wiki/Rubber-hose_cryptanalysis). It’s easy; all you have to do is smack the keyholder with a rubber hose until they reveal the private key. Have you ever been hit with a hose? It hurts.

Early-stage investors have a metric called the **Bus Factor**, the number of people who can get hit by a bus before the company dies. It’s sort of a proxy for investment risk. A startup where only one founder has industry or technical expertise has a Bus Factor of 1.

My company has something called the **Rubber Hose Factor**, a measure of security risk. How many humans have to be coerced before an account is compromised? Single rubber hose attacks are to be expected, a double attack conceivable, a triple Rubber Hose would require extraordinary circumstances and a really long hose.

![](/assets/images/2017/m7/the-rubber-hose-factor2.png)

[To launch a nuclear strike](https://www.bloomberg.com/politics/graphics/2016-nuclear-weapon-launch/), two out of five ICBM squadrons must simultaneously turn their launch keys. So, an unintended nuke would require two rubber hose attacks. Don’t worry, the squadrons are located in distant underground bunkers and surrounded with physical security layers as well.

How many successful rubber hose attacks are required to disable the Ethereum Network? **Two.**

![](/assets/images/2017/m7/the-rubber-hose-factor3.png)

*Ethereum hashrate distribution*

What about Bitcoin? Ostensibly **four**, but possibly just one.

![](/assets/images/2017/m7/the-rubber-hose-factor4.png)

*Bitcoin hashrate distribution*

It’s easy to overestimate your Rubber Hose Factor. Ethereum’s Parity client comes with a built-in multi-signature wallet, where outgoing transactions have to be signed by multiple account holders. That’s the right idea, except that no one ever looked at the wallet source code.

It only took [one person](https://github.com/paritytech/parity/pull/4805) to introduce a bug and another to merge the changes. That was enough to get a backdoor deployed to thousands of users, which was later exploited to the tune of $32 million in ether. Perceived Rubber Hose Factor: **Many**. Actual Rubber Hose Factor: **2.**

I don’t mean to give Parity developers a hard time; users are responsible for their own free software. But it’s worth pointing out that every [Bitcoin Core](https://github.com/bitcoin/bitcoin/pulls) update is reviewed by at least twelve eyeballs, and those eyeballs are connected to a half-dozen brains. The last thing you want is for users to believe that the Rubber Hose Factor is higher than it really is.

**Funny story:** Last year, the central bank of Bangladesh got [hacked](https://en.wikipedia.org/wiki/Bangladesh_Bank_robbery) and $81 million was sent to the Philippines. Bangladesh Bank officials [insisted](http://manilastandard.net/mobile/article/216192) that it was SWIFT’s fault, because they had a super secure computer system that required six different bank managers to place their palms on a touch screen before a transaction could be authorized. Turns out the touch screen was connected to a single malware-infected computer, which issued fraudulent transactions without any authorization at all. Perceived Rubber Hose Factor: **6**. Actual Rubber Hose Factor: **1**.

Don’t worry about those who get hacked in Ethereum. When life hands you [lemon socialism](https://en.wikipedia.org/wiki/Lemon_socialism), make lemonade.

[![](/assets/images/2017/m7/the-rubber-hose-factor5.png)

> We would support this. We're all in this together!
>
> — Bancor (@BancorNetwork) [July 22, 2017](https://twitter.com/BancorNetwork/status/888890136544649216)

***

{% include signup.md %}
