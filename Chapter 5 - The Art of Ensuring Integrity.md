# Chapter 5 The Art of Ensuring Integrity

## Introduction

- integrity = data remains **unchanged and trustworthy** by anyone or anything over its entire life cycle. 
- critical component to the design, implementation and usage of any system that stores, processes, or transmits data. 

This chapter begins by discussing the types of data integrity controls used such as **hashing algorithms, salting, and keyed-hash message authentication code (HMAC)**. 

The use of **digital signatures** and **certificates** incorporates the data integrity controls to provide users a way of verifying the **authenticity** of messages and documents. 

The chapter concludes with a discussion of **database integrity enforcement**. Having a well-controlled and well-defined data integrity system increases the stability, performance, and maintainability of a database system.

## 1 Types of Data Integrity Controls

### 1.1 Hashing Algorithms

#### What is Hashing?

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20190913233848/Untitled-Diagram.drawio-1.png" height=300 width=200/>



> - a tool to check  data remains unchanged in rest or transit
>
> - Hashing ensures data integrity by taking binary data (the message) and producing a **fixed-length** representation called the **hash value** or **message digest**
> - The hash tool uses a cryptographic hashing function to verify and ensure data integrity. 
> - It can also verify **authentication**. Hash functions replace clear text password or encryption keys because hash functions are **one-way functions.** This means that if a password is hashed with a specific hashing algorithm, it will always result in the same hash digest. It is considered one-way because with hash functions, it is computationally infeasible for two different sets of data to come up with the same hash digest or output.

Every time the data is changed or altered, the hash value also changes. Because of this, cryptographic hash values are often called **digital fingerprints**. 

They can detect duplicate data files, file version changes, and similar applications. These values guard against an accidental or intentional change to the data and accidental data corruption. Hashing is also **very efficient**. A large file or the content of an entire disk drive results in a hash value with the same size.

Hashing is a **one-way mathematical function** that is relatively easy to compute, but significantly harder to reverse. Grinding coffee is a good analogy of a one-way function. It is easy to grind coffee beans, but it is almost impossible to put all of the tiny pieces back together to rebuild the original beans.

#### Hashing Properties

A cryptographic hash function has the following properties:

- The input can be any length.

- The output has a fixed length.

- The hash function is one way and is not reversible.

- Two different input values will almost never result in the same hash values.

Hash functions are helpful to ensure that a user or communication error does not change the data accidentally. For instance, a sender may want to make sure that no one alters a message on its way to the recipient. The sending device inputs the message into a hashing algorithm and computes its fixed-length digest or fingerprint.

#### Hashing Algorithms

**Simple Hash Algorithm (8-bit Checksum)**

The 8-bit checksum is one of the first hashing algorithms, and it is the simplest form of a hash function. An 8-bit checksum calculates the hash by converting the message into binary numbers and then organizing the string of binary numbers into 8-bit chucks. The algorithm adds up the 8-bit values. The final step is to convert the result using a process called 2’s complement. The 2’s complement converts a binary to its opposite value, and then it adds one. This means that a zero converts to a one, and a one converts to a zero. The final step is to add 1 resulting in an 8-bit hash value.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605977082/Screenshot_2020-11-21_174429_qfpbgw.png" width=500/>

#### Modern Hashing Algorithms

There are many modern hashing algorithms widely used today. Two of the most popular are MD5 and SHA.

**Message Digest 5 (MD5) Algorithm**

Ron Rivest developed the MD5 hashing algorithm, and several Internet applications use it today. MD5 is a one-way function that makes it easy to compute a hash from the given input data but makes it very difficult to compute input data given only a hash value.

MD5 produces a 128-bit hash value. The Flame malware compromised the security of MD5 in 2012. The authors of the Flame malware used an MD5 collision to forge a Windows code-signing certificate. 

**Secure Hash Algorithm (SHA)**

The U.S. National Institute of Standards and Technology (NIST) developed SHA, the algorithm specified in the Secure Hash Standard (SHS). NIST published SHA-1 in 1994. SHA-2 replaced SHA-1 with four additional hash functions to make up the SHA family:

- SHA-224 (224 bit)

- SHA-256 (256 bit)

- SHA-384 (384 bit)

- SHA-512 (512 bit)

