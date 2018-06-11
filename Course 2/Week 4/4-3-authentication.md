# Authentication 

Authentication can be achieved in a number of ways.

 Passports, identity cards, driver's licenses, access cards, etc., are tokens we use for authentication every day. Other methods are more subtle, such as facial recognition  or voice recognition over the phone. It is a scientific fact that mom's voice activates different regions in children's brains, indicating that newborns may identify their mons by just listening **Rolando - reference please.** Handwriting patterns can be used in court as evidence of document ownership. And so on.

All the above are authentication factors. The more authentication factors are checked the more assured we can feel that someone is who they say they are, or represent who they claim to. How many of you would accept a passport or a driving license as a proof of identity without looking for a match between the passport's photo and their face? 

## The secret key

A proper authentication should consist of a combination of various factors that satisfy three main requirements: 

* *Uniqueness*: no other person, entity, or process should share the same attribute values.  
* *Forgery resistance*: it must be difficult to reproduce.
* *Verifiable*: this is a functional requirement. 

You probably already suspect that a secret cryptographic key satisfies these three requirements.  Let's see how it works:

1. First, it satisfies these requirements by having a very high probability is unique, because it is taken randomly out of huge key space. In RSA, for example, a key typically has $$2048$$ bit length, meaning that there are $$2^{2048}$$ 
different keys to choose from. 

2. Good cryptography makes guessing or recovering a key extremely unlikely. Moreover, messages cannot be encrypted/decrypted without holding the correct key.

3. It is possible to verify that someone holds a secret key without revealing the key. A digital signature in a certificate is an example of such a verification.   You might remember another example from the challenge we investigated in the very first week: If we have  a  secret $$m$$, encrypt it $$m' = enc(m, pk)$$ with the public key $$pk$$, publish the ciphered text $$m'$$, and challenge everyone to reveal the secret $$m$$. Only the person holding the correct secret key can decrypt $$m'$$.

The three reasons we've just listed show you why a good secret key satisfies the requirements of propoer authentication.  We can say with confidence that a secret cryptographic key is *the* authentication factor used in most computer systems today. 

## Adding authentication to communication protocol

We already have all the ingredients necessary to add authentication to a communication protocol. We will use our running example to show you how. In this example the professor would like to be convinced that Paul is sending the message. As stated before, Paul can give a proof of authenticity by using his private key, for example, by signing the message. The resulting protocol would look as follows.

![GitHub Logo](./images/msc-charts/weakly-secure-protocol-with-certificate.jpg)

The difference with respect to the previous version of the same protocol essentially lays in the second message. Importantly, Paul signs the message with his private key. This allows his Professor to verify that Paul actually sent the message. Of course, such a verification requires of a valid certificate, which Paul sends as well. Finally, it is worth noticing the Paul's message is double encrypted. Encrypting the message with the professor's public key ensures no one but the professor will read the message. The second encryption, with Paul's private key, is like putting the message within an envelope with wax seal. 

### Your task

It has taken quite a bit of effort, but we finally have our first secure communication protocol. You may wonder, how are we convinced that this protocol does the job? We are because we have checked this protocol with the formal verification tool [Scyther](https://www.cs.ox.ac.uk/people/cas.cremers/scyther/index.html).

What do you think the role of verification tools like Scyther might be in communications network security?
