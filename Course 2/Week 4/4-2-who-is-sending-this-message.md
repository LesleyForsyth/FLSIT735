## Who is sending this message? 

Have you ever gotten a call from an anonymous phone number? Have you received emails from an unknown email address? Would you reply to a bogus email? Would you open an attachment or click on link sent by an unfamiliar email address? I'm sure you wouldn't. 

As you've already seen when it comes to the IP/TCP, before we engage in exchanging data with someone on another network, communications protocols need to verify that person's identity.  To explain this further, let's go back to our running example. 

![GitHub Logo](./images/msc-charts/incomplete-protocol-with-certificate.jpg)

This protocol ensures the confidentiality of the message sent by Paul to the Professor because the Professor's public key is certified by  a trusted third party: the university. 

All right, now I want you to consider the following attack. 

![GitHub Logo](./images/msc-charts/attack-incomplete-protocol-with-certificate.jpg)

This is an easy attack.  The attacker only needs to intersect the message intended to both and reply on Paul's behalf. This is like allowing someone you have no trust in to talk on your behalf. The question is: where is the flaw? 

1. First, everybody knows the Professor's public key $$pk_{Prof}$$, so anyone can write him or her messages encrypted with this key.
2. Second, the Professor has no mean of verifying that the message is actually coming from Paul and not from someone else.  

We have just came up with the need of *authentication*, which is the action of verifying the identity of a user or process. 

## Your task

For an international flight, you identify yourself in the airport with your passport. After showing your passport in the counter you get a boarding pass with your personal and flight details. Security checks both our passport and boarding pass before we're allowed on the plane.

For domestic Australian flights, a boarding pass is all you need.

Which is the stronger security protocol, and why?


