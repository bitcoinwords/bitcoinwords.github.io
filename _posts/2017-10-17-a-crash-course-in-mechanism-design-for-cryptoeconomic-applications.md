---
title: "A Crash Course in Mechanism Design for Cryptoeconomic Applications"
permalink: "/a-crash-course-in-mechanism-design-for-cryptoeconomic-applications"

author: blockchannel

tags:
  - BlockChannel
  - 2017 Q4
  - Mining
  - Economics
  - Money

excerpt: A Crash Course in Mechanism Design for Cryptoeconomic Applications. Posted October 17, 2017.

classes: wide

defaults:
  - scope:
      type: posts
---

{% include donation.md %}

***

# [A Crash Course in Mechanism Design for Cryptoeconomic Applications](https://medium.com/blockchannel/a-crash-course-in-mechanism-design-for-cryptoeconomic-applications-a9f06ab6a976)
### By BlockChannel
### Posted October 17, 2017

### **Understanding the Basic Fundamentals of “Cryptoeconomics”**

![](/assets/images/2017/m10/a-crash-course-in-mechanism-design-for-cryptoeconomic-applications1.png)

**Note: This post was written by**[**Alex Evans**](https://medium.com/@ahe4nc)**, and was edited by**[**Steven McKie**](https://medium.com/@McKie)**for**[**BlockChannel**](https://medium.com/@BlockChannel)

If you’ve spent any amount of time in the cryptocurrency world in 2017, you’ve probably come across the term “**cryptoeconomics**.” If not, you can perhaps be excused for missing it among some of the more entertaining linguistic creations in the cryptocurrency space. [This post](https://thecontrol.co/cryptoeconomics-101-e5c883e9a8ff) by Nick Tomaino and [this video](https://www.youtube.com/watch?v=pKqdjaH1dRo) by Vitalik Buterin should get you up to speed.

In short, cryptoeconomics describes the combination of cryptography and economic incentives to design robust decentralized protocols and applications. According to this strain of thinking, Bitcoin succeeded where other decentralized protocols failed, not because of Proof-of-Work, the idea of decentralized cash, or even fault-tolerant consensus, but because it incorporated cryptoeconomics at the core of its consensus protocol. The grand vision of cryptoeconomics is therefore to extrapolate this success to embed cryptoeconomic incentives into everything — transactions, computation, storage, prediction, power.

Blockchains enable us to enforce scarcity and facilitate value transfer in areas where that would otherwise be impossible and, therefore, radically expand the range of problems to which economic incentives can successfully be applied. Viewed through this prism, cryptoeconomic systems are fundamentally new ways of incentivizing human behavior. And their potential is massive.

While this may be easy to see in theory, actually designing economic incentives is hard. In fact, there is an entire sub-discipline of economics dedicated to studying how to design protocols that incentivize rational actors to behave in socially desirable ways. This is called mechanism design. Though much ink has been spilt on the topic of cryptoeconomics in the last few months, we have little evidence that formal methods from mechanism design are being incorporated in the development of most new blockchain protocols (with some notable exceptions that will be discussed).

To put it mildly, this represents a missed opportunity. Others have stated it more assertively:

![](/assets/images/2017/m10/a-crash-course-in-mechanism-design-for-cryptoeconomic-applications2.png)

The purpose of this post is to introduce the basic concepts of mechanism design, and give a taste for their usefulness in the cryptocurrency world. If you’re working on a blockchain protocol or application, this will ideally provide you with some introductory resources for accessing the literature of mechanism design. My hope is that you walk away from this post, 1) convinced that mechanism design is extremely important to building robust decentralized systems and 2) equipped with the basic resources to start learning how to use tools from mechanism design in your own work. Please note that I am not expert on either crypto or mechanism design and would love feedback on this post from those of you who are.

To start, I provide a brief description of the key concepts and definitions from mechanism design. The goal is to introduce the basic vernacular of mechanism design in the most accessible way possible, in order to make the subsequent discussion of cryptocurrency applications comprehensible. This is not meant to provide a formal introduction to mechanism design. That is better accomplished by reviewing one or more of the following:

