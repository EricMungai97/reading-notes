# Cryptography

[Source](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)

**Caesar cipher**

Simplest and most widely know encryption technique.

It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
 
For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. 

This is an example of a `substitution cipher`

**Encryption**:

scrambling the data according to a secret key.

**Decryption**

Recovering the original data from scrambled data by using the secret key.

**Code Cracking**

Uncovering the original data without knowing the secret, by using a variety of clever techniques.


Encryption machines example include the enigma machine used by the Germans

**One way functions**

Mathematical functions that are easy to do in one direction, but are hard to reverse.

**Polymorphism** 

A cipher that changes itself with each use. Meaning that each time it is used, it produces a different set of results. So, if you encrypted the exact same set of data twice, each new encryption would be different from the previous one.



There are four primary types of cryptography in use today, namely:

[source](https://thebestvpn.com/cryptography/)

* Hashing 

* Symmetric cryptography

* Asymmetric cryptography

* Key exchange algorithms

***Hashing***

Hashing is a type of cryptography that changes a message into an unreadable string of text for the purpose of verifying the message’s contents, not hiding the message itself.

This type of cryptography is most commonly used to `protect the transmission of software and large files` where the publisher of the files or software offers them for download. 

Most common hashing algorithms are MD5 and SHA-1

***Symmetric Cryptography***

This type of cryptography uses a single key to encrypt a message and then decrypt that message upon delivery.

Its primary application is the protection of resting data since it requires that you have a secure channel for delivering the crypto key to the recipient, this type of cryptography is all but useless for transmitting data.

Most modern symmetric cryptography relies on a system known as `Advanced Encyrption Standards.`

***Asymmetric Cryptography***

Uses two different keys for encryption and decryption, as opposed to the single key used in symmetric cryptography.

The first key is a public key used to encrypt a message, and the second is a private key which is used to decrypt them.

It is used when transmitting email files, remotely connecting to servers, and even digitally signing PDF files.

***Key Exchange Algorithms***

A key exchange algorithm, like `Diffie-Hellman`, is used to safely exchange encryption keys with an unknown party.

There are four primary ways that cryptography is implemented in information security. These applications are called `cryptographic functions`.

They include :

1. Authentication

2. Non-repudiation

To prevent people from making false claims.

3. Confidentiality

With the right encryption tools, users can guard sensitive company data, personal medical records, or just lock their computer with a simple password.

4. Integrity

Ensuring that data is not viewed or altered during transmission or storage.

## Things I want to know more about

Entropy and Random Number Generation