# Authenticity

Since we reached the age of majority we have been asked not a few times to provide a handwritten signature as a proof that we agree on the terms and conditions specified in a given document. We also stamp our handwritten signature in our post correspondence, which makes it hard for other to tamper with our mails. Indeed, handwritten signatures are legally binding, because they are arguably hard to forge. It is hard to deny having not signed a document containing a signature just like yours.

Can we sign digital information in the same way we sign impressed documents? By doing so a certification authority could sign the content of a digital certificate, providing a proof of authenticity. 

## How can digital signatures be created?

We have seen in this course two types of cryptographic algorithms: symmetric and asymmetric. The former relies on a single shared key $k$ and both, encryption and decryption, are performed with the same key $k$. In asymmetric cryptography, instead, a pair of keys $(pk, sk)$ is available. At the moment we have been encrypting with the public key $pk$ and decrypting with the secret key $sk$. However, the curious student may wonder what would happen if we do the opposite, that is, what if one  encrypts with the secret key $sk$ and decrypts with the public key $pk$?

Let's recall the main functional requirement of asymmetric encryption as stated in Week 1. 

* $dec(enc(m, pk), sk)$ where $m$ is a message. That is to say, any message $m$ encrypted with the public key can be decrypted with the corresponding private key. 

It happens that the inverse process also works, which is:

* $dec(enc(m, sk), pk)$ where $m$ is a message. 

This second property states that asymmetric cryptography allows a message to be encrypted with the secret key and later be decrypted with the corresponding public key. How an asymmetric algorithm, like RSA, achieves that is not trivial and falls out of the scope of this course. But, as we did already in Week 1, we encourage the interested student to read more about public key cryptosystems, such as RSA, ElGamal, and Elliptic-curve. 

Now consider the following challenge. We have a secret $m$, encrypt it with the public key $pk$ of someone obtaining $m' = enc(m, pk)$, publish the ciphered text $m'$, and challenge everyone to reveal the secret $m$. It should be noticed that only one person can win this challenge: the owner of the correct secret key $sk$. This means that, by providing a correct reply to that challenge, a person can prove ownership of a secret key without revealing the secret. This process is called *authentication*.

Let's look at the above challenge in the opposite direction. We have a message $m$ and the public key $pk_{CA}$ of a certification authority CA. The challenge consists of providing a ciphered text $m'$ such that, after decryption with the public key $pk_{CA}$ gives the original message $m$, i.e. such that $m = dec(m', pk_{CA})$. As before, only one entity can win this challenge: the one owning the correct secret key $sk_{CA}$, supposedly only the certification authority CA knows the private key $sk_{CA}$. This means that $m'$ is a proof that only  CA could have encrypted $m$ with $sk_{CA}$. In this case $m'$ is said to be a *digital signature* over $m$, whilst the identity of the signer is the owner of the public key that decrypts $m'$. 

## Your task

In Week 1 you learned how to use OpenSSL to create a pair of asymmetric keys, encrypt with a public key and decrypt with the secret key. In this task you will do the inverse process, that is, you will encrypt with the secret key and decrypt with the corresponding public key. Make sure that the decrypted text corresponds to the original encrypted text.



