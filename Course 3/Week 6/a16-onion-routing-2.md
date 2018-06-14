# Onion encryption

Each runner should be able to open his and only his envelope. That's the main security requirement of secure onion routing. In this step we will look at how to enforce this encryption.

## Boxes within boxes

Imagine that we have a message "DATA" that we want to send to Alice (See picture below). Alice has a red secure box, so we put the message inside Alice's box. But, we need to send the message through Bob, and Bob has a purple secure box. So we put Alice's red secure box inside Bob's purple secure box. This is not the end, Bob says the receives messages from Charley only. Hence we put everything insider Charley's cyan secure box. 

![GitHub Logo](./images/onion-encryption.jpg)
<!---
(source: https://teamultimate.in/wp-content/uploads/2017/04/Untitled-1-1-768x768.jpg)
-->

I'm sure you notice that our "DATA" remains confidential. Neither Charley nor Bob open Alice's red secure box. To implement the onion routing, Charley first opens his box and sends the purple box to Bob. Bob does the same and sends the red box to Alice. Alice finally can opens her own box and receives the message. 

## Encryption over encryption

The process above can be mimic with encryption. If we encrypt the message "DATA" with the public key $pk_A$ of Alice we obtain $\{DATA\}_{pk_A}$. Now we re-encrypt with the public key $pk_B$ of Bob, obtaining $\{\{DATA\}_{pk_A}\}_{pk_B}$. Can Bob learn the message "DATA" out of the encrypted message $\{\{DATA\}_{pk_A}\}_{pk_B}$? No, "DATA" is encrypted with $pk_A$ and only Alice can decrypt it with its secret key. So we can handle the message to Bob, who can use his secret key and obtain $\{DATA\}_{pk_A}$. Bob himself cannot obtain "DATA", so he gives the encrypted message to Alice. Alice, using her own secret key, is finally able to retrieve "DATA" out of $\{DATA\}_{pk_A}$. 


## Your task

You may have notice that Charley has been ignored in the formulation of onion encryption. Your task is to extend the example above to three players, Alice, Bob, and Charley.