> This chapter
>
> by Vincent Conitzer;
>
> This article
>
> by Matthew Jackson and
>
> his two-part course
>
> with collaborators; Chapter 7 from
>
> this introductory text
>
> on Game Theory by Fundenberg and Tirole

Note that these are just a few resources that I found useful to getting introduced to the subject. Since mechanism design is an established area of economics research, I’m sure there are many others. If you know of any additional materials that you would recommend, please list these in the comment section.

**What is Mechanism Design?**

A useful caricature is to think of mechanism design like inverse game theory. In game theory, we take the game as a given and analyze its outcomes according to players’ utilities. In mechanism design we start by defining desirable outcomes and work backwards to create a game that incentivizes players towards those outcomes. Another (similarly caricatured) way of looking at it is to think of game theory as the positive side and mechanism design as the normative side of the same coin.
 
For example, you may be designing an auction where the goal is to allocate a good to the participant with the highest utility for it. Assuming everyone has *some* utility for the good, participants have an incentive to lie. So how do you design a game that incentivizes everyone to report their utilities truthfully? Should you implement open or sealed, ascending or descending bids? Should the winner pay the highest announced price or some other price? Equivalently, when designing a voting process that always choses the candidate that all voters prefer over all other candidates, should you chose winners based on plurality or majority? should there be one or multiple rounds of voting? Should voters submit a single choice or preference ordering? These are typical questions in mechanism design.

**Some Definitions**

Formally, a mechanism includes a finite set of **players** and a set of potential **social decisions**. Think of a set of voters and the group of potential candidates that can be chosen by the society. Players possess **private information**, also referred to as **signals** or **types**. Each individual’s type can represent her preferences — such as her preference for candidate A over B or her valuation for a good being sold in an auction — but the type can also be used to encode other types of private information — for example, she alone may know whether the good being sold is of high or low quality. We may also have a **common prior**, which is a probability distribution over types. Think of this in the context of poker: you may not know the players’ hands, but you know the probability of each hand occurring in a deck of 52 cards. Since the ‘optimal’ decision will inevitably depend on individuals’ types, we also typically define a **decision rule**, which maps types to social decisions.

Individuals’ utilities will thus be a function of their reported type (i.e. what they tell the type/preference aggregator, which may not be true), their actual type, and the output of the decision rule. Furthermore, we frequently include **transfer functions**, where a transferrable good (conveniently like a token) is used to incentivize players, usually by capturing the externalities that their actions impose on others. We can thus envision the **social choice function,** which maps reported types to outcomes as having segregated monetary and non-monetary components. This is what is being talked about when you see references to ‘quasi-linear’ utilities, i.e. preferences are linear in the monetary/transfer component.

In practice, as a designer you get to control the choice of mechanism, but not the players or their types. You may see these ‘given’ elements referred to as the **setting**. Adding a **mechanism** turns this Bayesian setting into a game (also referred to as a ‘game form’). Formally, a mechanism is a pair of message/strategy spaces and a function which maps messages/strategies to resulting social decisions and transfers. The mechanism can be deterministic, always outputting the same decision and payouts for a given, or can be probabilistic/randomized according to some rule.

> The central task in mechanism design is to
>
> specify a mechanism that incentivizes rational agents to behave in certain ways, based upon their private information, that lead to socially desired outcomes
>
> .

Generally, a mechanism is said to ‘implement’ a social choice function if, in equilibrium, the mapping from types to outcomes is the same as the mapping that would be chosen by the social choice function (you might therefore see mechanism design referred as “implementation theory”). We can require this to be an implementation in **dominant strategies** (where this holds for the agent regardless of the strategies of other agents) or simply an implementation in **Bayes-Nash equilibrium** (where no player has profitable deviations based on their beliefs about other players’ types and the strategies of those payers). The former obviously being a much stronger (and hence more limiting) assumption.

**The Revelation Principle**

