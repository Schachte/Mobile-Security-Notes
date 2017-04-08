#**Security Basics in Mobile Computing**

##Problems with Mobile Apps

    - Poor session management
    - Data leakage and lack of encryption
    - Insufficient input validation

##Security Problems in Medical Control Apps

    - Sensors have poor security protocols
    - They don't have the resources for strong security
    - Unprotected wifi, low storage, etc.

##Mobile App Safety Inter-relation

    - Security vulnerabiltiy can cause harm
        . Security protcols can add unexpected delays within the system
        . Improper safety assurance can compromise security

## What Is Network Security?

    - Confidentiality
        . Only the sender intended receiver should understand message contents
    - Authentication
        . Sender, receiver want to confirm identity of each other
    - Message Integrity
        . Verifying that the contents of the message were not altered in any way

## Cryptography Introduction

    - Set of math functions with set of nice properties. 
    - Depends not on the secrecy of the algorithm, but on the parameter of algorithm encryption key
    - In other words, no one cares if you are using obfuscation, xor cipher, AES, etc. It's the parameter that is secret, which is extremely difficult to break.

## Algorithms for Crypto
    
    - Symmetric Key Algorithm
        . One shared by a pair of users used for both encryption and decryption

    - Assymetric or (Public/Private Key)
        . Public - In public
        . Private - Key known only to individual user
