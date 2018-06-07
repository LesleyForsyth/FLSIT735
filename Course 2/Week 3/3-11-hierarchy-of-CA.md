# Hierarchy of Certification authorities 

You're probably already familiar with the concept of a bottleneck in information systems. An overloaded component in a system may severely limit its capacity  to process information and react to requests. These days, you're pretty unlikely to buy a single-core processor.  Instead, most people would go for a multi-core processor (like Intel Core i7) with two or more independent processing units called *cores*. Each core individually may be less powerful that a single-core processor, but in combination they overcome the bottleneck problem and allow for parallelism.

Well, millions of digital certificates are requested every day. 
Take a look to the picture below, which shows only shows certificates issued by [Let's Encrypt](https://letsencrypt.org/). If we were to rely too heavilty on a few certification authorities such as Comodo and VeriSign, we would create a bottleneck. As a result, we need to extend the trust we have of these main certification authorities to other entities as well. 

![GitHub Logo](./images/number-of-certificates.png)
<!---
(source: https://letsencrypt.org/stats/)
-->

Another drawback of having just a few certification authorities is reliability. Assume there is only one certification authority who all of us need to trust. If it was hacked, the whole world would be compromised, potentially leading to a catastrophe of unknown consequences. The diversification of certificate authorities reduces the risk of a single point of failure.

## Chain of certificates

Of course, it wouldn't be very helpful if we blinded trusted anyone and everyone just for the sake of diversity.  Nor would it help to distribute certificates randomly.  Instead, we use a hierarchical structure which resembles the way governments and militaries are organised. Such a hierarchical structure works as follows:

* The main certification authorities are called *root certification authorities.*  These sit at the top of the hierarchy. As we have seen and executed ourselves a little earlier, these authorities self-sign their certificates.
* Each root certification authority has subordinate certification authorities. Just like anyone else, the subordinate certification authority will need at least one valid certification to prove authenticity. This certificate should by the parent and root certification authority.
* Subordinate certification authorities can have their subordinate certification authorities, and so on.

The hierarchy of certification authorities looks a bit like the image below.

![GitHub Logo](./images/hierarchy-CA.gif)
<!---
(source: https://docs.oracle.com/cd/E19424-01/820-4811/images/hier.gif)
-->

Having a hierarchy of certification authorities helps with diversification by distributing the task of issuing certificates across a wide range on entities.
But it complicates the task of verifying the authenticity of a certificate. For example, assume we receive a certificate signed by "Engineering CA" but our system only trusts "Root CA".  In this case, we trust the certificate because a 'chain of trust' has been established - "Engineering CA" trusts "USA CA" who, in turn, trusts "Root CA."

Chains of trust are fundamental in any hierarchical structures across our society. But we do need to verify that the chain is correct. If someone comes to you and tells you- hey 'I'm the Minister of Education,' you are not going to believe that straight away. You would run your own verification process. The chain of trust in a hierarchy of certification authorities can be verified in a simple way. 

* All certificates issued by "Engineering CA" will contain a valid certificate from "USA CA", which is the parent certification authority. Thus, if a client does not trust "Engineering CA" it can still verify "USA CA" issued a valid certificate for "Engineering CA". 
* This process is repeated until we get to the root of the hierarchy. For example, if the client does not trust "USA CA" either, then it can still verify "Root CA", because all certificates given to "USA CA" contain a valid certificate issued by "Root CA".

A graphical representation of this process is given next.

 ![GitHub Logo](./images/chain-certificate.png)
<!---
(source: https://piv.idmanagement.gov/img/certificatechain_small.png)
-->

## Your task

Your operating systems probably contain certificates signed by subordinate certification authorities. Find one of those and check the "Certification Path". This will give you the chain of trust for that certificate. 

In Windows this can done by:

* going to "Manage Computer Certificates"
* going to "Intermediate Certification Authorities"
* choosing a certificate
* going to "Certification path"

