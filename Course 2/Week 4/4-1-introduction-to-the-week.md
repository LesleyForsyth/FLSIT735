# Authentication

Let's take stock of what you've learnt so far.

* Cryptography is not a panacea. It may solve the problem of protecting information from unauthorised access, but it creates the problem of sharing and exchanging cryptographic keys securely. 
* There are three types of cryptographic keys: namely symmetric keys, public keys, and private keys. Private keys are private and should not be shared. All we need to do is to keep them (password-protected) in a safe place. Public keys need to be shared securely by using digital certificates. 
* A digital certificate signed by a trusted certification authority should convince us that we are going to use a correct public key.

And this is what you are going to learn in this week.

* Even if cryptography is unbreakable, even if we use correct and secure keys, we still can use cryptography wrong.
* Communication protocols that use cryptography are called *security protocols*, and they are remarkably hard to get right. 
* Nevertheless, in the same way programming languages have compilers that look for programming errors, we have protocol verification tools that can help us to evaluate the security of a communication protocol. 


