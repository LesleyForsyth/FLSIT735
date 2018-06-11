# Introduction to SSL/TLS

You now know everything you need to know to understand the *SSL/TLS protocol*.

As long as you have been following this course carefully, you can absolutely figure out the most important security protocol used nowadays to secure electronic services: the *SSL/TLS* protocol. We will dedicate the second half of this week to understand the fundamentals and underlying components of this protocol. 

### SSL/TLS: what is it used for?

Electronic commerce, banking, business, are all commonplace today and have one feature in common: processes that once were executed physically and in person are now executed remotely through a computer network, at any time and from every where. To do so, the electronic services should mimic the same role that was performed in the past by, for example, bank tellers. A bank employee would first verify the identity of the client and then act as an intermediary between the client and the bank's computer system. 

In electronic services the network is the intermediary. And we should admit that a computer network is faster than a human when it comes to processing and transmitting information, but who is going to check the identity of the clients? You probably already know the answer: a security protocol. 

During the rest of the week we are going to study the most important security protocol used to secure electronic services, the *SSL/TLS* family of security protocols. Most of the traffic for electronic commerce, electronic business, and electronic government is currently being secured with SSL/TLS protocols. SSL/TLS is indeed responsible for the little lock in the corner of your web browser, which indicates that HTTP Secure (HTTPS) is being used.  So it's important that you know about the fundamental principles behind these protocols. 

Simply invoking SSL/TLS won't make your application more secure, in the same way that cryptography itself does not make communication stronger. It is necessary to understand the underlying components and features of the protocol, functional requirements, and security requirements as well. 

### The birth of SSL

The first electronic purchases started in the early 1990s. Of course, people had reservation about the transmission of credit card information through the internet, as man-in-the-middle attackers could be silently eavesdropping the network traffic. Software developers at Netscape communication therefore worked towards a protocol for allowing secure communication over an insecure network. Their idea was to introduce an intermediate layer between the transport layer and the application layer, named *the secure sockets layer (SSL)*. 

The first version of SSL was released in 1994. However it had a number of weaknesses. So it evolved in three versions - SSL 1.0, SSL 2.0, and SSL 3.0. The current version of SSL is called *TLS 1.0* (Transport Layer Security). The change of name is due to standardisation procedures, so TLS is typically referred as SSL/TLS. 

### Roadmap 

SSL/TLS sits in between the transport layer and application layer, allowing applications to use a secure connections on top of the existing network topology. Notice in the figure below that SSL/TLS consists of four main sub-protocols. 

1. *SSL handshake protocol:* allows the a client and server to identify each other and agree on the parameters for the connection, such encryption and decryption algorithms.  
2. *SSL Change Cipher protocol:* confirms the cipher suite to be used.
3. *SSL alert protocol:* signals problems with an SSL execution.
4. *Application data protocol:* takes data from the application using SSL and sends it through the established secure channel. 

![GitHub Logo](./images/ssl-stack.png)
<!---
(source: http://swrdfish.github.io/assets/ssl/ssl_stack.png)
-->

We will dedicate the remaining steps of this week to the study of these sub-protocols. 

### Your task 

Investigate how many websites currently use SSL/TLS.


