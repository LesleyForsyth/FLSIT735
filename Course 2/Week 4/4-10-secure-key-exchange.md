# Secure key exchange

Let's do things right this time. 

Do you recall replay attacks from last week? Do you remember how to prevent them? Well, we will use a similar technique in this step to fix the vulnerability exposed in the previous one. 

## Using nonces to keep track of a session

The way replay attacks are prevented is by using a nonce (random number) that links the messages of a given session. Because nonces are used only once, messages from previous sessions cannot be re-used.

The problem with the protocol in the last step is that an adversary is able to convince the server to use his key. SSL/TLS actually does not prevent this step of the attack. However, SSL/TLS do add two additional messages that allow the browser and server to be agree on the shared key. 

Let's look at a rough presentation of how this works, as depicted in the figure below.


![GitHub Logo](./images/msc-charts/secure-nonce-exchange.jpg)

The first thing I'd like to draw your attention to is that both browser and server exchange nonces $$n$$ and $$m$$, respectively. Those nonces will play a pivotal role later on.

Secondly, the actual key is indeed not sent at all encrypted with the public key of the server, but a *pre-master key* ($k_{pre}$) that will be used later to compute the actual key. Both the browser and the server can derive the *master key* simply by computing the hash over the pre-master key and the nonces you've already exchanged. That is, $$k_{master} = h(k_{pre}, m, n)$$.

Last, but not least, the server proves to the client that the master key was derived correctly. It does so by showing that it can encrypt with the master key: $$\{$Server-Done$, m, n\}_{k_{master}}$$. The client provides a similar proof to the server and Voilá! Now both can confidently use $$k_{master}$$ for further communication.

## Your task

What would happen if the protocol above ignores the last two messages? That is, the server and the client's proof that they can derive the master key?

Hint: Try to recreate the attack from the previous step. 
