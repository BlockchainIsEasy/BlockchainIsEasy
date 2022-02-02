---
layout: post
title: "Shortcomings with Ethereum and Bitcoin Blockchains"
author: surya
categories: [Advanced]
image: assets/images/shortcomings-cover.jpg
---

After finishing my article series on Introduction to DeFi, I wanted to go invest some of my money in the infamous decentralized liquidity pools on ethereum blockchain to earn interest on my deposits. I wanted to invest $100 in a liquidity pool ( Yeap, I am poor ) and the transaction fee I was asked to pay for depositing this $100 was a mind boggling $300.

Now decentralized protocols were made to bring finance to the common person and reduce the number of agents in the middle. However, a transaction fee of 3X on a $100 deposit hardly seems favorable for the common person. The transaction fee in Ethereum blockchain does not scale well with the amount of the ether transferred in the transaction. If I wanted to invest $10,000 in the liquidity pool, chances are the transaction fee would still be around $300. So everyone cannot reap the benefits of decentralization in its current scenario.

Not just the high transaction fees, ethereum and bitcoin suffer from other major issues as well.

<b>Proof of Work -</b>

If you know about bitcoin, you probably know about the enormous amount of energy bitcoin mining is consuming. According to the Cambridge Center for Alternative Finance (CCAF), Bitcoin currently ( as of May, 2021 ) consumes around 110 Terawatt Hours per year — 0.55% of global electricity production, or roughly equivalent to the annual energy draw of small countries like Malaysia or Sweden because of the enormous number of CPU cycles required for its consensus mechanism - Proof of Work. It is a heavy price to keep a protocol decentralized and trustless.

Following are snippets taken from [digiconmist](https://digiconomist.net/bitcoin-energy-consumption/)

![shortcomings-1]({{ site.baseurl }}/assets/images/shortcomings-1.png)
![shortcomings-2]({{ site.baseurl }}/assets/images/shortcomings-2.png)
![shortcomings-3]({{ site.baseurl }}/assets/images/shortcomings-3.png)

Most people would argue this energy could be allocated for much better things, and I agree.
The problem is not just the amount of energy being used but the number of people in this world who have access to such amounts of energy to mine cryptocurrency. Personally, I cannot afford to mine bitcoin in my laptop anymore. Since a lot of energy and computing power is required, the majority of mining pools in bitcoin are controlled by a few, rich players.

Following Pie chart has been borrowed from [this](https://www.blockchain.com/charts/pools) source.

![shortcomings-4]({{ site.baseurl }}/assets/images/shortcomings-4.png)

As you can see in the above chart, top 4-5 private players can collude to launch a 51% attack on the bitcoin network since they have the required computing power and compromise the security of the network. (Although it is not as easy, it is theoretically possible)


<b>Transaction Time and Number of Transactions per Second -</b>

Not just high transaction fees, but the ethereum blockchain network is suffering from high transaction time and low transaction throughput as well.
The basic requirement for a solution to solve a problem is for it to provide a better solution than whatever currently exists. So if crypto currencies like bitcoin or ethereum want to replace mainstream payments, they have to be at least as fast as the current centralized payment networks.
VisaNet is a 50 year old electronic payments system that fares far better than the top two cryptocurrencies of the world. VisaNet is not decentralized.

![shortcomings-5]({{ site.baseurl }}/assets/images/shortcomings-5.png)

Clearly, bitcoin and ethereum in their current state cannot compete with the existing mechanism for payments.

<b> Huge Size of Nodes - </b>

The amount of space taken by a single ethereum node is currently 690Gb. It is not feasible to run a single node on personal laptops or on mobile. There are a few work arounds for this issue currently where instead of running a full node on your machine, you can store just the Merkel trees of the blocks but these work arounds do not allow a node to participate fully in the ecosystem.

However, these issues are not new - they are as old as blockchain itself and these issues do not impede the progress of blockchain as a technology. As I write this blog, Ethereum is working on deploying Proof of Stake - an alternate consensus mechanism to proof of work which will consume much less energy and allow everyone to validate ( validation is proof of stake counterpart of mining ). In Eth 2.0, Ethereum blockchain will be sharded to reduce the amount of space required to hold blockchain node in devices and increase the number of transactions per second.
In our upcoming series, we will talk about the Scaling Ethereum chain and how the Ethereum community is planning to tackle these problems in detail. Lots of exciting stuff is coming up, stay tuned!