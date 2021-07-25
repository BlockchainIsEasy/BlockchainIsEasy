---
layout: post
title:  "Proof Of Work"
author: surya
categories: [ Introduction ]
image: assets/images/article-3.jpg
---

Before talking about the concept of Proof of work, we will discuss a very famous problem in computer science called “The Byzantine Generals” problem - or a slightly modified version of it.

Alice, Bob, Charlie and Doug are four generals of Byzantine army who want to conquer Block City. Each of the generals has his/her own unit and they are waiting outside the walls of Block city. Although each of the unit in Byzantine army has more soldiers than the entire population of the BlockCity, the Block city has high-tech defences and all the generals of the Byzantine army have to launch a coordinated attack at once to take down the city - all four of them have to attack at once and only then will they stand a chance of conquering the city. But there is a small problem here - each of the generals is at a different location outside the city and none of them met another general before, so none of the generals has any way of identifying a messenger or proving a message they received is actually from one of the three generals who is trying to conquer the city. The BlockCity citizens know this and they are trying to circulate fake messages outside the city to confuse the generals. 

How will the four generals co-ordinate and launch an attack at the same time to take down the Block City?

Turns out, we can solve this problem using the Proof of Work Concept used in BlockChain.

Now, say Bob wants to send other generals the following message - 
“Attack at dawn on Friday the 13th”
The other three generals are not sure whether the message is actually being sent by Bob or if it is a ruse by the Block City citizens, and the generals don't even know if other generals will agree to attack on this date. Now if you know how hashing works, you will know that every string’s hash gives a unique output.

For example, if I hash using <u>sha-256 algorithm</u> (the same one bitcoin uses) “Attack at dawn on Friday the 13th” I always get the following output - 
> 2077b09d4d2d6d7b2af4cc4484dcc5fafddfcef25d5a4c44eb72769c8bd55ca6

Now let us add a variable called count to our message and try to hash the message as a dictionary, it will be clear why we are trying to do this in a while, just bear with me 
String to be hashed - 

```
{
    count : 0, 
    message: "Attack at dawn on Friday the 13th"
}
```
>Hash - 9d4011d26b80fc55291cb91de8f3780ab59af9bfa056932874d118b7476809fa
     

If I change the count, the hash will change. For example. If the count is ‘1’
String to be hashed - 
```
{
    count : 1, 
    message: "2077b09d4d2d6d7b2af4cc4484dcc5fafddfcef25d5a4c44eb72769c8bd55ca6"
}
```
>Hash - 9df8a280df64ff28a9ca3a72c8f88377725bc8b3477c7409c33e9b4607a85b04

Now Alice is the smartest of the four generals. She noticed that she could use hashing and overcome the problem the byzantine army was facing. She said that she would only consider a message she received valid if the hash of the message has two zeroes in the beginning. 

Now the output of a hash function is random. So if we want to get a hash of a message such that there are two zeroes in the beginning, we have to keep changing the input until we get two zeroes in the front by trial and error. Now Bob, who wants to send a message, cannot change the message he wants to send, so he will order his soldiers to keep changing the count variable until the hash of the entire string (message + count) has two zeroes in the beginning. The soldiers start from 0 and in the 26th try, they succeed - 

String to be hashed- 
```
{
    count : 26,
    message: "Attack at dawn on Friday the 13th"
}
```
>Hash - 0086c2714ee25b6887b54b8dd69e1125ba6b88201e17164b6630d7a8f9355b07

Hashing a string 26 times took a lot of work, and the proof that Bob’s soldiers did this work is the hash in itself. Alice can hash the string with count = 26 and now she knows whoever sent this message to her, did the work of hashing several times to get two zeroes in the starting. 26 times is easy, and even the citizens of the Block city can do this work and send a fake message. But what if the requirement is three or four zeroes in the beginning (which is much harder to achieve) ? It might take hundreds or thousands of tries (changing the count) to get the required hash and the citizens of the Block City will not be able to produce the same hash to show proof that they did enough work. Meanwhile Bob, Charlie and Doug, who have an entire army, can keep hashing and send messages with required count proving that they are the people who have the army to do this hard work and thus, they are in fact, the generals whose message is legitimate.

Now you might ask me, what if a citizen luckily gets the correct count the first time he tries to hash, while that is totally possible, we can counter this problem by sending several messages, each with four zeros in the beginning. It is very unlikely that the citizens will get lucky every time without the manpower to compute the hash.

* Message 1 : Attack at dawn on Friday the 13th
* Message 2 : This is Bob, i want to confirm the attack at dawn on Friday the 13th
* Message 3 : The Block City shall be attacked at dawn on friday the 13th….and so on

The citizens of the Block City who do not have enough man power could not have computed the count such that the hash is starting with 3 or 4 zeroes every single time.

As you might have probably guessed by now, the same concept of proof of work is used in blockchain to ‘prove’ that a person has used the required amount of ‘computational resources’ required to create a block . We shall discuss more about block creation in future articles
