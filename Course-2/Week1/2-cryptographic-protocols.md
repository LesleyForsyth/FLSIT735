# Security protocols

To understand the flaw of the protocol used in the previous step to exchange confidential information with my favorite student Paul, we better use a graphical representation of the protocol. Such a graphical representation is given next. Note that, we are using $\{m\}_{pk_{Paul}}$ as a shorthand notation of $enc(m, pk_{Paul})$. We are also shortening the messages for the sake of simplicity.  


![GitHub Logo](./images/msc-charts/flawed-protocol1.jpg)

There are many flaws in this protocol, but we will focus on the most obvious one: how does Paul know that the received public key is the public key of his Professor? Obviously, the fact that message say so is not enough. This allows a trivial attack whereby an adversary sends exactly the same message to Paul with a minor modification. Instead of the Professor's public key, the attacker will provide his own public key to Paul. Paul's belief is that the message is coming from his Professor, and will use the key embedded in the message to send back his reply encrypted. However, it happens that the public key embedded in the message is the adversary's public key. Therefore, the adversary can easily decrypt Paul's message by using his own secret key. Confidentiality of the information lost!

A graphical representation of this attack is as follows.


![GitHub Logo](./images/msc-charts/flawed-protocol1-attacked.jpg)




## A real-life example

It is tempting to think that the protocol above is silly and no serious company would make a similar mistake. But the reality is that security protocols, despite being computer programs of just a few lines of code, are remarkably hard to get right. Case in point: the hard-drive manufacturer Western Digital offers self-encrypting hard drives. This feature saves users the time and expense of using full-disk encryption software, such as BitLocker and TrueCrypt. The drives use 256-bit AES encryption with a default, factory set, key that is password protected. However, there exists a hardcode password in the device, which an adversary can use to obtain the AES encryption/decryption key.

Does the flaw in the Western Digital drives sound familiar to you? Western Digital embedded a secret key in their drives, in the same way we embedded a public key in the message sent by the "Professor". In a sense, this is like hiding the key of our house below the doormat. 

## Your task

Reflect and discuss how you could improve the protocol between the professor and Paul in such a way that Paul's message remains confidential.

## Further reading

Read the original research paper "got HW crypto?
On the (in)security of a Self-Encrypting Drive series" and comment on other security flaws in the Western Digital self-encrypting drives.