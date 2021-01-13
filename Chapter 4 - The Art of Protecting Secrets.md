# Chapter 4 The Art of Protecting Secrets

## Introduction

- The principles of cryptology explain how modern day protocols and algorithms **secure data during communications and rest.** 
- **Access control** = a way of controlling access to a building, a room, a system, a database, a file, and information. Organizations employ a variety of access control techniques to protect confidentiality. This chapter will examine the four steps in the **access control process**:  identification ==> authentication ==> authorization ==> accountability. 
- the chapter describes the different **access control models** and **access control types.**
- the various ways users mask data. **Data obfuscation** and **stenography** are two techniques used to accomplish **data masking**.

## 1 Cryptography

### 1.1 Overview

#### What is Cryptography?

**Cryptology** is the science of making and breaking secret codes. **Cryptography** is a **way to store and transmit data** so only the intended recipient can read or process it. Modern cryptography uses computationally secure **algorithms** to make sure that cyber criminals cannot easily compromise protected information.

**Data confidentiality** ensures privacy so that only the intended receiver can read the message. Parties achieve this through encryption. 

**Encryption** = **process of scrambling data so that an unauthorized party cannot easily read it**.

- a **key** plays a critical role in encrypting and decrypting a message. The person possessing the key can decrypt the ciphertext to plaintext.

- An **algorithm** is the process or formula used to solve a problem. Julius Caesar is said to have secured messages by putting two sets of the alphabet, side-by-side, and then shifting one of them by a specific number of places. The number of places in the shift serves as the key. He converted plaintext into ciphertext using this key, and only his generals, who also had the key, knew how to decipher the messages. This method is the Caesar cipher. 

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1610524730/Untitled_Diagram_4_v0aivr.png"/>

#### Creating Ciphertext

Each encryption method uses a specific algorithm, called a **cipher**, to encrypt and decrypt messages. A cipher is a series of well-defined steps used to encrypt and decrypt messages. 

There are several methods of creating cipher-text:

- **Transposition** = verander volgorde
- **Substitution **= verwissel van plaats
- **One-time pad** = plaintext + secret key = new character (which then combines with the plaintext to produce ciphertext)

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1610296312/File_000_1_zdevm2.jpg" width=500 style="transform: rotate(270deg)">

Old encryption algorithms, such as the Caesar cipher or the Enigma machine, depended on the secrecy of the algorithm to achieve confidentiality. With modern technology, where reverse engineering is often simple, parties use public-domain algorithms. With most modern algorithms, successful decryption requires knowledge of the appropriate cryptographic keys. **This means that the security of encryption lies in the secrecy of the keys, not the algorithm.**

Some modern encryption algorithms still use transposition as part of the algorithm.

**Key management** is the most difficult part of designing a cryptosystem. Many cryptosystem have failed because of mistakes in their key management, and all modern cryptographic algorithms require key management procedures. 

In practice, most attacks on cryptographic systems involve attacking the key management system, rather than the cryptographic algorithm itself.

#### Two Types of Encryption

Cryptographic encryption can provide **confidentiality** by incorporating various tools and protocols.

There are two approaches to ensuring the security of data when using encryption. 

- <u>The first is to protect the algorithm</u>. If the security of an encryption system depends on the secrecy of the algorithm itself, the most important aspect is to guard the algorithm at all costs. Every time someone finds out the details of the algorithm, every party involved would need to change the algorithm. That approach does not sound very secure or manageable. 
- <u>The second approach is to protect the keys</u>. With modern cryptography, the algorithms are public. The cryptographic keys ensure the secrecy of the data. Cryptographic keys are passwords that are part of the input into an encryption algorithm together along with the data requiring encryption.

There are two classes of encryption algorithms:

**Symmetric algorithms** -  sender and receiver know  **pre-shared key** before encrypted communication . **A symmetric algorithms use the same key to encrypt and decrypt the plaintext**. 

:heavy_check_mark: ​simpler 

:heavy_check_mark: ​less computational power.

<img src="https://www.clickssl.net/wp-content/uploads/2019/12/symmetric-encryption.jpg" />

**Asymmetric algorithms** - Asymmetrical encryption algorithms use one key to encrypt data and a different key to decrypt data. One key is public and the other is private. Parties exchange secure messages without needing a pre-shared key

<img src="https://www.clickssl.net/wp-content/uploads/2019/12/asymmetric-encryption.jpg" />

