---
layout: post
title: "Ethereum Conceptual Model"
author: surya
categories: [Advanced]
image: assets/images/ethereum-conceptual-model-cover.jpg
---

Conceptual models are probably the most important aspect of learning. One of the reasons people have a hard time understanding Blockchain and distributed ledger protocols is probably because their Conceptual models are very different from traditional Centralised systems we are familiar with so far.
Before we dive into the conceptual model of Ethereum, let us talk a little abut our mental models of normal computers. Traditional computers were devices/machines on our table. You can make changes to a computer — like adding files, changing backgrounds, etc (change the state of your computer, say) as long as you are near your computer and have required access. If your computer is connected to the internet, you will be able to access information on another computer (server) across the world, and add information to the server if the server allows you to do so.
So following is a very high level model of how you can transfer money using the internet :
So using the internet, if Alice wanted to send money to Bob, Alice has to use her computer to send a request to the bank’s server (computer) to move money from her account to Bob’s account. The bank will perform a bunch of checks on its server (computer) and if Alice passes all those checks, the bank will move the money from Alice’s account to Bob’s account and send a message to Bob’s computer (or say, mobile) that money has been added to his account. Note that when money is being moved from Alice’s account to Bob’s account the information is being changed in the bank’s server (computer).


![conceptualmodel-1]({{ site.baseurl }}/assets/images/ethereum-conceptual-model-1.png)

Following is the conceptual model of how Ethereum works on a high level :

![conceptualmodel-2]({{ site.baseurl }}/assets/images/ethereum-conceptual-model-2.png)

Ethereum is essentially one big distributed computer. You do not have to send a request to a bank server to create a transaction, because in this case, your own computer is the bank’s server — more or less. So if Alice wants to send ether to Bob, all she has to do is create a transaction using Ethereum client. This Ethereum client sends a transaction to the Ethereum Virtual Machine which is present in her computer and if the transaction is valid, the state of Ethereum is changed. This change is state is communicated to all peers connected to Alice’s computer so they also can update their (instances of) Ethereum to the latest state.
So that is more or less the conceptual model of Ethereum.

Until next time!
