# Confidentiality and integrity

Because you already know how to sign a message, you can improve the protocol we have been analysing since the start of the week by simply making the professor to sign the first message. The resulting protocol would look as follows.

![GitHub Logo](./images/msc-charts/flawed-protocol3.jpg)

You may notice that the new protocol has an extra message, in which the professor sends his public key unencrypted. This is needed because we are assuming that Paul does not know the public key of the Professor, which would prevent him from decrypting the first message. Paul is convince 
