# Protecting private keys

All operating systems, browsers, mobile devices and, of course, certification authorities themselves, create self-signed certificates. 

Trusted self-signed certificates are commonly known as *root certificates*, because they are at the root of the hierarchy of trust between certification authorities. 

A lesson we learned from the previous step is that private keys are probably as valuable as the data encrypted with those keys. Non-authorized entities should have no access to our private keys. The question is: how can we make our private keys inaccessible to others and at the same time easily accessible to us?

## Storing a private key 

A private key can be stored as a normal file in a hard drive. But, this makes it a bit too easy (and tempting) for hackers to obtain the key. Hacking into our computer would be enough to get a copy. 

That is why private keys are often password protected. If the password is strong enough, a hacker will have a hard time decrypting the file. Of course, the drawback of this approach is that we will need to enter the password every time the private key is used, which may not be feasable if our computer or server is running services that auto-restart. 

Some organisations, such as the financial sector, cannot risk the loss of protected content. Regulations have been mandated to apply the most rigorous security protocols and procedures in highly critical information, such as financial data. For that level of security, there is dedicated hardware that stores the private keys and optimises various cryptographic operations. Placing our keys in dedicated hardware follows the principle of in-depth security, whereby we defend our system using different and independent methods. A hacker does not only need to penetrate our network, but also to hack the dedicated hardware where our keys are stored. 

Hardware used to store key material most follow security standards, such as the [FIPS-140](https://en.wikipedia.org/wiki/FIPS_140-2). For example, they ought to display evidence of physical tampering and access, which is used for intrusion detection and forensics. Advanced hardware also includes deletes the keys if they detect tampering occuring.

# Your task

As an individual, just as in an organisation,  we should protect our keys with a strong password. Your task this time is to use openssl to generate and store a password protected RSA key. 