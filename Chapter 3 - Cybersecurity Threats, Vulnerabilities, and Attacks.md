# Chapter 3 Cybersecurity Threats, Vulnerabilities, and Attacks

## 3.0 Introduction

Threats, vulnerabilities, and attacks are the central focus of cybersecurity professionals. 

- A **threat** is the possibility that a harmful event, such as an attack, will occur. 
- A **vulnerability** is a weakness that makes a target susceptible to an attack.
- An **attack** is a deliberate exploitation of a discovered weakness in computer information systems, either as specific targets or merely as targets of opportunity. 

Cyber criminals may have different motivations for selecting a target of an attack. Cyber criminals succeed by continuously searching for and identifying systems with clear vulnerabilities. Common victims include unpatched systems or systems missing virus and spam detection.

This chapter examines the most common cybersecurity attacks. Cybersecurity professionals must understand how each attack works, what it exploits, and how it affects the victim. The chapter begins by explaining the threat of malware and malicious code and then goes into explaining the types of deception involved with social engineering. A **cyberattack** is any type of offensive maneuver used by cyber criminals to target computer information systems, computer networks, or other computer devices. Cyber criminals launch offensive maneuvers against both wired and wireless networks.

## 3.1 Malware and Malicious Code

### 3.1.1 Types of Malware

#### 3.1.1.1 What is Malware?

Malicious software, or **malware** :

- is a term used to describe software designed to disrupt computer operations, or gain access to computer systems, without the user's knowledge or permission. 
- Malware has become an umbrella term used to describe all hostile or intrusive software.
- The term malware includes computer viruses, worms, Trojan horses, ransomware, spyware, adware, scareware, and other malicious programs.
- Malware may be obvious and simple to identify or it can be very stealthy and almost impossible to detect.

#### 3.1.1.2 Viruses, Worms, and Trojan Horses

**Viruses**

