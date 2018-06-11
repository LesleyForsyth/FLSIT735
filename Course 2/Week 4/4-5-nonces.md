# Nonces

Cryptographic keys are randomly chosen from a large key space so they tend to be unique. A *nonce* -a number used only once- is similar. 

A nonce is chosen randomly from a large number space, but, different to cryptographic keys, is meant to be used only once and tossed away immediately.

# Salted passwords

One of the earliest application of nonces in computer security can be found in the way operating systems store our passwords. Operating systems do not store our passwords in plaintext. Otherwise an attacker that successfully hacked our system and got administration rights would learn _everyones_ password.

Instead, a hash function is applied over every password. For example, instead of storing the password "password" (**never** use this password), the operating system stores the hash of "password", which might look like: 72AE25495A7981C40622D49F9A52E4F1565C90F048F59027BD9C8C8900D5C3D8

Because you have been doing your homework, you probably know that hash functions are hard to reverse. Thus a hacker with access to the password file of a operating system won't be able to obtain the original passwords easily. As written in the famous book "The Cuckoo’s Egg: Tracking a Spy Through the Maze of Computer Espionage": "..there's no way to reconstruct the avocado from the guacamole..." (Stoll 1989)

However, hackers don't need to reverse a hash function in order to guess the password that has been hashed. Instead, they can compute the hash of all words in a *dictionary.* If one of the words match up to the password, then it's been cracked. This technique is known as *dictionary attack* and still works. 

But we can make the life of hackers harder by adding a nonce to our passwords, known as a *salt*. Instead of hashing the word "password", we would hash the word "password+E1F53135E559C253" where E1F53135E559C253 is a nonce. Doing so, we force the hacker's dictionary to include each potential salt, which can be arbitrarily large. 

All operating systems and web server nowadays used salted passwords. 

### Using nonces in security protocols

To secure communication protocols against replay attacks, a similar technique to the addition of a salt to a password is applied. If a participant wants to start communicating, then a nonce is chosen and used during the whole session. For the next session, a different nonce is used, and so on. Let us see how this works in our running example: 

![GitHub Logo](./images/msc-charts/secure-protocol-with-nonces.jpg)

Now a replay attack would fail, because every execution of the protocol will start with a nonce $$n$$ that will never repeat. 

### Your task

Can you tell whether the following protocol resists replay attacks?

![GitHub Logo](./images/msc-charts/weak-protocol-with-nonces.jpg)

Why would it work?  Why would it fail?

###### Reference:

###### Stoll, C 1989, _The cuckoo's egg : tracking a spy through the maze of computer espionage_, New York : Doubleday



