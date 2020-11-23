# Chapter 4 The Art of Protecting Secrets

## 4.0 Introduction

The principles of cryptology explain how modern day protocols and algorithms secure communications. 

- **cryptology** is the science of making and breaking secret codes. 
- **cryptography** is the development and use of codes . 
- **cryptanalysis** is studying and breaking codes.

 Society has used cryptography for centuries to protect secret documents. For example, Julius Caesar used a simple alphabetic cipher to encrypt messages to his generals in the field. His generals would have knowledge of the cipher key required to decrypt the messages. Today, modern day cryptographic methods ensure secure communications.

**Access control** is, as its name suggests, a way of controlling access to a building, a room, a system, a database, a file, and information. Organizations employ a variety of access control techniques to protect confidentiality. This chapter will examine the four steps in the **access control process**: 

1) identification
2) authentication
3) authorization
4) accountability. 

In addition, the chapter describes the different access control models and access control types.

The chapter concludes by discussing the various ways users mask data. **Data obfuscation** and **steganography** are two techniques used to accomplish data masking.

## 4.1 Cryptography

### 4.1.1 Overview

#### 4.1.1.1 What is Cryptography?

**Cryptology** is the science of making and breaking secret codes. **Cryptography** is a way to store and transmit data so only the intended recipient can read or process it. Modern cryptography uses computationally secure algorithms to make sure that cyber criminals cannot easily compromise protected information.

**Data confidentiality** ensures privacy so that only the intended receiver can read the message. Parties achieve this through encryption. 

**Encryption** is the process of scrambling data so that an unauthorized party cannot easily read it.

When enabling encryption, readable data is plaintext, or **cleartext**, while the encrypted version is encrypted text or **ciphertext**. Encryption converts the plaintext readable message to ciphertext, which is the unreadable, disguised message. **Decryption** reverses the process. Encryption also requires a **key**, which plays a critical role in encrypting and decrypting a message. The person possessing the key can decrypt the ciphertext to plaintext.

Historically, parties have used various encryption algorithms and methods. An **algorithm** is the process or formula used to solve a problem. Julius Caesar is said to have secured messages by putting two sets of the alphabet, side-by-side, and then shifting one of them by a specific number of places. The number of places in the shift serves as the key. He converted plaintext into ciphertext using this key, and only his generals, who also had the key, knew how to decipher the messages. This method is the Caesar cipher. The figure shows a secret message using the Caesar cipher.

#### 4.1.1.2 Creating Ciphertext

Each encryption method uses a specific algorithm, called a **cipher**, to encrypt and decrypt messages. A cipher is a series of well-defined steps used to encrypt and decrypt messages. There are several methods of creating ciphertext:

- **Transposition** – letters are rearranged (Figure 1)

- **Substitution** – letters are replaced (Figure 2)

- **One-time pad** – plaintext combined with a secret key creates a new character, which then combines with the plaintext to produce ciphertext (Figure 3)

Old encryption algorithms, such as the Caesar cipher or the Enigma machine, depended on the secrecy of the algorithm to achieve confidentiality. With modern technology, where reverse engineering is often simple, parties use public-domain algorithms. With most modern algorithms, successful decryption requires knowledge of the appropriate cryptographic keys. <u>This means that the security of encryption lies in the secrecy of the keys, not the algorithm.</u>

Some modern encryption algorithms still use transposition as part of the algorithm.

**Key management** is the most difficult part of designing a cryptosystem. Many cryptosystems have failed because of mistakes in their key management, and all modern cryptographic algorithms require key management procedures. 

In practice, most attacks on cryptographic systems involve attacking the key management system, rather than the cryptographic algorithm itself.

#### 4.1.1.3 Two Types of Encryption

Cryptographic encryption can provide confidentiality by incorporating various tools and protocols.

There are two approaches to ensuring the security of data when using encryption. 

- The first is to protect the algorithm. If the security of an encryption system depends on the secrecy of the algorithm itself, the most important aspect is to guard the algorithm at all costs. Every time someone finds out the details of the algorithm, every party involved would need to change the algorithm. That approach does not sound very secure or manageable. 
- The second approach is to protect the keys. With modern cryptography, the algorithms are public. The cryptographic keys ensure the secrecy of the data. Cryptographic keys are passwords that are part of the input into an encryption algorithm together along with the data requiring encryption.



