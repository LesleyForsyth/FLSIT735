# Introduction to Week 3

During Week 1 we learned about mathematical constructs that can be used to encrypt our data in such a way that it can only be read by authorised parties, that is, those knowing the correct decryption key. Then in Week 2 we learned how computer networks are structured and where the danger is hidden. Particular attention was paid to the fact that anyone can seat in between our traffic, making it possible to eavesdrop, block, modify, and inject traffic. Against such a powerful adversary (or vulnerability depending how you look at it), cryptography by itself is not enough to secure communication.

Actually, most cyber security attacks nowadays do not break cryptography at all, essentially because cryptography is hard to break. Cryptanalysis is one of the less likely threats to our computer systems.
Instead, attackers look for ways to bypass cryptography by exploiting design flaws on the way cryptography is used. To illustrate this let us consider that a bike lock is unbreakable. Just as a cryptographic algorithm, it can be unlocked with the correct key only. A bad use of a secure lock may look as follows.

![GitHub Logo](./images/bike_stolen1.jpg)

Clearly most of the bike was lost by an incorrect use of a (supposedly secure) lock. Secure locks, if used improperly, may give a false feeling of security. In the same vein, cryptographic protocols, if poorly designed, do more harm than good as we tend to trust information that is encrypted.  

Another example. Suppose that I'm worried about my favorite student Paul, who is having health issues. Paul has a pair of asymmetric cryptographic keys $(pk_{paul}, sk_{paul})$. I have my own pair of keys as well $(pk_{Prof}, sk_{Prof})$. Then I write the following message to Paul.

* m = "Dear Paul, it's me, your Professor of Communications Network Security. Would you please tell me the nature of the health issue you are having at the moment. Because this is super sensitive information and we want no one to know about it, I'm sending herein my public key, which you can use to encrypt your reply and be confident that only me can decrypt your message. My public key is $pk_{Prof}$".  
* Once Paul receives the message $m$, he writes back a message $m'$ explaining his health problems, encrypt it with the public key $pk_{Prof}$ contained in $m$, and the send $enc(m', pk_{Prof})$ back to me.
* Finally, I receive Paul's response $enc(m', pk_{Prof})$, which I can decrypt by using my own secret key $sk_{Prof}$. 

## Your task

Do you see the flaw in this example? If so, well done! You are already a good analyst of security protocols and my request to you is that you share the founded flaw with your colleagues. If not, no worries, this course is about detecting and avoiding flaws of this type. 

## Further reading

The research paper "An Empirical Study of Cryptographic Misuse
in Android Applications" by Egele et al. and published in 2013, showed that  10,327 out of 11,748 Android applications in Google play use cryptographic APIs improperly. 
