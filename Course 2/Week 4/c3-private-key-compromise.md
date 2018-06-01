# Private key compromise

A certification authority called *Trustico* announced in March 2018 that as many as $23,000$ certificates will be re-generated because their private keys got compromised. It is unclear how those private keys were compromised. But companies ought to act quickly if the are certain or even suspect that their private keys are no longer secret. 

The lesson we should learn from the Trustico case is that, as security experts, we should be ready for the worst. And leaking a private key is close to be the worst that can happen to an organisation. Of course, public key infrastructure offers mechanisms to recover from key compromises, which essentially consists on tossing out any certificate that relies on a compromised key. This process is known as *revocation*.

## Revocation 


