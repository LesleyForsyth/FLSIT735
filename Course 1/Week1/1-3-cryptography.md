# Cryptography 

Humanity has developed extremely sophisticated communication languages in the form of symbols, words, and sounds, that together convey meaningful information. What is less obvious, is our ability to send information through public or insecure channels that only makes sense to a selected group of people. At the corporate and governmental level the ability to exchange confidential information gives an strategical advantage over the competition. At the individual level, people are interested on protecting their personal information against neighbors, jealous spouses, dictatorships, etc.

Hieroglyph is one the oldest language of symbols ever created. And this code was secret for everyone, but the Scribes. The scribes eventually despaired, but the mystery of what have been written in those stones remained until the 19th century, when Jean-François Champollion deciphered the Rosetta hieroglyphs. 

Many secret languages of symbols have been created, and you probably have developed one yourself to communicate with a colleague at School. The problem is that a secret language can hardly remain secret for a long time and, at the same time, replacing it is time consuming or even unfeasible. That is why the Caesar in Rome used a different mechanism to exchange confidential information. The well-known Latin language would be used by the Romans, but every letter is replaced by the letter that comes three positions later in the alphabet. That substitution was as follows. 

| a | b | c | d | e | f | g | h | i | j | k | l | m | n | ñ | o | p | q | r | s | t |
-------------------------------------------------------------------------------------
| D | E | F | G | H | I | J | K | L | M | N | Ñ | O | P | Q | R | S | T | A | B | C |

For instance, the plain text *caesar* would result in the encrypted text FDHXDV. 

It is probably a good time to define *cryptography* as a process whereby a plain text is transformed into something that looks like "garbage", but obviously it is not. The plain text is written in a known language, and then transformed into an encrypted text via some encryption algorithm. The encryption algorithm itself is important as we will see in this course. But equally important is a piece of information, known as the *key*, which leads the algorithm to produce an encrypted text that can later be decrypted by the corresponding decryption algorithm. 

To fully understand what we mean by an encryption and decryption algorithm we ought to relay on mathematics. Let $m$ be a message encoded in a binary alphabet $\{0, 1\}$, as the one used by current computers. Let $k$ be a text encoded in the same binary alphabet. An encryption algorithm is a function $f(m, k)$ that, on input a message $m$ and a key $k$, gives an *encrypted message* $m'$. The corresponding decryption algorithm is defined in a similar way, as a function $f^{-1}(m, k)$ that, on input an encrypted message $m'$ and a key $k$, gives the *original message* $m$. We can make even more precise the intended property by requiring that $f^{-1}(f(m, k), k) = m$, that is, a message $m$ encrypted with a key $k$ can be always decrypted by using the same key $k$.

![GitHub Logo](/images/encryption-model.jpg)
Format: ![Alt Text](url)

## Your task. 

Your task is to find out what's the key in the Caesar chipher. Then you will choose another key and use it to encrypt the following message: ``Hello, I'm X'' where X is replaced by your name. Finally, publish the encrypted message via the chat window. 