SHA-2 is a stronger algorithm, and it is replacing MD5. SHA-256, SHA-384, and SHA-512 are the next-generation algorithms.

#### Hashing applications

- check for errors in data

  > **Integrity ensures that data and information is complete and unaltered at the time of its acquisition.** This is important to know when a user downloads a file from the Internet or a forensic examiner is looking for evidence on digital media.
  >
  > To verify the integrity of all IOS images, Cisco provides MD5 and SHA checksums at Cisco’s Download Software website. The user can make a comparison of this MD5 digest against the MD5 digest of an IOS image installed on a device, as shown in the figure. The user can now feel confident that no one has tampered or modified the IOS image file

- secure password storage

  > Hashing algorithms turn any amount of data into a fixed-length fingerprint or digital hash. A criminal cannot reverse a digital hash to discover the original input. If the input changes at all, it results in a different hash. This works for protecting passwords. A system needs to store a password in a form that protects it and can still verify that a user’s password is correct.
  >
  > The figure shows the workflow for user account registration and authentication using a hash-based system. The system never writes the password to the hard drive, it only stores the digital hash.
  >
  > <img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605977416/Screenshot_2020-11-21_175003_akp2aq.png" height=350/>

- identification of data via a smaller value

  > **The field of digital forensics uses hashing to verify all digital media that contain files.** For example, the examiner creates a hash and a bit-for-bit copy of the media containing the files to produce a digital clone. The examiner compares the hash of the original media with the copy. If the two values match, the copies are identical. The fact that one set of bits is identical to the original set of bits establishes fixity. Fixity helps to answer several questions:
  >
  > - Does the examiner have the files he expects?
  >
  > - Is the data corrupted or changed?
  >
  > - Can the examiner prove that the files are not corrupt?
  >
  > Now the forensics expert can examine the copy for any digital evidence while leaving the original intact and untouched.
  >

- efficient storage of data in hash tables

  > <img src="https://res.cloudinary.com/practicaldev/image/fetch/s--7x2naWJ6--/c_imagga_scale,f_auto,fl_progressive,h_1080,q_auto,w_1080/https://cl.ly/dcc906e5110a/Image%25202019-05-12%2520at%252011.38.16%2520PM.png" height=300 />

### 1.2 Salting

#### What is Salting?

Salting makes password hashing more secure. If two users have the same password, they will also have the same password hashes. A salt, which is a random string of characters, is **an additional input to the password before hashing. This creates a different hash result for the two passwords** as shown in the figure. A database stores both the hash and the salt.

**In the figure, the same password generates a different hash because the salt in each instance is different. The salt does not have to be secret since it is a random number.**

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1605977677/Screenshot_2020-11-21_175428_vnxsmj.png"/>

**Salting prevents an attacker from using a dictionary attack** to try to guess passwords. Salting also makes it impossible to use lookup tables and rainbow tables to crack a hash

#### Preventing Attacks

**Lookup Tables**

A lookup table stores the pre-computed hashes of passwords in a password dictionary along with the corresponding password. A lookup table is a data structure that processes hundreds of hash lookups per second. **if a salt is used these kinds of attacks become impossible**

**Reverse Lookup Tables**

This attack allows the cybercriminal to launch a dictionary or brute-force attack on many hashes without the pre-computed lookup table. The cybercriminal creates a lookup table that plots each password hash from the breached account database to a list of users. The cybercriminal hashes each password guess and uses the lookup table to get a list of users whose password matched the cybercriminal’s guess

**Rainbow Tables**

Rainbow tables sacrifice hash-cracking speed to make the lookup tables smaller. A smaller table means that the table can store the solutions to more hashes in the same amount of space.

A Cryptographically Secure Pseudo-Random Number Generator (CSPRNG) is the best choice to generate salt. CSPRNGs generate a random number that has a high level of randomness and is completely unpredictable, so it is cryptographically secure.

To implement salting successfully, use the following recommendations:

- The salt needs to be unique for every user password.

- Never reuse a salt.

- The length of the salt should match the length of the hash function’s output.

- Always hash on the server in a web application.

Using a technique called key stretching will also help to protect against attack. **Key stretching** makes the hash function very slowly. This prevents high-end hardware that can compute billions of hashes per second less effective.

