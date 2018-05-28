# Introduction to SSL/TLS

Electronic commerce, banking, business, are all commonplace today and have one feature in common: processes that before where executed via physical interaction are now executed remotely through a computer network, at any time and from every where. To do so, electronic services ought to mimic the same role that was performed before by, for example, bank employees. A bank employee would first verify the identity of the client, and right after  act as an intermediary between the client and the bank computer system. 

In electronic services the network is the intermediary. And we should admit that a computer network is faster than a human processing and transmitting information. Thus businesses become more cost-effective and efficient. But, who is going to check the identity of the clients? You probably already know the answer: a security protocol. 

During this week we are going to study the most important security protocol used to secure electronic services, the *SSL/TLS* family of security protocols. Most of the traffic 
for electronic commerce, electronic business, and electronic government, is currently being secured with SSL/TLS protocols. Therefore, we find important to teach about the fundamental principles behind this family. 

Simply invoking SSL/TLS won't make your application more secure, in the same way that cryptography itself does not make communication stronger. It is necessary to understand the underlying components and features of the protocol, functional requirements, and security requirements as well. 

## A bit of history 

TLS (Transport Layer Security) is a security protocol that is used extensively on the Internet to authenticate and secure communications. TLS is an evolution from SSL and is an IETF (Internet Engineering Task Force) standard. SSL was originally developed by Netscape and has gone through multiple versions and a name change to TLS in 1999. The current TLS version is 1.2 with a draft 1.3 version currently in development. Given the nature and value of communications that we have on the internet, there is an expectation that our communications are private and that other parties in the communications are who they say they are. It is these two basic requirements that TLS addresses by providing a way for parties in a conversation to verify each other and to communicate privately. The most common TLS application is securing client connections to websites where the protocol can verify the identity of the website and secure the communications.

To deliver the goal of authenticated and private communication, the TLS protocol uses a range of security fundamentals. How these fundamental building blocks work is well known and they are continuously under examination by security researchers and other entities to identify weaknesses. Where weaknesses are identified, the security community will issue a fix or a recommendation to deprecate the use. This openness and continuous assessment has identified many vulnerabilities ranging from weaknesses in TLS implementation (e.g. POODLE) through to key size weaknesses due to brute force attacks.

## Roadmap 


| Security goals        | Techniques
| ------------- |:-------------:
| Authentication  | Digital certificates are used to establish trust between communicating partners.|
| Confidentiality | Encryption algorithms such as AES make sure that data is not visible to third parties. |
| Secret key exchange  | Key-exchange algorithms, such as  Diffe-Hellman,  are used to established a session key. |





