# Unified Kill Chain

The objective is to understand an attacker's “Kill Chain” so that defensive measures can be put in place to either pre-emptively protect a system or disrupt an attacker's attempt.

## What is "Threat Modelling"?

Threat modelling, is a series of steps to ultimately improve the security of a system. Threat modelling is about identifying risk and essentially boils down to:

1. Identifying what systems and applications need to be secured and what function they serve in the environment. For example, is the system critical to normal operations, and is a system holding sensitive information like payment info or addresses?
2. Assessing what vulnerabilities and weaknesses these systems and applications may have and how they could be potentially exploited
3. Creating a plan of action to secure these systems and applications from the vulnerabilities highlighted
4. Putting in policies to prevent these vulnerabilities from occurring again where possible (for example, implementing a software development life cycle (SDLC) for an application or training employees on phishing awareness).

It creates a high-level overview of an organization's IT assets (_an asset in IT is a piece of software or hardware_) and the procedures to resolve vulnerabilities.

UKC (Unifoed kill chain)framework helps identify potential attack surfaces and how these systems may be exploited.

The [Unified Kill Chain](https://www.unifiedkillchain.com/assets/The-Unified-Kill-Chain.pdf) published in 2017, aims to complement (**not compete**) with other cybersecurity kill chain frameworks such as Lockheed Martin’s and MITRE’s ATT\&CK.

Some large benefits of the UKC over traditional cybersecurity kill chain frameworks include the fact that it is modern and extremely detailed (**reminder**: it has 18 phases officially, whereas other frameworks may have a small handful)

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

## Phase: In (Initial Foothold)

An attacker will employ numerous tactics to investigate the system for potential vulnerabilities that can be exploited to gain a foothold in the system. For example, a common tactic is the use of reconnaissance against a system to discover potential attack vectors (such as applications and services).

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### Reconnaissance

([MITRE Tactic TA0043](https://attack.mitre.org/tactics/TA0043/))

UKC describes techniques that an adversary employs to gather information relating to their target achieved through means of passive and active reconnaissance.

Information gathered from this phase can include:

* Discovering what systems and services are running on the target
* Finding contact lists or lists of employees that can be impersonated or used in either a social engineering or phishing attack.
* Looking for potential credentials that may be of use in later stages,  such as pivoting or initial access.
* Understanding the network topology and other networked systems can be used to pivot too.&#x20;

### Weaponization&#x20;

([MITRE Tactic TA0001](https://attack.mitre.org/tactics/TA0001/))

This phase of the UKC describes the adversary setting up the necessary infrastructure to perform the attack. For example, this could be setting up a command and control server, or a system capable of catching reverse shells and delivering payloads to the system

### Social Engineering

([MITRE Tactic TA0001](https://attack.mitre.org/tactics/TA0001/))

This phase of the UKC describes techniques that an adversary can employ to manipulate employees to perform actions that will aid in the adversaries attack.

* Getting a user to open a malicious attachment.
* Impersonating a web page and having the user enter their credentials.
* Calling or visiting the target and impersonating a user (for example, requesting a password reset) or being able to gain access to areas of a site that the attacker would not previously be capable of (for example, impersonating a utility engineer).

### Exploitation

&#x20;([MITRE Tactic TA0002](https://attack.mitre.org/tactics/TA0002/))

&#x20;UKC describes how an attacker takes advantage of weaknesses or vulnerabilities present in a system. The UKC defines "Exploitation" as abuse of vulnerabilities to perform code execution. For example:

* Uploading and executing a reverse shell to a web application.
* Interfering with an automated script on the system to execute code.
* Abusing a web application vulnerability to execute code on the system it is running on.

### Persistence

([MITRE Tactic TA0003](https://attack.mitre.org/tactics/TA0003/))

### Defence Evasion ([MITRE Tactic TA0005](https://attack.mitre.org/tactics/TA0005/))

### Command & Control ([MITRE Tactic TA0011](https://attack.mitre.org/tactics/TA0011/))

The "Command & Control" phase of the UKC combines the efforts an adversary made during the "Weaponization" stage of the UKC to establish communications between the adversary and target system.

An adversary can establish command and control of a target system to achieve its action on objectives. For example, the adversary can:

* Execute commands.
* Steal data, credentials and other information.
* Use the controlled server to pivot to other systems on the network.

### Pivoting ([MITRE Tactic TA0008](https://attack.mitre.org/tactics/TA0008/))

## Phase: Through (Network Propagation)

This phase follows a successful foothold being established on the target network. An attacker would seek to gain additional access and privileges to systems and data to fulfil their goals

### Pivoting ([MITRE Tactic TA0008](https://attack.mitre.org/tactics/TA0008/))

### **Discovery (**[**MITRE Tactic TA0007**](https://attack.mitre.org/tactics/TA0007/)**)**

The adversary would uncover information about the system and the network it is connected to. Within this stage, the knowledge base would be built from the active user accounts, the permissions granted, applications and software in use, web browser activity, files, directories and network shares, and system configurations.

### **Privilege Escalation**

### **Execution(**[**MITRE Tactic TA0002**](https://attack.mitre.org/tactics/TA0002/)**)**

Recall when the adversary set up their attack infrastructure. Once the attacker has access to the system, they would use it as their staging site and a tunnel between their command operations and the victim’s network. The system would also be used as the distribution point for all malware and backdoors at later stages. and weaponised payloads? This is where they deploy their malicious code using the pivot system as their host. Remote trojans, C2 scripts, malicious links and scheduled tasks are deployed and created to facilitate a recurring presence on the system and uphold their persistence.

**Credential Access (**[**MITRE Tactic TA0006**](https://attack.mitre.org/tactics/TA0006/)**)**

**Lateral Movement** ([MITRE Tactic TA0008](https://attack.mitre.org/tactics/TA0008/))

## Phase: Out (Action on Objectives)

**Collection** [**MITRE Tactic (TA0009)**](https://attack.mitre.org/tactics/TA0009/)**After all the hunting for access and assets, the adversary will be seeking to gather all the valuable data of interest. This, in turn, compromises the confidentiality of the data and would lead to the next attack stage – Exfiltration. The main target sources include drives, browsers, audio, video and email.Exfiltration (**[**MITRE Tactic TA0010**](https://attack.mitre.org/tactics/TA0010/)**)**

To elevate their compromise, the adversary would seek to steal data, which would be packaged using encryption measures and compression to avoid any detection. The C2 channel and tunnel deployed in the earlier phases will come in handy during this process.

**Impact (**[**MITRE Tactic TA0040**](https://attack.mitre.org/tactics/TA0040/)**)**

If the adversary seeks to compromise the integrity and availability of the data assets, they would manipulate, interrupt or destroy these assets. The goal would be to disrupt business and operational processes and may involve removing account access, disk wipes, and data encryption such as ransomware, defacement and denial of service (DoS) attacks.

**Objectives**

With all the power and access to the systems and network, the adversary would seek to achieve their strategic goal for the attack.

For example, if the attack was financially motivated, they may seek to encrypt files and systems with ransomware and ask for payment to release the data. In other instances, the attacker may seek to damage the reputation of the business, and they would release private and confidential information to the public.