:negative_squared_cross_mark: more complex  

:negative_squared_cross_mark: slower

### 1.2 Private-key Encryption

#### The Symmetrical Encryption Process

**Symmetric algorithms** use the same pre-shared key to encrypt and decrypt data, a method also known as **private-key encryption**. For example, Alice and Bob live in different locations and want to exchange secret messages with one another through the mail system. Alice wants to send a secret message to Bob. Private-key encryption uses a **symmetric algorithm**. As illustrated by the keys in the figure, Alice and Bob have identical keys to a single padlock. The <u>key exchange happened prior to sending any secret messages</u>. Alice writes a secret message and puts it in a small box that she locks using the padlock. She mails the box to Bob. The message is safe inside the box as the box makes its way through the post office system. When Bob receives the box, he uses his key to unlock the padlock and retrieve the message. Bob can use the same box and padlock to send a secret reply back to Alice. If Bob wants to talk to Carol, he needs a new pre-shared key for that communication to keep it secret from Alice. The more people Bob wants to communicate with securely, the more keys he will need to manage.

#### Types of Cryptography

each method differs in the way that it groups bits of data to encrypt it.

- **block ciphers** =  transform a fixed-length block of plaintext into a common block of ciphertext of 64 or 128 bits. **Block size** is the amount of data encrypted at any one time. To decrypt this ciphertext, apply the reverse transformation to the ciphertext block, using the same secret key.

  > Block ciphers usually result in output data that is larger than the input data, because the ciphertext must be a multiple of the block size. For example, Data Encryption Standard (DES) is a symmetric algorithm that encrypts blocks in 64-bit chunks using a 56-bit key. To accomplish this, the block algorithm takes data one chunk at a time, for example, 8 bytes per chunk, until the entire block is full. If there is less input data than one full block, the algorithm adds artificial data, or blanks, until it uses the full 64 bits, as shown in Figure 1 for the 64 bits on the left.

  > For example, a 150-bit plaintext provides two blocks of 64 bits each with third block of balance 22 bits. The last block of bits needs to be padded up with redundant information so that the length of the final block equal to block size of the scheme. In our example, the remaining 22 bits need to have additional 42 redundant bits added to provide a complete block. The process of adding bits to the last block is referred to as **padding**.

- **stream ciphers** = Unlike block ciphers, stream ciphers encrypt plaintext o**ne byte or one bit at a time**. Think of stream ciphers as a block cipher with a block size of one bit. With a stream cipher, the transformation of these smaller plaintext units varies, depending on when they are encountered during the encryption process. Stream ciphers can be much faster than block ciphers, and generally do not increase the message size, because they can encrypt an arbitrary number of bits.

  > A5 is a stream cipher that provides voice privacy and encrypts cell phone communications. It is also possible to use DES in stream cipher mode.

- Complex cryptographic systems can combine block and stream in the same process.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605968102/Screenshot_2020-11-21_151430_ybqc6f.png"/>

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605968155/Screenshot_2020-11-21_151536_wh1aij.png"/>

#### Symmetric Encryption Algorithms

- **Digital Encryption Standard (DES)** 
- symmetric block cipher with 64-bit block size
  - uses a 56-bit key. 
  - It takes a 64-bit block of plaintext as input and outputs a 64-bit block of ciphertext. 
  - It always operates on blocks of equal size and it uses both permutations and substitutions in the algorithm. A **permutation** is a way of arranging all elements of a set.
- **3DES (Triple DES):**  Triple DES encrypts data three times and uses a different key for at least one of the three passes, giving it a cumulative key size of 112-168 bits. 3DES is resistant to attack, but it is much slower than DES. The 3DES encryption cycle is as follows:
  - Data encrypted by first DES
  - Data decrypted by second DES
  - Data re-encrypted by third DES
  - The reverse process decrypts the ciphertext. 
- **IDEA:** The International Data Encryption Algorithm (IDEA) uses 64-bit blocks and 128-bit keys. IDEA performs eight rounds of transformations on each of the 16 blocks that results from dividing each 64-bit block. IDEA was the replacement for DES, and now PGP (Pretty Good Privacy) uses it. PGP is a program that provides privacy and authentication for data communication. GNU Privacy Guard (GPG) is a licensed, free version of PGP.
- **AES:** The Advanced Encryption Standard (AES) has a fixed block size of 128-bits with a key size of 128, 192, or 256 bits. The National Institute of Standards and Technology (NIST) approved the AES algorithm in December 2001. The U.S. government uses AES to protect classified information.