**collision**

Hashing algoritmes moeten telkens een unieke output hebben voor verschillende inputs Wanneer je voor 2 verschillende input waarden dezelfde output waarde krijgt, spreekt men van een “collision” Een hashing algoritme verliest zijn nut als collisions bewust kunnen worden veroorzaakt.

### 1.3 HMAC

The next step in preventing a cybercriminal from launching a dictionary or brute-force attack on a hash is to add a secret key to the hash. Only the person who knows the hash can validate a password. One way to do this is to include the secret key in the hash using a hash algorithm called **keyed-hash message authentication code** (HMAC or KHMAC). HMACs use an additional secret key as input to the hash function. The use of HMAC goes a step further than just integrity assurance by **adding authentication**. An HMAC uses a specific algorithm that combines a cryptographic hash function with a secret key, as shown in the figure.

Only the sender and the receiver know the secret key, and the output of the hash function now depends on the input data and the secret key. Only parties who have access to that secret key can compute the digest of an HMAC function. This characteristic **defeats man-in-the-middle attacks and provides authentication of the data origin.**

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606020833/Screenshot_2020-11-22_055342_dyy8k3.png" width=400/>



Consider an example where a sender wants to ensure that a message remains unchanged in transit and wants to provide a way for the receiver to authenticate the origin of the message.

As shown in Figure 1, the sending device inputs data (such as Terry Smith’s pay of $100 and the secret key) into the hashing algorithm and calculates the fixed-length HMAC digest or fingerprint. The receiver gets the authenticated fingerprint attached to the message.

In Figure 2, the receiving device removes the fingerprint from the message and uses the plaintext message with its secret key as input to the same hashing function. If the receiving device calculates a fingerprint equal to the fingerprint sent, the message is still in its original form. Additionally, the receiver knows the origin of the message because only the sender possesses a copy of the shared secret key. The HMAC function proved the authenticity of the message.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606021164/Untitled_Diagram-Page-2_jgiflq.png"/>



HMACs can also authenticate a web user. Many web services use basic authentication, which does not encrypt the username and password during transmission. Using HMAC, the user sends a private key identifier (not the actual private key) and an HMAC. The server looks up the user’s private key and creates an HMAC. The user’s HMAC must match the one calculated by the server.

VPNs using IPsec rely on HMAC functions to authenticate the origin of every packet and provide data integrity checking.

As shown in the figure, Cisco products use hashing for entity authentication, data integrity, and data authenticity purposes:

- Cisco IOS routers use hashing with secret keys in an HMAC-like manner to add authentication information to routing protocol updates.

- IPsec gateways and clients use hashing algorithms, such as MD5 and SHA-1 in HMAC mode, to provide packet integrity and authenticity.

- Cisco software images on Cisco.com have an MD5-based checksum available so that customers can check the integrity of downloaded images.

**Note**: The term entity can refer to devices or systems within an organization.

## 2 Digital Signatures

### 2.1 Signatures and the Law

#### Non-Repudiation / accountability 

repudiate means to deny. Non-repudiation is a way to ensure that the sender of a message or document cannot deny having sent the message or document and that the recipient cannot deny having received the message or document. 

- **A digital signature ensures that the sender electronically signed the message or document**. Since a digital signature is unique to the individual creating it, that person cannot later deny that he or she provided the signature.
- **A digital signature ensures that the document was not altered after it was signed**.

### 2.2 How Digital Signature Technology Works

#### Processes of Creating a Digital Signature

**Asymmetric cryptography is the basis for digital signatures**. A public key algorithm like **RSA** generates two keys: one private and the other public. The keys are mathematically related.

Alice wants to send Bob an email that contains important information for the rollout of a new product. **Alice wants to make sure that Bob knows that the message came from her, and that the message did not change after she sent it.**

Alice creates the message along with a digest of the message. She then encrypts this digest with her private key as shown in Figure 1. Alice bundles the message, the encrypted message digest, and her public key together to create the signed document. Alice sends this to Bob as shown in Figure 2.

Bob receives the message and reads it. To make sure that the message came from Alice, he creates a message digest of the message. He takes the encrypted message digest received from Alice and decrypts it using Alice’s public key. Bob compares the message digest received from Alice with the one he generated. If they match, Bob knows that he can trust that no one tampered with the message as shown in Figure 3.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606022034/Untitled_Diagram-Page-2_1_m6zf47.png" width=500/>

