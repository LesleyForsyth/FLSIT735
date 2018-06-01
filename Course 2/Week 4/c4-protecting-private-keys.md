# Protecting private keys

A lesson we learned from the previous step is that private keys are probably as valuable as the data encrypted with those keys. As such, non-authorized entities should have no access to our private keys. The question is: how can we make our private keys inaccessible to others and at the same time easily accessible to us?

## Storing a private key 

A private key can be stored as a normal file in a hard drive. But,this makes it easier for hackers to obtain the key. Hacking into our computer would be enough to get a copy of our key. That is why often private keys are password protected. If the password is strong enough, a hacker will have a hard time to decrypt the file. Of course, the drawback of this approach is that we will need to enter the password every time the private key is used, which may be unfeasable if our computer or server is running services that auto-restart. 

Some organisations, such as the financial sector, cannot risk the lost of protected content. Actually, regulations mandate to apply the most rigorous security protocols and procedures in highly critical information, such as financial data. For that level of security, there exists dedicated hardware that stores the private keys as well as optimise various cryptographic operations. Placing our keys in a dedicated hardware follows the principle of in-depth security, whereby we defend our system using different and independent methods. A hacker does not only need to penetrate our network, but also to hack the dedicated hardware where our keys are stored. 

Hardware used to store key material most follow security standards, such as the FIPS-140. For example, they ought to show evidence of physical tampering and access, which is used for intrusion detection and forensics. Advanced hardware also includes active deletion of key material if tampering is detected.

# Your task

As an individual we better protect our keys with a strong password. Your task this time is to use openssl to generate and store a password protected RSA key. 