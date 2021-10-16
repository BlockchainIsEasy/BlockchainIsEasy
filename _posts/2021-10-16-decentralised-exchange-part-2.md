---
layout: post
title:  "Decentralised Exchange : Part 2 Uniswap"
author: surya
categories: [ Advanced ]
image: assets/images/decentralised-exchange-part-1.jpg
---

In the previous article, we established that an exchange is a place where buyers meet sellers - and looking at the prices at which assets are bought and sold, we can decide the 'Market Price' (Price the market gives an asset as a result of demand and supply) of an asset. 

Since we have to spent an entire article talking about centralized exchanges, let us talk about how decentralized exchange is different from centralized:
1. Conventional exchanges are considered centralized because the rules of exchange are dictated and enforced by a government-appointed entity. The fact that UniSwap is a decentralized exchange does not mean that no entity governs the rules of operation. In UniSwap, all governance-related decisions are decided by the process of voting. 
2. While conventional exchanges are only up for a specific time on weekdays, Decentralized exchanges like UniSwap are up and running 24/7. 
3. Strictly speaking, the core function of UniSwap is not that of an <b>"exchange,"</b> but that of a Market Maker (we briefly spoke about Market Makers in the last article). While conventional exchanges follow the 'Order Book' style, decentralized exchanges like UniSwap use 'Automated Marker maker' or 'Constant Function Market Maker' - More about this later in this article. 
4. In UniSwap, we are not really 'buying' or 'selling,' but we are essentially swapping one token for another. Now you know how UniSwap got its name.

What is the difference between buying or selling and swapping? Say you are in the New York Stock Exchange and want to sell my 10 Apple stocks and buy Tesla stocks. At the time of writing this article, 1 Apple stock is worth $146. I am selling my ten stocks which will give me $1460. 1 Tesla stock costs $763. I can buy 1 Tesla stock on the exchange and will be left with $679. However, suppose the New York Stock exchange had worked like a Decentralised exchange. In that case, I could have given the exchange 10 Apple stocks and gotten 1.913 stocks of Tesla. We would have swapped one stock for another.

![decentralised-exchange-part-2-1]({{ site.baseurl }}/assets/images/Decentralised_Exchange_2_1.png)

I like to visualize Automated Market Maker (AMM) as a robot with a bucket with lots of coins. We all can go to AMM and give him a token; it will throw the token we gave into the bucket and give you a certain quantity of the tokens you want in exchange. Now, if I go to UniSwap AMM with one eth and ask for bitcoin, how will UniSwap decide how much bitcoin to give in exchange for one eth? 

<h3>Liquidity Pools:</h3>

The liquidity pool is the bucket that our AMM robot has. In UniSwap, a liquidity Pool or a ‘bucket’ can have only two tokens. You give one token to the pool, and the AMM decides the amount of the other token you get. These tokens can be only a specific type of tokens called ERC-20 tokens (We shall write an article soon on types of tokens in Ethereum). For now, it is enough to know that ERC-20 is a type of token that can be created and transacted on the Ethereum blockchain. This also means UniSwap works only on the Ethereum blockchain and on tokens functional in it. 

<h3>Constant Function Market Maker:</h3>

Constant Function Market Makers are the Market Makers who use a mathematical function to determine how much of a token to give in exchange for another token. 

Now that we have got those definitions out of the way, let us talk about how UniSwap works. UniSwap uses mathematics to determine how to swap tokens. 

Now, we want to make sure that the basic supply-demand rules of economics stand - instead of a centralized entity determining the price based on the amount of buy or sell orders it gets, we will determine the price using maths. So if we have a Liquidity Pool of two tokens where one token is in high demand compared to another, we want the traders to pay a high price for the token in high demand. 

For the rest of this article, we shall try and explain the mathematics behind the swaps - 

<h3>The Simple Explanation: </h3>

Say there is a Liquidity Pool with two tokens A and B. I go to a Liquidity Pool with Tokens A and B, and we want to swap some A for B. The AMM calculates how many Tokens of B to give me using the following formula - 

```Ra X Rb = k (Constant)```

Here,
* Ra  - Is the Number of Tokens of A present in the Liquidity Pool.
* Rb - Is the Number of Tokens of B present in the Liquidity Pool
* k is a constant value

The formula essentially states that whatever happens, the product of the number of tokens of A and the number of tokens of B in a liquidity pool should remain constant. 

Let us assume that the current Liquidity Pool has 1000 tokens of A and 50 tokens of B, and we want to swap five tokens of B for A. We go to the Liquidity pool and give it five tokens of B. The AMM will determine how many tokens of A we are supposed to get by satisfying one condition. The product of the number of tokens A and B in the liquidity pool should remain constant.

Since the liquidity pool has 1000 tokens of A and 50 tokens of B, we have (1000 / 50) 20 tokens of A, so for five tokens of B, we will get 5 X 20 = 100 tokens of A.

After our transaction, the number of Tokens of A and B in the liquidity pool of A and B will change.
Now, Since 100 tokens of A are given in exchange for five tokens of B
* ```Ra = 900``` and
* ```Rb = 55```
Next time someone comes to our exchange to swap, we will be giving ```(900 / 55) 16.36 tokens of A``` for ```each token of B``` instead of 20.

We can draw a graph of how the swap price of both the tokens changed because of our transaction:

![decentralised-exchange-part-2-2]({{ site.baseurl }}/assets/images/Decentralised_Exchange_2_2.png)

If you can see in the above graph, if the demand for a token A increases, the amount of token A will decrease in the Liquidity pool because more traders will be willing to swap token B for token A. As the number of tokens of A reduces in the pool, token A becomes more costly; that is, you have to pay more tokens of B to get tokens of A - thus, the basic supply-demand rules of economics are honored.
That is all. That is the infamous Constant Function Market Maker Function (note that in the above case, the mathematical function we use is a product function, so our Constant Function Market Maker is Constant Product Market Maker) which is used to provide liquidity and enable you to swap one token on Ethereum blockchain with another. However, what we explained above is an extremely simplified version of the function for ease of understanding. You can stop here if you are not really into math, but if you are curious to dive deep, do read on - 

The fact that you are still reading this means you are not satisfied with the explanation above. You know math, and you probably pointed out the deadly flaw above - or you are just curious about what the rest of the article says!

In the above case:
The product of the number of tokens before the transaction 

```Ra X Rb = (1000 X 50) 50,000```.

But after the transaction

```Ra X Rb = (900 X 55) 49,500```.

What just happened? Why is the product of the constant product function not constant?
It turns out; the constant product function is slightly more complicated than ```Ra X Rb```. If you have an appetite for mathematics, we will try to explain how constant product market makers work in our next article. Stay Tuned!

Also, UniSwap is releasing a new version - V3 with modifications on top of its previous versions and some improvements to what we discussed in this article. We did not go in-depth into V3 since the intent of this article is to help you get a feel of how decentralized exchanges work and not explain UniSwap end to end. If you want to read more about the new version of UniSwap, check out this [article](https://uniswap.org/blog/uniswap-v3/).

