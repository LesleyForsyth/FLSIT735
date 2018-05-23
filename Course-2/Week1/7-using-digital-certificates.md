# 

It took us a few steps to learn how to correctly check that a public key does belong to the intended communication partner by means of a trusted third party or certification authority. Thus let us come back to our running example where a professor wants to communicate with one of his students, Paul. The broken protocol we proposed at the beginning of the week is the following. 

![GitHub Logo](./images/msc-charts/flawed-protocol1.jpg)

We already know that we can strengthen this protocol by ensuring that keys are managed properly. Hence we will use a trusted third party for students and professors: the university. Because students and professors are all well-recorded in the university databases, we will assume that the university issues a digital certificate for each student and staff member. Recall that a digital certificate has the following components. 

* $Id$: identifying information of the certificate's owner
* $pk$: public key of the  certificate's owner
* $\{h(Id, pk)\}_{sk_{CA}}$: the signature of the certification authority (CA) over the information above. Mathematically this is the encryption of the hash $h(Id, pk)$ of the information above with the private key $sk_{CA}$ of the certification authority (CA). 

The university has its own pair of public and private key $(pk_{Uni}, sk_{Uni})$. For the sake of simplicity we assume that "Professor" and "Paul" is enough identifying information to characterise the professor and Paul, respectively. Therefore, the university issues the following two certificates.

* $Cert_{Paul} = (``Paul", pk_{Paul}, \{h(``Paul", pk_{Paul})\}_{sk_{Uni}})$
* $Cert_{Prof} = (``Professor", pk_{Prof}, \{h(``Professor", pk_{Prof})\}_{sk_{Uni}})$

Now Paul may ask to receive the digital certificate $Cert_{Prof}$ from the professor rather than an unverifiable public key. By using the university's public key $pk_{Uni}$, Paul is able to verify the correctness of the obtained certificate by executing the following steps. 

1. First, the identifying information ("Professor") and public key $pk_{Prof}$ is extracted from the certificate $Cert_{Prof}$. 
2. Both the identifying information and the certificate are hashed together with a hash function $h$, obtaining the digest $d = h("Professor", pk_{Prof})$.
3. Paul extracts the signature $\{h(``Professor", pk_{Prof})\}_{sk_{Uni}}$ out of the certificate and decrypts it with the public key $pk_{Uni}$ of the university, hence obtaining the plain text $h(``Professor", pk_{Prof})$
4. Finally, Paul verifies that the computed digest $d$ is equal to the decrypted signature $h(``Professor", pk_{Prof})$. If so, then the certificate $Cert_{Prof}$ is correct.  

The improved protocol with certificate verification looks as follows. 

![GitHub Logo](./images/msc-charts/incomplete-protocol-with-certificate.jpg)


## Your task

Your task this time is of a practical nature. You should follow Robert Graham's instructions on how to verify the claim made by the Comodo hacker in 2011. All the joy is at: https://blog.erratasec.com/2011/03/verifying-comodo-hackers-key.html#.WwTi_EgiNPa

