---
layout: post
title:  "Decentralised Exchange Part 1: Centralised Exchanges"
author: surya
categories: [ Advanced ]
image: assets/images/decentralised-exchange-part-1.jpg
---

To understand how decentralized exchanges work, we have to know how regular a.k.a centralized exchanges work. That is what we shall discuss in this article.

When I was ten years old, I used to watch the news at 9 am every day with my dad. At the end of the news, the reporter would quickly give the <u>Stock Market summary</u> for the day - “National Stock Exchange’s benchmark index Nifty 50 rose by X points,” and I would not understand a single word in the sentence. 

Growing up, I understood that finance literature tends to make everything sound complicated - the stock exchange is a place that connects buyers with sellers. A guy comes to the exchanges and says, <u>‘I want to buy an apple for Rs. 10,’</u> and another guy comes to the exchange and says, <u>‘I want to sell an apple for Rs. 10,’</u> and the exchange connects those two people. The same thing happens to stocks, but the exchanges are a bit more sophisticated - they maintain something called <u>‘The Order Book.’</u> In the order book, the exchange keeps a list of <u>‘orders.’</u> Alice will come to the stock exchange and place an order “I want to buy Stocks of Company X, and I am willing to buy the stock as long as the price is below $10”. This order is recorded in the Order Book. Now, after some time, if Bob comes to the exchange and places an order, “I want to sell the stock of Company X for $9.5”. Now the exchange will <u>‘match’</u> the orders of Alice and Bob, take money from Alice, give it to Bob and take stocks from Bob and give it to Alice. 

Stock exchanges also have another characteristic - Price Discovery. Price Discovery is another fancy term for how valuable the people on the stock exchange think the stock is and how much they are willing to pay for it. Say, I am in a fruit market, and I want to buy apples, but I don't know how costly or cheap apples are, and I don't like (nobody likes) being cheated by the apple seller. 

The way I see it, there are two ways I can know I am paying a fair price - 

1. I have to find out which farm the apples were grown on, how much the total cost of cultivation of apples was, and how much the farmer sold the apples to the seller for, how much charge the seller incurs to run his business, and compare the cost at every single step and find out if the seller is giving me a reasonable price for these apples given their quality.
OR
2. I can go around the market and ask people who bought apples what price they bought apples for and buy for a similar price.

Any rational human would probably do the latter - so does a stock exchange. The price of a stock displayed is the price of its most recent transaction. If Alice, in the above case, bought the stock of Company X for $9.5, and that is the most recent transaction on the exchange, that will be the price of the stock of Company X on that exchange. The cost of stock in exchanges is determined by supply and demand. If there is more demand for a stock of Company X, people will offer more money to own it, and Alice might have to offer more than $10 for the stock - basic economics, I will throw in the diagram as well because we all love pictures.

![decentralised-exchange-part-1-2]({{ site.baseurl }}/assets/images/Decentralised_Exchange_2.png)

Now is probably a good time to talk about another fancy term in finance literature - <b>‘Liquidity’</b> of exchanges. Liquidity is the ease with which something can be bought or sold in the exchange. Imagine you want to sell a stock as soon as possible. If there are many people placing orders on an exchange, it is more likely that you can find someone willing to buy the stock at your price right now. Thus the exchange is liquid. Liquidity is one of the significant incentives for people to use exchanges in the first place. To provide liquidity to exchange all the time, there are people called “Market Makers” - their people are willing to buy or sell any stock, thereby creating liquidity to the market. If you want to sell a stock you are holding, no matter the price, Market Maker is the person you want to go to. He will give you a quote, “I will buy this stock for $X,” and he will find someone to sell the same stock for more than $X, thereby making money. The bottom line is, he will give you a buy or sell price for every stock on the exchange (ideally) so that you don’t come to the exchange and leave without finding a counterparty.

Now imagine you want to buy a cryptocurrency and for ease of explanation, let us assume you want to buy 0.01 ether using the money in your bank account. We can either find someone who has 0.01 ether and pay him the price he wants or go to a crypto exchange ( in real life, it is usually a mobile app ) that finds someone for you. Most of the mobile exchange apps we use to buy cryptocurrency like Binance, etc, work in a model similar to what is explained above. They try to connect sellers who have crypto to buyers who want to buy and charge a fee for doing so. 

At the time of writing of this article, 0.01 ether costs $33. Now say you downloaded a crypto exchange mobile app, created an account, verified your identity (yeap, in most cases, we need to provide proof of your identity to transact on these exchanges), and placed a buy order for 0.01 ether. The app connects you to a person on an exchange who wants to sell 0.01 ether. He will give you his bank account details, and once you transfer $33 to his account, he will transfer 0.01 eth on the Ethereum blockchain to your Ethereum address ( If you are not sure what blockchain addresses are, please check out our article on [Digital Signatures](https://blockchainiseasy.github.io/digital-signature/) ).

Note - Most exchanges create a crypto wallet for you to which the seller transfers cryptocurrency - in this case, Ether. For understanding exchanges, you don't need to know what a wallet is, but if you want to read about wallets in blockchain, check out this [article](https://www.investopedia.com/terms/b/blockchain-wallet.asp).

![decentralised-exchange-part-1-1]({{ site.baseurl }}/assets/images/Decentralised_Exchange_1.png)

If you want to buy crypto using the money you have in your bank, you HAVE to find someone to do the above transaction with you, and the best way of finding that person is an exchange (centralized). This is a centralized exchange - the centralized entity is the app that we used to find people to buy/sell crypto, and there is no ‘decentralized’ way of doing this as of now. Decentralized exchanges exist on blockchains (the most popular ones are on the Ethereum blockchain), and they help you exchange one cryptocurrency for another. Once you hop onto the blockchain, that is when the magic starts.

We will talk about how decentralized crypto exchanges work on the Ethereum blockchain by taking UniSwap as an example in our next article.