One of the foundational results in mechanism design is the **Revelation Principle**. In very broad strokes this states that any social choice function that can be implemented by any arbitrary mechanism, can also be implemented by a truthful, direct-revelation mechanism with the same equilibrium outcome. Here, a **direct-revelation mechanism** is one where agents simply declare their types to the mechanism, leading to a decision and set of transfers. A direct-revelation mechanism is truthful if truthfully reporting preferences is a dominant strategy (though, in the general case, we can require this to just be true in a Bayes-Nash equilibrium). You will find such mechanisms referred to as **truthful**, **incentive compatible**, or **strategy-proof**. The revelation principle has exceptionally powerful implications. In short, if you’re able to prove something to be true for these mechanisms, you have proved it to be true of all mechanisms! To see why this is true, imagine a random untruthful mechanism with an interface layer, which takes your preferences and strategically interacts with the mechanism to maximize your payout (like a fiduciary). Then you wouldn’t want to misreport your true preferences to the interface or you would get suboptimal payout. In essence, you don’t have to lie, because the mechanism lies for you! The observation that there is no loss in generality by focusing on just truthful, direct-revelation mechanisms is the key result that makes mechanism design work. Otherwise, you would have to prove theorems to be true for the massive set of indirect or untruthful mechanisms, which would make the subject practically useless.

**Mechanism Design as Constrained Optimization**

Now that we’ve defined some basic terms, what are the types of outcomes we can use mechanism design to enforce? What is a ‘good’ mechanism and how do we make sure we select it? You can think of this is as an optimization problem, where you are trying to maximize an **objective function** (such as your revenue), under a set of constraints. It makes sense to introduce some of the more common constraints you will come across.

**Incentive compatibility** is perhaps the most frequent constraint you will encounter. Other common constraints include **individual rationality**, where no agent loses by participating in the mechanism and **efficiency**, where the sum of individual utilities are maximized (not including monetary transfers). **Budget balance** constrains the mechanism to transfers that net to zero across individuals, while weak budget balance (also referred to as feasibility) simply requires that the mechanism not pay out more than it receives. A key problem that arises in the theory of mechanism design is that constraints, such that budget balance, efficiency, and individual rationality are often impossible to simultaneously satisfy under incentive compatibility and several impossibility theorems have been proven. Generally, the features of mechanisms can be said to hold for agents **ex-post**(regardless of the types of the agents), **ex-interim**(given any type for the agent and in expectations of the types of other agents), or **ex-ante** (i.e. in expectation over their own and other agents’ types). Returning to our poker analogy, you can think of what claims you can make before any cards are drawn from the deck (ex-ante), when you know your own hand (ex-interim), and when all hands are revealed (ex-post).

Imposing constraints will typically leave you with a set of several mechanisms to choose from, converting mechanism design to a (constrained) outcome optimization problem. For instance, in an auction you may be looking for an incentive compatible, individually rational mechanism that maximizes revenue. You may need your mechanisms to be efficiently computable, or to satisfy more complicated social goals such as equitable distribution of value. Those are just some examples and the list is practically infinite. As we’ll see in some of the examples, formally stating the goal of the mechanism can itself be one of the more difficult problems in mechanism design.

**Vickrey-Clarke-Groves Mechanisms**

A set of very powerful mechanism that you will encounter frequently are known as **Vickrey-Clarke-Groves** mechanisms. To explain these, let’s first think about an auction where a single good is being sold. Perhaps, the most obvious design would be to have all participants write down the price they would pay on piece of paper. After the bids are revealed, the player who bid highest price will receive the good and pay the price she bid. This would obviously not be incentive-compatible, as any player bidding her true value for the good would receive a utility of zero. A far better mechanism for incentive compatibility would be to allocate the good to the player with the highest bid, but have her only pay the value of the next highest bid. This is called a Vickrey auction. Each player in this setting has an incentive to bid her exact valuation for the good.

