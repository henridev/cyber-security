# Chapter 6 The Five Nines Concept

## Introduction

Organizations  want to **maximize availability of systems and data**  =>  measures to minimize or eliminate data loss and to minimize the downtime of mission critical processes because if employees cannot perform their regular duties, the organization is in jeopardy of losing revenue.

Organizations measure availability by percentage of **uptime**. 

- **concept of five nines**. Many industries must maintain the highest availability 
- This chapter discusses various approaches that organizations can take to help meet their **availability** goals. **Redundancy** provides backup and includes extra components for computers or network systems to ensure the systems remain available. Redundant components can include hardware such as disk drives, servers, switches, and routers or software such as operating systems, applications, and databases. 
- The chapter also discusses **resiliency**, the ability of a server, network, or data center to recover quickly and continue operation.

- Organizations must be prepared to respond to an incident by establishing procedures that they follow after an event occurs. The chapter concludes with a discussion of **disaster recovery** and **business continuity** planning which are both critical in maintaining availability to an organization’s resources.

## 1 High Availability

### The Five Nines

System and services have a 99,999% uptime and thus a downtime of around 5 min per year

**High availability** refers to a system or component that is continuously operational for a given length of time. To help ensure high availability:

- Eliminate **single points of failure**
- Design for **reliability**
- **monitor** systems
- **Detect** failures as they occur
- put in place **redundancy ** and **backups**

Sustaining high availability at the standard of five-nines 

- **can increase costs and utilize many resources.** The increased costs are due to the purchase of additional hardware such as servers and components. As an organization adds components, the result is an increase in **configuration complexity**. 
- increased configuration complexity **increases the risk factors.** The more moving parts involved, the higher the likelihood of failed components.

#### Designing High Availability System

Although the cost of sustaining high availability may be too costly for some industries, several environments require five nines.

High availability incorporates three major principles to achieve the goal of uninterrupted access to data and services:

- Elimination or reduction of **single-points of failure**
- **System Resiliency** = ability to maintain availability during disruptive events
- **Fault Tolerance** = continue operating if one or more components fail 

It is important to understand the ways to address a single point of failure. A single point of failure can include central routers or switches, network services, and even highly skilled IT staff. The key is that a loss of the system, process, or person can have a very disruptive impact on the entire system. The key is to have processes, resources, and components that reduce single points of failure. High availability clusters is one way to provide redundancy. These clusters consist of a group of computers that have access to the same-shared storage and have identical network configurations. All servers take part in processing a service simultaneously. From the outside, the server group looks like one device. If a server within the cluster fails, the other servers continue to process the same service as the failed device.

**Systems resiliency** refers to the capability to maintain availability of data and operational processing despite attacks or disrupting event. Generally, this requires redundant systems, in terms of both power and processing, so that should one system fail, the other can take over operations without any break in service. System resiliency is more than hardening devices; it requires that both data and services be available even when under attack.

**Fault tolerance** enables a system to continue to operate if one or more components fail. Data mirroring is one example of fault tolerance. Should a "fault" occur, causing disruption in a device such as a disk controller, the mirrored system provides the requested data with no apparent interruption in service to the user.

## 2 Measures to Improve Availability

### 2.1 Asset Management

#### Asset Identification

An organization needs to **know what hardware and software** are present as a prerequisite to knowing what the configuration parameters need to be. Asset management includes a complete **inventory of hardware and software**.

This means that the **organization needs to know all of components that can be subject to security risks,** including:

hardware system, operating system, hardware network device, network device operating system, software application, All firmware, All language runtime environments, All individual libraries

**An organization may choose an automated solution to keep track of assets.** An administrator should investigate any changed configuration because it may mean that the configuration is not up-to-date. It can also mean that unauthorized changes are happening.

#### Asset Classification

assigns all resources of an **organization into a group based on common characteristics.** An organization should apply an asset classification system to documents, data records, data files, and disks. The most critical information needs to receive the highest level of protection and may even require special handling. An organization can adopt a labeling system according to how valuable, how sensitive, and how critical the information is. Complete the following steps to identify and classify the assets of an organization:

- Determine the proper asset identification category.
- Establish asset accountability by identifying the owner for all information assets and application software.
- Determine the criteria for classification.
- Implement a classification schema.