There are two classes of encryption algorithms:



**Symmetric algorithms** - These algorithms use the same pre-shared key, sometimes called a secret key pair, to encrypt and decrypt data. Both the sender and receiver know the pre-shared key before any encrypted communication begins. As shown in Figure 1, symmetric algorithms use the same key to encrypt and decrypt the plaintext. Encryption algorithms that use a common key are simpler and need less computational power.

**Asymmetric algorithms** - Asymmetrical encryption algorithms use one key to encrypt data and a different key to decrypt data. One key is public and the other is private. In a public-key encryption system, any person can encrypt a message using the public key of the receiver, and the receiver is the only one that can decrypt it using his private key. Parties exchange secure messages without needing a pre-shared key, as shown in Figure 2. Asymmetric algorithms are more complex. These algorithms are resource intensive and slower to execute.

### 4.1.2 Private-key Encryption

#### 4.1.2.1 The Symmetrical Encryption Process

**Symmetric algorithms** use the same pre-shared key to encrypt and decrypt data, a method also known as **private-key encryption**. For example, Alice and Bob live in different locations and want to exchange secret messages with one another through the mail system. Alice wants to send a secret message to Bob. Private-key encryption uses a **symmetric algorithm**. As illustrated by the keys in the figure, Alice and Bob have identical keys to a single padlock. The <u>key exchange happened prior to sending any secret messages</u>. Alice writes a secret message and puts it in a small box that she locks using the padlock. She mails the box to Bob. The message is safe inside the box as the box makes its way through the post office system. When Bob receives the box, he uses his key to unlock the padlock and retrieve the message. Bob can use the same box and padlock to send a secret reply back to Alice. If Bob wants to talk to Carol, he needs a new pre-shared key for that communication to keep it secret from Alice. The more people Bob wants to communicate with securely, the more keys he will need to manage.

#### 4.1.2.2 Types of Cryptography

each method differs in the way that it groups bits of data to encrypt it.

- **block ciphers** =  transform a fixed-length block of plaintext into a common block of ciphertext of 64 or 128 bits. **Block size** is the amount of data encrypted at any one time. To decrypt this ciphertext, apply the reverse transformation to the ciphertext block, using the same secret key.

  Block ciphers usually result in output data that is larger than the input data, because the ciphertext must be a multiple of the block size. For example, Data Encryption Standard (DES) is a symmetric algorithm that encrypts blocks in 64-bit chunks using a 56-bit key. To accomplish this, the block algorithm takes data one chunk at a time, for example, 8 bytes per chunk, until the entire block is full. If there is less input data than one full block, the algorithm adds artificial data, or blanks, until it uses the full 64 bits, as shown in Figure 1 for the 64 bits on the left.

  For example, a 150-bit plaintext provides two blocks of 64 bits each with third block of balance 22 bits. The last block of bits needs to be padded up with redundant information so that the length of the final block equal to block size of the scheme. In our example, the remaining 22 bits need to have additional 42 redundant bits added to provide a complete block. The process of adding bits to the last block is referred to as **padding**.

- **stream ciphers** = Unlike block ciphers, stream ciphers encrypt plaintext one byte or one bit at a time, as shown in Figure 2. Think of stream ciphers as a block cipher with a block size of one bit. With a stream cipher, the transformation of these smaller plaintext units varies, depending on when they are encountered during the encryption process. Stream ciphers can be much faster than block ciphers, and generally do not increase the message size, because they can encrypt an arbitrary number of bits.

  A5 is a stream cipher that provides voice privacy and encrypts cell phone communications. It is also possible to use DES in stream cipher mode.

- Complex cryptographic systems can combine block and stream in the same process.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605968102/Screenshot_2020-11-21_151430_ybqc6f.png"/>

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605968155/Screenshot_2020-11-21_151536_wh1aij.png"/>

### 4.1.2.3 Symmetric Encryption Algorithms

