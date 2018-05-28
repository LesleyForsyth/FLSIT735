# Introduction to SSL/TLS

Electronic commerce, banking, business, are all commonplace today and have one feature in common: processes that before where executed via physical interaction are now executed remotely through a computer network, at any time and from every where. To do so, electronic services ought to mimic the same role that was performed before by, for example, bank employees. A bank employee would first verify the identity of the client, and right after  act as an intermediary between the client and the bank computer system. 

In electronic services the network is the intermediary. And we should admit that a computer network is faster than a human processing and transmitting information. Thus businesses become more cost-effective and efficient. But, who is going to check the identity of the clients? You probably already know the answer: a security protocol. 

During this week we are going to study the most important security protocol used to secure electronic services, the *SSL/TLS* family of security protocols. Most of the traffic 
for electronic commerce, electronic business, and electronic government, is currently being secured with SSL/TLS protocols. Therefore, we find important to teach about the fundamental principles behind this family. 

Simply invoking SSL/TLS won't make your application more secure, in the same way that cryptography itself does not make communication stronger. It is necessary to understand the underlying components and features of the protocol, functional requirements, and security requirements as well. 

## The born of SSL

The first electronic purchases started in the early 1990s. Of course, people had reservation about the transmission of credit card information through the internet, as man-in-the-middle attackers can be silently eavesdropping the network traffic. Software developers at Netscape communication therefore prosecuted the goal of establishing a secure communication over an insecure network. Their idea was to introduce an intermediate layer between the transport layer and the application layer, named *the secure sockets layer (SSL)*. And the first version of SSL was released by 1994.

Transition from SSL to TLS....

## Roadmap 


| Security goals        | Techniques
| ------------- |:-------------:
| Authentication  | Digital certificates are used to establish trust between communicating partners.|
| Confidentiality | Encryption algorithms such as AES make sure that data is not visible to third parties. |
| Secret key exchange  | Key-exchange algorithms, such as  Diffe-Hellman,  are used to established a session key. |





# The cost of public key infrastructure 

Public key encryption has enabled security solutions that were unthinkable during the era of symmetric encryption only. It allows messages to be signed and public keys to be distributed at will. In comparison with its counterpart, the symmetric cryptographic, asymmetric cryptography offers much more than simple encryption and decryption. However, public key or asymmetric cryptography comes at a price: efficiency. 

Asymmetric encryption is slower than symmetric encryption essentially because of two reasons. First, the key length of public key crypto systems is larger. RSA, for example, typically uses keys of size $1024$ or $2048$ bits, while AES uses keys of size $128$ or $256$ bits. A larger key size implies computation over larger numbers, hence more demand of computational resources. Second, symmetric ciphers are based on simple bitwise operations to achieve confusion and diffusion, such as XOR, modular addition, and lookup operations. Computer hardware has been optimised for decades to execute quickly this type of operations. Asymmetric encryption instead relies on trapdoor functions that are hard to *invert*. In RSA, for example, inverting, which is to say performing decryption in an asymmetric crypto system, requires performing exponentiation and multiplication of $1024$ bit numbers. Such operations are by far more complex than a simple addition or XOR.

Because we need our networks to run fast, public key encryption is used as little as possible. Whenever symmetric encryption can be used, then asymmetric encryption is essentially ignore. Does it mean that asymmetric crypto system are not used in practice? Absolutely not. As we saw last week, asymmetric cryptography provides a reliable way to establish trust between two entities in a network. Once this trust is established, symmetric cryptography takes over.  

## Transitioning from a asymmetric to symmetric cryptography

You may be thinking, if I trust already my communicating partner, all I need is a secret shared key with which to continue a secure communication by means of a symmetric cipher like AES. That's exactly the goal of cryptographic protocols known as *key exchange protocols*. 