AES is a strong algorithm that uses longer key lengths. AES is faster than DES and 3DES, so it provides both a solution for software applications as well as hardware use in firewalls and routers. Other block ciphers include Skipjack (developed by the NSA), Blowfish, and Twofish.

example des => https://drive.google.com/file/d/1fHAFeqnkDSAw7aLGprSrHPLLaygYcjXm/view?usp=sharing

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605969864/Untitled_Diagram_4_bcooqb.png"/>

### 1.3 Public-Key Encryption

#### The Asymmetrical Encryption Process

Asymmetric encryption, also called public-key encryption

- uses one key for encryption that is different from the key used for decryption. (or reverse)
- the message cannot be decrypted with a public key

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605970518/Screenshot_2020-11-21_155508_qhitwl.png"/>

For example, in Figure 1, Alice requests and obtains Bob’s public key. In Figure 2, Alice uses Bob’s public key to encrypt a message using an agreed-upon algorithm. Alice sends the encrypted message to Bob, and Bob then uses his private key to decrypt the message, as shown in Figure 3.

#### Asymmetric Encryption Algorithms

Asymmetric algorithms use formulas that anyone can look up. The pair of unrelated keys is what makes these algorithms secure. The asymmetric algorithms include:

- **RSA (Rivest-Shamir-Adleman)** - uses the product of two very large prime numbers with an equal length of between 100 and 200 digits. Browsers use RSA to establish a secure connection.
- **Diffie-Hellman** - provides an electronic exchange method to share the secret key. Secure protocols, such as Secure Sockets Layer (SSL), Transport Layer Security (TLS), Secure Shell (SSH), and Internet Protocol Security (IPsec), use Diffie-Hellman.
- **ElGamal** - uses the U.S. government standard for digital signatures. This algorithm is free for use because no one holds the patent.
- **Elliptic Curve Cryptography (ECC)** - uses elliptic curves as part of the algorithm. In the U.S., the National Security Agency uses ECC for digital signature generation and key exchange.

> diffie helman analogy
>
> <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Diffie-Hellman_Key_Exchange.svg/1200px-Diffie-Hellman_Key_Exchange.svg.png" width=300 height=400/>



### 1.4 Symmetric versus Asymmetric Encryption

#### Key Management

includes the generation, exchange, storage, use, and replacement of keys used in an encryption algorithm.

Key management is the most difficult part of designing a cryptosystem. Many cryptosystem have failed because of mistakes in their key management procedures. In practice, most attacks on cryptographic systems target the key management level, rather than the cryptographic algorithm itself.

There are several essential characteristics of key management to consider.

- key generation
- key verification
- key exchange
- key storage
- key lifetime 
- key revocation and destruction 

Two terms used to describe keys are:

- **Key length** - Also called the key size, this is the measure in bits.

- **Key space** - This is the number of possibilities that a specific key length can generate.

As key length increase, the key space increases exponentially. The key space of an algorithm is the set of all possible key values. Longer keys are more secure; however, they are also more resource intensive. Almost every algorithm has some weak keys in its keyspace that enable a criminal to break the encryption via a shortcut.

#### Comparing Encryption Types

It is important to understand the differences between symmetric and asymmetric encryption methods. Symmetric encryption systems are more efficient and can handle more data. 

However, key management with symmetric encryption systems is more problematic and harder to manage. Asymmetric cryptography is more efficient at protecting the confidentiality of small amounts of data, and its size and speed make it more secure for tasks such as electronic key exchange which is a small amount of data rather than encrypting large blocks of data.

Maintaining **confidentiality** is important for both data at rest and data in motion. In both cases, symmetric encryption is favored because of its speed and the simplicity of the algorithm. Some asymmetric algorithms can significantly increase the size of the object encrypted. Therefore, in the case of data in motion, use public key cryptography to exchange the secret key, and then symmetric cryptography to ensure the confidentiality of the data sent.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605972613/Screenshot_2020-11-21_163003_muqxrg.png"/>

#### Applications

Symmetric examples

- A one-time password-generating token is a hardware device that uses cryptography to generate a one-time password. A one-time password is an automatically generated numeric or alphanumeric string of characters that authenticates a user for one transaction of one session only. The number changes every 30 seconds or so. The session password appears on a display and the user enters the password.

- The electronic payment industry uses 3DES. 