> Signing a hash instead of the whole document provides efficiency, compatibility, and integrity. Organizations may want to replace paper documents and ink signatures with a solution that assures the electronic document meets all legal requirements.

#### Using Digital Signatures

The following two situations provide examples of using digital signatures:

- **Code signing** - Used to verify the integrity of executable files downloaded from a vendor website. Code signing also uses signed digital certificates to authenticate and verify the identity of the site.

- **Digital certificates** - Used to verify the identity of an organization or individual to authenticate a vendor website and establish an encrypted connection to exchange confidential data.

#### Comparing Digital Signature Algorithms

The three common digital signature algorithms are Digital Signature Algorithm (DSA), Rivest-Shamir-Adleman (RSA), and Elliptic Curve Digital Signature Algorithm (ECDSA). All three generate and verify digital signatures. These algorithms depend upon asymmetrical encryption and public key techniques. Digital signatures require two operations:

- Key generation
- Key verification

Both operations require key encryption and decryption.

DSA uses large number factorization. Governments use DSA for signing to create digital signatures. DSA does not extend beyond the signature to the message itself.

RSA is the most common public key cryptography algorithm in use today. RSA is named after the individuals who created it in 1977: Ron Rivest, Adi Shamir, and Leonard Adleman. RSA depends on asymmetrical encryption. RSA covers signing and also encrypts the content of the message.

DSA is faster than RSA as a signing services for a digital document. RSA is best suited for applications requiring the signing and verification of electronic documents and message encryption.

