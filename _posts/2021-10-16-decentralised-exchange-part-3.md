---
layout: post
title:  "Decentralised Exchange Part 3: The Constant Product Market Maker Function"
author: surya
categories: [ Advanced ]
image: assets/images/decentralised-exchange-part-1.jpg
---

In our last article, we spoke about how decentralized exchanges like UniSwap can use a mathematical function to provide liquidity - these functions are called Constant Function Market Makers of CFMMs. In this article, we will talk about the Constant Product Market Maker function in depth. But before we get started, here is some context - 

We want a program/robot/machine to provide liquidity (buy or sell whenever we want) in a market. We have a bucket that contains two different Tokens - A and B. In a market, there are a lot of tokens (or assets) but we can segregate all tokens into pairs of two and create buckets for them. We call these buckets Liquidity Pools. We want the program to automatically give a certain number of B tokens to a person who provides a certain number of A tokens to the bucket and vice versa.

We want to ensure that the basic supply-demand rules of economics stand - but instead of a centralized entity determining the price based on the amount of buy or sell orders it gets, we will determine the price using mathematics.

The Constant Product Market Maker Function : 

The formula for Constant Product function is not Ra X Rb but it is actually - 


>`( Ra + Δa - 𝚫a)( Rb + Δb - 𝚫b ) = k [Constant]`

Here:\\
<b>Ra</b> - Number of Tokens of A present in the Liquidity Pool\\
<b>Rb</b> - Number of Tokens of B present in the Liquidity Pool

<b>Δa</b> - Number of Tokens of A the trader has given to the exchange\\
<b>Δb</b> - Number of Tokens of B the trader has given to the exchange

<b>𝚫a</b> - Number of Tokens of A trader received from the exchange\\
<b>𝚫b</b> - Number of Tokens of B trader received from the exchange

Now say a Liquidity Pool has two tokens - `A` and `B`. There are <b>1000 tokens of A</b> and <b>50 tokens of B</b> and I want to swap the <b>5 tokens of B, I have for A</b>.

Putting the values in the above formula,

Ra = 1000,\\
Rb = 50,\\
Δa = 0,\\
Δb = 5,\\
𝚫a = This is the value we have to calculate,\\
𝚫b = 0.

The product of the number of tokens before the transaction is \\
`( 1000 X 50 ) 50,000`.\\
Thus,\\
`k = 50,000`

Substituting the values in the given formula, 

> `( 1000 + 0 -  𝚫a )( 50 + 5 - 0 ) = 50,000`

we get\\
`𝚫a = 90.90` (  remember we got 100 in the last article )

Therefore, for <b>5 tokens of B, I will get 90.9 tokens of A</b> according to this formula.

Now after the transaction, the number of tokens in the Liquidity Pool is\\
`Token A = 909.1`\\
`Token B = 55`

Product of the number of tokens A and B after the transaction in the liquidity Pool = `( 909.1 X 55 ) 50,000`.

Thus, the Product constancy is maintained. 

Although Product constancy is being maintained, there are two issues with the above formula -\\
We are not taking into account the transaction fees associated with swapping tokens in our calculations above. 
 
If we include the transaction fees into our calculations, the formula will look like this - 

> `( Ra + 𝛾Δa - 𝚫a)( Rb + 𝛾Δb - 𝚫b ) = k [Constant]`

where,
`(1 - 𝛾)` is Transaction Fee in percentage terms, charged by the exchange for facilitating your swap.\\
For example, if the transaction fee for each swap on the exchange is <b>0.3%</b>, then `𝛾 = (1 - 0.3) = 0.7`

Assume the transaction fee is <b>0.3%</b>. Now if we add transactions into our calculations for the example we considered above and try to calculate `𝚫a` we get

> `( 1000 + 0 -  𝚫a )( 50 + 0.7*5 - 0 ) = 50,000`

And `𝚫a = 65.42`

Thus if we also consider the transaction fee of <b>0.3%</b>, we will get `65.42 tokens of A` in exchange for `5 tokens of B` in a liquidity pool with `1000 tokens of A and 50 tokens of B`.
The product of the number of tokens of A and B after the transaction now be = `(934.579 X 55) 51,401.845`.

We started with a product of <b>50,000</b> and now we have <b>51,401.845</b> - the product has increased because of the transaction fee. The product in a Liquidity Pool keeps increases as traders transact with the pool and the excess of the product ( 1,401.845 in this case ) is for the <b>liquidity providers</b>.

The above function more or less behaves like the hyperbolic curve `X * Y = K` but with extra considerations for changes in values of X and Y and transaction fees. This means, as the demand for one token in the pool, say A, increases, the number of tokens of B required to swap one token of A (or the price of A relative to that of B) increases.

We did a lot of math, but that is, in general, how a constant function market maker works. There are different variations of what we explained, like Market Makers which use other functions or charge different transaction fees, but the underlying logic is more or less the same. 

If you want to explore more on this topic, please check out this [paper](https://web.stanford.edu/~guillean/papers/constant_function_amms.pdf). The main focus of this paper is the improvement of Oracles, but it gives us a good idea of how Constant Function Market Makers work mathematically.

