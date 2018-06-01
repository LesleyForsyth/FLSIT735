# Introduction to SSL/TLS

Electronic commerce, banking, business, are all commonplace today and have one feature in common: processes that before where executed via physical interaction are now executed remotely through a computer network, at any time and from every where. To do so, electronic services ought to mimic the same role that was performed before by, for example, bank employees. A bank employee would first verify the identity of the client, and right after  act as an intermediary between the client and the bank computer system. 

In electronic services the network is the intermediary. And we should admit that a computer network is faster than a human processing and transmitting information. Thus businesses become more cost-effective and efficient. But, who is going to check the identity of the clients? You probably already know the answer: a security protocol. 

During this week we are going to study the most important security protocol used to secure electronic services, the *SSL/TLS* family of security protocols. Most of the traffic 
for electronic commerce, electronic business, and electronic government, is currently being secured with SSL/TLS protocols. SSL/TLS is indeed responsible of the little lock in the corner of your web browser, which indicates that HTTP Secure (HTTPS) is being used.  Therefore, we find important to teach about the fundamental principles behind this family. 

Simply invoking SSL/TLS won't make your application more secure, in the same way that cryptography itself does not make communication stronger. It is necessary to understand the underlying components and features of the protocol, functional requirements, and security requirements as well. 

## The born of SSL

The first electronic purchases started in the early 1990s. Of course, people had reservation about the transmission of credit card information through the internet, as man-in-the-middle attackers can be silently eavesdropping the network traffic. Software developers at Netscape communication therefore prosecuted the goal of establishing a secure communication over an insecure network. Their idea was to introduce an intermediate layer between the transport layer and the application layer, named *the secure sockets layer (SSL)*. 

The first version of SSL was released in 1994. However it has a number of weaknesses as summarised below.



Transition from SSL to TLS....

## Roadmap 


| Security goals        | Techniques
| ------------- |:-------------:
| Authentication  | Digital certificates are used to establish trust between communicating partners.|
| Confidentiality | Encryption algorithms such as AES make sure that data is not visible to third parties. |
| Secret key exchange  | Key-exchange algorithms, such as  Diffe-Hellman,  are used to established a session key. |






