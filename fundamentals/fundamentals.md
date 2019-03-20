# Information security lifecycle

Information is an asset, and separate from physical assets. Arguably more valuable.

Technical security does not by itself protect against fraud. Administrative security covers unauthorized access to data.

Security is 3 parts: Technical security (passwords and such), Administrative security (policies and procedures) and finally physical security.

What does it mean to be secure? CIA: Confidentiality, Integrity and Availability.

C: username/password. For ensuring the right people only have access.
I: mitm attacks, information is visible and manipulatable.
A: ddos, destroying data etc. Clustering, backups provide availability.

For example, encryption provides both C and I.

There should be multiple layers of security: Prevention, Detection and Recovery.

## Access controls

These are similar to security layers: prevention, detection and correction. They are in support of the CIA triad.

Access control is usually first major control: authentication, authorization (permissions) and accounting.

Others include

* The CIA Triad
* Non-repudiation
* Identification
* Authentication
* Authentication Factors
* Authorization
* Access Control
* Access Control Models
* Accounting and Auditing
* Common Security Practices
* Implicit Deny
* Least Privilege
* Separation of Duties
* Job Rotation
* Mandatory Vacation
* Time of Day Restrictions
* Privileged Management

## Authentication

Is the first step of access control. Identification also helps with accountability and logging. We can't just have only password.

There are 3 types: something you know (password), something you are (fingerprint), something you have (fob. Synchronous[time-sensitive] and asynchronous). Async devices need a pin number to generate a password.

The problem with biometrics is there is some error values. It is a sensitivity vs failure attempt. Increasing sensitivity increases number of failures, FRR=false rejection error, or Type 1 error. If I decrease the sensitivty, we get FAR=false acceptance rates increases, Type 2. The intersection of the two curves is CER=crossover error-rate. I want a low CER.

## Access control

There are 3 types of access controls: technical, physical and administrative.

It's usually the first step and is AAA: (identification and) authentication, authorization and accounting/logging.

1. Identify the individual or entity.
2. Verify the identity.
3. Evaluate the rules, roles or permisssions.
4. Log each access attempt and function performed
5. Review the logs.

Access control categories are composed of different layers: preventative, detective, corrective and directive/deterrent(like a sign saying for authorized people only and is important for legal perspective).

Access control function implementation

|       	|  Administrative 	|   Physical	|  Technical 	|
|:-------|---	|---	|---	|
| Directive  	|   x	|   	|   	|
| Preventative  |  x 	|  x 	|  x 	|
| Detective  	|   	|  x 	|   x	|
| Corrective  	|   	|   	|   x	|
| Deterrent  	|   	|   x	|   x	|
|  Recovery	    |   x	|   	|   x	|
| Compensating  |   x	|   	|   x	|

There are two access control models, DAC and MAC.
DAC(discretionary access control) is basically a matrix/table with all the users, all the resources and in each cell the kind of permissions given.

MAC(mandatory access control). Found in military and government. You need to

1. classify information (secret, top secret, confidential)
2. Then assign clearance or categories to each user.

The owner of the data should be the one assigning permissions, not necessarily the technical person.

Third type of AC is NDA. This has things like role-based (for example HR members) or rule-based (firewalls).

## Implementing security

Where to start? Begin by identifying risk, and then accordingly implement proper controls and counter-measures.

Risk vs threat. Fire is a threat, risk is business terminilogy that quantifies the loss, usually monitary. The amount of loss == risk. Usually coupled with probability.

Threat is hacking, theft, earthquakes.

Vulernability is something that is unsecured.

## Cryptography

Encryption protocols and algorithms should be public, but the keys should be secret.

128 bit keylength == 2^128 permutations.

Encryption protocols use transposition and subsitution.

### Symmetric encryption

DES, 3DES, IDEA, AES, Blowfish.

For symmetric we use the same key for encryption and decryption. The problem is you now need to send the key to the decryptor.

It uses stream cipher and block cipher. Block cipher means dividing the text into blocks, then encrypt each block by itself, then move those blocks around. To decrypt you must reorganize and then combine and then decrypt.

Stream cipher encrypts byte by byte using XOR.

Initialization vector is 1 extra byte added to the key for extra randomization. This means we'll have a different hash, even for the same protocol and text.

Main problem with this type is that you'll need a huge amount of keys. n*(n-1)/2 for n=number of users. Key management is a problem.

EEE3 means encrypt 3 times with 3 different keys.
EDE2 means encrypt decrypt then encrypt again with 3 different keys.

### Asymmetric

RSA, Elgamal, ECC (designed for small devices).

Each user has 2 keys, mathematically related. Whatever is encrypted with public key can only be decrypted with private key. If I want to send an email to Alice, I use alice's public key, then send the cipher text. Alice decrypts with her private key.

A digital certificate has 2 functions. 1. Verifies that you are who you say you are by the issuer/authority. 2. It allows https using pub/private keys that come with the cert.

You can also implement your own certificate authority within your org.

If I encrypt a message with my private key and send it out, anyone with my public key can decrypt it. While this doesn't provide privacy, it does provide proof of ownership otherwise known as non-repudiation. This is the idea behind a digital signature.

### Hashing

We can use cryptopgrahpy for veryfying the integrity of a file. If the file changes, the hash will change. So, whenever I send somone a file I'll also send the hash, which should match if they were to hash the file themselves. It does not work in reverse. Hashing is only 1 way.

### Steganography

Hiding information inside a picture. It's a kind of cipher. In hex editors, all jpgs start with FF D8 and end with FF D9. If you examine the hex you can deduce if a file contains another hidden jpg, or other data. Hex editors also contain metadata like date, the type of camera and gps location.

### Policy

Falls under administrative security (recall the other two are technical and physical). These are the business functions that secure your data.