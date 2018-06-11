# Replay attacks

Congratulations! You now know how to handle public cryptographic keys and use them to exchange confidential messages securely. So it is time to move towards more ambitious goals. 

### Continuous communication 

Most communication on the internet extends over a long period of time. You connect to Google, Facebook, or your company's intranet every few minutes or so. When you download a file, the file is actually split in small packets that are delivered to your computer in an asynchronous way. Streaming video or music also requires a permanent connection and exchange of data. In a nutshell, communication protocols are invoked not once, but many times within the same application.

When we write your exam, we'll make sure that it is different to your previous ones. Otherwise, the students can copy/paste verbatim answers from previous exams. This is a form of *plagiarism* in academia, and unsurprisingly a similar technique can be used to attack security protocols. 

Case in point. Assume, in our running example, that the professor needs to ask check in with Paul, because he's been feeling ill. It would be tempting to use the same protocol, but that protocol would be vulnerable to *plagiarism*, or *replay attack* as it is know in the security community. Essentially, an attacker would eavesdrop the first communication between the professor and Paul, keeping a record of Paul's message: $$\{$$\{$Hi professor, this is my secret...$\}_{pk_{Prof}}$ $\}_{sk_{Paul}}$$.

If the professor executes the protocol a second time to ask Paul how he feels, the attacker can just *replay* the message previously obtained, making the professor believes that Paul health problems remain the same.
 
You can take a look at a graphical representation of this replay attack below. Note that, for the sake of simplicity, we have removed some details of the protocol, such as the certificate exchanges. 

![GitHub Logo](./images/msc-charts/replay-attack-protocol-with-certificate.jpg)

## Protecting against replay attacks

Protecting against replay tends to be "simple". In the same way exam questions should not be repeated, we need to make sure that the communication transcripts do not repeat themselves. Every message in a communication protocol should look unique. 

## Your task

Your task for this step is twofold: 

1. The simple one is to discuss what sources of *uniqueness* you have seen in this course so far. 
2. The less simple is to [investigate the impact of replay attacks](https://news.bitcoin.com/bitcoin-software-wars-the-case-against-replay-attack-protection/) in a hot technology like bitcoin. 




