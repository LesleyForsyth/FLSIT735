# Block ciphers

You may think that it is already time to see a "real-life" cipher, well, almost, but not quite yet. Allow me to list the four main questions you should be able to answer at the moment:

* What does an encryption and decryption algorithm is meant to do?
* When is an encryption/decryption algorithm said to be broken?
* Why is the length of the key important? 
* Why do keys need to be chosen randomly?

## DES

Assume you have a binary message $m$ of size $64$, i.e. $m \in \{0, 1\}^n$. If you are unsure how to convert standard characters in binary code take a look at the UTF-8 table below. Now, because you consider $m$ to convey sensitive information, you would like to encrypt it by using a cipher a lot more stronger than the Caesar cipher. That's exactly the task that the US standards body NBS (National Bureau of Standards) identified as a need back in 1973. 

![GitHub Logo](./images/binary-conversion.png)
<!--- (source: http://www.sciencefriday.com/wp-content/uploads/2015/08/UTF8-Table-7802.png) -->

After two years of submission and evaluation of different ciphers, a candidate proposed by IBM and known as DES was deemed acceptable. DES consists of a sequence of scramble operations, one after the other, such as permutation, XOR, and mapping. We leave the details of the operations within DES to a crypto course. But we provide next a figure that depicts how a plaintext is transformed into a ciphertext by means of $16$ rounds of scramble operations. 

![GitHub Logo](./images/DES.png)
<!--- (source: https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/DES-main-network.png/250px-DES-main-network.png) -->

## The end of DES

DES was widely used for government and industry cryptography for more than two decades. However, in 1999 researchers broke DES by using the power of a  distributed computer system.

Why was DES broken? The simple answer is that the key length was *too* short. DES was designed with an effective key length of 56 bits, which was hard to break at the time of its design. However, computers quickly became stronger, hence DES became vulnerable to exhaustive search. Exhaustive search is what you did in a previous task by trying out *all possible* 26 keys that the Caesar cipher can use. In the case of DES, one can try out all $2^{56}$ possible keys. 

## Your task

In order to get a feeling on how expensive exhaustive search can be, I encourage you to write a small program in your favorite programming language that iterates from 1 to $2^{56}$. Because here we are not evaluating your ability to write computer programs, we provide an example of such a program in Java next. 

~~~ java
public static void main(String[] args) {
    
    for (int n = 1; n <= 56; n++) {
        System.out.println("Iterating from 2 to the power of "+(n-1)+" to 2 to the power of "+n);
        for (int i = (int)Math.pow(2, n-1); i < Math.pow(2, n); i++);
    }
}
~~~

