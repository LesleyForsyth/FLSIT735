# Authentication

This is what you have learned throughout this week. 

* Cryptography is not a panacea. It may solve the problem of protecting information from unauthorised access, but, it creates the problem of sharing and exchanging cryptographic keys in a secure way. 
* There are three types of cryptographic keys, namely symmetric keys, public keys, and private keys. Private keys are private and should not be shared. All we need to do is to keep them (password-protected) in a safe place. Public keys need and can be shared securely by means of digital certificates. 
* A digital certificate signed by a trusted certification authority can be considered a fairly good proof that we are going to use a correct public key.

And this is what you are going to learn in the remainder of this week.

* Even if cryptography is unbreakable, even if we use correct and secure keys, we still can use cryptography wrong.
* Communication protocols that use cryptography are called *security protocols*, and they are remarkably hard to get right. 
* Nevertheless, in the same way programming languages have compilers that look for programming errors, we have protocol verification tools that can help us to evaluate the security of a communication protocol. 

## Who is sending this message? 

Haven't you received calls from an anonymous phone number? Haven't you received emails from an unknown email address? Would you reply to a bogus email? Would you open an attachment or click on link sent by an unfamiliar email address? I'm sure you won't. 

Communication protocols, before engaging in data exchange, also need to verify the identity of the communicating partners. To explain this further let us go back to our running example. 

![GitHub Logo](./images/msc-charts/incomplete-protocol-with-certificate.jpg)

This protocol ensures confidentiality of the message sent by Paul to the professor, as the public key of the professor is attested through a digital certificate by a trusted third party: the university. All right, now I want you to consider the following attack. 

![GitHub Logo](./images/msc-charts/attack-incomplete-protocol-with-certificate.jpg)

This is an easy attack, the attacker just needs to intersect the message intended to both and replies on Paul's behalf. This is like allowing someone you have no trust on to talk on your behalf. The question is: where is the flaw? 

1. First, everybody knows the professor's public key $pk_{Prof}$, so anyone can write messages to the professor encrypted with his public key.
2. Second, the professor has no mean to verify that the message is actually coming from Paul and not from someone else.  

We have just came up with the need of *authentication*, which is, the action of verifying the identity of a user or process. 

## Your task

You identify yourself in the airport with your passport. After showing your passport in the counter you get a boarding pass with your personal and flight details. In security check both our passport and boarding pass are checked. Comment why showing the boarding pass alone is not enough. 



