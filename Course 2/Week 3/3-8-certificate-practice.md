# Self-signed certificates

Should certification authorities use certificates? If so, who signs their certificates?

The answer to the first question is, yes. Certification authorities, as many other communicating entities on the internet, need to convey their own public keys to their clients and need to use certificates to do so. However, while others rely on certification authorities to issue their certificates, who issues the certificate of a certification authority? 

Well, themselves. 

You may think that this sounds like a bad idea, because everyone can create their own self-signed certificate. 

Let's have a go at that, then, and we'll come back to the question of whether or not it's a good idea for an authority to sign their own certificate after we've create our own.

### Creating a self-signed certificate with OpenSSL

As we did in right back in the first week, we are going to use OpenSSL to create cryptographic keys, encrypt, decrypt, and also create certificates. 

* Our first step is to create a private key, which we do by executing the command line `openssl genrsa -out private-key.pem 2048`

    - `genrsa` is a command used to RSA private keys
    - Recall that `-out` indicates the output file

* Now we are going to create a Certificate Signing Request (CSR). The CSR contains our identifying information, our public key, and much more. Sending the CSR help us obtain a certifice from a Certificate Authority. As you may have guessed, such a request should be signed, etc. However, we don't need those details here. Just bare in mind that at the very least a CSR contains our identifying information and public key. 

We can create a CSR with OpenSSL by executing the following: `openssl req -new -key private-key.pem -out certificate-request.csr`
    - `req` is the openssl command that manages certificate requests

* You will notice that the command req asks for additional information, such as your country, province, institution, etc. 

* Finally, we sign our own certificate request with our private key.  This is why it's called a self-signed certificate. To do so execute: `openssl x509 -req -in certificate-request.csr -signkey private-key.pem -out my-first-certificate.crt -days 365`

    - `x509` is an openssl command to manage X.509 certificates. X.509 is a standard that defines the format of public key certificates. Standardisation is important in IT, so we will explain X.509 certificates in more details later in this course.
    - `-req -in` indicates the input file containing our CSR
    - `-signkey` indicates the file with the private key we used to generate the CSR
    - `-out` as usual this sets the output file
    - `-days` sets the expiration date of the certificate within 365 days after its creation. As with our own passwords, certificates ought to be changed frequently. 

You may have noticed that during the process of creating a self-signed certificate we did not create a public key. That is because the `req` command generates a valid public key for us and stores it in the CSR. However, the public key can be easily extracted from a certificate with the OpenSSL tool. 

## Your task

All operating systems, browsers, mobile devices and, of course, certification authorities themselves, create self-signed certificates. Trusted self-signed certificates are commonly known as *root certificates*, because they are at the root of the hierarchy of trust between certification authorities. Your task is to find all the root certificates installed at your operating system. 

What did you notice?

