# Onion routing

Let's look at the anonymity problem now from a different perspective. What are we good at so far? We are good at sending a confidential message even in the presence of a man-in-the-middle attacker. Doesn't this ring a bell? 

Let's think about it. Protocols, like SSL/TLS, that we studied in the past few weeks, keep our information confidential even if an adversary in the middle is allowed to read and manipulate our traffic. This means that we have a way to pass information through *intermediate nodes* in such a way that none, but the final recipient, is able to learn that information. That's indeed the goal of SSL/TLS. 

So, can't we hide the IP address of the recipient in the same way we hide the content of the messages? The answer is, partially. 

## The olympic torch

It is a tradition in Olympic Games that the Olympic flame starts its trip from Olympia, Greece and ends at the Olympic cauldron during the opening ceremony. The flame is carried in a torch, transported usually by runners several months before the games. In the Berlin games 1938, for example, the flame was transported from Olympia to Berlin by 3,331 runners. 

![GitHub Logo](./images/torch.jpg)
<!---
(source: http://www.capitalfm.com/birmingham/events/olympic-torch-relay/olympic-torch-relay-day-44-leaving-birmingham/)
-->

Although the destination of the flame is widely known, runners don't really need to know where the flame is going to. All they need to know is where is the next runner they need to give the flame to. This is how *onion routing works*. 

Imagine that I give to the first runner en envelop with a message inside. The envelop has the address of the second runner. The second runner then opens the envelop and what he/she sees inside is another envelop, with indications to the third runner, and the process continues like that. 

## Your task

Discuss what characteristics an envelop as the one described above should have to ensure that the first runner does not open all of them.