- **3DES (Triple DES):** **Digital Encryption Standard (DES)** 

  - symmetric block cipher with 64-bit block size
  - uses a 56-bit key. 
  - It takes a 64-bit block of plaintext as input and outputs a 64-bit block of ciphertext. 
  - It always operates on blocks of equal size and it uses both permutations and substitutions in the algorithm. A **permutation** is a way of arranging all elements of a set.

  Triple DES encrypts data three times and uses a different key for at least one of the three passes, giving it a cumulative key size of 112-168 bits. 3DES is resistant to attack, but it is much slower than DES. The 3DES encryption cycle is as follows:

  - Data encrypted by first DES
  - Data decrypted by second DES
  - Data re-encrypted by third DES
  - The reverse process decrypts the ciphertext. 

- **IDEA:** The International Data Encryption Algorithm (IDEA) uses 64-bit blocks and 128-bit keys. IDEA performs eight rounds of transformations on each of the 16 blocks that results from dividing each 64-bit block. IDEA was the replacement for DES, and now PGP (Pretty Good Privacy) uses it. PGP is a program that provides privacy and authentication for data communication. GNU Privacy Guard (GPG) is a licensed, free version of PGP.

- **AES:** The Advanced Encryption Standard (AES) has a fixed block size of 128-bits with a key size of 128, 192, or 256 bits. The National Institute of Standards and Technology (NIST) approved the AES algorithm in December 2001. The U.S. government uses AES to protect classified information.

AES is a strong algorithm that uses longer key lengths. AES is faster than DES and 3DES, so it provides both a solution for software applications as well as hardware use in firewalls and routers. Other block ciphers include Skipjack (developed by the NSA), Blowfish, and Twofish.

example des => https://drive.google.com/file/d/1fHAFeqnkDSAw7aLGprSrHPLLaygYcjXm/view?usp=sharing

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605969864/Untitled_Diagram_4_bcooqb.png"/>

### 4.1.3 Public-Key Encryption

#### 4.1.3.1 The Asymmetrical Encryption Process

Asymmetric encryption, also called public-key encryption

- uses one key for encryption that is different from the key used for decryption.
- the message cannot be decrypted with a public key

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605970518/Screenshot_2020-11-21_155508_qhitwl.png"/>

For example, in Figure 1, Alice requests and obtains Bob’s public key. In Figure 2, Alice uses Bob’s public key to encrypt a message using an agreed-upon algorithm. Alice sends the encrypted message to Bob, and Bob then uses his private key to decrypt the message, as shown in Figure 3.

#### 4.1.3.2 Asymmetric Encryption Algorithms

Asymmetric algorithms use formulas that anyone can look up. The pair of unrelated keys is what makes these algorithms secure. The asymmetric algorithms include:

- **RSA (Rivest-Shamir-Adleman)** - uses the product of two very large prime numbers with an equal length of between 100 and 200 digits. Browsers use RSA to establish a secure connection.
- **Diffie-Hellman** - provides an electronic exchange method to share the secret key. Secure protocols, such as Secure Sockets Layer (SSL), Transport Layer Security (TLS), Secure Shell (SSH), and Internet Protocol Security (IPsec), use Diffie-Hellman.
- **ElGamal** - uses the U.S. government standard for digital signatures. This algorithm is free for use because no one holds the patent.
- **Elliptic Curve Cryptography (ECC)** - uses elliptic curves as part of the algorithm. In the U.S., the National Security Agency uses ECC for digital signature generation and key exchange.

> diffie helman analogy
>
> <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Diffie-Hellman_Key_Exchange.svg/1200px-Diffie-Hellman_Key_Exchange.svg.png" width=300/>



### 4.1.4 Symmetric versus Asymmetric Encryption

#### 4.1.4.1 Key Management

includes the generation, exchange, storage, use, and replacement of keys used in an encryption algorithm.

Key management is the most difficult part of designing a cryptosystem. Many cryptosystems have failed because of mistakes in their key management procedures. In practice, most attacks on cryptographic systems target the key management level, rather than the cryptographic algorithm itself.

There are several essential characteristics of key management to consider.

