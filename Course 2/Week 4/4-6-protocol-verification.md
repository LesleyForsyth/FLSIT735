# Protocol verification

 Finding flaws in security protocols is in practice extremely hard, requiring years of experience as a protocol analyst.
 
 So for those of you who found the flaw in the protocol given in the previous step's task, congratulations!
 
  Fortunately, there are tools that can help us with finding flaws. Although learning how to use these tools is not the aim of the course, we would like to show you how they work, to make you aware of their potential. 

### The Scyther tool 

In this demonstration we are going to use the Scyther tool ([see installation instruction](https://www.cs.ox.ac.uk/people/cas.cremers/scyther/install-generic.html)). This tool was developed at the University of Luxembourg and it is currently maintained by Prof. Cas Cremer at the University of Oxford. Scyther has been used to analyse various security standards, such as the IKEv1 and IKEv2 protocol suites and the ISO/IEC 9798 family of authentication protocols. 

We have developed the code for you the protocol we asked you to analyse in the previous task. The source code in Scyther looks as follows.

```
usertype String;

const hello-paul: String;
const hello-professor: String;

protocol professor-paul-protocol(Prof,Paul)
{
	role Prof
	{
		fresh n: Nonce;
		
		send_1(Prof,Paul, (hello-paul, n));
		recv_2(Paul,Prof, ({{hello-professor}pk(Prof)}sk(Paul), n));

		claim(Prof,Niagree);
	}	
	
	role Paul
	{
		var N: Nonce;
		
		recv_1(Prof,Paul, (hello-paul, N));
		send_2(Paul,Prof, ({{hello-professor}pk(Prof)}sk(Paul), N));

	}
}
```

Scyther will identify an attack to the above protocol which is similar in nature to a replay attack, which works as follows:

 The attacker eavesdrops the first communication between the professor and Paul, keeping a record of Paul's message: $$\{$$\{$Hi professor, this is my secret...$\}_{pk_{Prof}}$ $\}_{sk_{Paul}}, n$$, where $$n$$ is the nonce used by the professor. Once the professor executes the protocol a second time to get an update on how Paul feels, he sends a different nonce, say $$n'$$. The adversary then replays the previous message ($$\{$$\{$Hi professor, this is my secret...$\}_{pk_{Prof}}$ $\}_{sk_{Paul}}, n$$) with a small modification. Instead of $$n$$ the attacker will use $$n'$$. The Professor will then happily accept the response as valid. As usual, a graphical representation is given next. 

![GitHub Logo](./images/msc-charts/replay-attack-protocol-with-nonces.jpg)

## Your task

Explain why this attack is not possible in the following protocol.

![GitHub Logo](./images/msc-charts/secure-protocol-with-nonces.jpg)

