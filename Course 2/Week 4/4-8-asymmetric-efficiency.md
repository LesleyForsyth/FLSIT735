# The cost of public key infrastructure 

Public key encryption has enabled security solutions that were unthinkable during the era of symmetric encryption.

It allows messages to be signed and public keys to be distributed at will. In comparison with its counterpart, the symmetric cryptographic, asymmetric cryptography offers much more than simple encryption and decryption. However, asymmetric cryptography comes at a price: efficiency. 

Asymmetric encryption is slower than symmetric encryption essentially because of two reasons. First, the key length of public key crypto systems is larger. RSA, for example, typically uses keys of size $$1024$$ or $$2048$$ bits, while AES uses keys of size $$128$$ or $$256$$ bits. A larger key size implies computation over larger numbers, hence it puts a greater demand on computational resources. Second, symmetric ciphers are based on simple bitwise operations to achieve confusion and diffusion, such as XOR, modular addition, and lookup operations. Computer hardware has been optimised for decades to execute these type of operations quickly. Asymmetric encryption instead relies on trapdoor functions that are hard to *invert*. In RSA, for example, inverting, which is to say performing decryption in an asymmetric crypto system, requires performing exponentiation and multiplication of $$1024$$ bit numbers. Such operations are by far more complex than a simple addition or XOR.

Because we need our networks to run fast, public key encryption is used as little as possible. Whenever symmetric encryption can be used, then asymmetric encryption is essentially ignored. Does that mean that asymmetric crypto system are not used in practice? Absolutely not. As we saw last week, asymmetric cryptography provides a reliable way to establish trust between two entities in a network. Once this trust is established, symmetric cryptography takes over.  

## Transitioning from an asymmetric to symmetric cryptography

You may be thinking, if I already trust my communications partner, all I need is a shared secret key with which to continue a secure communication, using a symmetric cipher like AES. That's exactly the goal of cryptographic protocols known as *key exchange protocols*, and that's what SSL/TLS does.

Let's take a look at a standard example where a web browser connects to a server, such as Amazon. First, the browser needs to make sure that it is going to use the correct public key for Amazon's web server. For that, the browser requests a certificate from Amazon and verifies it upon reception. Until this point we haven't done anything different to the last week's exercises, except that the name of the communicating entities are different. 

Now comes the trick. Because neither the browser nor Amazon are willing to continuously use public key encryption for communication, the browser generates a temporal key or password. In the figure below this password is set to be "pass123". Of course, the password should remain secret for everyone except for the Amazon server, so the browser encrypts it with Amazon's public key. The remaining traffic will then be encrypted/decrypted using exclusively the key or password "pass123". 


![GitHub Logo](./images/msc-charts/password-exchange.jpg)

## Your task 

Would you use a password for encryption/decryption or a nonce?

Why?