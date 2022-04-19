---
layout: post
title: "Does your product idea really need blockchain though?"
author: surya
categories: [Advanced]
image: assets/images/need-cover.jpg
---
In the early days of my blockchain learning, I flirted with the idea of building decentralized Uber, Facebook — basically building every popular site or app on blockchain. As I dived deeper into blockchain, I realized blockchain solves a few problems very well — but there is a catch, blockchain solves only few problems very well. Remaining are better off being solved in traditional ways. So how do we know which problems can be solved using blockchain?
Before answering that question, let’s talk about the ‘Blockchain Trilemma’. First coined by Vitalik Buterin, the founder of Ethereum, the blockchain trilemma explains how blockchain developers have to compromise among Security, Scalability or Decentralization. Traditional applications are made Scalable and Secure at the cost of decentralization. Whereas current day public blockchains are Secure and Decentralized at the cost of Scalability. Let us take an example of an application we run on our phone like, say, Instagram. Instagram is pretty fast (faster than Ethereum for sure, although fair comparison is a little difficult) and anyone who wants to use Instagram can just download it from play store or Mac store, create an account in a few seconds and start using it. Most important aspects of Instagram data and code are stored in a server far from our home and we access them using the internet.
Following is an extremely oversimplified version of how it works :

![need-1]({{ site.baseurl }}/assets/images/Need-1.png)

As you can see, the control of the application lies in a server where as users can access the data and the logic of the application to the extent they are entitled. Whenever a user wants to use the application, all he has to do is send a request to the server and he will get what he wants, and all developers at instagram have to do is make the server secure.
In contrast to traditional models, a public blockchain like Ethereum looks something like the following :

![need-1]({{ site.baseurl }}/assets/images/Need-2.png)

In this model, each and every node has all the data and logic needed to run the application by themselves on their machine. And every node tries to connect to other nodes (or peers) in the network to update the state of the application (Data or Logic or both).
In the first case, the application was completely centralized with one central server having the control over all the data and logic. In the second case, the control of the application is decentralized among all the participants of the network. But this type of decentralization comes at a cost. Since we cannot compromise on security, most popular public blockchain networks compromise on scalability. Ethereum is nearly not as fast as traditional payments systems and it is much more difficult to onboard a user onto Ethereum as a node than getting a credit card (If we consider our user to be technologically agnostic, which majority of users are).

Ethereum community is trying to solve the scaling problem by moving to proof of work and exploring various other solutions like rollups, but in the context of our article, before deciding you need to use blockchain, your idea or solution might need the following requirements:
* You need to store data : If our application does not have to store data, we don’t have to worry about a lot of things, including using blockchain.
* Multiple Users should be able to add data : If you are not able to write data, it does not make any sense for you to host the data and logic of the application in your laptop, same goes for every other user on the network.
* Users on the network do not trust each other or they gain to benefit by exploiting each other:
If all the users in the network trust each other, you don’t really have to use blockchain. If Alice paid me 10 Bitcoin and every user on the bitcoin network trusts that Alice is not a malicious user, then we don’t really have to check whether Alice has 10 Bitcoin in the first place to pay you or not. In the real world, you cannot trust people on the internet to play fair, especially when they stand to economically benefit from scamming the network.
* Users on the network cannot trust a Centralized third party :
This is probably the most important factor that distinguishes Web2 application from Web3. Not all applications need the centralized third party to be trustworthy — most of the time, if the centralized third party is not trustworthy, they stand to lose more than any individual user of the application.

Reviewing the four points above,
If your application needs to store data, and multiple (usually all) the users of the network should be able to add data to the network and you do not believe in a centralized third party to store your data or application logic, each and every node has to store the data and application logic with themselves in their machine and when a user in the network adds new data to the network, it has to be propagated to all users the other in the network.
When users in the network are not trust-worthy or the network is ‘trustless’, every user has to secure the data in his machine to prevent attacks by others.
If you take a second look at the diagram of how blockchain works above, you will find that this is exactly the case.

Until next time!