# Authentication factors

Authentication can be achieved in a number of ways. Passports, identity cards, access cards, etc., are authentication tokens used in everyday life. Others are more subtle, such as face recognition in face-to-face interaction or voice recognition over the phone. It is a scientific fact that mom's voice activates different regions in children's brains, indicating that newborns may identify their mons by just listening. Handwriting patterns can be used in court as evidence of document ownership. And so on.

All the above are authentication factors. The more authentication factors are checked the higher the assurance on the identity of a person or entity. How many of you would accept a passport or a driving license as a proof of identity without looking for a match between the passport's photo and the person? 

## The secret key

A proper authentication factor, or a combination of various factors, ought to satisfy three main requirements: 

* *Uniqueness*: no other person, entity, or process should share the same attribute values.  
* *Forgery resistance*: it must be difficult to reproduce, otherwise the uniqueness property would be violated. 
* *Verifiable*: this is a trivial functional requirement. 

You probably already suspect that a secret cryptographic key satisfies those three requirements. 

1. First, with very high probability is unique, because it is taken randomly out of huge key space. In RSA, for example, a key typically has $2048$ bit length, meaning that there are $2^{2048}$ different keys to choose from. 
2. Good cryptography makes guessing or recovering a key extremely unlikely. Moreover, messages cannot be encrypted/decrypted without holding the correct key. 
3. It is possible to verify that someone holds a secret key without revealing the key. A digital signature in a certificate is an example of such a proof. Another example is the challenge we proposed in a previous step this Week. Which is, we have  a  secret $m$, encrypt it $m' = enc(m, pk)$ with the public key $pk$ of someone, publish the ciphered text $m'$, and challenge everyone to reveal the secret $m$. Only the person holding the correct secret key can decrypt $m'$.

The three reasons above make a secret key a good authentication factor for communicating processes. And with confident we can say that a secret cryptographic key is *the* authentication factor used on most computer systems today. 

## Adding authentication to communication protocol

We already have all the ingredients necessary to add authentication to a communication protocol. And we will use our running example to illustrate the concept. In this example the professor would like to be convinced that Paul is sending the message. As stated before, Paul can give a proof of authenticity by using his private key, for example, by signing the message. The resulting protocol would look as follows.

![GitHub Logo](./images/msc-charts/weakly-secure-protocol-with-certificate.jpg)

The difference with respect to the previous version of the same protocol essentially lays in the second message. Importantly, Paul signs the message with his private key. This allows his professor to verify that Paul actually sent the message. Of course, such a verification requires of a valid certificate, which Paul sends as well. Finally, it is worth noticing the Paul's message is double encrypted. Encrypting the message with the professor's public key ensures no one, but the professor, will read the message. The second encryption, with Paul's private key, is like putting the message within an envelope with wax seal. 

# Your task

It has taken quite a bit of effort, but we finally have our first secure communication protocol. You may wonder, how are we convinced that this protocol does the job? We are because we have checked this protocol with the formal verification tool Scyther: https://www.cs.ox.ac.uk/people/cas.cremers/scyther/index.html

Your task is to investigate and discuss the role of formal verification tools for security protocols. 