A generalization of the Vickrey auction, is the pivotal mechanism (also called the Clarke mechanism or “the” VCG mechanism, though VCG can sometimes refer to the more general class of mechanisms). The mechanism works as follows. For every individual, we run the mechanism without her and choose the outcome that maximizes the utility of all other players given their reported types. Then we include the individual and run the mechanism again. The latter is the outcome chosen. Each player pays (or collects) the difference between the sum of utilities for the other players in the two cases. Effectively, this payment is equivalent to the individual’s social cost or benefit. Since the individual has no way of affecting the sum of utilities that occurs without her, she is effectively trying to maximize the sum of her own and everyone else’s utility. But this is exactly the same as maximizing total social utility! Aligning incentives in this way ensures not just incentive-compatibility, but also guarantees efficiency. It is also easy to find ex-post individually rational and weakly budget balanced versions of this mechanism with some pretty mild additional assumptions. We can also add arbitrary terms to the payout that the individual can’t influence (such as giving each individual some constant amount regardless of the outcome), without changing the underlying incentives. This more general set of mechanisms are called **Groves Schemes**, which are always dominant strategy incentive-compatible. They also happen to be to be the only efficient mechanisms where truth is a dominant strategy.

Though Groves Schemes are clearly a powerful class of mechanisms, they are highly susceptible to collusion between actors. We will see later how this can be highly problematic in a cryptoeconomic setting.

**Straightforward Applications**

Now that we have assembled the basic ingredients from mechanism design, let’s look at some potential applications to the cryptocurrency world. I start with by mentioning (a non-exhaustive set) of direct applications, before we dive into more involved areas of research.

