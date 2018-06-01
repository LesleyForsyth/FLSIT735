# Generation of digital certificates

We shouldn't just trust a key or a certificate from anyone.

As we established in the previous step, we must havea lready established a secure channel or a else use a trusted third party to attest the legitimacy of the digital certificate. 


A trusted third party entity in charge of issuing digital certificates is called a *certification authority*. As this course advances you will notice that certification authorities play a prominent role in how critical applications, such as electronic commerce, secure e-mail and virtual private networks, operate on the Internet. Millions of certificates are issued every year by a few certification authorities worldwide, which are used to enable secure communication and protect billions of transactions.

In this step we are going to look at how certification authorities generate digital certificates.

# Content of a digital certificate

A digital certificate typically contains the following information:

* Owner's public key 
* Owner's identifying information
* Certification authority identification

The process (illustrated in the figure below) of obtaining a valid certificate requires the user to generate a pair of public and secret keys. The user then contacts a certification authority to request a valid certificate, binding the user's identity with the generated public key in the process. Recall that the private key should not be distributed, not even to a trustworthy certification authority. The certification authority will then verify the user's identity and approve the generation of a certificate. 

![GitHub Logo](./images/obtain-cert.gif)
<!--- (source: https://sites.google.com/site/ddmwsst/_/rsrc/1472874337832/digital-certificates/obtain-cert.gif) -->

To remain valud, a digital certificate must satisfy the following security requirements:

1. *Identification:* a proper mechanism of identification should be in place to make sure that the owner's data and public key is correct. Note that a user requesting a digital certificate may be a person, organisation, web entity or software application. 
2. *Integrity:* an assurance that a certificate has not been altered (intentionally or not) must be provided. 
3. *Authenticity:* proof that a digital certificate has been issued by a given certification authority should be given.

Certification authorities have different means to identify the owner of a certificate. Depending on the type of the entity requesting a certificate, a certification authority would launch an appropriate verification process. For example, to obtain a certificate for a website, the certification authority may ask you to prove that you have administrative rights to it. If the website is linked to an organisation, then the applicant may need to prove affiliation and administrative rights to that organisation as well. 

Those identification processes are normally administrative and do not depend on cryptography. Thus we are not going to discuss them further in this unit. Integrity and authenticity will be covered in the next steps, though.

## Your task

Discuss how you think university degrees satisfy the three security requirements stated above, namely identification, integrity, and authenticity. 