For example, the U.S. government uses sensitivity to classify data as follows: top secret; secret; confidential; public trust; and unclassified.

Asset management manages the lifecycle and inventory of technology assets including devices and software. As part of an IT asset management system, an organization specifies the acceptable IT assets that meet its objectives. This practice effectively reduces the different asset types. For example, an organization will only install applications that meet its guidelines. When administrators eliminate applications that do not meet the guidelines, they are effectively increasing security.

#### Asset Standardization

identify specific hardware and software products that the organization uses and supports. When a failure occurs, prompt action helps to maintain both access and security. If an organization does not standardize its hardware selection, personnel may need to scramble to find a replacement component. Non-standard environments require more expertise to manage and they increase the cost of maintenance contracts and inventory.

The United States Computer Emergency Readiness Team (US-CERT) and the U.S. Department of Homeland Security sponsor a dictionary of **common vulnerabilities and exposure (CVE)**. CVE contains a standard identifier number with a brief description, and references to related vulnerability reports and advisories. The MITRE Corporation maintains the CVE List and its public website.

#### Threat Identification

begins with the process of creating a CVE Identifier for publicly known cybersecurity vulnerabilities. Each CVE Identifier includes the following:

- The CVE Identifier number

- A brief description of the security vulnerability

- Any important references

Click [here](http://cve.mitre.org/cve/identifiers/) to learn more about CVE Identifier

#### Risk Analysis

is the process of analyzing the dangers posed by natural and human-caused events to the assets of an organization.

- **Quantitative Risk Analysis** : A quantitative analysis assigns numbers to the risk analysis process (Figure 1). The asset value is the replacement cost of the asset. The value of an asset can also be measured by the income gained through use of the asset. The exposure factor (EF) is a subjective value expressed as a percentage that an asset loses due to a particular threat. If a total loss occurs, the EF equals 1.0 (100%). In the quantitative example, the server has an asset value of $15,000. When the server fails, a total loss occurs (the EF equals 1.0). The asset value of $15,000 multiplied by the exposure factor of 1 results in a single loss expectancy of $15,000. 
  - The annualized rate of occurrence (ARO) is the probability that a loss will occur during the year (also expressed as a percentage). An ARO can be greater than 100% if a loss can occur more than once a year.
  - The calculation of the annual loss expectancy (ALE) gives management some guidance on what it should spend to protect the asset.
- **Qualitative Risk Analysis** : uses opinions and scenarios. Figure 2 provides an example of table used in qualitative risk analysis, which plots the likelihood of a threat against its impact. For example, the threat of a server failure may be likely, but its impact may only be marginal.
  - A team evaluates each threat to an asset and plots it in the table. The team ranks the results and uses the results as a guide. They may determine to take action on only threats that fall within the red zone.
  - The numbers used in the table do not directly relate to any aspect of the analysis. For example, a catastrophic impact of 4 is not twice as bad as a marginal impact of 2. This method is subjective in nature.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606037013/Untitled_Diagram-Page-2_2_hbzdk1.png" width=500/>

#### Mitigation

involves **reducing the severity of the loss or the likelihood of the loss from occurring**. Many technical controls mitigate risk including authentication systems, file permissions, and firewalls. Organization and security professionals must understand that risk mitigation can have both positive and negative impact on the organization. Good risk mitigation finds a balance between the negative impact of countermeasures and controls and the benefit of risk reduction. There are four common ways to reduce risk:

- *Accept* the risk and periodically re-assess

- *Reduce* the risk by implementing controls

- *Avoid* the risk by totally changing the approach

- *Transfer* the risk to a third party

A short-term strategy is to accept the risk necessitating the creation of contingency plans for that risk. People and organizations have to accept risk on a daily basis. Modern methodologies reduce risk by developing software incrementally and providing regular updates and patches to address vulnerabilities and misconfigurations.

Outsourcing services, purchasing insurance, or purchasing maintenance contracts are all examples of risk transfer. Hiring specialists to perform critical tasks to reduce risk can be a good decision and yield greater results with less long term investment. A good risk mitigation plan can include two or more strategies.

### 2.2 Defense in Depth

will not provide an impenetrable cyber shield, but it will help an organization minimize risk by keeping it one-step ahead of cyber criminals.

- **layering** 
  - To make sure data and information remains available, an organization must create different layers of protection. A layered approach provides the most comprehensive protection. 
  - If cyber criminals penetrate one layer, they still have to contend with several more layers with each layer being more complicated than the previous. 
  - Layering is creating a barrier of **multiple defenses** that coordinate together to prevent attacks. 

> For example, an organization might store its top secret documents on a server in a building surrounded by an electronic fence.

- **limiting** 
  - reduces the possibility of a threat. 
  - An organization should restrict access so that users only have the level of access required to do their job. 

> For example, the people in the marketing department do not need access to payroll records to perform their jobs.

Technology-based solutions such as using file permissions are one way to limit access; an organization should also implement procedural measures. A procedure should be in place that prohibits an employee from removing sensitive documents from the premises.

- **diversity** If cyber criminals penetrate one layer, the same technique will not work on all of the other layers. **Breaching one layer of security does not compromise the whole system**. An organization may use different encryption algorithms or authentication systems to protect data in different states.
- **Obscuring** information can also protect data and information. An organization should not reveal any information that cyber criminals can use to figure out what version of the operating system a server is running or the type of equipment it uses. For example, error messages should not contain any details that cyber criminals could use to determine what vulnerabilities are present. Concealing certain types of information makes it more difficult for cyber criminals to attack a system.
- **Complexity** does not necessarily guarantee security. If an organization implements complex systems that are hard to understand and troubleshoot, it may actually backfire. If employees do not understand how to configure a complex solution properly, it may make it just as easy for cyber criminals to compromise those systems. To maintain availability, a security solution should be simple from the inside, but complex on the outside.

### 2.3 Redundancy

#### Single Points of Failure

 is the weak link in the chain that can cause disruption of the organization's operations.

- the solution to a single point of failure is to **modify the critical operation so that it does not rely on a single element.** 
- The organization can also build **redundant** components into the critical operation to take over the process should one of these points fail.

#### N+1 Redundancy

ensures system availability in the event of a component failure. Components (N) need to have at least one backup component (+1). For example, a car has four tires (N) and a spare tire in the trunk in case of a flat (+1).

In a data center, N+1 redundancy means that the system design can withstand the loss of a component. The N refers to many different components that make up the data center including servers, power supplies, switches, and routers. The +1 is the additional component or system that is standing by ready to go if needed.

>  An example of N+1 redundancy in a data center is a power generator that comes online when something happens to the main power source. Although an N+1 system contains redundant equipment, **it is not a fully redundant system**.

#### RAID

A redundant array of independent disks (RAID) combines multiple physical hard drives into a single logical unit to provide data redundancy and improve performance. RAID takes data that is normally stored on a single disk and spreads it out among several drives. If any single disk is lost, the user can recover data from the other disks where the data also resides.

- RAID can also increase the speed of data recovery. Using multiple drives will be faster retrieving requested data instead of relying on just one disk to do the work.
- A RAID solution can be either hardware-based or software-based. A hardware-based solution requires a specialized hardware controller on the system that contains the RAID drives. The following terms describe how RAID stores data on the various disks:
  - **Parity** - Detects data errors.
  
  - **Striping** - Writes data across multiple drives.
  
  - **Mirroring** - Stores duplicate data on a second drive.
  
    

<img src="https://www.mycloudwiki.com/wp-content/uploads/2016/07/raid.jpg" height=300/>



#### Spanning Tree

verhoogt beschikbaarheid (**availbality**) door netwerk tegen een **single point of failure** te beschermen. dit punt kan een switch of netwerk kabel zijn.

probleem => bij fysieke redundancy in een netwerk komen vaak loops en duplicate frame errors voor wat zware gevolgen kan hebben voor **switched networks**.

oplossing => **Spanning Tree Protocol (STP) => The basic function of STP is to prevent loops on a network when switches interconnect via multiple paths. STP ensures that redundant physical links are loop-free.** It ensures that there is only one logical path between all destinations on the network. STP intentionally blocks redundant paths that could cause a loop.

Blocking the redundant paths is critical to preventing loops on the network. The physical paths still exist to provide redundancy, but STP disables these paths to prevent the loops from occurring. If a network cable or switch fails, STP recalculates the paths and unblocks the necessary ports to allow the redundant path to become active.

- PC1 sends a broadcast out onto the network.

- The trunk link between S2 and S1 fails, resulting in disruption of the original path.

- S2 unblocks the previously blocked port for Trunk2 and allows the broadcast traffic to traverse the alternate path around the network, permitting communication to continue.

- If the link between S2 and S1 comes back up, STP again blocks the link between S2 and S3.

  <img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606038436/Untitled_Diagram-Page-2_3_fmwumd.png" width=400/>

#### Router Redundancy

The default gateway is typically the router that provides devices access to the rest of the network or to the Internet. If there is only one router serving as the default gateway, it is a **single point of failure**. The organization can choose to install an additional standby router.

below the forwarding router and the standby router use a **redundancy protocol** to determine which router should take the active role in forwarding traffic. Each router is configured with a physical IP address and a virtual router IP address. End devices use the virtual IP address as the default gateway. The forwarding router is listening for traffic addressed to 192.0.2.100. The forwarding router and the standby router use their physical IP addresses to send periodic messages. The purpose of these messages is to make sure both are still online and available. If the standby router no longer receives these periodic messages from the forwarding router, the standby router will assume the forwarding role

The ability of a network to dynamically recover from the failure of a device acting as a default gateway is known as **first-hop redundancy.**

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606038748/Screenshot_2020-11-22_105216_hei9wi.png" width=450>

#### Router Redundancy Options

The following list defines the options available for router redundancy based on the protocol that defines communication between network devices:

- **Hot Standby Router Protocol (HSRP)** - HSRP provides high network availability by providing first-hop routing redundancy. A group of routers use HSRP for selecting an active device and a standby device. In a group of device interfaces, the active device is the device that routes packets; the standby device is the device that takes over when the active device fails. The function of the HSRP standby router is to monitor the operational status of the HSRP group and to quickly assume packet-forwarding responsibility if the active router fails.

- **Virtual Router Redundancy Protocol (VRRP)** - A VRRP router runs the VRRP protocol in conjunction with one or more other routers attached to a LAN. In a VRRP configuration, the elected router is the virtual router master, and the other routers act as backups, in case the virtual router master fails.

- **Gateway Load Balancing Protocol (GLBP)** - GLBP protects data traffic from a failed router or circuit, like HSRP and VRRP, while also allowing load balancing (also called load sharing) between a group of redundant routers.

### 2.4 System Resilience / weerstand

resilience **is the methods and configurations used to make a system or network tolerant of failure.** 

> For example, a network can have redundant links between switches running STP. Although STP does provide an alternate path through the network if a link fails, the switchover may not be immediate if the configuration is not optimal.

Routing protocols also provide resiliency, but fine-tuning can improve the switchover so that network users do not notice. Administrators should investigate non-default settings in a test network to see if they can improve network recovery times.

Resilient design is more than just adding redundancy. It is critical to understand the business needs of the organization, and then incorporate redundancy to create a resilient network.

Application resilience is the application’s ability to react to problems in one of its components while still functioning. Downtime is due to failures caused by application errors or infrastructure failures. An administrator will eventually need to shut down applications for patching, version upgrades, or to deploy new features. Downtime can also be the result of data corruption, equipment failures, application errors, and human errors.

Many organizations try to balance out the cost of achieving the resiliency of application infrastructure with the cost of losing customers or business due to an application failure. Application high availability is complex and costly. The figure shows three availability solutions to address application resilience. As the availability factor of each solution increases, the complexity and cost also increase.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606040241/Screenshot_2020-11-22_111612_kcb9sa.png" style="zoom:70%;" />



## 3 Incident Response

### 3.1 Incident Response Phases

procedure gevolgd door organisaties wanneer een buitengewoon event plaatsvindt. 

When an incident occurs, the organization must know how to respond. 

- An organization needs to develop an **incident response plan** 
- a **Computer Security Incident Response Team (CSIRT)** to manage the response. 

phases:

1. preparation.
2. Detection and Analysis
3. Isolate, eradication and recovery
4. Post-incident follow-up

### 3.2 Incident Response Technologies

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606141025/Untitled_Diagram-Page-2_4_uyoobu.png" height=800/>

#### NAC Network Admission Control

- allows authorized users with compliant systems access to the network. A compliant system meets all of the **policy requirements** of the organization. 
- NAC evaluates an incoming device against the policies of the network. 
- NAC quarantines the systems that do not comply and manages the remediation of noncompliant systems.
- a NAC framework can use the existing network infrastructure and third-party software to enforce the security policy compliance for all endpoints. 
- a NAC appliance controls network access, evaluates compliance, and enforces security policy. Common NAC systems checks include:
  - Updated virus detection
  - Operating systems patches and updates
  - Complex password enforcement

#### IDS Intrusion Detection Systems

 (intrusion detection system) passively monitor the traffic on a network. The figure shows that an IDS-enabled device copies the traffic stream and analyzes the copied traffic rather than the actual forwarded packets. Working offline, it compares the captured traffic stream with known malicious signatures, similar to software that checks for viruses. Working offline means several things:

- IDS **works passively**

- IDS device is physically positioned in the network so that traffic must be mirrored in order to reach it

- Network traffic does not pass through the IDS unless it is mirrored

Passive means that the IDS monitors and reports on traffic. It does not take any action. This is the definition of operating in promiscuous mode.

- The advantage of operating with a copy of the traffic is that the IDS does not negatively affect the packet flow of the forwarded traffic. 
- The disadvantage of operating on a copy of the traffic is that the IDS cannot stop malicious single-packet attacks from reaching the target before responding to the attack. An IDS often requires assistance from other networking devices, such as routers and firewalls, to respond to an attack.

#### IPS Intrusion Prevention Systems

a device that can immediately detect and stop an attack.  An IPS device operates in **inline mode**. This means that all incoming and outgoing traffic must flow through it for processing. As shown in the figure, an IPS does not allow packets to enter the trusted side of the network unless it has analyzed the packets. It can detect and immediately address a network problem.

An IPS monitors network traffic. It analyzes the contents and the payload of the packets for more sophisticated embedded attacks that might include malicious data. Some systems use a blend of detection technologies, including signature-based, profile-based, and protocol analysis-based intrusion detection. This deeper analysis enables the IPS to identify, stop, and block attacks that would pass through a traditional firewall device. When a packet comes in through an interface on an IPS, *the outbound or trusted interface does not receive that packet until the IPS analyzes the packet.*

- The advantage of operating in inline mode is that the IPS can stop single-packet attacks from reaching the target system. 
- The disadvantage is that a poorly configured IPS can negatively affect the packet flow of the forwarded traffic.

The biggest difference between IDS and IPS is that an IPS responds immediately and does not allow any malicious traffic to pass, whereas an IDS allows malicious traffic to pass before addressing the problem.

#### NetFlow and IPFIX

unimportant

#### Advanced Threat Intelligence

can help organizations detect attacks during one of the stages of the cyberattack and sometimes before with the right information.

Organizations may be able to detect indicators of attack in its logs and system reports for the following security alerts:

- Account lockouts

- All database events

- Asset creation and deletion

- Configuration modification to systems

Advanced threat intelligence is a type of event or profile data that can contribute to security monitoring and response. As the cyber criminals become more sophisticated, it is important to understand the malware maneuvers. With improved visibility into attack methodologies, an organization can respond more quickly to incidents.

## 4 Disaster Recovery

### Disasters Recovery Planning

#### Disaster Recovery Plan

An organization puts its disaster recovery plan (DRP) into action while the disaster is ongoing and employees are scrambling to ensure critical systems are online. The DRP includes the activities the organization takes to assess, salvage, repair, and restore damaged facilities or assets.

**A DRP needs to identify which processes in the organization are the most critical. During the recovery process, the organization restores its mission critical systems first**

#### Implementing Disaster Recovery Controls

Disaster recovery controls minimize the effects of a disaster to ensure that resources and business processes can resume operation.

There are three types of IT disaster recovery controls:

- **Preventative measures** include controls that prevent a disaster from occurring. These measures seek to identify risks.

- **Detective measures** include controls that discover unwanted events. These measures uncover new potential threats.

- **Corrective measures** include controls that restore the system after a disaster or an event.

### Business Continuity Planning

business continuity goes a step further than DRP because it means making sure that critical process continue. 

A business continuity plan is a broader plan than a DRP because it includes getting critical systems to another location while repair of the original facility is under way. Personnel continue to perform all business processes in an alternate manner until normal operations resume.

Availability ensures that the resources required to keep the organization going will continue to be available to the personnel and the systems that rely on them.

#### Business Continuity Considerations

Business continuity controls are **more than just backing up data and providing redundant hardware**. Organizations need employees to properly configure and operate systems. Data can be useless until it provides information. An organization should look at the following:

- Documentatie configuraties

- zorg voor alternatieve communicatiekanalen 

- Stroomvoorzieningen failsafe maken

- Nagaan wat de impact voor de applicaties zijn

- Nagaan hoe geautomatiseerde taken (tijdelijk) handmatig kunnen overgenomen worden.

#### Business Continuity Best Practices

As shown in the figure, the National Institute of Standards and Technology (NIST) developed the following best practices:

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1606141682/Screenshot_2020-11-23_152743_nqthnc.png" width=400/>

## 5 reconnaissance and enumeration 

 reconnaissance :arrow_right: scanning :arrow_right: gain access :arrow_right: maintain access :arrow_right: clear tracks ​

### 5.1 reconnaissance 

- passive = no direct interaction with target
- active = direct interaction with target

### 5.2 scanning

thanks to the previous step we now know what to scan 

- active scanning (eg. ping sweeper)
- passive scanning (eg. network scanner)

scanning types : 

- port scanning 
- network scanning 
- vulnerability scanning 

#### scanning tools

**ping** : can be used to find out certain thresholds for data reception

```shell
henridebel@DESKTOP-JRH2IMI:/mnt/c/WINDOWS/system32$ sudo ping www.hln.be -f -l 2000
ping: WARNING: probably, rcvbuf is not enough to hold preload
PING e27717.dscb.akamaiedge.net (92.123.236.51) 56(84) bytes of data.

--- e27717.dscb.akamaiedge.net ping statistics ---
52261 packets transmitted, 50907 received, 2.59084% packet loss, time 4926ms
rtt min/avg/max/mdev = 31.480/75.136/202.474/23.190 ms, pipe 2002, ipg/ewma 0.094/54.235 ms
```

**trace route** : network diagnostic commands for displaying possible routes and measuring transit delays of packets across an Internet Protocol network

**nslookup** : to figure out ip-adres, domain name ...

some of it's feautres include : 

- host-discovery = discover hosts on a network
- port-scanning = discover which ports are listening to one or more target computers
- version detection 
- OS detection
- Nmap scripting engine = allows users to write (and share) simple scripts to automate a wide variety of networking tasks.

```shell
henridebel@DESKTOP-JRH2IMI:/mnt/c/WINDOWS/system32$ sudo nslookup www.hln.be
Server:         192.168.42.129
Address:        192.168.42.129#53

Non-authoritative answer:
www.hln.be      canonical name = dpp-hln-wc.edgekey.net.
dpp-hln-wc.edgekey.net  canonical name = e27717.dscb.akamaiedge.net.
Name:   e27717.dscb.akamaiedge.net
Address: 81.242.3.178
Name:   e27717.dscb.akamaiedge.net
Address: 81.242.3.203
Name:   e27717.dscb.akamaiedge.net
Address: 81.242.3.177
Name:   e27717.dscb.akamaiedge.net
Address: 81.242.3.153
Name:   e27717.dscb.akamaiedge.net
Address: 81.242.3.169
Name:   e27717.dscb.akamaiedge.net
Address: 81.242.3.208
Name:   e27717.dscb.akamaiedge.net
Address: 2a02:26f0:1b00::5c7b:ee38
Name:   e27717.dscb.akamaiedge.net
Address: 2a02:26f0:1b00::5c7b:ee0a
Name:   e27717.dscb.akamaiedge.net
Address: 2a02:26f0:1b00::5c7b:ee68
```

**port scanner** 

- port = gateway through which an application of service communicates via a network 

### 5.3 enumeration 

- after scanning
- which services are being used ? 
- which versions of the services are used  ?