- key generation
- key verification
- key exchange
- key storage
- key lifetime 
- key revocation and destruction 

Two terms used to describe keys are:

- **Key length** - Also called the key size, this is the measure in bits.

- **Keyspace** - This is the number of possibilities that a specific key length can generate.

As key length increase, the keyspace increases exponentially. The keyspace of an algorithm is the set of all possible key values. Longer keys are more secure; however, they are also more resource intensive. Almost every algorithm has some weak keys in its keyspace that enable a criminal to break the encryption via a shortcut.

#### 4.1.4.2 Comparing Encryption Types

It is important to understand the differences between symmetric and asymmetric encryption methods. Symmetric encryption systems are more efficient and can handle more data. 

However, key management with symmetric encryption systems is more problematic and harder to manage. Asymmetric cryptography is more efficient at protecting the confidentiality of small amounts of data, and its size and speed make it more secure for tasks such as electronic key exchange which is a small amount of data rather than encrypting large blocks of data.

Maintaining **confidentiality** is important for both data at rest and data in motion. In both cases, symmetric encryption is favored because of its speed and the simplicity of the algorithm. Some asymmetric algorithms can significantly increase the size of the object encrypted. Therefore, in the case of data in motion, use public key cryptography to exchange the secret key, and then symmetric cryptography to ensure the confidentiality of the data sent.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605972613/Screenshot_2020-11-21_163003_muqxrg.png"/>

#### 4.1.4.3 Applications

There are many applications for both symmetric and asymmetric algorithms.

A one-time password-generating token is a hardware device that uses cryptography to generate a one-time password. A one-time password is an automatically generated numeric or alphanumeric string of characters that authenticates a user for one transaction of one session only. The number changes every 30 seconds or so. The session password appears on a display and the user enters the password.

The electronic payment industry uses 3DES. Operating systems use DES to protect user files and system data with passwords. Most encrypting file systems, such as NTFS, use AES.

Four protocols use asymmetric key algorithms:

- Internet Key Exchange (IKE), which is a fundamental component of IPsec Virtual Private Networks (VPNs).

- Secure Socket Layer (SSL), which is a means of implementing cryptography into a web browser.

- Secure Shell (SSH), which is a protocol that provides a secure remote access connection to network devices.

- Pretty Good Privacy (PGP), which is a computer program that provides cryptographic privacy and authentication to increase the security of email communications.

A VPN is a private network that uses a public network, usually the Internet, to create a secure communication channel. A VPN connects two endpoints such as two remote offices over the Internet to form the connection.

VPNs use IPsec. IPsec is a suite of protocols developed to achieve secure services over networks. IPsec services allow for authentication, integrity, access control, and confidentiality. With IPsec, remote sites can exchange encrypted and verified information.

Data in use is a growing concern to many organizations. When in use, data no longer has any protection because the user needs to open and change the data. System memory holds data in use and it can contain sensitive data such as the encryption key. If criminals compromise data in use, they will have access to data at rest and data in motion.

## 4.2 Access Controls

### 4.2.1 Types of Access Controls

- physical
- logical
- administrative
- mac
- dac
- rbac

### 4.2.3 Identification

#### 4.2.3.1 What is Identification?

enforces the rules established by the authorization policy. A subject requests access to a system resource. Every time the subject requests access to a resource, the access controls determine whether to grant or deny access. For example, the authorization policy determines what activities a user can perform on a resource. A unique identifier ensures the proper association between allowed activities and subjects. A username is the most common method used to identify a user. A username can be an alphanumeric combination, a personal identification number (PIN), a smart card, or biometric, such as a fingerprint, retina scan, or voice recognition. A unique identifier ensures that a system can identify each user individually; therefore, allowing an authorized user to perform the appropriate actions on a particular resource.

### 4.2.4 Authentication Methods

#### 4.2.4.1 What You Know

#### 4.2.4.2 What You Have

### 4.2.4.3 Who You Are

#### 4.2.4.4 Multi-factor Authentication

#### 4.2.4.5 Activity - Identify Authentication Methods

### 4.2.5 Authorization

#### 4.2.5.1 What is Authorization?

