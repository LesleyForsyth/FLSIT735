# Wrapup

In this week you have learned:

* that cryptographic keys need to be handle with care, otherwise cryptography is useless
* that certification authorities are trusted third parties in charge of distributing digital certificates that convey correct public keys
* how a client can verify the authenticity and integrity of a certificate by checking the digital signature of the certificate
* that confidentiality in many applications is not enough; security protocols must resist other attacks as well, such as replay attacks. 
* Protection against replay attacks is achieved by introducing fresh data at every execution of a protocol, such as a nonce
* We can verify that security protocols do their job by using formal verification tools, such as Scyther
