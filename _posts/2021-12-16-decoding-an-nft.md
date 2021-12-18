---
layout: post
title: "Decoding an NFT"
author: airesh
categories: [Advanced]
image: assets/images/nft-cover.jpg
---

An address is the most crucial identifier on the Blockchain. Everyone's wallet on Blockchain is nothing but an account linked to an address. You will need to submit many documents to get an account number linked to you to open a bank account on an average day. In Blockchain, it's as easy as making tea 😄Ok, I would say I've found that hard too sometimes! But coming back to the point, it's effortless to create an account on a Blockchain network.
Creating an account on Ethereum for a developer is a one-line command.

```
geth account new
```

For an everyday person, it's as easy as clicking a "Create account" button on any wallet. 

![NFT-1]({{ site.baseurl }}/assets/images/nft-create-account.png)

Doing this gives you something called a key-value pair. Imagine you lock something with a unique key(your private key). But this package can only be opened by another key related to yours, and the latter key is what you give the entire world. From this "public key," we derive your address. This address can now hold your account balance and a few other properties that help the Blockchain network.

So far, we have with us:
1. A private key,
2. A public key,
3. An address derived from this public key.

![NFT-2]({{ site.baseurl }}/assets/images/nft-normal-wallet.jpg)

Now let’s add a couple of properties to the account state. 
1. Storage hash that links to the storage of the account
2. Code hash that links to the accounts code.

![NFT-3]({{ site.baseurl }}/assets/images/nft-smart-contract.jpg)

What do we have here?

<b>A Smart Contract!</b>

However, this account is not controlled by any user with a private key. It is governed solely by the code it contains. This code, once deployed, cannot be altered! As you can see here, the Smart Contract is nothing but a wallet that has some code logic that operates that wallet.

<hr/>

Today you created a work of art. On this day, you drew a cube with such perfect dimensions that this piece of craft felt personal to you. This art was such a masterpiece that all you wanted to do now was treasure this piece of art for eternity(slightly exaggerated, but this should work 😄).

![NFT-4]({{ site.baseurl }}/assets/images/nft-cube.jpg)

How can you make sure this art is traced back to you? How can you ensure that someone cannot copy this piece of art later and claim it as theirs? 

<hr/>

As a developer, I take the code section of the Smart Contract we created above and add a few attributes to it. Imagine I make a basket that collects cubes: "programmatically."(In the programming world, this basket is called an array). I take unique cubes created by artists, add them to my basket, and return a number to you. Any artist can later use this number to track their cube.

<img src="{{ site.baseurl }}/assets/images/nft-bucket-array.jpg" width="300" alt="NFT-Bucket">

Now you and I both know that this code cannot be altered once deployed. Hence before deploying this code, I add a few accessibility functions that any artist can later use to upload their art and get this number.

So what do we have in our code so far?
* A bucket that stores our cubes
* A Create helper that helps artists upload their cube into the bucket and get a number.
* An "ownerOf" helper.

<img src="{{ site.baseurl }}/assets/images/nft-code.jpg" width="300" alt="NFT-code">

Now, what is this ownerOf helper?

This helper function returns the address of the artist that uploaded the cube! As an artist participating in the blockchain network, you will have your wallet(as shown above) with an address linked to you. To upload your cube into the Smart Contract, in this case, the bucket, you will need to call the Create helper and sign that transaction with your address. The code will now map that number returned to you to your address.

And now, since no one cannot alter the code once deployed(as we've mentioned a million times by now), you can display to the entire world your piece of art with soundproof evidence that you are the owner of this.

All this, in a nutshell, is an NFT. You are uploading your piece of art with your address linked to prove to the world that you were the creator. 

We can now start modifying the code to add many more helper functions. I can add a Transfer helper to transfer the ownership of my art to some other address(when sold in an auction, perhaps). I can add some logic that makes the owner of my art continuously transfer money to me, maybe yearly. I can create music instead of art and upload that digitally. I can create a billion pokemon and scatter them around in an Augmented Reality world, and you can catch these Pokemon and prove to the world as a whole that you own this rare species of Pokemon 😄. The possibilities are endless. 

<h2>Conclusion:</h2>

1. We saw how easy it is to create a virtual bank account on the Blockchain.
2. We saw how Smart Contract is a simple extension to this account and is controlled by its code logic.
3. We understood how an artist could immortalize their art and prove to others that it is theirs.
4. A brief understanding of how NFTs are created.

There might be many questions that may arise reading this thread. Please do comment below so that we can answer them in a future article.
