---
layout: post
title:  "Getting Started with Ethereum"
author: surya
categories: [ Advanced ]
image: assets/images/intro-to-eth.jpeg
featured: true
---

One of the major selling points of Bitcoin when it was launched, apart from the fact that it was completely decentralized, was that it is <u>Programmable Money</u>. I can create a transaction in the Bitcoin network to pay someone at a point in time in the future and it will be executed without fail. But the level of programming we can do in the Bitcoin network is limited.

Before we talk about the limitations of Bitcoin, we have to discuss the <u><b>Turing Completeness</b></u> of a programming language. A programming language is considered to be <u><b>Turing Complete</b></u> if we can run any program in a machine using this language given enough time and memory. Mainstream languages like JavaScript and Python are Turing complete but the Bitcoin blockchain is not Turing complete. In simple terms, we cannot write a for loop in the Bitcoin blockchain. In more simple terms, Bitcoin is not entirely programmable. There are several limitations to what you can program Bitcoin to do.

Now the immediate question arises, why is Bitcoin not Turing Complete? Surely a genius who could come up with a way to decentralize and program money could make it Turing complete. The reason Bitcoin is not Turing complete is because if Bitcoin is Turing complete, its complexity increases and an increase in complexity implies a less secure network. As you have probably guessed by now, Ethereum was created to solve this problem. 

In the Ethereum blockchain, code can be written in a programming language called <u><b>Solidity</b></u>. Solidity is Turing complete. From the above discussion, you might infer that Ethereum is not as safe as the blockchain network as Solidity is Turing complete. This is not entirely true. Complexity in a truly complete programming language arises not because of the language, but because the programmer might not be able to write a code that is free of any vulnerabilities. So as long as you write robust code, you have nothing to worry about and it turns out, writing robust code is not easy. To explain the ramifications of not writing robust code, let us talk about the story of a decentralized organization created on Ethereum blockchain called <u><b>The DAO</b></u>.

The DAO was created in May 2016. A few members of the Ethereum community announced that they would create a completely decentralized Venture Capital firm on the Ethereum blockchain. Venture Capital firms, for those of you who are not familiar with the term, fund and mentor startups or other young and growing companies. Anyone on the Ethereum blockchain could send Ethereum’s cryptocurrency - Ether to The DAO and in return, they would be given DAO tokens. The DAO platform would allow anyone to pitch an idea and the DAO token holders would vote on which idea gets funding. All this would be done by programs written in Solidity running on the Ethereum blockchain without any human intervention (except, of course, the voting part)

The DAO was an unexpected success and it was able to raise 12.7M ether - around $150 million at that time ( and it is a whopping $40 billion at the time this article is being written ). This was the largest crowdfunding campaign in history. I wish I could stop the story here and say “Yeap, that is all, happy ending” but I am afraid it is not. A hacker found a vulnerability in the code of The DAO and stole 3.6 million Ethereum - approximately $70 million at that time ( $11 billion at the time of writing ) from The DAO.

And this, my dear friends, <b>might</b> be one of the reasons why the Bitcoin blockchain was not made Turing complete. But just because The DAO was a failure does not mean Ethereum is not safe. That is like hiring a web developer to build a website for you in python and blaming python when the website gets hacked. It's not python’s fault guys, it's the web developers. However, the takeaway from this story is that, when money is involved, people have to be extra careful while writing code and completely understand what they are working on. This also happens to be the motivation for starting this series of blog articles on how the Ethereum blockchain works. Since we already wrote a series on the Bitcoin blockchain, and most of the core blockchain concepts are the same for Ethereum and Bitcoin, we shall start from where we left in the Bitcoin series. Check out our series on [Bitcoin blockchain here](https://blockchainiseasy.github.io/about-blockchain-is-easy/).

There is a long way to go before we complete understand ethereum blockchain completely, but we think the best place to get started is 

* [Smart Contracts](https://blockchainiseasy.github.io/smart-contracts/)

One of the most improtant features of ethereum blockchain is to be able to obtain data from outside the blockchain network. This can be achieved using 

* [Oracles](https://blockchainiseasy.github.io/oracles/)

I think its time we dive deeper into ethereum and understand

* [Node and Web3](https://blockchainiseasy.github.io/Web3-and-node/)

Now, we are ready to understand what all the fuss is about NFTs

* [Decoding an NFT](https://blockchainiseasy.github.io/decoding-an-nft/)

If you want to read more about <b>The DAO</b>, check out this [article](https://medium.com/swlh/the-story-of-the-dao-its-history-and-consequences-71e6a8a551ee). 
