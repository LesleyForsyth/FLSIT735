# Cryptographic keys

While doing your homework in the previous step you probably realised that the Caesar cipher relies on a fundamental assumption: the enemy is not supposed to know that we are shifting each letter three positions within the alphabet. Otherwise the enemy would be able to decipher any encrypted message, as you did in the previous task. 

We can, however, add a bit of uncertainty to the Ceaser cipher by keeping secret the number of shifts the cipher executes. That is, instead of shifting a letter $3$ times, the cipher could shifts $n$ times every letter where $n$ is positive secret number. For example, if $n = 10$, then we obtain the following substitution table. 

| a | b | c | d | e | f | g | h | i | j | k | l | m |n | ñ | o | p | q | r | s | t | u | v | w | x | y | z| 
|---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|
| K | L | M | N | Ñ | O |P | Q | R | S | T | U | V | W | X | Y | Z | A | B | C | D | E | F | G | H | I | J |

Now the encryption of **caesar** would result in **MKÑIKH**, rather than **FDHXDV** as in our previous task. 

You may have noticed already that *cryptography* is a process whereby a plain text is transformed into something that looks like "garbage", but obviously it is not. The plain text is written in a known language, and then transformed into an encrypted text via some encryption algorithm. The encryption algorithm itself is important as we will see in this course. But equally important is a piece of information, known as the *key*, which leads the algorithm to produce an encrypted text that can later be decrypted by the corresponding decryption algorithm. 

## Your task. 

Your task is to find out what's the key in the Caesar chipher. Then you will choose another key and use it to encrypt the following message: ``Hello, I'm X'' where X is replaced by your name. Finally, publish the encrypted message via the chat window. 


