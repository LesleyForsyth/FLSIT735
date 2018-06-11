# Key exchange

As you may have discussed in the task of the previous step, browsers and computer programs have no need to use "passwords" in the way we (users) understand them. Instead, programs use a strong type of password known as *nonces*. As you already know, a nonce is just a large random number that is meant to be used once. The protocol depicted in the previous step can be easily adapted to use a nonce instead of a password as follows.

![GitHub Logo](./images/msc-charts/nonce-exchange.jpg)


## Vulnerability

This is one of those moments where you should be standing up from your desk and yelling - what is this nonsense all about!? And you would be right. The protocol above is totally broken. It resembles to SSL/TLS, but obviously it is not.

Recall that in security our main job is to be paranoid, always looking for the worst scenario and what can go wrong. Then you may wonder - hold on, how does the server knows that the message $$\{72AE25495A...\}_{pk_{Amazon}}$$ is being sent from the client. Because if it doesn't, then an adversary could send his own key instead, like $$\{111111111...\}_{pk_{Amazon}}$$. The server is unaware of where the message is coming from, so will wrongly attribute it the client. You are very familiar with the rest of the story. If the server uses the key $111111111...$ for encryption, the adversary will have a good time decrypting the traffic. 

## Your task

What ideas can you come up with on how to prevent the attack described above? 

