# AES

The insecurity of DES, mainly due to a short key size, led NIST (National Institute of Standards and Technology) to open a public competition for the successor to DES in January 1997.  The criteria used to evaluate a cipher  included not only cryptographic strength or unbreakability, but also ease of implementation and performance in software and hardware. The winner was *the Rijndael cipher*, designed by two Belgian cryptograhers Joan Daemen and Vincent Rijmen in October 2000. 

The Rijndael cipher was formally standarised in November 2001, taking the name of AES (Advanced Encryption Standard). AES is the symmetric cipher of choice for the majority of applications today. AES is even used for keeping secret classified information of the U.S. government.

What does make AES stronger than DES? In short, AES accepts keys of size 128, 192 and 256 bits. Exhaustive search over a key space of size $2^{128}$ is already prohibitive expensive. Fifty supercomputers able to check a billion billion ($10^{18}$) AES keys per second would be capable of checking around $10^{27}$ keys per year. Therefore, it would require around $10^{12}$ years to exhaust the 128-bit AES key space. Whilst DES would be broken in $0.03$ seconds by the same computer configuration. 


AES permits the use of 256-bit keys. Breaking a symmetric 256-bit key by brute force requires 2128 times more computational power than a 128-bit key. 




 (128 bits are enough to resist exhaustive key search; the two other sizes are mostly a way to comply to rigid US military regulations)
has no academic weakness worse than exhaustive key search
should be as fast as 3DES (AES turned out to be much faster than 3DES in software, typically 5 to 10 times faster)
The resistance of AES towards differential and linear cryptanalysis comes from a better "avalanche effect" (a bit flip at some point quickly propagates to the complete internal state) and specially crafted, bigger "S-boxes" (a S-box is a small lookup table used within the algorithm, and is an easy way to add non-linearity; in DES, S-boxes have 6-bit inputs and 4-bit outputs; in AES, S-boxes have 8-bit inputs and 8-bit outputs). The design of the AES benefited from 25 years of insights and research on DES. Also, the AES was chosen through an open competition with 15 candidates from as many research teams around the world, and the total amount of brain resources allocated to that process was tremendous. The original DES designers were genius, but one could say that the aggregate effort of cryptographers for the AES has been far greater.

On a philosophical point of view, we could say that what makes a cryptographic primitive secure is the amount of effort invested in its design. At least, that effort is what creates the perception of security: when I use a cryptosystem, I want it to be secure, but I also want to be certain that it is secure (I want to sleep at night). The public design and analysis process helps quite a lot in building that trust. NIST (the US body for standardization of such things) learned that lesson well, and decided to again choose an open competition for SHA-3.

## Key length 

The first key-recovery attacks on full AES were due to Andrey Bogdanov, Dmitry Khovratovich, and Christian Rechberger, and were published in 2011.[28] The attack is a biclique attack and is faster than brute force by a factor of about four. It requires 2126.2 operations to recover an AES-128 key. For AES-192 and AES-256, 2190.2 and 2254.6 operations are needed, respectively. This result has been further improved to 2126.0 for AES-128, 2189.9 for AES-192 and 2254.3 for AES-256,[29] which are the current best results in key recovery attack against AES.