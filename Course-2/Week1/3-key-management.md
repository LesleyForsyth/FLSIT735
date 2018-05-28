# Key management

Cryptography works under the assumption that the sender and the receiver share some secret key. 

It most be clear at this point that cryptography, although extremely strong and important, is by itself insufficient to secure your computer systems. One can use cryptography just in the wrong way, as in the bike example provided in the previous step, or fail to manage and storage cryptographic keys properly. 
We will focus first on the second issue, that is, how to properly exchange and storage cryptographic keys. 

The question we would like to address here is: how Paul can be sure that he is using the public key of the professor and not the public key of an attacker? 

## Secure channel

A solution to the question above can be the use of a secure channel. For example, the professor can give his public key to the students in person. This, however, does not work with online students. For online students an alternative can be FutureLearn, which is indeed a secure medium of information exchange between students and professors. 

## Trusted third party

When there is no secure channel to exchange cryptographic keys, as in electronic commerce applications, the most common alternative is to rely on a trusted third party. Trusted third parties are commonplace in everyday life. We rely on university degrees as a proof of knowledge because the society trusts on universities, on driving licenses as a proof of driving skills because the police trusts the driving regulations imposed by a government, etc. 

## Digital certificates

Proof of ownership of a public key in computer networks are handled similarly to a proof of knowledge in current society, that is, by providing a valid *digital certificate*. 
Not everyone is allowed to issue digital certificates, in the same way that not every institutions is allowed to issue university degrees. It would be particularly dangerous if we accept digital certificates from an attacker. Therefore, every computer system has a list of *certification authorities*, which are entities authorised to issue certificates, in which to trust. 

## Your task

A software that makes heavy use of digital certificates is your web browser, being either Mozilla, Chrome, Opera, Zafari, etc. Your task is to go to the advanced settings of your browser and find the list of "Trusted Root Certification Authority". In Chrome, for example, that list is within the "manage certificates" section. Share with your colleagues the number of certificate issuers that your browser trust on. 

