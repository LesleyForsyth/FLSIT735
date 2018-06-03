# Key exchange

As you may have discussed in the task of the previous step, browsers and computer programs have no need to use "passwords" in the way we (users) understand them. Instead, programs use a strong type of password known as *nonces*. As you already know, a nonce is just a large random number that is meant to be used once. The protocol depicted in the previous step can be easily adapted to use a nonce instead of a password as follows.

![GitHub Logo](./images/msc-charts/nonce-exchange.jpg)

For the sake of exposition we have deliberately omitted not a few details in the protocol above. Something that you will encounter in your career in Information Technology often is the burden of dealing with different versions of software, protocols, ciphers, etc. For example, if you travel to another country chances are that you may face a different language. So you will probably start your communication with others asking: do you speak X? Where X can be English, Spanish, Chinese, Hindi, etc. This is known in communication protocols as a *negotiation phase* or *handshake*.

## Vulnerability

This is one of those moments where you stand up from your desk and yell - what a nonsense is this? And you would be right. The protocol above is totally broken. It resembles to SSL/TLS, but obviously it is not. 

Recall that in security our main job is to be paranoid, always looking for the worst scenario and what can go wrong. Then you may wonder-  hold on, how does the server knows that the message $\{72AE25495A...\}_{pk_{Amazon}}$ is being sent from the client. Because if it doesn't, then an adversary could send his own key instead, like $\{111111111...\}_{pk_{Amazon}}$. The server is unaware of where the message is coming from, so will wrongly attribute it the client. You are very familiar with the rest of the story. If the server uses the key $111111111...$ for encryption, the adversary will have a good time decrypting the traffic. 

## Your task

I want you to raise ideas on how to prevent the above attack. 

