---
layout: post
title:  "Digital Ledger"
author: surya
categories: [ Basics ]
image: assets/images/article-4.jpg
---

If Alice wanted to transfer 10,000 bucks to Bob, she would go to a bank and ask the clerk to perform a transaction. The clerk will record this transaction in his ledger, remove 10,000 bucks from Alice’s account and add 10,000 bucks to Bob’s account. The ledger is not distributed since the clerk in the bank is the only person who has it. Now if Bob wants to transfer these 10,000 bucks to Charlie, he has to go to the bank again, ask the clerk who records the transaction in the ledger.

![Distributed-Ledger1]({{ site.baseurl }}/assets/images/Distributed-Ledger1.png)

The whole point of Blockchain technology is to remove the need for this clerk (the middleman). We do not want a third party to control and keep an account of all our transactions. Imagine, instead of the clerk in the bank maintaining a ledger, Alice, Bob and Charlie have their ledgers on a network. Whenever one of them performs a transaction, each of them updates their ledger. Now in a world where everyone is honest, trustworthy, and updates their ledger like a good boy, this would be the beginning and the end of the blockchain. But, we can't trust everyone in the world. Blockchain is built in a way that we do not have to trust anyone else in the network.
I'll leave this thought hanging. We will finish this line of thought in the next article.

All of us at some point heard about how Blockchain is a form of a <u>distributed ledger</u>. Blockchain, as the name suggests, is a chain of blocks and each block is a ledger with a bunch of transactions that are slightly complicated than <u><b>Alice paid Bob 10,000 bucks</b></u>. Each block has a reference of the previous block with it and points to the next block in the blockchain.

Given below is an oversimplified version of blockchain, but it helps us get the basic understanding.

![Distributed-Ledger2]({{ site.baseurl }}/assets/images/Distributed-Ledger2.png)

[Here](https://www.blockchain.com/btc/block/0000000000000000000d20bbd16fb5ff61d7824a4e9f3807db79a918690617fc) is a link to an actual block on the Bitcoin blockhain.

It would be useful to know that there are two types of people on the Blockchain network:
1. People who want to transact, pay or receive crypto currency and
2. Miners. 

The first type of participants broadcast messages such as 'Alice paid Bob 20', 'Bob paid Charlie 100' and so on and so forth.
The second type of participants, the Miners. They are responsible in <u><b>mining</b></u> the above transactions into a block. What does that mean? That means, in essence, three things.
1. Get last blocks hash
2. Continously store all latest transactions after the last block
3. Combine the above two along with <u>count</u> and hash the result.

As and when the hash turns out to have the required number of zeroes in the beginning, that entire information is stored in the next block. This block is appended and now becomes the latest block. This miner now tells every other miner,
> I have successfully <u>mined</u> all the transactions so far and have created the next block. Please stop trying to mine this block, add this block to your ledger and move on to the next!
Everyone else on the network is notified of this as well and add the next block to their chain. This is what makes the ledger on the blockchain. A copy of each block with everyone.

Lastly, one might ask, what if two miners simultaneously mine a block. This is a perfectly valid situation. In such a scenario, the longest chain is considered as the right chain. Let's take the following scenario. Block A and Block B are mined at the same time after the latest block. Some participants in the network find block A and start mining the next block on top of block A and similarly for block B. Now a miner with block A in its chain mines another block before any other miner with block B in their chain. These other miners notice that this chain is longer. They now <u>orphan</u> block B and use chain with block A as their main chain.

![Distributed-Ledger3]({{ site.baseurl }}/assets/images/Distributed-Ledger3.png)

Let's now connect everything we've learnt so far and move onto our final article, the Bitcoin blockchain!