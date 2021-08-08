---
layout: post
title:  "Digital Signatures"
author: surya
categories: [ Basics ]
image: assets/images/article-2.jpg
---
Sign for a check, pin for credit and debit cards, OTP for internet banking - how does it work in blockchain? Well, it turns out there is something called the <u>Digital Signature</u> for blockchain which is arguably safer than OTPs or physical signatures or pins. But before we get into <u>Digital Signatures</u> we need to talk about how we identify someone who wants to transact on blockchain - in other words, if blockchain is a global bank, how do we create an account in our bank and send and receive money?

When we want to open an account in a bank, we have to fill in forms, give proof for our address, citizenship, and whatnot. Finally, after a week or two of tedious work, we get our bank account created. When it comes to blockchain, it turns out, creating an account is as easy as typing a few commands. Anyone with a computer can generate something called the <u>Private Key</u>. When it comes to a bank, you create an account and then attach a password to it, but in blockchain, we generate the password first. The private key is our password, and whoever has the private key can send or receive money from our account. Hence we need to be careful not to share our private key with anyone.

Private keys are randomly generated, hexadecimal strings of size 32 bits. Following is an example of a private key -

><div align="center"><i><b>L4mWWJeTCGcWTB4KQcPi6rdBCGVGsgbhDVRkzphraGYGgBJxtgPv</b></i></div>
<!-- <br> -->

Of course, now that I have revealed this private key, it is of no use. I should not use its corresponding address to store or transact bitcoins.

Now using this private key that we generated, we can create something called a <u>Public Key</u>. Cryptography works such that, even though we can generate <u>Public Key</u> from a Private Key, we cannot figure out the Private Key from the <u>Public Key</u>. As the name <u>Public Key</u> infers, it can be used by anyone. In the case of Bitcoin, the hash of your Private Key is your Bitcoin address. 

I know we used a lot of terms there, so here is the summary - 
* How can we generate a Private Key? - Randomly, literally any random 32 bit hexadecimal string
* How can we get a Public Key from a Private Key? - Elliptic Curve Cryptography
* How can we get our Bitcoin address from a Public Key? Simple, the hash of your public key is your bitcoin address.

<div style="margin:40px;height:20px;"></div>

![digital-sign1]({{ site.baseurl }}/assets/images/digital-sign1.jpg)

<div style="margin:40px;height:20px;"></div>

If you want to understand the math behind generating a Public Key from a Private Key, you can read more about Elliptic Curve Cryptography [here](https://medium.com/@ebuschini/elliptic-curve-cryptography-5611863346e8), and you can learn more about hashing [here](https://medium.com/@isuruj/introduction-to-hashing-5b4daf343889). 

Using the private key I mentioned above, I generated the following Bitcoin Address - 

><div align="center"><i><b>1MbKk4rXZJY2zanHQVQGtH2NBaFfaarLoy</b></i></div>

Anyone can send Bitcoin to this address.

Now that we have a Private Key, we can use our Private Key to <u>sign</u> any message. When the Private Key <u>signs</u> a message, you get something called a <u>Digital Signature</u>. We won't dive deep into Bitcoin transactions as that is another blog article altogether, but imagine you have to pay your friend Alice 20 Bitcoins. You can create a new transaction and for the sake of convenience, let's say the transaction looks like this - 

‘Transfer 20 bitcoins from my account to Alice's’ (real bitcoin transactions look very different).

And you sign it with your Private Key to create your <u>Digital Signature</u>.

![digital-sign2]({{ site.baseurl }}/assets/images/digital-sign2.png)

Creating a <u>Digital Signature</u> is like signing a cheque. In a physical cheque, the bank will know your physical signature by looking at it. In the case of blockchain, we need some means to verify that the signature is yours and that it is valid before transferring the amount from your account to Alice. Of course, we cannot reveal our Private Key, so we need some means for a random computer on the blockchain network to prove that the signature is yours, without actually looking at your Private Key. This is where the beauty of Public Key cryptography comes into the picture.

If you take your digital signature, the transaction (message) and your public key, we can actually check whether the message was signed by the person who has the Private Key of the corresponding public key or not.

![digital-sign3]({{ site.baseurl }}/assets/images/digital-sign3.jpg)

In the above scenario, we can check whether your Private Key signed the transaction or not without actually looking at your Private Key. Thus, everyone in the blockchain network can verify whether or not you were the one who created this transaction. If the transaction is indeed valid, the transaction will be recorded into the blockchain ledger and the 20 Bitcoins will now belong to Alice.