Like most areas of cryptography, the RSA algorithm is based on two mathematical principles; modulus and prime number factorization. Click [here](https://www.youtube.com/watch?v=wXB-V_Keiu8) to learn more about how RSA uses both modulus and prime number factorization.

ECDSA is the newest digital signature algorithm that is gradually replacing RSA. The advantage of this new algorithm is that it can uses much smaller key sizes for the same security and requires less computation than RSA.

## 3 Certificates

### 3.1 The Basics of Digital Certificates

#### What is a Digital Certificate?

- **A digital certificate is equivalent to an electronic passport**. 
- They enable users, hosts, and organizations to exchange information securely over the Internet. 
- Specifically, a digital certificate **authenticates** and **verifies** that users sending a message are who they claim to be. 
- Digital certificates **can also provide confidentiality for the receiver with the means to encrypt a reply**.

#### Using Digital Certificates

Refer to the figure to help understand how digital certificates are used to authenticate a person or entity. In this scenario, Bob is purchasing an online item from Alice's website. Bob's browser will use Alice's digital certificate to ensure he is actually shopping on Alice's website and to secure traffic between them.

**Step 1**: Bob decides to buy something on Alice's website and clicks on "Proceed to Checkout". His browser initiates a secure connection with Alice's web server and displays a lock icon in the security status bar.

**Step 2**: Alice's web server receives the request and replies by sending its digital certificate containing the web server public key and other information to Bob's browser.

**Step 3**: Bob's browser checks the digital certificate against stored certificates and confirms that he is indeed connected to Alice's web server. Only trusted certificates permit the transaction to go forward. If the certificate is not valid, then communication fails.

**Step 4**: Bob's web browser creates a unique session key that will be used for secure communication with Alice's web server.

**Step 5**: Bob's browser encrypts the session key using Alice's public key and sends it to Alice's web server.

**Step 6**: Alice's web server receives the encrypted message from Bob's browser. It uses its private key to decrypt the message and discover the session key. Future exchange between the web server and browser will now use the session key to encrypt data.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606032200/Screenshot_2020-11-22_090310_c3m8lw.png" width=450/>

#### What is a Certificate Authority?

On the Internet, continually exchanging identification between all parties would be impractical. Therefore, individuals agree to accept the word of a neutral third party. Presumably, the third party does an in-depth investigation prior to the issuance of credentials. After this in-depth investigation, the third party issues credentials that are difficult to forge. From that point forward, all individuals who trust the third party simply accept the credentials that the third party issues.

For example, in the figure Alice applies for a driver’s license. In this process, she submits evidence of her identity, such as birth certificate, picture ID, and more to a government-licensing bureau. The bureau validates Alice’s identity and permits Alice to complete a driver’s examination. Upon successful completion, the licensing bureau issues Alice a driver license. Later, Alice needs to cash a check at the bank. Upon presenting the check to the bank teller, the bank teller asks her for ID. The bank, because it trusts the government-licensing bureau, verifies her identity and cashes the check.

A **certificate authority (CA)** functions the same as the licensing bureau. The CA issues digital certificates that authenticate the identity of organizations and users. These certificates also sign messages to ensure that no one tampered with the messages.

### 3.2 Constructing a Digital Certificate

#### What is Inside a Digital Certificate?

As long as a digital certificate follows a **standard structure**, any entity can read and understand it regardless of the issuer. **X.509** is a standard for a **public key infrastructure (PKI)** to manage digital certificates. 

PKI is the policies, roles, and procedures required to create, manage, distribute, use, store, and revoke digital certificates. The **X.509** standard specifies that digital certificates contain the standard information shown in the figure.

<img src="https://www.researchgate.net/profile/Sangram_Ray/publication/263526947/figure/fig1/AS:296060175044620@1447597654757/ECC-based-X509-certificate-format.png" width=450/>

#### The Validation Process

verifying a certificates validity: 

Browsers and applications perform a validation check before they trust a certificate to ensure they are valid. The three processes include the following:

- **Certificate Discovery** validates the *certification path* by checking each certificate starting at the beginning with the root CA’s certificate

- **Path Validation** selects a certificate of the issuing CA for each certificate in the chain

- **Revocation** determines whether the certificate was revoked and why

#### The Certificate Path

**certificate path** An individual gets a certificate for a public key from a commercial CA. The certificate belongs to a chain of certificates called the chain of trust. The number of certificates in the chain depends on the hierarchical structure of the CA.

The figure shows a certificate chain for a two tier CA. There is an offline Root CA and an online subordinate CA. The reason for the two-tier structure is that X.509 signing allows for easier recovery in the event of a compromise. If there is an offline CA, it can sign the new online CA certificate. If there is not an offline CA, a user has to install a new root CA certificate on every client machine, phone, or tablet.

<img src="https://d1smxttentwwqu.cloudfront.net/wp-content/uploads/2018/11/browser_certification_paths.png" width=700/>



## 4 Database Integrity Enforcement

### 4.1 Database Integrity

Databases provide an efficient way to store, retrieve, and analyze data. As data collection increases and data becomes more sensitive, it is important for cybersecurity professionals to protect the growing number of databases. Think of a database as an electronic filing system. 

#### Data Integrity

 refers to the **accuracy, consistency, and reliability** of data stored in a database. The responsibility of data integrity falls on database designers, developers, and the organization’s management.

The four data integrity rules or constraints are as follows:

- **Entity Integrity**: All rows must have a unique identifier called a Primary Key (Figure 1).

- **Domain Integrity**: All data stored in a column must follow the same format and definition (Figure 2).

- **Referential Integrity**: Table relationships must remain consistent. Therefore, a user cannot delete a record which is related to another one (Figure 3).

- **User-defined Integrity**: A set of rules defined by a user which does not belong to one of the other categories. For example, a customer places a new order. The user first checks to see if this is a new customer. If it is, the user adds the new customer to the customers table.

#### Data Entry Controls

**Data entry** involves inputting data to a system. A set of controls ensures that users enter the correct data.

**Drop Down Master Data Controls**

Have a drop down option for master tables instead of asking individuals to enter the data. An example of drop down master data controls is using the locations list from the U.S. postal address system to standardize addresses.

**Data Field Validation Controls**

Set up rules for basic checks including:

- Mandatory input ensures that a required field contains data

- Input masks prevent users from entering invalid data or help ensure that they enter data consistently (like a phone number, for example)

- Positive dollar amounts

- Data ranges ensure that a user enters data within a given range (like a date of birth entered as 01-18-1820, for example)

- Mandatory second person approval (a bank teller receives a deposit or withdraw request greater than a specified value triggers a second or third approval)

- Maximum record modification trigger (the number of records modified exceeds a predetermined number within a specific period of time blocks a user until a manager identifies whether or not the transactions were legitimate)

- Unusual activity trigger (a system locks when it recognizes unusual activity)

### 4.2 Database Validation

#### Validation Rules

checks that data falls within the parameters defined by the database designer. A validation rule helps to ensure the completeness, accuracy and consistency of data. The criteria used in a validation rule include the following:

- Size – checks the number of characters in a data item

- Format – checks that the data conforms to a specified format

- Consistency – checks for the consistency of codes in related data items

- Range – checks that data lies within a minimum and maximum value

- Check digit – provides for an extra calculation to generate a check digit for error detection

> <img src="https://www.thebookdesigner.com/wp-content/uploads/2012/01/Screen-shot-2012-01-11-at-8.08.37-PM.png"/>

#### Data Type Validation

is the simplest data validation and verifies that a user entering data is consistent with the type of characters expected. For example, a phone number would not contain alpha characters. Databases allow three data types: integer, string, and decimal

#### Input Validation

 One of the most vulnerable aspects of database integrity management is controlling the data input process. Many well-known attacks run against a database and insert malformed data. The attack can confuse, crash, or make the application divulge too much information to the attacker. Attackers use automated input attacks.

For example, users fill out a form via a Web application to subscribe to a newsletter. A database application automatically generates and sends email confirmations. When users receive their email confirmations with a URL link to confirm their subscription, attackers modify the URL link. These modifications include changing the username, email address, or subscription status. The email returns back to the server hosting the application. If the Web server did not verify that the email address or other account information submitted matched the subscription information, the server received bogus information. Hackers can automate the attack to flood the Web application with thousands of invalid subscribers to the newsletter database.

#### Anomaly Verification

refers to identifying patterns in data that do not conform to expected behavior. These non-conforming patterns are anomalies, outliers, exceptions, aberrations, or surprises in diﬀerent database applications. Anomaly detection and verification is an important countermeasure or safeguard in identifying fraud detection. Database anomaly detection can identify credit card and insurance fraud. Database anomaly detection can protect data from massive destruction or changes.

Anomaly verification requires verification data requests or modifications when a system detects unusual or surprising patterns. An example of this is a credit card with two transactions in vastly different request locations in a short time. If a transaction request from New York City occurs at 10:30 a.m. and a second request comes from Chicago at 10:35 a.m., the system triggers a verification of the second transaction.

A second example occurs when an unusual number of email address modifications happen in an unusual number of database records. Since email data launch DoS attacks, the email modification of hundreds of records could indicate that an attacker is using an organization’s database as a tool for his or her DoS attack.

### 4.3 Database Integrity Requirements

A database is like an electronic filing system. Maintaining proper filing is critical in maintaining the trustworthiness and usefulness of the data within the database. Tables, records, fields, and data within each field make up a database. In order to maintain the integrity of the database filing system, users must follow certain rules. 

#### Entity Integrity

is an integrity rule, which states that every table must have a primary key and that the column or columns chosen to be the primary key must be unique and not NULL. Null in a database signifies missing or unknown values. Entity integrity enables proper organization of data for that record.

#### Referential Integrity

The basis of **referential integrity** is **foreign keys**. A foreign key in one table references a primary key in a second table. The primary key for a table uniquely identifies entities (rows) in the table. Referential integrity maintains the integrity of foreign keys.

#### Domain Integrity

ensures that all the data items in a column fall within a defined set of valid values. Each column in a table has a defined set of values, such as the set of all numbers for credit card numbers, social security numbers, or email addresses. Limiting the value assigned to an instance of that column (an attribute) enforces domain integrity. Domain integrity enforcement can be as simple as choosing the correct data type, length and or format for a column.

## 5 Summary

This chapter discussed how the art of integrity ensures that data remains unchanged by anyone or anything over its entire life cycle. This chapter began by discussing the types of data integrity controls. Hashing algorithms, password salting, and keyed-hash message authentication code (HMAC) are important concepts for the cyber heroes to use in the implementation of digital signatures and certificates. These tools provide a way for cybersecurity specialists to verify the authenticity of messages and documents. The chapter concluded with a discussion of database integrity enforcement. Having a well-controlled and well-defined data integrity system increases the stability, performance, and maintainability of a database system.

