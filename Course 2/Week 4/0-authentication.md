# Integrity 

Likely, many of you came up with the following solution to the previous task: by encrypting the first message of the protocol we make sure that the adversary cannot modify it. That sounds reasonable, and let us take a look to a first attempt where we use the Paul's public key to encrypt the first message. 

![GitHub Logo](./images/msc-charts/flawed-protocol2.jpg)

By using Paul's public key we make sure that only Paul can decrypt the message. However, does it really prevent an adversary from modifying the original message? Recall that a public key is public. So nothing prevents an attacker from encrypting his own message with Paul's public key. Therefore, a similar attack to the one spotted in the previous step is as follows. 

![GitHub Logo](./images/msc-charts/flawed-protocol2-attacked.jpg)

Hence the question remains: how can we prevent an adversary from modifying our traffic without being detected? In other words, how can we ensure that the integrity of our data is maintained over its entire lifecycle? The answer can be found in the well-known concept of signatures. 

## Signatures

Since we reached the age of majority we have been asked not a few times to provide a handwritten signature as a proof that we agree on the terms and conditions specified in a given document. We also stamp our handwritten signature in our post correspondence, which makes it hard for other to tamper with our mails. Indeed, handwritten signatures are legally binding, because they are arguably hard to forge. It is hard to deny having not signed a document containing a signature just like yours.

The next question is obvious: can we sign digital information in the same way we sign impressed documents? 

## Digital signatures

We have seen in this course two types of cryptographic algorithms: symmetric and asymmetric. The former relies on a single shared key $k$ and both, encryption and decryption, are performed with the same key $k$. In asymmetric cryptography, instead, a pair of keys $(pk, sk)$ is available. At the moment we have been encrypting with the public key $pk$ and decrypting with the secret key $sk$. However, the curious student may wonder what would happen if we do the opposite, that is, what if one  encrypts with the secret key $sk$ and decrypts with the public key $pk$?

Let's recall the main functional requirement of asymmetric encryption as stated in Week 1. 

* $dec(enc(m, pk), sk)$ where $m$ is a message. That is to say, any message $m$ encrypted with the public key can be decrypted with the corresponding private key. 

It happens that the inverse process also works, which is:

* $dec(enc(m, sk), pk)$ where $m$ is a message. 

This second property states that asymmetric cryptography allows a message to be encrypted with the secret key and later be decrypted with the corresponding public key. How an asymmetric algorithm, like RSA, achieves that is not trivial and falls out of the scope of this course. But, as we did already in Week 1, we encourage the interested student to read more about public key cryptosystems, such as RSA, ElGamal, and Elliptic-curve. 

Now consider the following challenge. We have a secret $m$, encrypt it $m' = enc(m, pk)$ with the public key $pk$ of someone, publish the ciphered text $m'$, and challenge everyone to reveal the secret $m$. It should be noticed that only one person can win this challenge: the owner of the correct secret key $sk$. This means that, by providing a correct reply to that challenge, a person can prove ownership of a secret key without revealing the secret. This process is called *authentication* and we will come back to it in a couple of steps more.

Let's look at the above challenge in the opposite direction. We have a message $m$ and the public key $pk_{Prof}$ of, say the professor. The challenge consists of providing a ciphered text $m'$ such that, after decryption with the public key $pk_{Prof}$ gives the original message $m$, i.e. such that $m = dec(m', pk_{Prof})$. As before, only one person can win this challenge: the person owning the correct secret key $sk_{Prof}$, in this case the professor. This means that $m'$ is a proof that only the professor could have encrypted $m$ with $sk_{Prof}$. This process is called *digital signing*. 

## Your task

In Week 1 you learned how to use OpenSSL to create a pair of asymmetric keys, encrypt with a public key and decrypt with the secret key. In this task you will do the inverse process, that is, you will encrypt with the secret key and decrypt with the corresponding public key. Make suer that the decrypted text corresponding to the original encrypted text. 



