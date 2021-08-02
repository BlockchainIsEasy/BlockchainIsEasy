---
layout: post
title:  "Digital Signatures"
author: surya
categories: [ Basics ]
image: assets/images/article-2.jpg
---
Sign for a check, pin for credit and debit cards, OTP for internet banking - how does it work in blockchain? Well, it turns out there is something called ‘the digital signature’ for blockchain which is arguably more safe than OTPs or physical signatures or pins. But before we get into Digital Signatures we need to talk about how we identify someone who wants to transact on blockchain - in other words, if blockchain is a global bank, how do we create an account in our bank and send and receive money?

When we want to open an account in a bank, we have to fill in forms, give the proof for our address, citizenship and what not and finally after a week or two of tedious work we get our bank account created. When it comes to blockchain, it turns out, creating an account is as easy as typing a few commands. Anyone with a computer can generate something called ‘The Private key’. When it comes to a bank, you create an account, and then attach a password to it, but in the case of blockchain, we create the password first. The private key is our password, and whoever has the private key can send or receive money from our account, thus we need to be careful not to share our private key with anyone.

Private keys are randomly generated hexadecimal strings of size 32 bits.Following is an example of a private key - 

<div align="center">L4mWWJeTCGcWTB4KQcPi6rdBCGVGsgbhDVRkzphraGYGgBJxtgPv</div>

Of course now that I have revealed this private key, it is of no use and I should not use it’s corresponding address to store or transact bitcoins.

Now using this private key which we generated, we can create something called a ‘Public Key’. And Cryptography works such that, even though we can generate Public Key from Private Key, we cannot figure out the Private Key from the Public Key. As the name Public Key sounds, it can be shared with anyone. In the case of bitcoin, the hash of your private key is your Bitcoin address. 

I know we used a lot of terms there, so here is the summary - 
* How can we generate a Private Key? - Randomly, literally any random 32 bit hexadecimal string
* How can we get a Public Key from a private key? - Elliptic Curve Cryptography
* How can we get our bitcoin address from a Public Key? Simple, the hash of your public key is your bitcoin address.

<div style="margin:40px;height:20px;"></div>

![walking]({{ site.baseurl }}/assets/images/digital-sign1.jpg)

<div style="margin:40px;height:20px;"></div>

If you want to understand the math behind generating a Public Key from a private key, you can read more about Elliptic Curve Cryptography, and you can learn more about hashing here. 

Using the private key I mentioned above, I generated the following BitCoin Address - 

><div align="center">1MbKk4rXZJY2zanHQVQGtH2NBaFfaarLoy</div>

Anyone can send bitcoin to this address.

Now we have a private key, we can use our Private Key to ‘sign’ any message. When the private key ‘signs’ a message you get something called a ‘digital signature’. We won't dive deep into bitcoin transactions as that is another blog article, but imagine you have to pay your friend Alice 20 bitcoins. You can create a transaction and for the sake of convenience, let's say the transaction looks like this - 
‘Transfer 20 bitcoins from my account to Alice's’ (real bitcoin transactions look very different).

And you sign it with your Private Key to create your ‘digital signature’. 

---
Image comes here

---

Creating a digital signature is like signing a cheque, but in a physical cheque, the bank will know your physical signature by looking at it. In the case of blockchain, we need some means to verify that the signature is actually yours and that it is valid before transferring the amount from your account to Alice. Of course, we cannot reveal our private key, so we need some means for a random computer on the blockchain network to prove that the signature is actually yours, without actually looking at your private key. This is where the beauty of public key cryptography comes into picture.

If you take your digital signature, the transaction (message) and your public key, we can actually check whether the message was signed by the person who has the private key of the corresponding public key or not.

---
Image comes here

---

In the above scenario, we can check whether your private key signed the transaction or not without actually looking at your private key. Thus, everyone in the blockchain network can verify whether or not you were the one who created this transaction. If the transaction is indeed valid, the transaction will be recorded into the block chain ledger and the 20 bitcoins will now belong to Alice.
