# Welcome back

It's good to see you again.

You may be tired of hearing by now how important it is to know our enemy.  But, when you think about it, every cryptographic technique and every security protocol we've discussed so far has been put in place to thwart the man in the middle attacker.  The reason the 'man in the middle' (who, obviously but necessary to say, is not always a man) is so insidious is that we trust them precisely _because_ they pretend to be someone or something that they are not.

This week, we're going to dive right into the heart of the question of identity by taking a close look at *security protocols.* 

By the end of the week, you will be able to:

* apply protocol verification tools
* evaluate the security of a communication protocol

### Taking stock

Let's take stock of what you've learnt so far.

Cryptography is not a panacea. It may solve the problem of protecting information from unauthorised access, but it creates the problem of sharing and exchanging cryptographic keys securely. 

There are three types of cryptographic keys: namely symmetric keys, public keys, and private keys. Private keys are private and should not be shared. All we need to do is to keep them (password-protected) in a safe place. Public keys need to be shared securely by using digital certificates. 

A digital certificate signed by a trusted certification authority should be enough to convince us that we are going to use a correct public key.

This week, you'll discover that even if cryptography is unbreakable, even if we use correct and secure keys, we still can get it wrong.  Communication protocols that use cryptography are called *security protocols*, and they are remarkably hard to get right. Nevertheless, in the same way programming languages have compilers that look for programming errors, we have protocol verification tools that can help us to evaluate the security of a communication protocol. 

### Your task

What experience have you had with applying protocol verification tools?

What are you most interested in trying out?