A virus is <u>malicious executable code attached to another executable file</u>, such as a legitimate program. Most viruses require end-user initiation, and can activate at a specific time or date. Computer viruses usually spread in one of three ways: from removable media; from downloads off the Internet; and from email attachments. Viruses can be harmless and simply display a picture or they can be destructive, such as those that modify or delete data. In order to avoid detection, a virus mutates. The simple act of opening a file can trigger a virus. A boot sector, or file system virus, infects USB flash drives and can spread to the system’s hard disk. Executing a specific program can activate a program virus. Once the program virus is active, it will usually infect other programs on the computer or other computers on the network. The Melissa Virus was an example of a virus spread via email. Melissa affected tens of thousands of users and caused an estimated $1.2 billion in damage. Click [here](http://www.whoishostingthis.com/blog/2015/06/01/8-worst-viruses/) to read more about viruses.

**Worms**

Worms are <u>malicious code that replicates by independently exploiting vulnerabilities in networks</u>. Worms usually slow down networks. Whereas a virus requires a host program to run, worms <u>can run by themselves</u>. Other than the initial infection, worms no longer require user participation. After a worm affects a host, it is able to spread very quickly over the network. Worms share similar patterns. They all have an enabling vulnerability, a way to propagate themselves, and they all contain a payload.

Worms are responsible for some of the most devastating attacks on the Internet. For example, in 2001, the Code Red worm infected 658 servers. Within 19 hours, the worm infected over 300,000 servers.

**Trojan horse**

A Trojan horse is <u>malware that carries out malicious operations under the guise of a desired operation</u> such as playing an online game. This malicious code exploits the privileges of the user that runs it. A Trojan horse differs from a virus because <u>the Trojan binds itself to non-executable files</u>, such as image files, audio files, or games.

#### 3.1.1.3 Logic Bombs

A logic bomb is <u>a malicious program that uses a trigger to awaken the malicious code.</u> For example, triggers can be dates, times, other programs running, or the deletion of a user account. The logic bomb remains inactive until that trigger event happens. Once activated, a logic bomb implements a malicious code that causes harm to a computer. A logic bomb can sabotage database records, erase files, and attack operating systems or applications. Cybersecurity specialists recently discovered logic bombs that attack and destroy the hardware components in a workstation or server including the cooling fans, CPU, memory, hard drives and power supplies. The logic bomb overdrives these devices until they overheat or fail.

#### 3.1.1.4 Ransomware

<u>Ransomware holds a computer system, or the data it contains, captive until the target makes a payment.</u> Ransomware usually works by encrypting data in the computer with a key unknown to the user. The user must pay a ransom to the criminals to remove the restriction.

Some other versions of ransomware can take advantage of specific system vulnerabilities to lock down the system. Ransomware propagates as a Trojan horse and is the result of a downloaded file or some software weakness.

Payment through an untraceable payment system is always the criminal’s goal. Once the victim pays, the criminal supplies a program that decrypts the files or sends an unlock code. 

#### 3.1.1.5 Backdoors and Rootkits

A **backdoor** refers <u>to the program or code introduced by a criminal who has compromised a system</u>. The backdoor bypasses the normal authentication used to access a system. A few common backdoor programs are Netbus and Back Orifice, which both allow remote access to unauthorized system users. The purpose of the backdoor is to grant the cyber criminals <u>future access to the system even if the organization fixes the original vulnerability used to attack the system</u>. Usually, criminals have authorized users unknowingly run a Trojan horse program on their machine to install the backdoor.

A **rootkit** <u>modifies the operating system to create a backdoo</u>r. Attackers then use the backdoor to access the computer remotely. Most rootkits take advantage of software vulnerabilities to perform privilege escalation and modify system files. **Privilege escalation** takes advantage of programming errors or design flaws to grant the criminal elevated access to network resources and data. It is also common for rootkits to modify system forensics and monitoring tools, making them very hard to detect. Often, a user must wipe and reinstall the operating system of a computer infected by a rootkit.

### 3.1.2 Email and Browser Attacks

#### 3.1.2.1 Spam

Email is a universal service used by billions worldwide. As one of the most popular services, email has become a major vulnerability to users and organizations. Spam, also known as junk mail, is unsolicited email. In most cases, spam is a method of advertising. However, spam can send harmful links, malware, or deceptive content. The end goal is to obtain sensitive information such as a social security number or bank account information. Most spam comes from multiple computers on networks infected by a virus or worm. These compromised computers send out as much bulk email as possible.

#### 3.1.2.2 Spyware, Adware, and Scareware

Spyware is software that enables a criminal to obtain information about a user’s computer activities. Spyware often includes activity trackers, keystroke collection, and data capture. In an attempt to overcome security measures, spyware often modifies security settings. Spyware often bundles itself with legitimate software or with Trojan horses. Many shareware websites are full of spyware.

Adware typically displays annoying pop-ups to generate revenue for its authors. The malware may analyze user interests by tracking the websites visited. It can then send pop-up advertising pertinent to those sites. Some versions of software automatically install Adware. Some adware only delivers advertisements, but it is also common for adware to come with spyware.

Scareware persuades the user to take a specific action based on fear. Scareware forges pop-up windows that resemble operating system dialogue windows. These windows convey forged messages stating that the system is at risk or needs the execution of a specific program to return to normal operation. In reality, no problems exist, and if the user agrees and allows the mentioned program to execute, malware infects his or her system.

#### 3.1.2.3 Phishing

Phishing is a form of fraud. Cyber criminals use email, instant messaging, or other social media to try to gather information such as login credentials or account information by masquerading as a reputable entity or person. Phishing occurs when a malicious party sends a fraudulent email disguised as being from a legitimate, trusted source. The message intent is to trick the recipient into installing malware on his or her device or into sharing personal or financial information. An example of phishing is an email forged to look like it came from a retail store asking the user to click a link to claim a prize. The link may go to a fake site asking for personal information, or it may install a virus.

**Spear phishing**  is a highly targeted phishing attack. While phishing and spear phishing both use emails to reach the victims, spear phishing sends customized emails to a specific person. The criminal researches the target’s interests before sending the email. For example, a criminal learns that the target is interested in cars and has been looking to buy a specific model of car. The criminal joins the same car discussion forum where the target is a member, forges a car sale offering, and sends an email to the target. The email contains a link for pictures of the car. When the target clicks on the link, he or she unknowingly installs malware on the computer. 

#### 3.1.2.4 Vishing, Smishing, Pharming, and Whaling

- Vishing is phishing using voice communication technology. Criminals can spoof calls from legitimate sources using voice over IP (VoIP) technology. Victims may also receive a recorded message that appears legitimate. Criminals want to obtain credit card numbers or other information to steal the victim’s identity. Vishing takes advantage of the fact that people trust the telephone network.
- Smishing (Short Message Service phishing) is phishing using text messaging on mobile phones. Criminals impersonate a legitimate source in an attempt to gain the trust of the victim. For example, a smishing attack might send the victim a website link. When the victim visits the website, malware is installed on the mobile phone.
- Pharming is the impersonation of a legitimate website in an effort to deceive users into entering their credentials. Pharming misdirects users to a fake website that appears to be official. Victims then enter their personal information thinking that they connected to a legitimate site.
- Whaling is a phishing attack that targets high profile targets within an organization such as senior executives. Additional targets include politicians or celebrities.

#### 3.1.2.5 Browser Plugins and Browser Poisoning

Security breaches can affect web browsers by displaying pop-up advertising, collecting personally identifiable information, or installing adware, viruses, or spyware. A criminal can hack a browser’s executable file, a browser’s components, or its plugins.

- **Plugins**, The Flash and Shockwave plugins from Adobe enable the development of interesting graphic and cartoon animations that greatly enhance the look and feel of a web page. Plugins display the content developed using the appropriate software. Until recently, plugins had a remarkable safety record. As Flash-based content grew and became more popular, criminals examined the Flash plugins and software, determined vulnerabilities, and exploited Flash Player. Successful exploitation could cause a system crash or allow a criminal to take control of the affected system. Expect increased data losses to occur as criminals continue to investigate the more popular plugins and protocols for vulnerabilities.
- **SEO Poisoning**, Search engines such as Google work by ranking pages and presenting relevant results based on users’ search queries. Depending on the relevancy of web site content, it may appear higher or lower in the search result list. SEO, short for Search Engine Optimization, is a set of techniques used to improve a website’s ranking by a search engine. While many legitimate companies specialize in optimizing websites to better position them, SEO poisoning uses SEO to make a malicious website appear higher in search results. The most common goal of SEO poisoning is to increase traffic to malicious sites that may host malware or perform social engineering. To force a malicious site to rank higher in search results, attackers take advantage of popular search terms.
- **Browser Hijacker** A browser hijacker is malware that alters a computer's browser settings to redirect the user to websites paid for by the cyber criminals' customers. Browser hijackers usually install without the user's permission and are usually part of a drive-by download. A drive-by download is a program that automatically downloads to the computer when a user visits a web site or views an HTML email message. Always read user agreements carefully when downloading programs to avoid this type of malware.

## 3.2 Deception

### 3.2.1 The Art of Deception

#### 3.2.1.1 Social Engineering

Social engineering is a completely non-technical means for a criminal to gather information on a target. Social engineering is an attack that attempts to manipulate individuals into performing actions or divulging confidential information.

Social engineers often rely on people’s willingness to be helpful but also prey on people’s weaknesses. For example, an attacker could call an authorized employee with an urgent problem that requires immediate network access. The attacker could appeal to the employee’s vanity, invoke authority using name-dropping techniques, or appeal to the employee’s greed.

#### 3.2.1.2 Social Engineering Tactics

These are some types of social engineering attacks:

- **Pretexting** - This is when an attacker calls an individual and lies to them in an attempt to gain access to privileged data. An example involves an attacker who pretends to need personal or financial data in order to confirm the identity of the recipient.
- **Something for Something (Quid pro quo)** - This is when an attacker requests personal information from a party in exchange for something, like a gift.

### 3.2.2 Deception Methods

#### 3.2.2.1 Shoulder Surfing and Dumpster Diving

A criminal observes, or shoulder surfs, to pick up PINs, access codes or credit card numbers. An attacker can be in close proximity to his victim or the attacker can use binoculars or closed circuit cameras to shoulder surf. That is one reason that a person can only read an ATM screen at certain angles. These types of safeguards make shoulder surfing much more difficult.

"One man's trash is another man's treasure". This phrase can be especially true in the world of dumpster diving which is the process of going through a target's trash to see what information an organization throws out. Consider securing the trash receptacle. Any sensitive information should be properly disposed of through shredding or the use of burn bags, a container that holds classified or sensitive documents for later destruction by fire.

#### 3.2.2.2 Impersonation and Hoaxes

Impersonation is the action of pretending to be someone else. For example, a recent phone scam targeted taxpayers. A criminal, posing as an IRS employee, told the victims that they owed money to the IRS. The victims must pay immediately through a wire transfer. The impersonator threatened that failure to pay will result in an arrest. Criminals also use impersonation to attack others. They can undermine the credibility of individuals by using website or social media postings.

A hoax is an act intended to deceive or trick. A cyber hoax can cause just as much disruption as an actual breach would cause. A hoax elicits a user reaction. The reaction can create unnecessary fear and irrational behavior. Users pass hoaxes through email and social media. 

#### 3.2.2.3 Piggybacking and Tailgating

Piggybacking occurs when a criminal tags along with an authorized person to gain entry into a secure location or a restricted area. Criminals use several methods to piggyback:

- They give the appearance of being escorted by the authorized individual

- They join a large crowd pretending to be a member

- They target a victim who is careless about the rules of the facility

Tailgating is another term that describes the same practice.

A mantrap prevents piggybacking by using two sets of doors. After individuals enter an outer door, that door must close before entering the inner door.

## 3.3 Attacks

### 3.3.1 Types of Cyber Attacks

#### 3.3.1.1 Denial of Service

Denial-of-Service (DoS) attacks are a type of network attack. A DoS attack results in some sort of interruption of network services to users, devices, or applications. There are two major types of DoS attacks:

- **Overwhelming Quantity of Traffic** – The attacker sends an enormous quantity of data at a rate that the network, host, or application cannot handle. This causes a slowdown in transmission or response, or a crash of a device or service.

- **Maliciously Formatted Packets** – The attacker sends a maliciously formatted packet to a host or application and the receiver is unable to handle it. For example, an application cannot identify packets containing errors or improperly formatted packets forwarded by the attacker. This causes the receiving device to run very slowly or crash.

DoS attacks are a major risk because they can easily interrupt communication and cause significant loss of time and money. These attacks are relatively simple to conduct, even by an unskilled attacker.

The goal of a denial-of-service attack is to deny access to authorized users making the network unavailable (remember the three underlying security principles: confidentiality, integrity, and availability). 

A **Distributed DoS Attack (DDoS)** is similar to a DoS attack, but it originates from multiple, coordinated sources. As an example, a DDoS attack could proceed as follows:

An attacker builds a network of infected hosts, called a botnet, comprised of zombies. Zombies are the infected hosts. The attacker uses handler systems to control the zombies. The zombie computers constantly scan and infect more hosts, creating more zombies. When ready, the hacker instructs the handler systems to make the botnet of zombies carry out a DDoS attack.

#### 3.3.1.2 Sniffing

occurs when attackers examine all network traffic as it passes through their **NIC**, independent of whether or not the traffic is addressed to them or not. Criminals accomplish network sniffing with a software application, hardware device, or a combination of the two. As shown in the figure, sniffing views all network traffic or it can target a specific protocol, service, or even string of characters such as a login or password. Some network sniffers observe all traffic and modify some or all of the traffic as well.

Sniffing also has its benefits. Network administrators may also use sniffers to analyze network traffic, identify bandwidth issues, and troubleshoot other network issues.

Physical security is important in preventing the introduction of sniffers on the internal network.

#### 3.3.1.3 Spoofing

Spoofing is an impersonation attack, and it takes advantage of a trusted relationship between two systems. If two systems accept the authentication accomplished by each other, an individual logged onto one system might not go through an authentication process again to access the other system. An attacker can take advantage of this arrangement by sending a packet to one system that appears to have come from a trusted system. Since the trusted relationship is in place, the targeted system may perform the requested task without authentication.

There are multiple types of spoofing attacks.

- **MAC address** spoofing occurs when one computer accepts data packets based on the MAC address of another computer.

- **IP spoofing** sends IP packets from a spoofed source address to disguise itself.

- **Address Resolution Protocol (ARP)** is a protocol that resolves IP addresses to MAC addresses for transmitting data. ARP spoofing sends spoofed ARP messages across a LAN to link the criminal’s MAC address with the IP address of an authorized member of the network.

- The **Domain Name System (DNS)** associates domain names with IP addresses. DNS server spoofing modifies the DNS server to reroute a specific domain name to a different IP address controlled by the criminal.

#### 3.3.1.4 Man-in-the-middle

A criminal performs a man-in-the-middle (MitM) attack by <u>intercepting communications between computers to steal information crossing the network</u>. The criminal can also choose to manipulate messages and relay false information between hosts since the hosts are unaware that a modification to the messages occurred. MitM allows the criminal to take control over a device without the user’s knowledge.

#### 3.3.1.5 Zero-Day Attacks

A zero-day attack, sometimes referred to as a zero-day threat, is a computer attack that tries to exploit software vulnerabilities that are unknown or undisclosed by the software vendor. The term zero hour describes the moment when someone discovers the exploit. During the time it takes the software vendor to develop and release a patch, the network is vulnerable to these exploits, as shown in the figure. Defending against these fast-moving attacks requires network security professionals to adopt a more sophisticated view of the network architecture. It is no longer possible to contain intrusions at a few points in the network.

#### 3.3.1.6 Keyboard Logging

Keyboard logging is a software program that records or logs the keystrokes of the user of the system. Criminals can implement keystroke loggers through software installed on a computer system or through hardware physically attached to a computer. The criminal configures the key logger software to email the log file. The keystrokes captured in the log file can reveal usernames, passwords, websites visited, and other sensitive information.

Keyboard loggers can be legitimate, commercial software. Parents often purchase key logger software to track the websites and behavior of children using the Internet. Many anti-spyware applications are able to detect and remove unauthorized key loggers. Although keylogging software is legal, criminals use the software for illegal purposes.

### 3.3.2 Wireless and Mobile Device Attacks

#### 3.3.2.1 Grayware and SMiShing

Grayware is becoming a problem area in mobile security with the popularity of smartphones. Grayware includes applications that behave in an annoying or undesirable manner. Grayware may not have recognizable malware concealed within, but it still may pose a risk to the user. For example, Grayware can track the user’s location. The authors of grayware usually maintain legitimacy by including an application’s capabilities in the small print of the software license agreement. Users install many mobile apps without really considering their capabilities.

SMiShing is short for SMS phishing. It uses Short Message Service (SMS) to send fake text messages. The criminals trick the user into visiting a website or calling a phone number. Unsuspecting victims may then provide sensitive information such as credit card information. Visiting a website might result in the user unknowingly downloading malware that infects the device.

#### 3.3.2.2 Rogue Access Points

A rogue access point is a wireless access point installed on a secure network without explicit authorization. A rogue access point can be set up in two ways. The first is when a well-intentioned employee is trying to be helpful by making it easier to connect mobile devices. The second way is when a criminal gains physical access to an organization by sneaking in and installs the rogue access point. Since both are unauthorized, both pose risks to the organization.

A rogue access point can also refer to a criminal’s access point. In this instance, the criminal sets up the access point as a MitM device to capture login information from users.

An Evil Twin attack uses the criminal’s access point improved with higher power and higher gain antennas to look like a better connection option for users. After users connect to the evil access point, the criminals can analyze traffic and execute MitM attacks.

#### 3.3.2.3 RF Jamming

Wireless signals are susceptible to electromagnetic interference (EMI), radio-frequency interference (RFI), and may even be susceptible to lightning strikes or noise from fluorescent lights. Wireless signals are also susceptible to deliberate jamming. Radio frequency (RF) jamming disrupts the transmission of a radio or satellite station so that the signal does not reach the receiving station.

The frequency, modulation, and power of the RF jammer needs to be equal to that of the device that the criminal wants to disrupt in order to successfully jam the wireless signal.

#### 3.3.2.4 Bluejacking and Bluesnarfing

Bluetooth is a short-range, low-power protocol. Bluetooth transmits data in a personal area network, or PAN, and can include devices such as mobile phones, laptops, and printers. Bluetooth has gone through several version releases. Easy configuration is a characteristic of Bluetooth, so there is no need for network addresses. Bluetooth uses pairing to establish the relationship between devices. When establishing the pairing, both devices use the same passkey.

Bluetooth vulnerabilities have surfaced, but due to the limited range of Bluetooth, the victim and the attacker need to be within range of each other.

- Bluejacking is the term used for sending unauthorized messages to another Bluetooth device. A variation of this is to send a shocking image to the other device.

- Bluesnarfing occurs when the attacker copies the victim's information from his device. This information can include emails and contact lists.

#### 3.3.2.5 WEP and WPA Attacks

**Wired Equivalent Privacy** (WEP) is a security protocol that attempted to provide a wireless local area network (WLAN) with the same level of security as a wired LAN. Since physical security measures help to protect a wired LAN, WEP seeks to provide similar protection for data transmitted over the WLAN with encryption.

WEP uses a key for encryption. There is no provision for key management with WEP, so the number of people sharing the key will continually grow. Since everyone is using the same key, the criminal has access to a large amount of traffic for analytic attacks.

WEP also has several problems with its initialization vector (IV) which is one of the components of the cryptographic system:

- It is a 24-bit field, which is too small.

- It is cleartext, which means it is readable.

- It is static so identical key streams will repeat on a busy network.

**Wi-Fi Protected Access (WPA)** and then WPA2 came out as improved protocols to replace WEP. WPA2 does not have the same encryption problems because an attacker cannot recover the key by observing traffic. WPA2 is susceptible to attack because cyber criminals can analyze the packets going between the access point and a legitimate user. Cyber criminals use a packet sniffer and then run attacks offline on the passphrase.

### 3.3.3 Application Attacks

#### 3.3.3.1 Cross-Site Scripting

Cross-site scripting (XSS) is a vulnerability found in web applications. XSS allows criminals to inject scripts into the web pages viewed by users. This script can contain malicious code.

Cross-site scripting has three participants: the criminal, the victim, and the website. The cyber-criminal does not target a victim directly. The criminal exploits vulnerability within a website or web application. Criminals inject client-side scripts into web pages viewed by users, the victims. The malicious script unknowingly passes to the user's browser. A malicious script of this type can access any cookies, session tokens, or other sensitive information. If criminals obtain the victim’s session cookie, they can impersonate that user.

#### 3.3.3.2 Code Injection

One way to store data at a website is to use a database. There are several different types of databases such as a Structured Query Language (SQL) database or an Extensible Markup Language (XML) database. Both XML and SQL injection attacks exploit weaknesses in the program such as not validating database queries properly.

- **XML Injection** : When using an XML database, an XML injection is an attack that can corrupt the data. After the user provides input, the system accesses the required data via a query. The problem occurs when the system does not properly scrutinize the input request provided by the user. Criminals can manipulate the query by programming it to suit their needs and can access the information on the database. All sensitive data stored in the database is accessible to the criminals and they can make any number of changes to the website. An XML injection attack threatens the security of the website.
- **SQL Injection** The cybercriminal exploits a vulnerability by inserting a malicious SQL statement in an entry field. Again, the system does not filter the user input correctly for characters in an SQL statement. Criminals use SQL injection on websites or any SQL database.

Criminals can spoof an identity, modify existing data, destroy data, or become administrators of the database server.

#### 3.3.3.3 Buffer Overflow

A buffer overflow occurs when data goes beyond the limits of a buffer. Buffers are memory areas allocated to an application. By changing data beyond the boundaries of a buffer, the application accesses memory allocated to other processes. This can lead to a system crash, data compromise, or provide escalation of privileges.

The CERT/CC at Carnegie Mellon University estimates that nearly half of all exploits of computer programs stem historically from some form of buffer overflow. The generic classification of buffer overflows includes many variants, such as static buffer overruns, indexing errors, format string bugs, Unicode and ANSI buffer size mismatches, and heap overruns.

#### 3.3.3.4 Remote Code Executions

Vulnerabilities allow a cybercriminal to execute malicious code and take control of a system with the privileges of the user running the application. Remote code execution allows a criminal to execute any command on a target machine.

Take, for example, Metasploit. Metasploit is a tool for developing and executing exploit code against a remote target. Meterpreter is an exploit module within Metasploit that provides advanced features. Meterpreter allows criminals to write their own extensions as a shared object. Criminals upload and inject these files into a running process on the target. Meterpreter loads and executes all of the extensions from memory, so they never involve the hard drive. This also means that these files fly under the radar of antivirus detection. Meterpreter has a module for controlling a remote system’s webcam. Once a criminal installs Meterpreter on the victim’s system, he or she can view and capture images from the victim’s webcam.

#### 3.3.3.5 ActiveX Controls and Java

When browsing the web, some pages may not work properly unless the user installs an ActiveX control. ActiveX controls provide the capability of a plugin to Internet Explorer. ActiveX controls are pieces of software installed by users to provide extended capabilities. Third parties write some ActiveX controls and they may be malicious. They can monitor browsing habits, install malware, or log keystrokes. ActiveX controls also work in other Microsoft applications.

Java operates through an interpreter, the Java Virtual Machine (JVM). The JVM enables the Java program’s functionality. The JVM sandboxes or isolates untrusted code from the rest of the operating system. There are vulnerabilities, which allow untrusted code to go around the restrictions imposed by the sandbox. There are also vulnerabilities in the Java class library, which an application uses for its security. Java is the second biggest security vulnerability next to Adobe’s Flash plugin.



## 3.4 Summary

Threats, vulnerabilities, and attacks are the central focus of cybersecurity professionals. This chapter discussed the various cybersecurity attacks that cyber criminals launch. The chapter explained the threat of malware and malicious code. The chapter discussed the types of deception involved with social engineering. It also covered the types of attacks that both wired and wireless networks experience. Finally, the chapter discussed the vulnerabilities presented by application attacks.

Understanding the types of possible threats allows an organization to identify the vulnerabilities that make it a target. The organization can then learn how to defend itself against cybersecurity deception and maneuvering.

