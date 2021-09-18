---
layout: post
title:  "Maker's DAI"
author: surya
categories: [ Advanced ]
image: assets/images/maker-dai.jpeg
---

Bitcoin and subsequent cryptocurrencies were created to decentralize ‘money’ and to be used in day-to-day lives to purchase goods. But most of the cryptocurrencies today are used exclusively for speculation and investment because of the volatility in their prices. Now imagine the value of the US Dollar changed as much as bitcoin - the cost of a coffee is $1 now and $2 five seconds later! The world would plunge into chaos.

The reason any country’s currency has value is that it is considered a ‘legal tender’ by the government of that country. For example, there is a legal obligation for every citizen of the US to attach the same value to $1 and anyone who does not do so can be sent to prison. 

Most of our problems will be solved if we create a cryptocurrency whose value is the same as that of the US Dollar. But the issue is, if I create a cryptocurrency, it will not be considered legal tender since I am not the government. 

The solution to this sounds simple at first glance. I create a cryptocurrency and give 1 token to everyone who gives me $1 and store it in a vault. I take out $1 from the vault and give it to anyone who gives me 1 token of the cryptocurrency I created. But there is a problem with such an arrangement. You have to trust me to keep your dollars safe and give it back to you whenever you need it in exchange for the cryptocurrency I created - I am no different than a normal bank. The system is neither decentralized nor trustless.

So how can we make a stable coin decentralized? Enter Maker’s DAI. Maker is a decentralized organization that created something called <u><b>The Maker Protocol</b></u>. The Maker Protocol makes sure that the value of 1 DAI is equal to 1 USD. It does so by incentivizing the participants in its network to keep the price of the DAI stable and close to USD.

But how do we get the assets to back the value of DAI and without a central authority to control and be responsible for all the assets? This is where the ingenuity of Maker Protocol comes to play. DAI gets its assets to back its value by giving out loans.

<u>How DAI’s Loans work:</u>

Before we talk about DAI loans, we need to know that the loans given out by DAI protocol are controlled by code and this code cannot be changed. And this code always assumes 1 DAI = 1 USD.

Now, If I want some DAI, I will have to deposit an asset as collateral in DAI’s vaults. There are only specific assets that Maker Protocol supports currently. Let us say I deposited 0.13 ether (etherium is supported as collateral by Maker Protocol) in the vault. After depositing the ether in my vault, I am entitled to take a loan in DAI. Like all loans, there is an interest that has to be paid in order to take this loan. This interest is called <u>Stability Fee</u>.

<u>Couple of Definitions:</u>

* Collateral Ratio = (Total Value of Collateral locked in Vault) / Debt 
* Liquidation Ratio = Minimum Permissible value of Collateral Ratio (currently 1.5)

At the time of writing, the cost of 0.13 ether is $450. Now if I use the 0.13 eth I deposited in my vault to take a loan of 200 DAI, my current collateral ratio will be equal to 450 (current value of collateral in Dollars locked in the vault) / 200 (since the maker Protocol’s code always assumed 1 DAI  = 1 Dollar)
= 2.25

If tomorrow, the value of my 0.13 eth falls to $290, my Collateral ratio will be equal to 1.45 which is less than the Liquidity Ratio of 1.5. In this case, the Liquidity Ratio has been breached. When this happens the Maker Protocol <u>Liquidates</u> the vault.

Liquidation: When Liquidation occurs, Maker Protocol basically immediately buys the collateral in my vault. You do not lose your collateral in the vault when it is liquidated, but you get the current price of the vault and you are charged a <u>Liquidation Penalty Fee</u> for letting your vault Liquidate.

Amount you receive after Liquidation = Value of collateral - (Debt + Stability Fee + Liquidation Penalty Fee)

So essentially, you get back your money after deducting the Debt you borrowed, the interest you have to pay for the loan taken so far (stability fee), and the penalty for letting your vault liquidate (Liquidation Penalty Fee)

Now this collateral which has been liquidated is immediately auctioned off for interested participants on the network to buy.

Phew! That was a lot of information. Here is a summary - 
1. You need to put some collateral in a vault to be able to borrow DAI as a loan
2. The interest you pay for that loan is the ‘Stability Fees’
3. You can happily borrow DAI from your vault as long as the Collateral Ratio of your vault is greater than the liquidation ratio. If the Collateral Ratio falls below the Liquidation Ratio, Liquidation is triggered
4. In Liquidation, Maker Protocol auctions off the contents of your vault and you have to pay a penalty called Liquidity penalty Ratio for letting your vault liquidate.

Now you might be wondering why we started talking about decentralized loans when we want to know how we can create a decentralized Stable Coin. We are almost there.
I already mentioned that the program which manages the loans in Maker Protocol always assumes 1 DAI = 1 USD.

Now, if in the market, the price of 1 DAI is less than the price of 1 Dollar, it is cheaper to pay back your loan
For example, if 1 DAI =  $0.9
I can buy 200 DAI which I borrowed before in the market for just $180 and pay back my loan. Since when I issued the loan, I was given 1 DAI for every Dollar, I just made $20 profit! The participants are incentivised to pay back their loans. This DAI which is paid back to the Maker Protocol is burned (destroyed) to reduce the total supply of DAI which increases the price of DAI.

If the price of 1 DAI is greater than the price of 1 Dollar, we can create free money by locking in collateral and getting more DAI. If 1 DAI  = $1.1, I can essentially lock 0.13 etherium in my contract, take a loan of 200 DAI and sell it for $220 and make a profit of $20. This will increase the supply of DAI and reduce the price of DAI eventually.

Now, this might look like a weak system dependent on a lot of external factors, but it works. Never underestimate the power of incentive!

Following is the price chart of DAI since its inception.

![maker-dai-graph]({{ site.baseurl }}/assets/images/maker-dai-graph.jpeg)

Few noteworthy features of Maker’s DAI - 
1. You do not need a credit score to take loans, all you need is collateral
2. Everyone is charged the same Stability and Liquidity Fee
3. Maker does not lend more than the collateral it has - making it less risky.

Now there is a lot more to DAI than what I explained in this article. People who are already familiar with DAI might complain that I never mention MKR token or explain how auctions work, etc, but that was not the intention of this article. I tried to simplify things so that it will be easier for you to form a mental model of how the Protocol Works. 

If you want to know more about Maker DAO and DAI check out the following links! (Please note that DAO is Decentralised Autonomous Organisation and DAI is the name of the stable coin in this context)

* [MakerDAO docs](https://docs.makerdao.com/)
* [Awesome MakerDAO](https://awesome.makerdao.com/)
