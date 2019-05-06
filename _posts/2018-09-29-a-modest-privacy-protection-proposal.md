---
title: "A Modest Privacy Protection Proposal"
permalink: "/a-modest-privacy-protection-proposal" 

tags:
  - Jameson Lopp
  - Cy18 Q3

excerpt: Jameson Lopp has been doxxed and wants to help you stay safe. In this post, he lays out a framework to protect your privacy. Posted September 29, 2018.

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


# [A Modest Privacy Protection Proposal](https://medium.com/s/story/a-modest-privacy-protection-proposal-5b47631d7f4c)
## How to reclaim your privacy in the surveillance age
### By [Jameson Lopp](https://medium.com/@lopp)
### Posted September 29, 2018

![](/assets/images/cy18/cy18q3m9/lopp-1.png){: .align-center}
Photo: [Bernard Hermant](https://unsplash.com/@bernardhermant?utm_source=medium&utm_medium=referral)/[Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

It's hard to retain much privacy in the information age — the internet has a nearly perfect limitless memory and we're placing a ton of sensitive data onto it. After [being swatted in 2017](http://www.cbs17.com/news/victim-of-durham-swatting-incident-thinks-motive-was-tied-to-digital-currency_20180313070019716/1036234884), I set out on a mission to start my life over with a renewed focus on privacy. While I was motivated by changes in the Bitcoin ecosystem (an increased [rate of physical attacks](https://github.com/jlopp/physical-bitcoin-attacks)), this guide is meant to be comprehensive for people living in the USA and generally helpful for other citizens of the world. The journey has been long and arduous because there simply aren't many resources out there for how to achieve what I wanted.

### Why protect privacy?

You may be thinking "I'm not doing anything wrong — why should I be concerned about privacy?" It's important to over-invest in privacy because once it's lost, it's really challenging to recover. Consider this: you may not be a target right now — but you may become one in the future as your wealth increases, you endorse unpopular political or religious perspectives or... you make a single post on social media in poor judgment.

In December 2013, Justine Sacco, a woman with 170 Twitter followers, [posted a very bad joke](https://www.nytimes.com/2015/02/15/magazine/how-one-stupid-tweet-ruined-justine-saccos-life.html) as she was boarding a plane. Sacco slept during her 11-hour plane trip and woke up to find out that she was the number-one Twitter topic worldwide, with celebrities and bloggers all over the globe denouncing her and encouraging all their followers to do the same. Sacco's employer, New York internet firm [IAC](https://en.wikipedia.org/wiki/IAC_%28company%29), declared that she had lost her job as director of corporate communications. At least one Twitter user showed up at the Cape Town airport to photograph her arrival. Point being: In the Information Age, it doesn't take much for you to attract the ire of millions of people.

If an unforeseen event such as this happens to you, do you really want to have to move to a new address for safety? It turns out there's no one-size-fits all solution to this problem — it has to be customized to suit each person's needs and be appropriate for the jurisdiction in which you reside. With that said, I'll cover high-level privacy threat vectors and as many of the details as possible for mitigating them in this post.

### Privacy goals

It's important to note the goal of this guide: It's not "how to completely disappear." If you want perfect privacy, then just close all of your online accounts and move to the middle of nowhere. Rather, my goal is to show you how to achieve the best possible privacy while still retaining your existing reputation.

Also, some of the following are specific to your jurisdiction. Most privacy guides are written for Americans because they are under more attacks with frivolous lawsuits, tracked by more private investigators, targeted for more asset seizures, and jailed for more homeland security charges than any other country.

There are four major levels of privacy protection:

1. Protection against the average person who knows how to search the web
2. Protection against someone with resources to hire a cheap private investigator
3. Protection against someone willing to indefinitely fund a top-tier private investigator
4. Protection against agents of nation states with nearly unlimited funds

Most folks are concerned about none of these potential attackers, while some may only be interested in protection against the first level. I can only speak about the first few levels; if you want to hide from governments you'll have to search elsewhere.

### Pricing people out of privacy

Before we begin, I want to be clear that many of the techniques come at a cost. I had to fill out hundreds of pages of paperwork, spend around $30,000 in legal/banking/service fees, and endure a four-month process in order to achieve my goals. I estimate annual recurring costs of over $15,000 for my extreme setup. I had to speak to half a dozen attorneys before I found one that was even comfortable helping me. Once I did have an attorney, this made it easier for me to work with bankers because they were more assured that my intentions were legal and I wasn't trying to cover up criminal activity.

And it's not just about money — the amount of time and effort required even to perform the financially "cheap" aspects of this guide are sufficient to turn most people off from attempting them. If you're willing to dedicate a weekend and a couple hundred dollars, you should at least be able to substantially improve your online privacy, which will put you in the top one percent of internet users.

Again, everyone should customize their privacy plan according to their individual needs and resources. Some of the below suggestions are moderate in nature, while others require far more commitment. Learn about them, anyway. The truth is, surveillance has become the norm. Most people are willing to sacrifice privacy in return for convenience, and swimming against the tide makes for a challenging journey.

My primary takeaway after countless hours of research is that we give a lot of personal information to many different merchants and service providers that are vulnerable to hacking and social engineering. You should assume that over a long enough period of time, any data you give to third parties will be made public — whether or not it happens intentionally is irrelevant. The general solution to many of these data leaks is to use proxies of all kinds: electronic, legal, and human. Let's dive into specifics.

### Mitigating real-time location tracking

The best thing you can do is stop carrying around a portable surveillance device (mobile phone), but they're so darn convenient! At the very least, though, you can disable location history whenever possible such as with [Google-based services](https://support.google.com/accounts/answer/3118687?hl=en). You should turn off GPS on your phone, though apps may still be able to get rough location data via cell triangulation. Though you may not even want to trust that the tracking is actually turned off. It's probably best [not to log into Google services](https://www.theverge.com/2018/8/13/17684660/google-turn-off-location-history-data) using an account that can be tied to your real identity. Consider creating a throwaway account for mobile use. More details on protecting your phone are in the next section.

A much harder threat to defend against is the rise of CCTV with facial recognition, tattoo recognition, and even gait recognition. You can opt-out of some facial recognition with online services such as Facebook and Google, but not others such as Amazon and Apple. And of course, who knows if that data may still be getting resold and used elsewhere, even if you opt out? Since walking around with a mask is often illegal or will draw unwanted attention, it seems that there is no great solution to CCTV at the moment. The optimal solution would be some sort of wearable device that blinds cameras, though all of the incarnations thus far emit infrared and are only capable of blinding infrared nighttime surveillance cameras that don't have IR filters installed.

You could try a product such as the [Justice Cap](http://www.justicecaps.com/), though it's only going to work well during low light conditions against cheap cameras that don't have infrared filters. If you do go this route you'll want the highest powered LEDs you can find and if you can get them to pulse, that would likely be even more effective.

<iframe width="560" height="315" src="https://www.youtube.com/embed/fywvB4Unjv4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Along a similar vein was [this privacy visor](https://www.youtube.com/watch?v=HbXvZ1XKdWk&t=1s) that emits infrared light in order to defeat facial recognition, though it's probably not a great way to blend into a crowd.

[Reflectacles](https://debuglies.com/2016/12/04/new-anti-facial-recognition-glasses-protect-users-privacy-from-cctv-cameras/), on the other hand, don't emit IR light — they reflect it. This seems like a more low-key and low-tech solution.

A [recent study](https://arxiv.org/pdf/1803.04683.pdf) showed that perhaps going the other way will work well: projecting infrared onto your own face may defeat most facial recognition software. With sophisticated calibration, the researcher showed that you could even fool face detection software to get false positives and effectively make it think you are a specific person.

![](/assets/images/cy18/cy18q3m9/lopp-2.png){: .align-center}
Image: Zhe Zhou, Di Tang, Xiaofeng Wang, Weili Han, Xiangyu Lui, and Kehuan Zhang/Fudan University via [arXiv](https://arxiv.org/pdf/1803.04683.pdf)

You can also try wearing [a photorealistic mask](http://thatsmyface.com/custom-wearable-masks/). However, note that [in some jurisdictions it's illegal](http://www.anapsid.org/cnd/mcs/maskcodes.html) to wear a mask in public. And you'll once again just end up attracting attention from other members of the public.

The most practical solution seems to be low tech: wear a hat with a large brim such as a baseball cap, along with large dark or mirrored sunglasses that cover a significant portion of your face.

Failing all else, you can always [go Juggalo](https://www.thefader.com/2018/07/03/juggalo-makeup-facial-recognition-insane-clown-posse)...

### Protect your phone

Many services require you to provide a phone number when you sign up and they may even validate that you control it by sending a unique code via SMS. If you don't want to give away information such as your phone provider or area code, you should buy a virtual phone number that forwards to your real phone number. You could use a service like [Tossable Digits](http://www.tossabledigits.com), though they only accept credit card payments so you'd need to use a prepaid card or virtual credit card to retain your privacy. For even stronger privacy, consider using a service that accepts cryptocurrency, such as [NumberProxy](https://numberproxy.com). Note that virtual phone numbers/proxies may have issues receiving 2FA SMS codes from web services. They also tend to be unable to send and receive group SMS messages.

For maximum privacy, you should only use a prepaid phone service so that they don't know your name. You should assume that every phone service provider not only knows your location (by triangulating cell tower pings) but also [resells that information.](https://www.zdnet.com/article/us-cell-carriers-selling-access-to-real-time-location-data/) What they don't know can't be used against you.

It turns out this is harder than you might expect! From my extensive experience watching [_The Wire_](https://www.hbo.com/the-wire) multiple times, I figured I'd be able to walk into any store selling prepaid phone SIMs, plunk down some cash, and walk out with a burner. Turns out brick and mortar stores like Best Buy will often require ID in order for you to buy a phone plan, even if it's prepaid! I ended up having to go online and buy a SIM with a prepaid plan that I purchased via a prepaid debit card and had delivered to a private mailbox.

At the software level, the operating systems and apps on phones tend to have [abysmal privacy](https://www.gnu.org/proprietary/malware-mobiles.html). If you want top-notch privacy, your best option at the time of writing is [RattlesnakeOS](https://github.com/dan-v/rattlesnakeos-stack), which is taking the reins from CopperheadOS (no longer maintained). Something to keep an eye out for is [Purism's Librem phone](https://puri.sm/shop/librem-5/), which will hopefully be released in 2019.

### Protect your residence

In order to achieve privacy that will protect you from a variety of attacks upon your home, you need to break any ties between your name and your residence. To be clear, you must consider your current location compromised — these techniques only work if they are used on a residence that has never been tied to your identity. This means either having official documents listed in someone else's name or in the name of a legal entity that can't be linked to you.

In the U.S. there are a few states with especially strong privacy protection for Limited Liability Corporations — New Mexico, Nevada, and Wyoming. You can read one [comparison of legal differences here](https://www.myusacorporation.com/articles/delaware-vs-nevada-vs-wyoming) and [another here](https://cindysnewmexicollcs.com/Incorporating/vs-Nevada-Delaware-Wyoming). To get an idea of a high-end privacy protection setup, check out the "[Ultra Asset Protection Package](https://wyomingcompany.com/prices-top/)" from Wyoming Corporate Services:

![](/assets/images/cy18/cy18q3m9/lopp-3.png){: .align-center}

As we can see, more sophisticated setups basically use the "shell company" paradigm to wrap the actual ownership of assets with a variety of legal entity layers that are difficult, if not impossible, to peel away. Once these legal entities are formed, you should use them to purchase / rent / lease property and pay for any services such as utilities and deliveries at your residence.

One helpful thing to keep in mind when setting up new services is to remember that there are plenty of "address-challenged" people who don't have a permanent address because they live in recreational vehicles / live a nomadic lifestyle. There seem to be a lot more of them than people trying to protect their privacy. As such it may be easy to find [practical advice](http://www.technomadia.com/2012/07/chapter-9-nomadic-logistics-domicile-mail-taxes-banking-and-voting/) by reading forums and websites devoted to nomadic lifestyles. It's also useful when explaining your situation to others. That is, you're less likely to be questioned if you just say "my RV doesn't have a fixed address" than if you say "I'm trying to protect myself from data leaks."

Once you are settled into your new location, you may want to take it to the next level when you are on phone calls or video chats. You'll want to ensure that you don't leak information via ambient noise or visuals. In this case I'd recommend setting up your camera to have a blank wall behind you or just buy a [collapsible screen](https://www.amazon.com/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=collapsible+screen+background). For noise, place the microphone in a small [isolation booth](https://www.amazon.com/Portable-Microphone-Studio-Voice-Isolation/dp/B00G2KP10G) or build one by lining the sides of a cardboard box with [noise absorbing material](https://www.amazon.com/Soundproofing-Acoustic-Studio-Foam-Panels/dp/B01B3Y6QDG/ref=sr_1_3?ie=UTF8&qid=1527781641&sr=8-3&keywords=noise+absorbing+panels). For the ultra paranoid, be aware that something as innocent as a storm outside could help attackers to pinpoint your location.

Are you worried about surveillance from laser microphones? If you complete the rest of this guide, hopefully no one can find your residence in the first place — but if you want to be extra safe, consider a [noise generator](https://www.amazon.com/Shomer-Tec-SHLSD-Laser-Surveillance-Defeater/dp/B00ABV7J0C).

Another issue to consider is EXIF data in photos. You shouldn't post photos that you have taken near your physical location as they may very well include embedded GPS coordinates, especially if the photo was taken with a smartphone. The only way to be sure about this is to use an [EXIF](http://exifpurge.com/) cleaner (Windows/Mac) or [ExifTool](https://www.shellhacks.com/remove-exif-data-images-photos-linux/) (Linux) to scrub metadata before posting such photos online.

Yet another edge case concern is related to your time zone. If you are making public posts that get timestamped then it doesn't take a ton of your post data to narrow down which longitude you're living near via temporal analysis. This may not matter much if you live along a well-populated longitude, but if you're living somewhere more (longitudinally) remote such as Hawaii, New Zealand, or Greenland, it could be a dead giveaway.

![](/assets/images/cy18/cy18q3m9/lopp-4.png){: .align-center}
Temporal analysis of spends out of [336xGpGweq1wtY4kRTuA4w6d7yDkBU9czU](https://bitinfocharts.com/bitcoin/address/336xGpGweq1wtY4kRTuA4w6d7yDkBU9czU) via BitInfoCharts

Above is an example of temporal analysis on a bitcoin address that holds quite a few BTC. The times listed are in GMT and we can see that daily activity begins at 12 a.m. GMT and drops off after 3 p.m. GMT. These times happen to line up with 9 a.m. and midnight, Tokyo time. It turns out that this is the cold wallet for a Japanese exchange called CoinCheck.

This should be obvious, but you shouldn't make public posts about physical businesses because it gives away your location. This includes "checking in" on FourSquare, tagging photos and status updates on Instagram/Facebook/etc, and even posting business reviews on Yelp/Google/Facebook. One caveat is if you do so for misdirection by making posts about places that aren't near your residence. (More on misdirection later.)

You may think some of the above is overkill, but remember when [4chan found Shia LaBeouf's secret art location](https://www.vice.com/en_us/article/d7eddj/4chan-does-first-good-thing-pulls-off-the-heist-of-the-century1) in a little more than a day? First, they used planes seen overhead to narrow down via public flight path info, then they used positions of stars to narrow further. The final piece of info that gave it away was when a user drove around the area honking their car horn. Don't underestimate the power of the internet to crowdsource investigations.

### Protect your snail mail

You should never receive _any_ mail or deliveries in your own name at your address. Little known fact: All mail that goes through the US Postal System [gets scanned and put into a database](https://www.nytimes.com/2013/07/04/us/monitoring-of-snail-mail.html?hp&_r=1&&pagewanted=all). Is that database secure? Best to assume it's not...

**Optimal ($$$)**: Rent the cheapest apartment you can find just to receive mail. Since it's a "real address" it won't raise any red flags with services to which you give it.

**Decent ($$)**: If you have a good relationship with an attorney, they may be willing to accept mail on your behalf. You can also use a "[ghost address](https://jjluna.com/ghost-addresses/)" via JJ Luna's contacts.

**Decent ($)**: Buy a virtual address/remailing service. You can even combine several of these together to create a sort of "onion routing" for your physical mail. Each "hop" will only know about the hop before and the hop after it. Some options are [EarthClassMail](http://www.earthclassmail.com/) and [TravelingMailBox](http://www.travelingmailbox.com/).

**Better than nothing ($)**: Buy a Post Office Box/mailbox in a UPS Store.

Once you have your proxy address(es) set up, you'll want to use them for every service that doesn't require proof of residence. This includes:

* Credit cards
* Domain names
* Bank accounts
* Subscriptions and memberships
* Online services

### Protect "real property"

"Real property" is a category of items for which you are taxed on a recurring basis simply for owning, which creates public records, a.k.a. privacy leaks. Most commonly this will be a house, any vehicles you own, though in some jurisdictions it can also cover pets! On a related note, income taxes are not public record, but over [75,000 IRS employees in the US](https://www.irs.gov/statistics/irs-budget-and-workforce) have access to them... they're not _exactly_ private.

Once again, you'll need to register these assets under an LLC/legal entity that can't be tied to your identity. For liability and privacy purposes you will likely want separate LLCs to own real estate versus owning vehicles. This is to reduce the number of links to your residence: If an attacker manages to find one of your vehicles and sees that it's owned by "NoName LLC," the first thing they will do is search for all publicly registered property owned by "NoName LLC" — if this same LLC owns your residence, your privacy has been compromised.

Another thing to note with regard to vehicles is that if you don't want your name on the insurance policy, you'll need to get commercial fleet insurance and in my experience, this can be about twice as expensive as personal insurance.

### Protect your real name

Since you will inevitably end up interacting with people as you go about your life, you'll want an alias that can't be connected to you. A first name and last name that is common to your area (but not suspiciously common) should suffice, as it will be more forgettable. If you need help thinking of a common name, look up census data from your region. If you're in the US, you can use [this name generator service](https://namey.muffinlabs.com/).

It's not like folks are going to be asking for your government ID unless you're purchasing age-restricted goods and services. Just make sure that you keep it simple and consistently use the same pseudonym; otherwise, you're likely to forget which 'nym you gave to which service provider.

### Keep a low profile

Another common privacy strategy other than using proxies is to "hide in the crowd." As such, when you're out in public you should strive to be unnoticeable and unmemorable. Don't wear flashy clothes, don't make exotic body modifications, blend in with local styles and customs. Don't drive a rare car, don't make any noticeable exterior modifications such as wheels, stickers, or vanity plates.

### Protect your internet privacy

Your ISP, various government agencies, and who knows who else may be monitoring your internet traffic.

Many popular web services are chock full of various tracking software, much of which is simply trying to correlate your internet browser with your interests in order to better target advertising at you.

You'll also want to protect yourself from various online activity trackers such as advertisers and social networks. I recommend installing these browser extensions:

* [Privacy Badger](https://www.eff.org/privacybadger)
* [uBlock Origin](https://github.com/gorhill/uBlock/)
* [HTTPS Everywhere](https://www.eff.org/https-everywhere)

You can also provide protection for all devices on your network including smart TVs and mobile apps by configuring your router to use a local DNS server that is running [Pi-hole](https://pi-hole.net/). It will block any network requests for known advertisers and trackers.

While you're at it, change the default search engine for your browsers to be [one that is pro-privacy](https://restoreprivacy.com/private-search-engine/).

You should also switch to a pro-privacy email service. Similar to choosing a VPN, there's no clear "best" provider. There's a good [comparison guide here](https://thatoneprivacysite.net/vpn-comparison-chart/).

If you want to take it to the extreme, consider quitting the use of all Google services. There's a great guide here:

[**How I Fully Quit Google (And You Can, Too)** _My enlightening quest to break free of a tech giant_ medium.com](https://medium.com/@excinit/how-i-fully-quit-google-and-you-can-too-4c2f3f85793a "https://medium.com/@excinit/how-i-fully-quit-google-and-you-can-too-4c2f3f85793a")

You can secure a decent amount of your web browsing from snooping third parties by installing browser extensions, but it's not foolproof — the aforementioned entities can still see which domains / IP addresses you're visiting, even though they can't peer into the data packets that are going back and forth.

VPNs are quite important for protecting your internet privacy. When you're at home they prevent the websites and other online services from knowing your real IP address, and thus your geographic location. When you're not at home and using WiFi access points operated by untrustworthy third parties, it prevents them from snooping on your traffic. It's really hard to decide on the best VPN, because there are many factors at play, so I'll leave you to research that. There's a great guide [here](https://thatoneprivacysite.net/).

What I definitely recommend is setting up your home network to automatically use your VPN — you can accomplish this by buying a router that has a built-in VPN client. By having the VPN configured at the router level, any device that connects to your router will automatically be protected by your VPN without requiring configuration on the device itself. There's a lot of good info [here](https://restoreprivacy.com/vpn-routers/).

I'm a fan of the [AsusWRT Merlin firmware](https://sourceforge.net/projects/asuswrt-merlin/) which provides a lot of additional functionality on top of the stock ASUS firmware, including more complex routing policies. By using the Merlin firmware you can specify certain devices (like video streamers) to not use the VPN and you can configure a kill switch with just a few minutes of tinkering. After running VPNs at the router level for several months I noticed that, from time to time, the VPN connections would fail. If you don't have [a kill switch enabled](https://www.vpnuniversity.com/routers/use-selectivepolicy-routing-kill-switch-asuswrt-merlin), you won't know if your VPN fails until perhaps you notice that you aren't getting as many CAPTCHAs as usual when logging into web apps. A kill switch is a must so that you instantly know when you are no longer protected by a VPN.

Also note that you won't be able to put video streaming services behind a router that is configured to send ALL traffic through a VPN; they'll lock out your account because they assume you are trying to bypass regional content restrictions. The solutions to this are to either use one with firmware that supports selective routing as linked above (and create an exclusion rule for streaming devices) or to use a two-router setup that's chained from your modem (where the first router is) for non-VPN devices, and the second router for VPN devices. If you're not a networking expert, you may need a hand from a geeky friend to help set that up.

You can purchase some VPNs anonymously with a throwaway email account and cryptocurrency. For next-level purchase privacy here, note that any [bitcoin-accepting VPN provider](https://www.bestvpn.com/best-vpn-bitcoin/) can be purchased with monero via [xmr.to](https://xmr.to).

Using a router with VPN support is the most user-friendly way to protect all of your devices, but it comes at a cost. The CPU(s) on the router will likely become your bottleneck with regard to bandwidth. In my testing with a top of the line multi-CPU router, it wasn't possible to achieve over 50 Mbit/S speeds due to the CPUs maxing out while performing the encryption and decryption operations.

![](/assets/images/cy18/cy18q3m9/lopp-5.png){: .align-center}
First spike: maxing out downstream at 43 Mb/S. Second spike: maxing out upstream at 48 Mb/S. Screenshot: Jameson Lopp

A downside here is that if you have a very fast ISP that's over 50 Mb/S, an off-the-shelf consumer router, even a high-end one with multiple processors, is going to be bottlenecked by its CPU. If this bottleneck is a concern for you then you'll need to invest more effort into building a Linux-based router on beefier hardware. [Here's](https://blog.tjll.net/building-my-perfect-router/) a good guide, though you'd want to invest more than $50 in the hardware.

The above is great for your at-home devices, though note that you'll also want to configure VPNs manually on your mobile devices that are going to leave your home network from time to time. In my experience, VPNs that support OpenVPN are the easiest to configure on various devices.

Finally, you'll want to make this setup more robust. Routing all of your traffic through one server creates a single point of failure, and sometimes a VPN server can get overwhelmed and become unresponsive for a lengthy period of time. What to do? Configure _multiple_ active VPN connections! The tricky part that took a fair amount of research was how to do this in a way so that the kill switch doesn't activate if any of the servers go down, which would make your setup even _less_ robust.

For AsusWRT Merlin firmware, the answer is explained in [this forum post](https://www.snbforums.com/threads/confused-as-to-how-to-make-the-kill-switch-work.46544/#post-404524). TL;DR: you should define four or five VPN clients, set them all to start on boot, but only enable the kill switch on the last VPN client. That way, if any of them fail the routing rules for a lower priority client will kick in, while if the last VPN client fails AND all of the other clients have failed, the kill switch will activate and block all traffic.

A note on DNS leaks — if you're protecting all of your traffic with VPN tunnels then it ought to also be making DNS queries through the VPN. However, if you aren't protecting all of your devices with VPNs then consider running a [Pi-Hole DNS server](https://pi-hole.net/) on your home network. It will block DNS queries to advertising domains and reduce your overall query volume by caching results. You can configure the upstream DNS server that it uses to be a pro-privacy server such as [Cloudflare's 1.1.1.1](https://blog.cloudflare.com/announcing-1111/).

### Protect your PC

In order to prevent data leaks due to malware, install covers over your webcams. I'm a fan of the [magnetic SpiShutter](https://www.amazon.com/SpiShutter-Classic-Black-Magnetic-Macbook/dp/B00I1CN3YY) for MacBooks, otherwise you can just buy a simple [adhesive sliding shutter](https://www.amazon.com/Allinko-Computer-Macbook-Notebook-Surface/dp/B07D4DZD1J?th=1).

At the software level, you can take back some control of what various processes in your computer are accessing by running a firewall such as [Little Snitch](https://www.obdev.at/products/littlesnitch/index.html). You can also run antispyware apps such as [Micro Snitch](https://www.obdev.at/products/microsnitch/index.html), which will alert you when processes try to access your microphone or camera. If you want the best privacy and security, you really shouldn't run OS X or Windows, but rather a [privacy-focused flavor of Linux](https://www.techradar.com/news/best-linux-distro-privacy-security).

If you're at Edward Snowden-levels of paranoia then you'll want to break out the soldering kit and physically remove the hardware connections for cameras and microphones. As Edward states, this is a "pain in the ass."

<iframe width="560" height="315" src="https://www.youtube.com/embed/S4LOyi3EMWU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

If you're a Linux nerd and you want extreme privacy without destroying your hardware, buy a [Librem laptop](https://puri.sm/product-category/laptops/). They run on open source hardware with hardware switches to enable/disable the webcam/microphone and the wifi/Bluetooth. It also runs a stripped-down version of Debian with no proprietary closed source software packages.

### Protect online accounts

This is good advice for anyone in general, but you should do what you can to keep unwanted intruders out of your online accounts — _especially_ your email account. The average person uses the same password or three across all of their online services and they just memorize them. This is a single point of failure and when a single one of those services suffers a data breach, you can be sure that your username and password will be sold on the black market and fed into bots that try to use them to log into every popular online service. You've [probably already been "pwned"](https://haveibeenpwned.com/) and don't even know it.

This means using a [good password manager](https://www.howtogeek.com/240255/password-managers-compared-lastpass-vs-keepass-vs-dashlane-vs-1password/) such as [LastPass](https://www.lastpass.com/)/[1Password](https://1password.com/)/[KeePass](https://keepass.info/) to generate strong random unique passwords for every online service you use and to add second-factor authentication to every online account that supports it. While you're at it, protect your password manager with a hardware 2FA device such as a [Yubikey](https://www.yubico.com/), [Trezor](https://wiki.trezor.io/User_manual:Two-factor_Authentication_with_U2F), or [Ledger](https://support.ledgerwallet.com/hc/en-us/articles/115005198545-Fido-U2F).

The prior listed password managers are convenient and reasonably secure, though they put your privacy in the hands of a third party. They also have design flaws that can potentially expose your entire password database to malware. The ultimate security and privacy (but less convenient) password managers let you control your own data and use a hardware token for decryption. Lance Vick, lead security engineer at BitGo, [has a great guide here.](https://github.com/lrvick/security-token-docs/blob/master/Use_Cases/Password_Mangement.md)

Pay special attention to your email account — most people only have a single email address that likely has a ton of sensitive information in it, and if an attacker gains control of your email account they can probably use it to reset passwords to most of your other online accounts. This is a single point of failure; consider using different email accounts for different purposes, and protect them with hardware 2FA.

### Protect communication channels

Any email, phone call, or text message you send can be intercepted because they're sent across public networks without being encrypted. Trying to fix email with PGP encryption is pretty much a lost cause; consider using a secure email such as Cisco's [Registered Envelope Service.](https://res.cisco.com) You can pretty easily improve phone call and text message security by buying a burner phone and using end-to-end encrypted apps such as [Signal](https://www.signal.org/), [Whatsapp](https://www.whatsapp.com/), and [Telegram](https://telegram.org/) on it. You can use other services such as [Send Safely](https://sendsafely.com) to transfer larger documents.

For the ultra privacy conscious it's worth noting that Signal, Whatsapp, and Telegram are all closed, centralized walled gardens that can still sell your metadata even though they can't read the content of your messages. Signal and Whatsapp require a phone number, making it much more work for you to have a private account. They can find out who you are talking to and when you are talking to them. More private but slightly less user-friendly alternatives are decentralized open communications systems like [Riot](https://matrix.org/docs/projects/try-matrix-now.html), XMPP with OTR, and IRC with OTR.

### Protect your financial data

Most mainstream financial services are highly insecure and have poor privacy. You can protect those services using standard online account strategies as mentioned earlier — strong passwords and hardware 2FA. And certainly don't input your real address with any of those providers.

Credit reporting agencies have created huge targets by centralizing tons of sensitive information, thus they [get hacked](https://www.washingtonpost.com/business/technology/equifax-hack-hits-credit-histories-of-up-to-143-million-americans/2017/09/07/a4ae6f82-941a-11e7-b9bc-b2f7903bab0d_story.html) [from time to time](https://www.engadget.com/2015/10/01/tmobile-experian-hack/), resulting in rampant identity theft.

Many Americans are familiar with "the big three" credit bureaus, but it turns out that there are [quite a few more](https://www.creditreportproblems.com/credit-reporting-agencies.htm)!

You should freeze your credit reports; this will prevent anyone from requesting a copy and potentially finding sensitive data. Here are links to freeze your credit report for major providers in the U.S.:

* [TransUnion](https://freeze.transunion.com/sf/securityFreeze/landingPage.jsp)
* [Equifax](https://www.freeze.equifax.com/Freeze/jsp/SFF_PersonalIDInfo.jsp)
* [Experian](https://www.experian.com/freeze/center.html)
* [Innovis](https://www.innovis.com/securityFreeze/index)
* [SageStream](https://www.sagestreamllc.com/security-freeze/)
* [Advanced Resolution Services](https://www.doctorofcredit.com/two-credit-bureaus-you-should-freeze-before-you-apply-for-a-u-s-bank-credit-card/#Freezing_ARS_Advanced_Resolution_Services)
* [Clarity Services](https://www.clarityservices.com/support/security-freeze/)
* [CoreLogic](https://www.corelogic.com/downloadable-docs/clrps-cra-ltr-security-freeze-request-110216-v1.1.pdf)

I also recommend submitting forms to opt out of as many data brokerages as possible — you can find an [extensive list here](https://www.stopdatamining.me/opt-out-list/).

You should also stop using normal credit cards except perhaps while traveling — more details on that in the next section.

### Protect your purchases

Cash is still the king of financial privacy, though it's less convenient than plastic and downright unusable for online purchases. Another downside I've encountered recently is that it is becoming more common for merchants to not be able to provide sufficient change. I can only assume this is because far fewer customers are using cash.

A more convenient and still highly private option is to carry prepaid debit/gift cards you purchased with cash. The next best privacy option is to use a debit/credit card in the name of your LLC. Make sure it doesn't have your real name or address on it; the billing address should be the billing address of your LLC (the address of the registered agent or of a private mailbox). This can be tricky because card providers tend to require a real name on every card they issue. I don't have a specific solution I can share here other than to recommend making some banker friends who will work the system on your behalf.

Virtual disposable credit cards are great for privacy and security. You can limit your attack surface by giving unique card details to each merchant and setting spend limits on each card.

[Entropay](https://entropay.com/)

* Up to 10 virtual prepaid Visa cards at a time
* Some fees apply

[MyCard2Go](https://www.mycard2go.com)

* Prepaid physical Visa card
* Limited to €100 without identity verification
* Some fees apply

[Netspend](https://www.netspend.com/prepaid-debit/)

* Create virtual prepaid Visa cards or Mastercards
* Some fees apply

[Privacy](https://privacy.com/)

* Create unlimited virtual Visa cards
* Supports custom card spending policies
* Must provide checking account details
* Free

[SpectroCard](https://spectrocard.com/en)

* Create virtual or plastic prepaid Mastercards
* Some fees apply

[TangoCard](https://www.tangocard.com/the-tango-card/)

* Create virtual gift cards for participating merchants
* Free

For folks with a U.S. bank account, the most convenient option seems to be [Privacy.com](https://www.privacy.com). However, by default, they will ask for the login info to your online checking account. For the best privacy, you should ask them to enable your account via ACH integration to ensure that they can't read all of your bank account's activity.

Note: What Privacy.com doesn't tell you is that there are global limits for maximum daily/monthly usage. I'm not sure what the defaults are, but the daily limit seems to default to less than $2,000. If you email support, they'll increase your limits, though your limit will depend upon your usage history.

Also note that you may encounter issues with single-use Privacy.com virtual cards. It turns out this is because a number of merchants actually make multiple charges to your card. Often this is because they make a pre-authorization charge at the time of sale, then cancel it and make the real charge upon shipping the product. I've also run into issues with merchants such as Home Depot where they have multiple delivery services (local vs. shipping carriers) and they make separate card charges for each one even if you created a single order. Also, some services may not accept these virtual cards at all because they get identified as prepaid cards and some merchants consider those to be too risky to process.

Also worth noting is that Privacy.com has a policy against creating multiple cards for the same company, which isn't clear when you're setting up your account. This can result in charges being declined on the Privacy.com end.

![](/assets/images/cy18/cy18q3m9/lopp-6.png){: .align-center}
Screenshot: Jameson Lopp

Finally, if you want even stronger privacy, you can create what equates to a double proxy on your purchases by creating a Privacy.com account that is linked to your LLC bank account. Note that Privacy.com likely won't approve your account immediately because it's geared toward personal checking accounts, but it should be reviewed and approved within a few days of signing up.

### Protect your driver's license data

This one is tricky because DMVs in the U.S. must comply with the [REAL ID Act](https://en.wikipedia.org/wiki/Real_ID_Act), which requires proof of residence. Generally, this means showing bills or financial statements that are mailed to your residence. Of course, if you've followed the above procedures then you shouldn't be receiving any mail at your residence that has your name on it! And unfortunately, commercial remailing addresses (such as the private mailbox services discussed earlier) are kept in databases and you will often be prevented from using them for anything requiring a residential address.

In terms of threat models, the average person probably can't access the DMV data to see what address is on your driver's license, but licensed private investigators have access to tools that often do have this data. There are also likely thousands of government employees who can access this data, and [countless incidents of abuse](https://www.usatoday.com/story/news/nation/2015/03/17/dmv-data-safeguarded/24886267/) have been cataloged over the years. And in fact, [many states](https://www.kxan.com/news/investigations/state-selling-your-identity-despite-laws-against-it/1156465537) make [tens of millions of dollars](https://www.local10.com/news/florida-makes-63m-selling-drivers-info) a year by [selling DMV records](https://www.wivb.com/news/new-york-state-uncovered/kearns-state-dmv-selling-registration-info-a-breech-of-the-publics-trust/1143057553) to third parties. Thus it's important to decide what you need protection against — if you think that someone may go to the trouble of hiring a PI to track you down, you should consider going to the effort of protecting your driver's license.

As mentioned previously, you may find some helpful information on RV forums. It seems like many nomads find a friend nearby to use their address as a registered residence. Of course, this requires that you trust the person with your mail and that there are no issues with their address being associated with your name — you don't want to make your friends a target!

I can't offer specific advice here because it varies from jurisdiction to jurisdiction, but there should be alternative forms that you can submit in order to provide certification of your residence address. This was an area where I needed help from an attorney. If you have sufficient resources then you should consider renting a cheap apartment that you use as your official residence, but don't actually spend much time there.

Regardless of what you end up doing with your driver's license, you should consider having a "passport card" issued if your country offers them. You can carry this card around and use it as proof of identity without exposing your physical address, as your address is [not listed on your U.S. passport](https://getawaytips.azcentral.com/what-information-does-a-us-passport-contain-12178670.html).

### Traveling and crossing borders

If you drive a car, there's a high likelihood that cameras will capture your license plates, scan them, and connect them to your identity. There are [various products](https://www.photoblocker.com/photoshield-cover.html) you can buy to help obscure the plate from cameras, though it's unclear how effective they are.

This is another data leak that you can somewhat protect against by only registering vehicles to an anonymous LLC. For the ultra paranoid, note that many newer vehicles come with built-in GPS tracking in the form of a service such as OnStar. You may wish to take extra steps to disable this hardware or simply not purchase a vehicle equipped with it.

If you want to take vehicle privacy to the extreme, one option may be to not own one at all. This is easy in high-density urban environments, though nearly impossible in rural areas. If you're in a semi-densely populated area then you can create accounts with ridesharing services that are registered with your anonymous LLCs and use them to order cars as needed.

When you cross the borders of nation-states, you are subject to extremely high levels of scrutiny. There are two schools of thought for protecting your privacy here:

1. Carry your data with you, encrypted at rest
A. Pro: convenience
B. Con: no plausible deniability
2. Carry no data, just fresh unencrypted devices
A. Pro: border agents can have access and find nothing
B. Con: must transfer the data by other means

If you don't want to cross borders with data then you can ship an encrypted drive to your destination ahead of time, or you can take a snapshot of your hard drive and upload an encrypted disk image that you download upon reaching your destination. Another option is to keep data on an always-running computer at your home that you then download your files from via SFTP/SCP/a more user-friendly tool such as [Syncthing](https://syncthing.net/). Or you can just run your "real" computer on a private server somewhere and use your laptop as a thin client, using protocols such as RDP and SSH to remote into the server.

Johnathan Corgan [wrote a tool](https://github.com/jmcorgan/ubuntu-remaster) to create fully encrypted live boot Ubuntu images with custom content. It outputs ISO images you can either burn to DVD or make a bootable USB stick out of. You can also run the images in a virtual machine.

For international travelers, you have probably noticed the installation of automated border control machines that scan your passport and take your photo. You probably don't have much choice but to use them when entering a country for which you are not a citizen, but if you are entering your own country you should be able to opt out and avoid having your photo taken.

When traveling you will probably end up staying at hotels. If it's known that you will be in a certain city (such as for a conference) then you should protect yourself from being found at a specific hotel by using a pseudonym. This used to be a lot easier because you could give any name you wanted to a hotel and pay with cash. But these days most hotels are going to want ID and a credit card. JJ Luna recommends that you get around this issue by adding an "authorized user" to one of your existing credit cards in the name of your desired pseudonym. You can make the reservation and payment in that name, and while you will give your real ID to the concierge at check-in, they generally don't care if it matches the reservation. This is a common thing for authors, actors, and musicians — if you are questioned then just state that the reservation is under your professional name rather than your legal name because your credit card was issued under your professional name.

### Voting

Registering to vote is high risk (it creates a public record).

### Crime

Obviously, you shouldn't commit crime; if you get caught it's going to create a set of very public records. However, there's a flip side: becoming a _victim_ of crime can have a similar negative impact upon your privacy due to the public records that are created by the justice system! Good opsec means being aware of the company you keep and staying out of sketchy situations that could cause you to become collateral damage. It also means that if you witness something that makes you call for emergency responders, you should consider doing so from a burner phone and not leaving any identifying information.

### Protect your family

This one's tough. The larger the size of your family that's living at your residence, the larger the attack surface on your privacy. Anyone who can be tied to you needs to have the same level of privacy protection — your privacy is only as strong as the weakest link.

**Marriage**: This creates a public record and ties you to someone. As far as I'm aware there is no requirement for a county-issued marriage license — that form of registration is voluntary. Given that weddings tend to be fairly public events, you should probably get married in a location other than where you reside.

**Children**: Create birth records, health records, and school records. The school records are difficult to work around; the best options seem to be either homeschooling or private school, which are both expensive in different ways.

### Stretch goal: Leave false trails

If you have the resources to do so, consider using misdirection as another tactic. If someone is hunting you down, they probably have limited resources. By purposefully leaking incorrect data, you can leave trails of breadcrumbs that lead to dead ends and frustrate folks who are trying to penetrate your privacy shield.

How might you do this?

* Choose a location that is plausible you may be moving to.
* Tell friends and acquaintances who are never going to actually visit you that this location is where you're moving.
* Change your location data on social media profiles to say you're there.
* Set up cheap accounts in that area that may show up on public reports.

No one has unlimited time; most attackers will give up after spending a certain amount of resources and failing to find you.

### Data cleanup and protection

Depending upon your jurisdiction you may have different options available to you to [ask for personally identifiable information to be removed](https://www.reddit.com/r/privacy/comments/94pimi/remove_your_address_from_background_check_data/) from various services. Though depending upon your desired level of protection this may be a waste of time — once data has been leaked you can never be SURE that it is deleted.

If you take the most extreme route of burning your old life and starting anew then you shouldn't bother with data removal, because leaving your old data out there can serve as misdirection/false trails.

### Limitations

You're not going to be able to hide from government agents by using these tactics — there will be a legal trail of breadcrumbs. Also, given the pervasiveness of networked surveillance cameras this day in age, you can't completely avoid the eyes of Big Brother in urban environments. It's safe to assume that various entities are sucking up these data streams and applying various facial/tattoo/gait recognition algorithms to them.

One weak point certainly becomes the third parties with which you are communicating. There were several points along the way when clueless folks with whom I was interacting leaked data that could be used to correlate the entities I formed with my identity; I plugged the ones that I could and just have to hope that the others went unnoticed. In order to protect against this, don't even open the possibility for someone who is helping you set up a new service to screw up and correlate the new service with your identity. Don't give them your real email address or your real phone number.

You also have to be very careful about reviewing what your service providers are doing. I had several points at which I had to direct a service provider to stop what they were doing. For example, I had a banker send me an authorization form to issue a credit card for my LLC that had my real name on it as the cardholder. That would have been a massive privacy leak to the credit card provider and every merchant with whom I interacted, as they'd now be able to make the association between the LLC and myself.

### Stress-test your setup

The only way to be sure that you have achieved the level of privacy that you desire is to hire experts to try to break through the shields you have erected. Find an experienced private investigator or two and ask them to dig into your life. At this point it will come down to how much digging you are willing to pay for, which you should decide based upon how motivated you expect your attackers may be.

An experienced PI should start by doing various database searches, trying to find trails you may have left behind. If this initial search fails to find any leaks, you may wish to take it a step further and ask them to try to socially engineer your friends and family to see if any of them could be tricked into leaking information about you.

Are you an expert in this field? Can you find holes in my proposal? Can you help me improve my privacy? If so, send an email to opsec@lopp.net and let's chat.

### Educational resources

The following are some educational resources that I used to jump start my research that were not linked in the main body of this guide:

* [Jolly Roger's Security Guide for Beginners](https://www.deepdotweb.com/jolly-rogers-security-guide-for-beginners/)
* [How to Disappear](https://www.amazon.com/How-Disappear-Digital-Footprint-Without/dp/1599219778/)
* [How to Protect Your Financial Privacy and Keep Your Accounts Secure](https://radicalpersonalfinance.com/461-how-to-protect-your-financial-privacy-and-keep-your-accounts-secure-interview-with-justin-carroll-from-the-complete-privacy-and-security-podcast/)
* [JJ Luna — International Privacy Consultant](https://jjluna.com/)
* [Intel Techniques by Michael Bazzell](https://inteltechniques.com/contact.html)
* [How to Vanish](http://www.howtovanish.com/)
