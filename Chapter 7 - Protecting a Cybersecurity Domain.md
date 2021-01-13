# Chapter 7 Protecting a Cybersecurity Domain

## 7.1 Defending Systems and Devices

### 7.1.1 Host Hardening

- beveiliging van OS
  - pas configuratie aan
  - verwijder onnodige software
  - voer beveligingspatches en updates uit 
- installeer **anti-malware** (let op dat de anti-malware zelf betrouwbaar is)
- beheer **patches**
- installeer host-gebasseerde **firewal** => softwarefirewall is een programma dat op een computer wordt uitgevoerd om verkeer tussen de computer en andere aangesloten computers toe te staan of te weigeren. De softwarefirewall past een reeks regels toe op datatransmissies door inspectie en filtering van datapakketten.
- installeer **Host-intrussion-detection-system** (HIDS) => software die verdachte activiteiten controleert 
- configureer **VPN** voor beveiligde communicatie over een publiek netwerk 

### 7.1.2 Hardening Wireless and Mobile Devices

- **WEP** (wired equivalent privacy) => <u>niet meer veilig</u>
- **WPA/WPA-2** (wifi protected access)
  - gebasseerd op AES (advanced encryption standard) = private key encryption
  - WPA-2 is current standard
- **wederzijdse authenticatie** => proces waarbij bij beide entiteiten zich bij elkaar authentificeren
  - voorkomt **man-in-the-middle** (rogue access points)

### 7.1.3 Host Data Protection

- bestand **toagangscontrole**
- bestand **encryptie**
- gegevens en systeem **backups**

### 7.1.4 Images and Content Control

#### Content Screening and Blocking

**content screening** = Content control software Beperkt de inhoud waartoe een gebruiker toegang heeft met een webbrowser via internet.

#### Disk Cloning and Deep Freeze

**Disk cloning** => <u>copies the contents of the computer’s hard disk to an image file</u>. For example, an administrator creates the required partitions on a system, formats the partition, and then installs the operating system. She installs all required application software and configures all hardware. The administrator then uses disk-cloning software to create the image file. The administrator can use the cloned image as follows:

- To automatically wipe a system and restore a clean master image

- To deploy new computers within the organization

- To provide a full system backup

**Deep Freeze** => <u>“freezes” the hard drive partition</u>. When a user <u>restarts</u> the system, the system <u>reverts to its frozen configuration</u>. The system does not save any changes that the user makes, so any applications installed or files saved are lost when the system restarts.

If the administrator needs to change the system’s configuration, she must first <u>“thaw”</u> the protected partition by disabling Deep Freeze. After making the changes, she must re-enable the program. The administrator can configure Deep Freeze to restart after a user logs out, shuts down after a period of inactivity, or shuts down at a scheduled time.

### 7.1.5 Physical Protection of Workstations

- Security Cables and Locks
- Logout Timers
- GPS Tracking
- Inventory and RFID Tags

## 7.2 Server Hardening

### A. Secure Remote Access

externe toegang = elke combinatie van hardware en software die gebruikers op afstand toe tot een lokaal intern netwerk

#### Telnet, SSH, and SCP

- **telnet** = old and **unsecure** method of remote access in which data was sent in plaintext
- **shh** = provides a secure protocol for **encrypted** remote access 
- **scp** (secure copy) = safely transports files between two systems. it uses SSH for file-transfer (and authentication) so it ensures integrity and confidentiality for data in transit

### B. Administrative Measures

#### Securing Ports and Services

- administator moet kijken welke services noodzakelijk zijn en welk risico ze mogelijk vormen 

```
open **poorten** kunnen helpen bij achterhalen welke **services** er actief zijn op een **host**

**IP address** - zorgt voor connectie met correcte machine  

**port** - zorgt voor de juiste service op een machine  ( range 0 to 65535) 

**socket** -  IP address + port + protocol (TCP and UDP)

The first 1000 ports are reserved for specific applications, and on Linux can normally own be used by a daemon / application that has super user privileges. These are referred to as well known ports. Some are defined in RFC 1340, and more are defined by IANA.
```

#### Privileged Accounts

accounts met vaak verhoogde of onbeperkte toegang. dergelijke accounts moeten voldoende beveiligd worden of eventueel verwijderd worden. 

#### Group Policies

onderdeel van **active directory** (windows). laat toe bepaalde **beveiligingsmaatregelen** op te stellen voor een **groep gebruikers** 

#### Enable Logs and Alerts

- belankrijk voor accountability (A in 3*A of confidentiality)
- registreert gebeurtenissen op systeem 

### C. physical Protection of Servers

- Power
- Heating, Ventilation, and Air Conditioning (HVAC)
- Hardware Monitoring

## 7.3 Network Hardening





<img src="https://fiverr-res.cloudinary.com/images/q_auto,f_auto/gigs/127371705/original/34d51e6c379e180511771c46e6da7e0f9e19159e/configure-and-troubleshoot-router-firewall-and-switches-i-work-on-the-project.jpg" width=500/>

**NOC** (network operations center) => centrums die een gedetailleerde **status van een netwerk** geven. ze zijn ground zero voor oplossen van netwerkproblemen. 

**firewalls** = hardware of softwareoplossingen die een **netwerksbeveiligingsbeleid** afdwingen door te **voorkomen** dat **ongeautoriseerd** of **potentieel gevaarlijk** verkeer het netwerk binnendringt. 