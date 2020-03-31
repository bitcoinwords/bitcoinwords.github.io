---
title: "So You Think Bitcoin Mining is Wasteful?"
permalink: "/so-you-think-bitcoin-mining-is-wasteful"

author: danielfrumkin

tags:
  - Daniel Frumkin
  - CY20 Q1
  - Mining
  - Waste
  - Efficiency


excerpt: Daniel compares energy usage of Bitcoin and video games. Posted March 5, 2020.

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [So You Think Bitcoin Mining is Wasteful?](https://medium.com/braiins/so-you-think-bitcoin-mining-is-wasteful-f93cf849a2b9)
### By [Daniel Frumkin](https://medium.com/@danielfrumkin)
### Posted March 5, 2020

![](/assets/images/2020/m3/df1.png)

Much has been said in the past couple of years about the amount of electricity consumed by Bitcoin mining. In fact, negative environmental impact has become one of the go-to talking points for Bitcoin pundits to criticize the digital currency.

However, data provided without context can be _very_ misleading, and this is often the case when journalists write about Bitcoin mining. The total (estimated) energy consumption is indeed quite high, and still growing rapidly as the network hash rate continues to climb. However, the real world impact is frequently misrepresented and misunderstood.

In this article, we’ll be comparing the electricity consumption of Bitcoin mining with all of the world’s videogame consoles and computers. Then we’ll discuss the difference in typical electricity _sources _for the two and their respective environmental impacts.

Let’s begin with an update on the most common of comparisons: Bitcoin vs. countries.

## Bitcoin’s Electricity Consumption Relative to Countries
It became popular around 2017 to compare Bitcoin’s total electricity consumption with that of entire countries. To that end, the University of Cambridge created a handy tool called the [Cambridge Bitcoin Energy Consumption Index](https://www.cbeci.org/) (CBECI) that tracks annualized electricity consumption of Bitcoin mining and makes interesting comparisons to provide some context.

As of November 2019, Bitcoin’s estimated energy consumption is in the same range as Colombia, Venezuela, and Chile.

![](/assets/images/2020/m3/df2.png)

It should be noted, however, that this is still asmall amount compared to the top global electricity consumers: China (5564 TWh per year) and USA (3902 TWh per year).

Now let’s get to the real comparison we want to know about…

## Bitcoin vs. Video Games — Electricity Consumption
First, it’s important to clarify that the following calculations are _estimates_ with potentially high error margins.

Bitcoin mining’s energy consumption varies depending on the total network hash rate and the efficiency of each mining machine being used. For example, producing 100 Eh/s with only the newest and most efficient ASICs would consume substantially less electricity than, say, 100 Eh/s with only ASICs from 2017 and earlier.

With that being said, CBECI has a rather robust [methodology](https://www.cbeci.org/methodology/) for calculating electricity consumption, so we feel comfortable using their estimate of **71.55 TWh per year** as of November 2019.

![](/assets/images/2020/m3/DF3.png)

Global electricity consumption of video game playing is substantially more difficult to estimate. For one, there is a large diversity of devices that are being used for gaming. Consoles such as the PlayStation 4 and Xbox One consume less electricity than high end gaming computers such as a Digital Storm — Velox, so treating all gameplay equally will not be remotely accurate. On top of that, there is the extra complication that gaming consoles and computers don’t run 24/7, unlike Bitcoin mining machines.

Accurately estimating the energy consumption of video game playing around the globe requires consideration of these factors and many others. In fact, it’s well beyond the scope of this simple blog article. Fortunately, a team of researchers at Lawrence Berkeley National Laboratory carried out an incredibly thorough [research study](https://docs.google.com/a/lbl.gov/viewer?a=v&pid=sites&srcid=bGJsLmdvdnxncmVlbmdhbWluZ3xneDo0ZDBmMTI1MTViZTViODY5) on the energy consumption of video game playing in California in 2018. They took into account factors such as the popularity of various gaming systems, their respective efficiencies, typical user behavior, and much more.

You can get a better idea of the thoroughness of their methodology from the graphics below calculating the weighted consumption of a wide selection of gaming systems based on typical user behavior.

![](/assets/images/2020/m3/df4.png)

![](/assets/images/2020/m3/df5.png)

Ultimately, after taking all of this data into account, the research team concluded that the annual consumption of video game play in the state of California for 2016 was approximately _4.1 TWh per year_.

![](/assets/images/2020/m3/df6.png)

Now, our only remaining task is to somehow extrapolate that estimate to cover video game playing for the entire world. (This is a good time to reiterate that these estimates have a high potential error margin.)

First, we need to use the estimate from California to come up with an estimate of the total United States consumption. California’s population is approximately 40 million people, while the whole of the US population is approximately 327 million. If we assume that the behavior of video game players in the rest of the US resembles California, then we can simply multiply California’s 4.1 TWh/y consumption by the ratio 327/40. From that, we get 33.5 TWh/y as the total consumption for the USA.

Next, we’ll use data collected by NewZoo and presented in WePC’s 2019 [Video Game Industry Overview](https://www.wepc.com/news/video-game-statistics/#video-gaming-industry-overview) to further extrapolate for the total energy consumption of video game playing worldwide. In this case, data about revenue is far easier to come by than more nuanced data about the number of gamers around the world and their typical user behaviors. (Note that according to NewZoo, “the revenues are based on consumer spending in each country and exclude hardware sales, tax, business-to-business services, and online gambling and betting revenues.”)

![](/assets/images/2020/m3/df8.png)

Considering that the US accounts for 32% of global gaming revenue, we’re going to make the (admittedly far from perfect) assumption that it also accounts for about 32% of global energy consumption from gaming. In that case, we arrive to a grand total of **104.7 TWh per year consumed by video game play worldwide.**

## So What’s the Takeaway?
Based on our very rough estimates, we found that the worldwide electricity consumption of people playing video games is **46% higher **than the total consumption of Bitcoin mining as of November 2019. However, since these are such imprecise estimates, the bigger takeaway is simply that the two amounts are pretty close to each other. This provides much better context as to the true scope and impact of modern day Bitcoin mining than comparing the annualized energy consumption directly to small countries.

But it’s even more important to understand _where _that energy is coming from. In their June 2019 report, the cryptocurrency investment and research firm CoinShares **estimated that more than 74% of all Bitcoin mining electricity comes from renewable energy sources**. In fact, about 50–60% of the total hash rate comes from Sichuan province in China during its wet season due to the abundance of cheap hydropower there, much of which would otherwise go unused because it is difficult to store and transport. When the wet season is over, many miners move their operations elsewhere to harness cheap thermal and wind power.

The reality is that access to cheap electricity is a necessity in order for miners to compete long-term. With this economic incentive to find the lowest cost electricity possible, many miners have set up shop in rural locations where excess renewable energy is produced. This is simple supply and demand: the supply in these locations is high, and the demand is practically nonexistent since the excess energy is so difficult to store and transport to urban areas where there are consumers.

On the other hand, the US Energy Information Administration estimated that only 23% of the world’s electricity generation came from renewable sources in 2015. Since the majority of video game playing likely occurs in urban areas, it’s reasonable to guess that the same 23% figure is a decent estimate for the amount of renewable energy powering gameplay. In that case, we get the following breakdowns.

![](/assets/images/2020/m3/df9.png)

## Explore More
As Den Held explains in his article, [Proof of Work is Efficient](https://medium.com/@danhedl/pow-is-efficient-aa3d442754d3), “Bitcoin is a super commodity, minted from energy, the fundamental commodity of the universe. PoW transmutes electricity into digital gold.” To put it another way, Bitcoin is like the batteries we don’t yet have, capable of storing excess energy and carrying its value through [time](https://twitter.com/misir_mahmudov/status/1103437467963834369?lang=en).

_Are there any other topics related to Proof of Work and Bitcoin mining that you’d like us to cover? Let us know by leaving a comment below or tweeting @braiins\_sytsems @slush\_pool._

***

{% include signup.md %}