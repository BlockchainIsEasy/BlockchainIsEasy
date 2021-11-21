---
layout: post
title:  "Node and Web3"
author: airesh
categories: [ Advanced ]
image: assets/images/web3-and-node.jpg
---

While learning Blockchain and this entire ecosystem in general, I had many questions that I didn't find the answers to very quickly. With so many terms and jargon being used, it was challenging to wrap my head around some concepts even when it was very easy for others. In this article, I aim to explain some of those terms. Diving right in!

Let's start by painting a picture!
A decentralized system is, as the term suggests, decentralized - not centralized. Our digital ledger article(attach the link) discussed how each node carries a ledger copy. That means every node on this Blockchain maintains the same data. So let's say Alice's laptop has this copy of the chain. Now Bob wants to create a [Crypto Kitty](https://www.cryptokitties.co/) baby. Somewhere on this chain lies the function call which Bob has to execute to generate this Kitty. 

You can imagine the Blockchain smart contracts to be a huge ground of Tetris Blocks.

![NodeAndWeb3-1]({{ site.baseurl }}/assets/images/Blockchain_playground.png)

The image above can be considered to be a smart contract that lies in the address given. Each block here is a function and has a particular structure(determined by parameters and function name). Given the address of this smart contract and the structure(commonly called an ABI), Bob can call the function and execute it.

![NodeAndWeb3-2]({{ site.baseurl }}/assets/images/Included_blocks.png)

Bob broadcasts his function execution as a transaction to all the nodes present on the chain. The miner nodes now receive this transaction and try to mine the next block with this transaction in it. Alice here may be one of two types of nodes. Alice might try to mine this block and obtain some rewards(cryptocurrency) as an incentive. Or, she might try to participate in this Blockchain with a copy of this entire chain on her laptop(which is also equally important). So, in a nutshell:
1. The transaction goes out to all nodes.
2. The miner nodes get to work.
3. The <b>mined</b> block gets broadcast to all the nodes again.
4. The non-miner nodes record this block. The miner nodes record this block as well and now try to start mining the next block.

Now you might be thinking of the consequences of this. Every transaction done by every person on this Blockchain is recorded. This complete copy is also present in every node on the Blockchain. So as you can figure, one must be very cautious in deciding what will be stored in the Blockchain. Moreover, one cannot create a function that takes up a lot of computing resources. It could potentially block off the entire functioning of the Blockchain network. Hence there is a limit to each of these values.

<h2>Data Storage on a smart contract</h2>
A smart contract has these two primary things, states/variables and functions. States store values and functions do operations on these values. Smart contracts store variables and their values in a key-value format. There are exactly 2^256 unique keys available in a smart contract. Each storing 32 bytes (2^5). Hence a contract can store (2^256 * 2^5) bytes which are 2^261 bytes. There may be other problems, such as [hash collision](https://freemanlaw.com/hash-collisions-explained/) before one can reach this storage level.

<h2>Importance of efficient code on a smart contract</h2>
Executing a function on the Ethereum blockchain or any other blockchain with smart contracts mean that you have to use someone else's computing resources. As you very well know, nothing in this world comes for free 😄. Whenever you want to execute a transaction on the Blockchain, you need to pay a small transaction fee. A miner's job is to mine the transaction sent into a given block. Bob will pay the miner a small miners fee to do so. But if the transaction executes a function that may run in an infinite loop, Bob is completely wasting the miners' resources. Hence there are two main concepts introduced here: <b>Gas limit</b> and <b>Gas fees</b>.

<h2>Gas limit, Gas fees</h2>
To run a car, you need gas. You pay the gas station X dollars to get Y amount of gas that runs your vehicle for a certain distance. Similarly, when you execute a transaction, you tell the miner you are willing to pay X Gas fees to complete Y amount of computations. Two cases can occur here. The limit you set is more than what was required or lesser.
When the limit is more, the remaining amount is refunded back into your account. But if the limit is less, the transaction is reverted, and you still lose all the money you spent.
E.g., to execute a simple transaction of sending money from Alice to Bob requires a minimum of 21,000 Gas units. If Alice decides to pay 200 gwei([Giga Wei](https://en.wikipedia.org/wiki/Wei_Dai)), the miners' fee spent for this transaction is 21,000 * 200 = 4,200,000 gwei or 0.0042 ETH(each gwei is equal to 0.000000001 ETH/10^-9 ETH). So if Alice wants to pay Bob 1 ETH, she has to spend 1.0042 ETH. 0.0042 ETH here is the total gas price or, in common terms, the miners' fee.

<h2>How does Bob send the transaction?</h2>
We've been talking about how Bob sends a transaction to the Ethereum smart contract. But how does Bob go about doing it? 
In comes Web3! 

![NodeAndWeb3-3]({{ site.baseurl }}/assets/images/web3_api.jpg)
Web3 is the gateway through which one interacts with the nodes. You might have heard of Metamask. Metamask provides the users with an interface to interact with the Ethereum nodes. Querying data, executing functions, sending Ether to other accounts, Metamask can do all this and more. Metamask also acts as a wallet account through which you can store your cryptocurrencies. Like Metamask, there are innumerable apps available to help everyday users like us interact with the Blockchain nodes.

<h2>Conclusion</h2>
To summarise, we have learned how:
1. Nodes are responsible for picking transactions and mining them into blocks.
2. Nodes store all the data on the Blockchain. All the data is open to everyone to verify. This is what gives Blockchain the security we all know.
3. We have seen what a miner's fee is and why each transaction on the Blockchain requires it.
4. We also saw what Web3 is and how it helps us interact with the nodes of the Blockchain.

A few links for further reading:
1. [Ethereum EVM illustrated](https://takenobu-hs.github.io/downloads/ethereum_evm_illustrated.pdf)
2. [Gas and Fees](https://ethereum.org/en/developers/docs/gas/)
3. [Accounts, Transactions, Gas, and Block Gas Limits in Ethereum](https://hudsonjameson.com/2017-06-27-accounts-transactions-gas-ethereum/)
4. [Contract internal storage size](https://ethereum.stackexchange.com/questions/986/can-a-contracts-internal-storage-keep-increasing-forever)
5. [Estimating Smart Contract costs](https://medium.com/scrappy-squirrels/estimating-smart-contract-costs-f65acf818c26)

