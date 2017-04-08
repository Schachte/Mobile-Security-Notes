# **Security Basics in Mobile Computing**

## Problems with Mobile Apps

    - Poor session management
    - Data leakage and lack of encryption
    - Insufficient input validation

## Security Problems in Medical Control Apps

    - Sensors have poor security protocols
    - They don't have the resources for strong security
    - Unprotected wifi, low storage, etc.

## Mobile App Safety Inter-relation

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

<hr>

## Symmetric Key Example

    - Substitution Cipher
        . Substituting one thing for another 
        . Basic plaintext, but letters are changed into a corresponding cipher text
    - How hard is it to break such a simple cipher?
        . You can try to find the most used letters, look at the frequency distribution of the words and try to break it
        . Compare the frequency distribution of the cipher text with english word distribution
        . The effort to brute-force such a problem would be 26! * number of letters.
        . The problem is you don't know what the correct end result is..
        . 26 raised to the power of the 26 depending on what matching algo. you use

<hr>

## Symmetric Key Properties

    - Bob and Alice sharew the same symmetric key K.
    - Alice sends a message encrypted with the K(a-b) cipher.
    - Symmetric keys mean if Bob decrypts the message with the K(a-b) cipher he will get the original
        . K(a-b(message)) -> K(a-b(K(a-b(message)) = message

## DES Crypto vs. AES Crypto

    - 56bit, not very secure. Takes a couple days to break. 
    - AES comes along and it's 256bit. (Exponential increase in time to break) 149 trillion years.
    - Almost impossible to store on sensors, the primes are too large to store on small devices

## Public Key Cryptography

    - Sender and receiver do not share the same private key.
    - Public encryption key is known to everyone
    - Private decryption is only known to the receiver
    - There is no hard and fast rule that public is always public and private is always private
    - Properties of Public Key Encryption
        1) Need + and - key for a single person s.t. KB-(KB+(message)) = message
        2) Given public key (+) it should be impossible to compute the private key (-)

## Example of Public Key Working

    - Alice sends Bob a message with Bob's public key. 
    - He simple uses his private key on K(b+(m)) to get the original message

## Choosing keys for RSA
    
    1) Must agree on two large prime numbers (1024 bits each) - 2^(sqrt(n)/2) exponential
    2) Compute n = pq, z = (p-1)(q-1)
    3) Choose e with no common fsctors
    4) Choose d st e*d - 1 is exactly divisible by Z (ed mod z = 1)
    5) Publickey is (n,e) private key is (n,d)

## Decrypting RSA

    1) Given the (n,e) and (n,d) as computed above
    2) Encrypt bit pattern m, c = m^e mod n
    3) Decrypt bti pattern c, m = c^d mod n
    4) m = (m^e mod n)^d mod n

## Cryptographic Hash

    - Message integrity, message sent from someone to another person can make sure not tampered with
    - Takes input m, produces fixed length value
    - Computationally impossible to find two different message x,y suck that H(x) = H(y).
    - Finding a collision with X will take years to find Y.
    - Impossible to reverse a cryptographic hashing function

## Digitial signatures

    - Take your private key and encrypt message send to someone
    - They verify the message contents by applying public key on item
    - However, encrypting a long message with private key is too expensive, so you use hash function
    - To verify the integiry of the digest, you apply hash to the large message H(m), then you run the private key onto the hash and it should equal H(m) <- Confusing. 
    - Banjeree says these are legacy algorithms.. Doesn't matter tbh.




    