One of most obvious and direct applications of mechanism design is token sales. Auction theory is by far the most developed application space for mechanism design. Mechanisms for auctions have also been studied extensively in computer science, in no small part due to the fact that large technology companies like eBay and Google derive most of their revenues from online auctions. If you’re planning a token sale this is where you can find true ‘off-the-shelf’ solutions from studying mechanism design (though we will encounter some of the failures of traditional auction theory in a crypto setting later on). You can find some arguments about competing token sale models, [here](http://vitalik.ca/general/2017/06/09/sales.html), [here](https://medium.com/@Vlad_Zamfir/a-safe-token-sale-mechanism-8d73c430ddd1), and [here](http://continuations.com/post/161776542685/optimal-token-sales). Many of these can trivially be formulated in terms of traditional auction theory.

Prediction markets, which have recently seen several decentralized variants, are another example of an area where traditional mechanism design research has a lot to say. Here, the objective might be to specify incentive compatible mechanisms that extract the true beliefs of agents about the probability of different events in order to make accurate predictions. As with auctions, the theory has tools to deal with more sophisticated assumptions, such as situations where agents behave strategically and/or may seek to manipulate the beliefs of other agents in order to alter market prices in their favor. There are also some more awkward problems, such the fact that agents’ private information isn’t always easily convertible to discrete probabilities. For example, say I have a friend on the coaching staff for Golden State who told me that Steph Curry injured his ankle. It’s not clear how a piece of private information like this can be converted to a precise probability for whether Golden State will win their next game (P.S., I harbor no ill will for Steph Curry or his ankle). As with auctions, a special set of problems arises when considering a decentralized version of these markets. I refer you to projects such [Augur](https://augur.net/) or [Gnosis](https://gnosis.pm/), though more theoretical treatment of the topic of decentralized prediction markets can be found [here](http://www.econinfosec.org/archive/weis2014/papers/Clark-WEIS2014.pdf) and [here](http://bitcoinhivemind.com/papers/truthcoin-whitepaper.pdf).

**Analyzing Namecoin**

[This paper](http://randomwalker.info/publications/namespaces.pdf) by Carlsten et al is a great example of how mechanism design can be used when reasoning about decentralized systems. The authors argue that while Namecoin solves a critical technical problem (effectively squaring [Zooko’s triangle](https://en.wikipedia.org/wiki/Zooko%2527s_triangle)), the system runs into a number of thorny economic challenges. The article shows that barely 0.02% of registered domains belonged to non-squatters and displayed non-trivial content at the time of writing, while the secondary market for domains was practically nonexistent. I believe this reinforces the point that as a protocol creator, you simply cannot neglect the design of proper user incentives, regardless of technical merits of your project.
 
What makes Namecoin suitable for mechanism design is the intrinsic scarcity of human-meaningful domains, which necessitates a proper resource-allocation process. The authors therefore deploy mechanism design thinking to explain Namecoin’s failures and reason about the goals of decentralized namespaces under different user utility models. This demonstrates one of the trickiest challenges of mechanism design in practice: specifying the model of user utilities and deriving clear design objectives. For instance, if we assume agents to have fixed, independent preferences for each name, then a Vickrey auction will result in an efficient outcome (as discussed in the introduction). If, more realistically, we assume diminishing marginal utilities for names (e.g. John Doe’s utility for the domain “JohnDoe” is significantly lower after he has already received the “John_Doe” domain), then perhaps similar results can be achieved through the [priority mechanism](https://web.stanford.edu/~niederle/HouseAllocation.pdf). However, when incorporating time-varying preferences, the mechanism design problem becomes too complex to even clearly articulate what the goals of the system should be.

The analysis also looks at the effects of different choices in the design space: How strong should the individual’s control over a name be? How should the primary market allocate names? How should the system redistribute revenue from name sales? Methodically laying out the design space in this manner and analyzing economic tradeoffs is an indispensable tool in designing any blockchain application. Beyond serving as a case study for how mechanism design can be used to analyze decentralized systems, the analysis also reveals several practical paths forward for improving Namecoin: higher fees to deter squatters, deploying auctions/algorithmic pricing schemes to narrow the gap between the price for a name and its true market value, and a mechanism for users to recuperate investment by returning unused names to the primary market.

**Open Challenges: Ethereum Foundation**

Perhaps the most active research about applications of mechanism design in the cryptocurrency world is the work of the Ethereum foundation. To get a sense, I again refer to you to Vitalik’s video linked to in the introduction, as well as [this deck](http://fc17.ifca.ai/wtsc/Vitalik%2520Malta.pdf). Of particular importance are the security models that he proposes and assumptions used, so it makes sense to briefly review these here for completeness.

A common model used in traditional fault tolerance research is the honest majority model, which assumes that at least 51% of participants are fundamentally honest. Vitalik and company argue that this can be a problematic assumption. As such, researchers should instead reason about security under specific assumptions about 1) The level of coordination between participants; 2) The budget of the attacker (the maximum amount the attacker would have to pay) and 3) The cost of the attacker (the actual cost incurred by the attacker). Correspondingly we can think of several different security models, outside of honest majorities. We can then look at fault tolerance and cryptoeconomic security margins (i.e. the economic cost of violating certain protocol guarantees) under the assumptions of each model.

Uncoordinated majority models assume protocol participants make independent choices and no actor controls more than a given percentage of the network (here participants are self-interested and not necessarily honest). Coordinated choice models on the other hand assume that most or all actors are colluding through some agent or coalition of agents, though we can sometimes assume free entry from non-colluding actors. The bribing attacker model is one where actors make independent decisions, but an attacker exists who can incentivize other actors to make certain choices through conditional bribes. For illustrative purposes, take a look at the Shellingcoin example Vitalik uses in both presentations. In short, in a model where payments are only made to actors who vote with the majority, an attacker can guarantee a fixed payment higher than that of voting with the current consensus to those who deviate from the consensus and end up in the minority. The attacker can thus effectively corrupt the game with a high budget, but an actual cost of zero, as none all the bribed defectors end up in the majority. Bitcoin and other proof-of-work protocols are, at least in theory, susceptible to this type of attack (though someone would have to credibly demonstrate a massive budget).

**Introducing Cooperative Game Theory**

As a supplement, I also found [this story](https://blog.ethereum.org/2016/12/06/history-casper-chapter-1/) from Vlad Zamfir to be especially interesting. It chronicles the evolution of thinking in Proof-of-Stake research that led the team to arrive at its current set of cryptoeconomic methodologies as well as the security deposit and penalty mechanism in the current version of Casper. I especially recommend the fourth and fifth parts of the series where he discusses cooperative game theory. Not to spoil the story, but the punchline (to me) is the observation that “blockchain architecture is mechanism design for oligopolistic markets.” Regardless of your thinking on the topic, it is hard to argue that centralization in both cryptocurrency holdings and mining power is not a realistic assumption in practice. What makes this incredibly challenging from a modelling standpoint is that most mechanism design work you’ll find addresses settings from noncooperative game theory. Indicatively, some of the most widely studied mechanisms (such as the Groves Mechanism introduced above), collapse under assumptions of collusion between agents.

Thankfully, cooperative/coalitional game theory is a well-developed field and you can find many good introductions online. Generally, the goal is to analyze what types of coalitions can be created, what the payouts are under each (through a function called the characteristic function), and how the coalition should divide its payout to achieve goals such as stability. Often, we think about the grand coalition where all agents participate (e.g. everyone mining on the longest consensus chain) and think about distributing the payoffs under a transfer scheme/solution concept called the **Shapley Value**, where each individual receives her marginal contribution to the coalition. We could also often think about the “core” set of imputations (individually rational and efficient payments), where coalitions of agents don’t have an incentive to deviate and analyze stability based on whether this set is empty vs non-empty, unique vs not. Following Vitalik et al, we can think of incentives in two broad categories. One being payments, such as mining rewards (which jive well with our idea of transfers) and the other being privileges, which allow their holders to extract rents, such as transaction fees.

**Smart Contact Applications**

Beyond analyzing the consensus layer, Vitalik’s presentation discusses direct applications of mechanism design to smart contracts. For example, the Vickrey auction that we had so many nice things to say about can suffer from challenges in a crypto setting. For example, users could submit multiple bids and selectively open the one that guarantee the highest payout. You could then may respond by suggesting a deposit to deter such actors. But then you would have to specify a deposit size relative to the bid size in the mechanism, which can destroy the key features of the sealed-bid, second-price auction. The challenge Vitalik identifies is that mechanism design often relies on a trusted intermediary to ensure correctness and privacy for players. A blockchain can guarantee correctness, but not privacy.

There are also typically more factors to specify in the cryptoeconomic setting than in traditional applications of mechanism design. In centralized settings, we often think of a central agent running the mechanism in a way that maximizes revenue subject to certain constraints. This makes things much simpler to analyze. In a decentralized setting, however, we may have to define an algorithmic agent to “run” the mechanism and have to reason carefully about the behavior of that agent in the mechanism as well as the implications for the monetary policy of the protocol. For example, if we expect the mechanism to violate budget balance, should the agent redistribute revenue to players? Should excess currency collected be removed from circulation? Should the agent be able to mint new currency when making transfers to players? These questions require close attention, as decisions can introduce undesirable kinks into the incentives of players (e.g. maximizing the amount to be redistributed can become a non-trivial component of their utility).

**Final Thoughts**

While mechanism design has become a staple in computer science research, few entrepreneurs and developers appear to be thoughtfully applying this type of thinking to designing blockchain protocols. Even fewer academic economists have started to seriously study the game theoretic properties of blockchain protocols.

That said, I am optimistic that as the enormous opportunities presented by cryptoeconomics become clearer, these disjoint communities will start to converge. In the interim, I hope that you found this article to be useful in introducing some of the tools and open questions that definite the possibilities of cryptoeconomic mechanism design. For feedback, comments, and discussion, feel free to get in touch at [alexander.evans@lowes.com](mailto:alexander.evans@lowes.com) (Lowe’s Ventures) or in the comment section.

**Want more perspective? Here’s a recent post by Coindesk.com also explaining “cryptoeconomics”:**

[**Making Sense of Cryptoeconomics - CoinDesk**
*In this CoinDesk opinion piece, Stark argues that the term "cryptoeconomics" is widely misunderstood, despite being a…*www.coindesk.com](https://www.coindesk.com/making-sense-cryptoeconomics/)

***

{% include signup.md %}
