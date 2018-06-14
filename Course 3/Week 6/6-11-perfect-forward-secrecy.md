# Perfect forward secrecy

What does happen if your secret key is compromised? 

When a secret key is compromised all messages encrypted with such a key can be decrypted, hence confidentiality is lost. We have been looking at end-to-end encryption as a mean to communicate privately. But end-to-end encryption is of no use if it relies on a single point of failure: the secrecy of a secret key.

## The problem

Consider the following SSL/TLS-like protocol, which we studied last week. 

![GitHub Logo](./images/msc-charts/nonce-exchange.jpg)
<!---
(source: )
-->

Now ask yourself what would happen if the secret key of Amazon's certificate is leaked. You may notice that all the communication between Amazon and Browser is being encrypted with a session key $72AE25495A...$. Is this key really secret?

No. The adversary knows the secret key $sk_{Amazon}$, so he can decrypt the message $\{72AE25495A...\}_{pk_{Amazon}}$, obtaining the session key $72AE25495A...$. This means that the adversary is able to decrypt all traffic between Amazon and Browser. This how end-to-end encryption inevitably fails.

But this is not the only problem. If the adversary has been eavesdropping previous communication between Amazon and Browser, he can also break the confidentiality of those by executing the same strategy. In a nutshell, the lost of a secret key has compromised the confidentiality of present and past communications. 

## The solution

An obvious solution to the problem above is: don't loose your secret keys. However, we are all potentially vulnerable to hacking, even the most powerful security agencies.

There is another solution, though. We can try to make it hard for the adversary to learn our past session keys even if the secret key is compromised. 
Doing so we guarantee that even if attackers manage to gain access to the private key of a certificate, they are not able to decrypt communication from the past. 

## Your task


