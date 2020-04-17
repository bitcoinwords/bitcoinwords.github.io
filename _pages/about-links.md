---
permalink: /about-links/
title: "About Links"
defaults:
  # _pages
  - scope:
      path: "About Links"
      type: pages
    values:
      layout: single
      author_profile: true
---

[![Links logo](/assets/images/links-logo.png)](https://bitcoinwords.github.io/links/docs/planet.news.html)
{: .half}

The goal of **[Links](https://bitcoinwords.github.io/links/docs/planet.news.html)** is to deliver you the absolute best commentary on Bitcoin. Our sources are carefully curated and constantly updated as we uncover more signal. 

## <i class="fas fa-rss"></i> RSS and <i class="fas fa-bolt"></i> Lightning Network
This project is the product of RSS and Lightning Network. 

RSS (Really Simple Syndication) is a protocol that enables the distribution of blogs and pods. If you're subscribed to a pod in iTunes or Spotify, RSS is the magic that pulls in new episodes.

This also applies to blogs. Some people read blogs with "feed readers". A popular one is [@feedly](https://twitter.com/feedly). You can grab the url from almost any blog or webpage, plug it in a feed reader, and it will use RSS to pull in new articles to your feed reader. This allows you to have the new articles delivered to you, rather than going to each web page.

The Links project takes RSS from carefully curated Bitcoin blogs and wraps them in Bitcoin Lightning Network. All the blog posts that are pulled into Links are paywalled with Lightning Network invoices.

The million satoshi question is this... **Will people pay to read curated content?**

We'll be trying to figure it out. 

### Enabling Technologies for Links

* [GitHub](https://github.com/) Pages is the hosting and git powerhouse
* [Planet Pluto](https://github.com/feedreader) is the static page builder that does the RSS magic. Shout out to [Gerald Bauer](https://github.com/geraldb) for this amazing code.
* [Lightning Feed Wrapper](https://lnpay.co/paywall/xml-feeds) by [LNPay.co](https://lnpay.co/) is the all star that takes the RSS feeds and wraps them in LIghtning Network. Major props to [Tim K](https://twitter.com/BootstrapBandit) on being reckless enough to build this!