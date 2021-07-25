---
layout: post
title:  "Digital Ledger"
author: surya
categories: [ Basics ]
image: assets/images/article-4.jpg
---

If Alice wanted to transfer 10,000 bucks to Bob, she would go to a bank and ask the clerk to perform a transaction. The clerk will record this transaction in his ledger, remove 10,000 bucks from Alice’s account and add 10,000 bucks to Bob’s account. The ledger is not distributed since the clerk in the bank is the person who has it. Now if Bob wants to transfer these 10,000 bucks to Charlie, he has to go to the bank again, ask the clerk, record the transaction in the ledger. 

---
Image comes here

---

The whole point of Blockchain technology is to remove the need for this clerk (the middleman). We do not want a third party to control and keep an account of all our transactions. Imagine instead of the clerk in the bank maintaining a ledger, Alice, Bob and Charlie have their own ledgers on a network and whenever one of them performs a transaction, each of them updates their ledger. Now in a world where everyone is honest and trustworthy and updates their ledger like a good boy, this would be the beginning and the end of blockchain, but we don't trust everyone in the world and we don't need to have to. Blockchain was created in such a way that we do not have to trust anyone else in the network - i'll leave this thought hanging, we will finish this line of thought in the next article

All of us at some point heard about how blockchain is a form of ‘distributed ledger’ and that is true, Block chain is literally a chain of blocks and each block is a ledger with a bunch of transactions which are slightly complicated that “Alice paid Bob 10,000 bucks”. Each block has a reference of the previous block with it and points to the next block in the blockchain.

Given below is an oversimplified version of blockchain, but it helps us get the basic understanding

---
Image comes here

---

Before we dive into blockchain and how it works, it would be useful to know that there are two types of people on the Blockchain network - People who want to transact, pay or receive crypto currency and miners. Miners have one job. Whenever someone broadcasts a transaction like ‘Alice paid Bob 20 bucks’ (new transaction, say)the miner will collect all the transactions from the previous blog till now and he/she will append the block to the latest block, in the figure above, block 5 and new block - block 6 is created in the blockchain. Once the miner has created this block, it is published in the blockchain and everyone else in the network will add this new block to the copy of the block chains they have with them

Now there are a lot of miners on a blockchain network and each of them can create a lock and there is a possibility that two miners create two blocks from the same parent, and this might go on so how do we know which chain is valid? The answer is very simple, we consider the longest chain in the network, all the other branches to the main chain will be discarded.

---
Image comes here

---

Now bitcoin mining is not as easy as just taking a bunch of transactions, creating a block and adding it to the chain. We will explore what it takes to add a block, and why so much energy is being consumed in ‘mining’ bitcoin in our next article.