controls what a user can and cannot do on the network after successful authentication. After a user proves his or her identity, the system checks to see what network resources the user can access and what the user can do with the resources. As shown in the figure, authorization answers the question, “What read, copy, create, and delete privileges does the user have?” Authorization uses a set of attributes that describes the user’s access to the network. The system compares these attributes to the information contained within the authentication database, determines a set of restrictions for that user, and delivers it to the local router where the user is connected. Authorization is automatic and does not require users to perform additional steps after authentication. Implement authorization immediately after the user authenticates.

#### 4.2.5.2 Using Authorization

### 4.2.6 Accountability

#### 4.2.6.1 What is Accountability?

traces an action back to a person or process making the change to a system, collects this information, and reports the usage data. The organization can use this data for such purposes as auditing or billing. The collected data might include the log in time for a user, whether the user log in was a success or failure, or what network resources the user accessed. This allows an organization to trace actions, errors, and mistakes during an audit or investigation.

#### 4.2.6.2 Implementing Accountability

### 4.2.7 Types of Security Controls

#### 4.2.7.1 Preventive Controls

#### 4.2.7.2 Deterrent Controls

#### 4.2.7.3 Detective Controls

#### 4.2.7.4 Corrective Controls

#### 4.2.7.5 Recovery Controls

#### 4.2.7.6 Compensative Controls

#### 4.2.7.7 Activity – Compare Types of Security Controls

## 4.3 Obscuring Data

### 4.3.1 Data Masking

#### 4.3.1.1 What is Data Masking?

Data masking technology secures data by replacing sensitive information with a non-sensitive version. The non-sensitive version looks and acts like the original. This means that a business process can use non-sensitive data and there is no need to change the supporting applications or data storage facilities. In the most common use case, masking limits the propagation of sensitive data within IT systems by distributing surrogate data sets for testing and analysis. Information can be dynamically masked if the system or application determines that a user request for sensitive information is risky.

Data masking can replace sensitive data in non-production environments to protect the underlying information.

There are several data masking techniques that can ensure that data remains meaningful but changed enough to protect it.

#### 4.3.1.2 Data Masking Techniques

**Substitution** replaces data with authentic looking values to apply anonymity to the data records.

**Shuffling** derives a substitution set from the same column of data that a user wants to mask. This technique works well for financial information in a test database, for example.

**Nulling** out applies a null value to a particular field, which completely prevents visibility of the data.

### 4.3.2 Steganography

#### 4.3.2.1 What is Steganography?

conceals data (the message) in another file such as a graphic, audio, or other text file. The advantage of steganography over cryptography is that the secret message does not attract any special attention. No one would ever know that a picture actually contained a secret message by viewing the file either electronically or in hardcopy.

There are several components involved in hiding data. 

- First, there is the embedded data, which is the secret message. 
- The cover-text (or cover-image or cover-audio) hides the embedded data producing the stego-text (or stego-image or stego-audio).
- A stego-key controls the hiding process.

The approach used to embed data in a cover-image is using **Least Significant Bits (LSB)**. This method uses bits of each pixel in the image. A pixel is the basic unit of programmable color in a computer image. The specific color of a pixel is a blend of three colors—red, green, and blue (RGB). Three bytes of data specify a pixel’s color (one byte for each color). Eight bits make up a byte. A 24-bit color system uses all three bytes. LSB uses a bit of each of the red, green, and blue color components. Each pixel can store 3 bits.

The figure shows three pixels of a 24-bit color image. One of the letters in the secret message is the letter T, and inserting the character T changes only two bits of the color. The human eye cannot recognize the changes made to the least significant bits. The result is a hidden character.

On average, not more than half of the bits in an image will need to change to hide a secret message effectively.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605973865/Screenshot_2020-11-21_165052_a8i8fo.png"/>

#### 

### 4.3.3 Data Obfuscation

#### 4.3.3.1 Obfuscation

#### 4.3.3.2 Applications

#### 4.3.3.3 Packet Tracer - Configuring VPN Transport Mode

#### 4.3.3.4 Packet Tracer - Configuring VPN Tunnel Mode

## 4.4 Summary

### 