- Operating systems use DES to protect user files and system data with passwords. 
- Most encrypting file systems, such as NTFS, use AES.

Four protocols use asymmetric key algorithms:

- Internet Key Exchange (IKE), which is a fundamental component of IPsec Virtual Private Networks (VPNs).

- Secure Socket Layer (SSL), which is a means of implementing cryptography into a web browser.

- Secure Shell (SSH), which is a protocol that provides a secure remote access connection to network devices.

- Pretty Good Privacy (PGP), which is a computer program that provides cryptographic privacy and authentication to increase the security of email communications.

**VPN**

A VPN is a private network that uses a public network, usually the Internet, to create a secure communication channel. A VPN connects two endpoints such as two remote offices over the Internet to form the connection.

VPNs use IPsec. IPsec is a suite of protocols developed to achieve secure services over networks. 

**IPsec services** allow for **authentication**, **integrity**, **access control**, and **confidentiality**. With IPsec, remote sites can exchange **encrypted** and verified information.

**Data in use** is a growing concern to many organizations. When in use, data no longer has any protection because the user needs to open and change the data. System memory holds data in use and it can contain sensitive data such as the encryption key. If criminals compromise data in use, they will have access to data at rest and data in motion.

## 2 Access Controls

### Types of Access Controls

- **physical = daadwerkelijke barrières** die worden ingezet om direct contact met systemen te voorkomen. Het doel is om te voorkomen dat onbevoegde gebruikers fysieke toegang krijgen tot faciliteiten, apparatuur en andere bedrijfsmiddelen. Fysieke toegangscontrole bepaalt wie kan binnenkomen (of verlaten), waar ze kunnen binnenkomen (of
  verlaten) en wanneer ze kunnen binnenkomen (of verlaten).
- **logical =  hardware- en softwareoplossingen** die worden gebruikt om de toegang tot bronnen en systemen te beheren. Deze op technologie gebaseerde oplossingen omvatten tools en protocollen die computersystemen gebruiken voor identificatie, authenticatie, autorisatie en verantwoording (accountability).
- **administrative =  beleid en procedures** die door organisaties gedefinieerd zijn om alle aspecten van het controleren van ongeautoriseerde toegang te implementeren en af te dwingen. Administratieve controles zijn gericht op personeel en zakelijke praktijken.

onderwerp / subject (gebruiker / proces) <= toegangscontrole => object  (bestand / poort / invoer- uitvoerapparaat )

- **Mandatory access control** = **beperkt de acties** die een onderwerp op een object kan uitvoeren. .  Een **<u>autorisatieregel</u>** dwingt af of een onderwerp al dan niet toegang heeft tot het object. (ex topsecret in army)

- **Discretionaire toegangscontrole** = **verleent** of **beperkt** object **toegang** bepaald door de eigenaar van het object. 
  
  > Zoals de naam al aangeeft, zijn besturingselementen discretionair omdat een objecteigenaar met bepaalde toegangsrechten deze rechten kan doorgeven aan een ander onderwerp. (ex rwrx on linux)
  
- **role based access control** = gebaseerd op de rol van het onderwerp. Rollen zijn functies binnen een organisatie.
  
  > Voor specifieke rollen zijn machtigingen vereist om bepaalde bewerkingen uit te voeren. Gebruikers verwerven machtigingen via hun rol. RBAC kan werken in combinatie met DAC of MAC door het beleid van beide af te dwingen.
  
