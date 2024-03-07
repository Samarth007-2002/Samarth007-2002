# Threat Intelligence Tools

#### Threat Intelligence Classifications:

Threat Intel is geared towards understanding the relationship between your operational environment and your adversary. With this in mind, we can break down threat intel into the following classifications:&#x20;

* **Strategic Intel:** High-level intel that looks into the organisation's threat landscape and maps out the risk areas based on trends, patterns and emerging threats that may impact business decisions.
* **Technical Intel:** Looks into evidence and artefacts of attack used by an adversary. Incident Response teams can use this intel to create a baseline attack surface to analyse and develop defence mechanisms.
* **Tactical Intel:** Assesses adversaries' tactics, techniques, and procedures (TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations.
* **Operational Intel:** Looks into an adversary's specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organisation (people, processes, and technologies) that may be targeted.

## UrlScan.io

[Urlscan.io](https://urlscan.io) is a free service developed to assist in scanning and analysing websites. It is used to automate the process of browsing and crawling through websites to record activities and interactions.

#### Scan Results

URL scan results provide ample information, with the following key areas being essential to look at:

* **Summary:** Provides general information about the URL, ranging from the identified IP address, domain registration details, page history and a screenshot of the site.
* **HTTP:** Provides information on the HTTP connections made by the scanner to the site, with details about the data fetched and the file types received.
* **Redirects:** Shows information on any identified HTTP and client-side redirects on the site.
* **Links:** Shows all the identified links outgoing from the site's homepage.
* **Behaviour:** Provides details of the variables and cookies found on the site. These may be useful in identifying the frameworks used in developing the site.
* **Indicators:** Lists all IPs, domains and hashes associated with the site. These indicators do not imply malicious activity related to the site.

## Abuse.ch

[Abuse.ch](https://abuse.ch) is a research project hosted by the Institue for Cybersecurity and Engineering at the Bern University of Applied Sciences in Switzerland. It was developed to identify and track malware and botnets through several operational platforms developed under the project. These platforms are:

* **Malware Bazaar:**  A resource for sharing malware samples.
* **Feodo Tracker:**  A resource used to track botnet command and control (C2) infrastructure linked with Emotet, Dridex and TrickBot.
* **SSL Blacklist:**  A resource for collecting and providing a blocklist for malicious SSL certificates and JA3/JA3s fingerprints.
* **URL Haus:**  A resource for sharing malware distribution sites.
* **Threat Fox:**  A resource for sharing indicators of compromise (IOCs).

### [MalwareBazaar](https://bazaar.abuse.ch)

As the name suggests, this project is an all in one malware collection and analysis database. The project supports the following features:

* Malware Samples Upload: Security analysts can upload their malware samples for analysis and build the intelligence database. This can be done through the browser or an API.
* **Malware Hunting:** Hunting for malware samples is possible through setting up alerts to match various elements such as tags, signatures, YARA rules, ClamAV signatures and vendor detection.

### [FeodoTracker](https://feodotracker.abuse.ch)

With this project, Abuse.ch is targeting to share intelligence on botnet Command & Control (C\&C) servers associated with Dridex, Emotes (aka Heodo), TrickBot, QakBot and BazarLoader/BazarBackdoor. This is achieved by providing a database of the C\&C servers that security analysts can search through and investigate any suspicious IP addresses they have come across. Additionally, they provide various IP and IOC blocklists and mitigation information to be used to prevent botnet infections.

### [SSL Blacklist](https://sslbl.abuse.ch)

Abuse.ch developed this tool to identify and detect malicious SSL connections. From these connections, SSL certificates used by botnet C2 servers would be identified and updated on a denylist that is provided for use. The denylist is also used to identify JA3 fingerprints that would help detect and block malware botnet C2 communications on the TCP layer.

You can browse through the SSL certificates and JA3 fingerprints lists or download them to add to your deny list or threat hunting rulesets.

### [URLhaus](https://urlhaus.abuse.ch)

As the name points out, this tool focuses on sharing malicious URLs used for malware distribution. As an analyst, you can search through the database for domains, URLs, hashes and filetypes that are suspected to be malicious and validate your investigations.

The tool also provides feeds associated with country, AS number and Top Level Domain that an analyst can generate based on specific search needs.

### [ThreatFox](https://threatfox.abuse.ch)

With ThreatFox,  security analysts can search for, share and export indicators of compromise associated with malware. IOCs can be exported in various formats such as MISP events, Suricata IDS Ruleset, Domain Host files, DNS Response Policy Zone, JSON files and CSV files.

## PhishTool

[PhishTool](https://www.phishtool.com) seeks to elevate the perception of phishing as a severe form of attack and provide a responsive means of email security. Through email analysis, security analysts can uncover email IOCs, prevent breaches and provide forensic reports that could be used in phishing containment and training engagements.

PhishTool has two accessible versions: Community and Enterprise. We shall mainly focus on the Community version and the core features in this task. Sign up for an account via this [link](https://app.phishtool.com/sign-up/community) to use the tool.

The core features include:

* **Perform email analysis:** PhishTool retrieves metadata from phishing emails and provides analysts with the relevant explanations and capabilities to follow the email’s actions, attachments, and URLs to triage the situation.
* **Heuristic intelligence:** OSINT is baked into the tool to provide analysts with the intelligence needed to stay ahead of persistent attacks and understand what TTPs were used to evade security controls and allow the adversary to social engineer a target.
* **Classification and reporting:** Phishing email classifications are conducted to allow analysts to take action quickly. Additionally, reports can be generated to provide a forensic record that can be shared.

We are presented with an upload file screen from the Analysis tab on login. Here, we submit our email for analysis in the stated file formats. Other tabs include:\


* **History:** Lists all submissions made with their resolutions.
* **In-tray:** An Enterprise feature used to receive and process phish reports posted by team members through integrating Google Workspace and Microsoft 365.

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/4c5d66d92d6aeb83d67961be5239842d.png" alt=""><figcaption></figcaption></figure>

#### Analysis Tab

Once uploaded, we are presented with the details of our email for a more in-depth look. Here, we have the following tabs:

* **Headers:** Provides the routing information of the email, such as source and destination email addresses, Originating IP and DNS addresses and Timestamp.
* **Received Lines:** Details on the email traversal process across various SMTP servers for tracing purposes.
* **X-headers:** These are extension headers added by the recipient mailbox to provide additional information about the email.
* **Security:** Details on email security frameworks and policies such as Sender Policy Framework (SPF), DomainKeys Identified Mail (DKIM) and Domain-based Message Authentication, Reporting and Conformance (DMARC).
* **Attachments:** Lists any file attachments found in the email.
* **Message URLs:** Associated external URLs found in the email will be found here.

We can further perform lookups and flag indicators as malicious from these options. On the right-hand side of the screen, we are presented with the Plaintext and Source details of the email.

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/03364f3a4fb2177cce13abc3b181bca9.gif" alt=""><figcaption></figcaption></figure>

Above the Plaintext section, we have a Resolve checkmark. Here, we get to perform the resolution of our analysis by classifying the email, setting up flagged artefacts and setting the classification codes. Once the email has been classified, the details will appear on the Resolution tab on the analysis of the email.

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/b13d63d0c2fe177085a1b487efb4065e.gif" alt=""><figcaption></figcaption></figure>

## Cisco Talos Intelligence

Cisco Talos encompasses six key teams:

* **Threat Intelligence & Interdiction:** Quick correlation and tracking of threats provide a means to turn simple IOCs into context-rich intel.
* **Detection Research:** Vulnerability and malware analysis is performed to create rules and content for threat detection.
* **Engineering & Development:** Provides the maintenance support for the inspection engines and keeps them up-to-date to identify and triage emerging threats.
* **Vulnerability Research & Discovery:** Working with service and software vendors to develop repeatable means of identifying and reporting security vulnerabilities.
* **Communities:** Maintains the image of the team and the open-source solutions.
* **Global Outreach:** Disseminates intelligence to customers and the security community through publications.

Accessing the open-source solution, we are first presented with a reputation lookup dashboard with a world map. This map shows an overview of email traffic with indicators of whether the emails are legitimate, spam or malware across numerous countries. Clicking on any marker, we see more information associated with IP and hostname addresses, volume on the day and the type.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/0*SW1Qm6nlpffXFxzk.png" alt="" height="359" width="700"><figcaption></figcaption></figure>

At the top, we have several tabs that provide different types of intelligence resources. The primary tabs that an analyst would interact with are:

* **Vulnerability Information:** Disclosed and zero-day vulnerability reports marked with CVE numbers and CVSS scores. Details of the vulnerabilities reported are provided when you select a specific report, including the timeline taken to get the report published. Microsoft vulnerability advisories are also provided, with the applicable snort rules that can be used.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/0*ArXc8B6gZeI9nJDz.gif" alt="" height="352" width="700"><figcaption></figcaption></figure>

* **Reputation Center:** Provides access to searchable threat data related to IPs and files using their SHA256 hashes. Analysts would rely on these options to conduct their investigations. Additional email and spam data can be found under the **Email & Spam Data tab**.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/0*X1BYSy9WrJ7EeGe-.gif" alt="" height="356" width="700"><figcaption></figcaption></figure>

<figure><img src="https://miro.medium.com/v2/resize:fit:700/0*bHsp_WgQTHBezNAx.gif" alt="" height="356" width="700"><figcaption></figcaption></figure>

### Task7 <a href="#efe6" id="efe6"></a>

Use the .eml file you’ve downloaded in the previous task, PhishTool, to answer the following questions.

## Answer the questions below <a href="#f2d3" id="f2d3"></a>

### What is the listed domain of the IP address from the previous task? <a href="#id-34c0" id="id-34c0"></a>

Go up to the first paragraph of the this task and click on the link to the Talos Intelligence site, to open it in a new tab.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*BUwk32p5X_Yg88auQ945ug.png" alt="" height="60" width="700"><figcaption></figcaption></figure>

When the page load, there is a search box labeled Reputation Lookup. In this search box put the IP address that we defanged from the previous task. Press enter or click the search icon.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*HgL1_m93i89uj1rejK4R1g.png" alt="" height="322" width="700"><figcaption></figcaption></figure>

Now we will have info on this IP address, under Owner Details is the Domain name and answer to the question. Once you find it, highlight copy (ctrl + c) and paste (ctrl + v) or type, the answer into the TryHackMe answer field and click submit.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*s7Iy-R1Db_YgMpHln6gaaQ.png" alt="" height="342" width="700"><figcaption></figcaption></figure>

**Answer: scnet.net**

### What is the customer name of the IP address? <a href="#dc94" id="dc94"></a>

Staying on the current Talos page we are on scroll down till you see Additional Information. Then click on the WHOIS tab.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*K7KuqZOJJzO4c7IPd0tCWg.png" alt="" height="410" width="700"><figcaption></figcaption></figure>

Scroll down till you see the Second # start , this is the section that has the customer infomation in it. Look down through till you see either Customer: or CustName: this is the answer to the question. Once you find it, highlight copy (ctrl + c) and paste (ctrl + v) or type, the answer into the TryHackMe answer field and click submit.

<figure><img src="https://miro.medium.com/v2/resize:fit:539/1*gkUz8aASs2yceui3G0-DOg.png" alt="" height="435" width="539"><figcaption></figcaption></figure>

**Answer: Complete Web Reviews**

## **Task8 Scenario**

### Examine the File <a href="#id-20aa" id="id-20aa"></a>

Now that we have the file opened in our text editor, we can start to look at it for intel.

<figure><img src="https://miro.medium.com/v2/resize:fit:586/1*8Vh0RZYm0CF8Rz-Un5AUHQ.png" alt="" height="94" width="586"><figcaption></figcaption></figure>

From lines 6 thru 9 we can see the header information, here is what we can get from it.

* **Sender** — LeHuong-accounts@gmail.com
* **Reciever —** chris.lyons@supercarcenterdetroit.com
* **Date —** Thu, 14 Dec 2017 19:14:14 +0100

So we have some good intel so far, but let's look into the email a little bit further. We can look at the contents of the email, if we look we can see that there is an attachment. They are masking the attachment as a pdf, when it is a zip file with malware.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*OYnNNvHIQ_fRzTPmoxoDfA.png" alt="" height="151" width="700"><figcaption></figcaption></figure>

* **Attachment Name —** Proforma Invoice P101092292891 TT slip pdf.rar.zip

Also, the strange string of characters under line 45 is the actual malware, it is base64 encoded as we can see from line 43.

Lastly, we can look at the stops made by the email, this can be found in lines 1 thru 5. With possibly having the IP address of the sender in line 3.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*unuiXwX5BHIalqpXIRfYYw.png" alt="" height="112" width="700"><figcaption></figcaption></figure>

* **Senders IP? —** 134.19.187.230
* **Receivers IP —** 217.61.97.194

### Phish Tool <a href="#dd31" id="dd31"></a>

We can now enter our file into the phish tool site as well to see how we did in our discovery. To do so, first you will need to make an account, I have already done this process, so I will show you how to add the email file and then analyze it. Once you have logged in at the top, you will see an Analysis link, click it to be taken to the page to upload an email file.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*8npHLQ4LjmLoL5DlJ1jsuA.png" alt="" height="68" width="700"><figcaption></figcaption></figure>

In the middle of the page is a blue button labeled Choose File, click it and a window will open.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*pubr1ZOWjGIV8yIZ1_Tw9g.png" alt="" height="418" width="700"><figcaption></figcaption></figure>

Navigate to your Downloads folder, then double-click on the email2 file to open it in Phish tool.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*Vi2rxwsTnybBSJP-dlrhoA.png" alt="" height="429" width="700"><figcaption></figcaption></figure>

Already, it will have intel broken down for us ready to be looked at. All the header intel is broken down and labeled, the email is displayed in plaintext on the right panel.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*YHEE9c18uhdPMToMVQDyUA.png" alt="" height="243" width="700"><figcaption></figcaption></figure>

The thing I find very interesting is if you go over to the Attachments tab, we get the name, file type, file size, and file hashes. We can use these hashes to check on different sites to see what type of malicious file we could be dealing with.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*aN07BFZhmHmc60trwVTtZA.png" alt="" height="256" width="700"><figcaption></figcaption></figure>

So let’s check out a couple of places to see if the File Hashes yields any new intel.

### Cisco Talos Intelligence <a href="#eae2" id="eae2"></a>

Heading back over to [Cisco Talos Intelligence](https://talosintelligence.com), we are going to paste the file hash into the Reputation Lookup bar.

<figure><img src="https://miro.medium.com/v2/resize:fit:486/1*xHuZsvtY286cUk_WeSrEgw.png" alt="" height="218" width="486"><figcaption></figcaption></figure>

This time though, we get redirected to the Talos File Reputation Lookup, the file hash should already be in the search bar. You should only need to prove you are not a robot, if you are a robot good luck, then click the orange search button.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*a-33eJM0w_s0UXcAExVrZw.png" alt="" height="369" width="700"><figcaption></figcaption></figure>

Talos confirms what we found on VirusTotal, the file is malicious. Also we gained more amazing intel!!!

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*PdH5263phNcQHQHGRj-JSA.png" alt="" height="477" width="700"><figcaption></figcaption></figure>

## **Task9 Scenario**

* **Senders IP? —** 134.19.187.230
* **Receivers IP —** 217.61.97.194

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*unuiXwX5BHIalqpXIRfYYw.png" alt="" height="112" width="700"><figcaption></figcaption></figure>

Lastly, we can look at the stops made by the email, this can be found in lines 1 thru 5. With possibly having the IP address of the sender in line 3.

Also, the strange string of characters under line 45 is the actual malware, it is base64 encoded as we can see from line 43.

* **Attachment Name —** Proforma Invoice P101092292891 TT slip pdf.rar.zip

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*OYnNNvHIQ_fRzTPmoxoDfA.png" alt="" height="151" width="700"><figcaption></figcaption></figure>

So we have some good intel so far, but let's look into the email a little bit further. We can look at the contents of the email, if we look we can see that there is an attachment. They are masking the attachment as a pdf, when it is a zip file with malware.

* **Sender** — LeHuong-accounts@gmail.com
* **Reciever —** chris.lyons@supercarcenterdetroit.com
* **Date —** Thu, 14 Dec 2017 19:14:14 +0100

From lines 6 thru 9 we can see the header information, here is what we can get from it.

<figure><img src="https://miro.medium.com/v2/resize:fit:586/1*8Vh0RZYm0CF8Rz-Un5AUHQ.png" alt="" height="94" width="586"><figcaption></figcaption></figure>

Now that we have the file opened in our text editor, we can start to look at it for intel.

### Examine the File <a href="#id-20aa" id="id-20aa"></a>

## &#x20;

#### Examine the File <a href="#id-4cf8" id="id-4cf8"></a>

### Text Editor <a href="#id-34fa" id="id-34fa"></a>

Now that we have the file opened in our text editor, we can start to look at it for intel.

<figure><img src="https://miro.medium.com/v2/resize:fit:574/1*tYJe4CkKD82zv9TK1TAIew.png" alt="" height="99" width="574"><figcaption></figcaption></figure>

We can see the Header information from lines 12 thru 16

* **Sender —** quickbooks@notification.inttuit.com
* **Date —** Wed, 13 Oct 2021 23:19:15 +0900

Scrolling down to lines 78 thru 80 show that we have an attachment that is base64 encoded.

<figure><img src="https://miro.medium.com/v2/resize:fit:606/1*qL8l5LsCr6Tk3IW6w1jLZw.png" alt="" height="79" width="606"><figcaption></figcaption></figure>

* **Attachment Name —** Sales\_Receipt 5606.xls
* **File Type —** xls, excel file

Also, the strange string of characters under line 80 is the actual file, it is base64 encoded as we can see from line 80.

### Phish Tool <a href="#id-4314" id="id-4314"></a>

Now lets upload the file to Phish tool to see what else we can gleam from it. So head over to [Phish Tool](https://www.phishtool.com), and log in. Once your logged in click on the Analysis tab in the top right of the site.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*aLiJxHVSB-_O1PdxkBufYQ.png" alt="" height="16" width="700"><figcaption></figcaption></figure>

In the middle of the page is a blue button labeled Choose File, click it and a window will open.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*pubr1ZOWjGIV8yIZ1_Tw9g.png" alt="" height="418" width="700"><figcaption></figcaption></figure>

Navigate to your Downloads folder, then double-click on the Email3.eml file to open it in Phish tool.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*EK3-uy6zfo6IAq_Yl5Riig.png" alt="" height="130" width="700"><figcaption></figcaption></figure>

Already, it will have intel broken down for us ready to be looked at. All the header intel is broken down and labeled, the email is rendered in the panel on the right.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*ez9qIK6lMAxV_CwZFfQrZw.png" alt="" height="193" width="700"><figcaption></figcaption></figure>

Clicking over onto the Attachments tab we see that the OLE analysis is that a Macro will be run.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*6Zv7cqo2TYKyNmMr8lVq5w.png" alt="" height="316" width="700"><figcaption></figcaption></figure>

Let’s take a look at the file hash and see what we can find

### VirusTotal <a href="#id-2954" id="id-2954"></a>

Let’s check out [VirusTotal ](https://www.virustotal.com/gui/home/upload)(I know it wasn’t discussed in this room but it is an awesome resource). Once you are on the site, click the search tab on the right side.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*0whNBtRlFGsC_9ixb0a-Lg.png" alt="" height="661" width="700"><figcaption></figcaption></figure>

Click on the search bar and paste (ctrl +v) the file hash, the press enter to search it.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*OmEICJi9ekM_6KYA7et_AA.png" alt="" height="613" width="700"><figcaption></figcaption></figure>

VirusTotal also shows that it is malware!!!!!

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*IA2ogoPf8vWwM7MHgLypHg.png" alt="" height="351" width="700"><figcaption></figcaption></figure>

