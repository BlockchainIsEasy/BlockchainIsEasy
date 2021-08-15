---
layout: post
title:  "Proof Of Work"
author: surya
categories: [ Basics ]
image: assets/images/article-3.jpg
---

Before talking about the concept of Proof of Work, we will discuss a very famous problem in computer science called the <u><b>Byzantine Generals</b></u> problem - or a slightly modified version of it.

Alice, Bob, Charlie, and Doug are four generals of the Byzantine army who want to conquer BlockCity. Each of the generals has his/her unit and they are waiting outside the walls of Block city. Although each of the units in the Byzantine army has more soldiers than the entire population of the BlockCity, the BlockCity has high-tech defenses and all the generals of the Byzantine army have to launch a coordinated attack at once to take down the city - all four of them have to attack at once and only then will they stand a chance of conquering the city. But there is a small problem here - each of the generals is at a different location outside the city. None of them met another general before, so none of the generals has any way of identifying a messenger or proving a message they received is actually from one of the three generals who are trying to conquer the city. The BlockCity citizens know this and are trying to circulate fake messages outside the city to confuse the generals.

How will the four generals coordinate and launch an attack simultaneously to take down the BlockCity?

It turns out we can solve this problem using the Proof of Work Concept used in Blockchain.

Now, say Bob wants to send other generals the following message - 

> Attack at dawn on Friday the 13th

The other three generals are not sure whether this message is being sent by Bob or if it is a ruse by the BlockCity citizens. The generals don't even know if other generals will agree to attack this date. 

If you know how hashing works, you are aware that every string's hash gives a unique output.

For example, if I hash the above <i>Attack at dawn on Friday the 13th</i> message using the [sha-256 algorithm](https://emn178.github.io/online-tools/sha256.html)(the same one bitcoin uses), I always get the following output - 
> 2077b09d4d2d6d7b2af4cc4484dcc5fafddfcef25d5a4c44eb72769c8bd55ca6

You can try it out [here](https://emn178.github.io/online-tools/sha256.html).

Now let us add a variable called count to our message and try to hash the message as a dictionary(or objects in Javascript). It will be clear why we are trying to do this in a while, just bear with me!

Object to be hashed - 

```
{
    count: 0, 
    message: "Attack at dawn on Friday the 13th"
}
```
>Hash - 308ccb8a7f3a048359aad7d27ce44d216b5386bf861ba89ece141c3a5c8df65e

If I change the count, the hash will change. For example. If the count is ‘1’
String to be hashed - 
```
{
    count: 1, 
    message: "2077b09d4d2d6d7b2af4cc4484dcc5fafddfcef25d5a4c44eb72769c8bd55ca6"
}
```
>Hash - 8208e5bb1f14f10eeb11b4c18eb3a577fa6026d2799f1eb4bb1c7a1723903762

Now Alice is the smartest of the four generals. She noticed that she could use hashing and overcome the problem the Byzantine army was facing. She said that she would only consider a message she received valid if the hash of the message has two zeroes in the beginning.

Now the output of a hash function is random. So if we want to get a hash of a message such that there are two zeroes in the beginning, we have to keep changing the input until we get two zeroes in the front by trial and error. Now Bob, who wants to send a message, cannot change the message, so he will order his soldiers to keep changing the count variable until the hash of the entire string (message + count) has two zeroes in the beginning. The soldiers start from 0 and on the 316th try, they succeed - 

String to be hashed- 
```
{
    count: 316,
    message: "Attack at dawn on Friday the 13th"
}
```
>Hash - 00e978e541d9ba82fa0e6b8feeda91a6683fd91375bc364ad624d6f068e69937

Hashing a string 316 times took a lot of work, and the proof that Bob’s soldiers did this work is the hash in itself. Alice can hash the string with the count as 316. Now she knows whoever sent this message to her, did the work of hashing several times to get two zeroes in the starting. 316 times is easy, and even the citizens of BlockCity can do this work and send a fake message. But what if the requirement is three or four zeroes in the beginning (which is much harder to achieve)? It might take hundreds or thousands of tries (changing the count) to get the required hash and the citizens of BlockCity will not be able to produce the same hash to show proof that they did enough work. Meanwhile, Bob, Charlie, and Doug, who have an entire army, can keep hashing and send messages with the required count proving that they are the people who have the army to do this hard work. Thus, proving that they are in fact, the generals whose message is legitimate.

Now you might ask me, what if a citizen luckily gets the correct count the first time he tries to hash. While that is theoretically possible, we can counter this problem by sending several messages, each with four zeros in the beginning. It is improbable that the citizens will get lucky every time without the manpower to compute the hash.

* Message 1 : Attack at dawn on Friday the 13th
* Message 2 : This is Bob, I want to confirm the attack at dawn on Friday the 13th
* Message 3 : The BlockCity shall be attacked at dawn on friday the 13th.

so on and so forth.

The citizens of the BlockCity who do not have enough manpower could not have computed the count such that the hash is starting with 3 or 4 zeroes every single time.

As you might have probably guessed by now, the same concept of proof of work is used in blockchain to <u>prove</u> that a person has used the required amount of <u>computational resources</u> required to create a block. Although, unlike the problem above, we do not have to send various versions of the same message. It is sufficient enough to publish it once. We shall discuss more on how Bitcoin implements Proof of Work in future articles.