- **Op regels gebaseerde toegangscontrole** = toegangscontrolelijsten (EN: Access Control Lists - **ACL's**) om te helpen bepalen of toegang moet worden verleend. 

  > Een reeks regels is opgenomen in de ACL. De beslissing om al dan niet toegang te verlenen hangt af van deze regels. Een voorbeeld vanzo'n regel is er een die stelt dat geen enkele werknemer buiten kantooruren of in het weekend toegang mag hebben tot het salarisdossier.

### Access control process 

#### Identification

- enforces the rules established by the **authorization policy**. 

- A **subject** requests access to a **system resource.** 
- Every time the subject requests access to a resource, the **access controls** determine whether to grant or deny access. 

For example, the authorization policy determines what activities a user can perform on a resource. A unique identifier ensures the proper association between allowed activities and subjects. A username is the most common method used to identify a user. A username can be an alphanumeric combination, a personal identification number (PIN), a smart card, or biometric, such as a fingerprint, retina scan, or voice recognition. A unique identifier ensures that a system can identify each user individually; therefore, allowing an authorized user to perform the appropriate actions on a particular resource.

#### Authentication (who are you)

can be 3 things

- what you know
- what you have 
- who you are

**multi-factor authentication** = combination of above

#### Authorization (what can you do)

controls what a user can and cannot do on the network **after successful authentication.** 

After a user proves his or her identity, the system checks to see what network resources the user can access and what the user can do with the resources. 

authorization answers the question, “What read, copy, create, and delete privileges does the user have?” Authorization uses a set of **attributes** that describes the user’s access to the network. The system compares these attributes to the information contained within the **authentication database,** determines a set of restrictions for that user, and delivers it to the local router where the user is connected. 

**Authorization is automatic** and does not require users to perform additional steps after authentication. Implement authorization immediately after the user authenticates.

**autorisatiebeleid** legt de **autorisatieregels** vast voor toagangsbeheer

#### Accountability

**traces an action back to a person or process** making the change to a system, collects this information, and reports the usage data. The organization can use this data for such purposes as auditing or billing. The collected data might include the log in time for a user, whether the user log in was a success or failure, or what network resources the user accessed. This allows an organization to trace actions, errors, and mistakes during an audit or investigation.

### Types of Security Controls

#### Preventive Controls

#### Deterrent Controls

#### Detective Controls

#### Corrective Controls

#### Recovery Controls

#### Compensative Controls

## 3 Obscuring Data

### 3.1 Data Masking

Data masking technology secures data by **replacing sensitive information with a non-sensitive version.** 

The non-sensitive version looks and acts like the original. This means that a business process can use non-sensitive data and there is no need to change the supporting applications or data storage facilities. In the most common use case, masking limits the propagation of sensitive data within IT systems by distributing surrogate data sets for testing and analysis. Information can be dynamically masked if the system or application determines that a user request for sensitive information is risky.

Data masking can replace sensitive data in non-production environments to protect the underlying information.

There are several data masking techniques that can ensure that data remains meaningful but changed enough to protect it.

#### Data Masking Techniques

**Substitution** replaces data with authentic looking values to apply anonymity to the data records.

**Shuffling** derives a substitution set from the same column of data that a user wants to mask. This technique works well for financial information in a test database, for example.

**Nulling** out applies a null value to a particular field, which completely prevents visibility of the data.

### 3.2 Stenography

conceals data (the message) in another file such as a graphic, audio, or other text file. The advantage of steganography over cryptography is that the secret message does not attract any special attention. 

There are several components involved in hiding data. 

- First, there is the **embedded data**, which is the secret message. 
- The **cover-text** (or cover-image or cover-audio) hides the embedded data producing the **stego-text** (or stego-image or stego-audio).
- A **stego-key** controls the hiding process.

The approach used to embed data in a cover-image is using **Least Significant Bits (LSB)**. This method uses bits of each pixel in the image. A pixel is the basic unit of programmable color in a computer image. The specific color of a pixel is a blend of three colors—red, green, and blue (RGB). Three bytes of data specify a pixel’s color (one byte for each color). Eight bits make up a byte. A 24-bit color system uses all three bytes. LSB uses a bit of each of the red, green, and blue color components. Each pixel can store 3 bits.

The figure shows three pixels of a 24-bit color image. One of the letters in the secret message is the letter T, and inserting the character T changes only two bits of the color. The human eye cannot recognize the changes made to the least significant bits. The result is a hidden character.

On average, not more than half of the bits in an image will need to change to hide a secret message effectively.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605973865/Screenshot_2020-11-21_165052_a8i8fo.png"/>

### 3.3 Data Obfuscation

is het gebruik en de praktijk van gegevensmaskering en steganografietechnieken in het beroep van cyberbeveiliging en cyberinformatie:

- Verduistering is de kunst om de boodschap verwarrend,
dubbelzinnig of moeilijker te begrijpen te maken.
- Een systeem kan opzettelijk berichten door elkaar halen om
ongeautoriseerde toegang tot gevoelige informatie te voorkomen.
- Softwarewatermerken beschermen software tegen onbevoegde
toegang of wijziging.
- Softwarewatermerken voegen een geheim bericht in het
programma toe als bewijs van eigendom.
- Het geheime bericht is het softwarewatermerk. Als iemand het
watermerk probeert te verwijderen, is het resultaat een
niet-functionele code.

