# Pyramid of pain

This concept is being applied to cybersecurity solutions like [Cisco Security](https://gblogs.cisco.com/ca/2020/08/26/the-canadian-bacon-cisco-security-and-the-pyramid-of-pain/), [SentinelOne](https://www.sentinelone.com/blog/revisiting-the-pyramid-of-pain-leveraging-edr-data-to-improve-cyber-threat-intelligence/), and [SOCRadar](https://socradar.io/re-examining-the-pyramid-of-pain-to-use-cyber-threat-intelligence-more-effectively/) to improve the effectiveness of CTI (Cyber Threat Intelligence), threat hunting, and incident response exercises.

The ‘pain’ here is supposed to be the pain felt by attackers once a particular kind of indicator for their attack becomes known.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

## Hash Values (Trival)

&#x20;file hashes – the kind of IoCs that we are all used to dealing with on a daily basis. These are easy to acquire and widely shared, so availability of these is typically good. The problem, though, is that it is also relatively painless for attackers to change a file’s hash; indeed, much modern malware even does this “autonomously” – so-called [polymorphic malware](https://www.sentinelone.com/blog/ursnif-polymorphic-delivery-mechanism-explained/) – and it’s comparatively easy to write malicious software that creates copies of itself with a different file hash each time.

For example just appending a meaning less string in the malware can change the hash value.

## IP Address (Easy)

Analyst can just block the IP before getting discovered&#x20;

One of the ways an attackers can make it challenging to successfully carry out IP blocking is by using Fast Flux.

Fast Flux is a DNS technique used by botnets to hide phishing, web proxying, malware delivery, and malware communication activities behind compromised hosts acting as proxies. The purpose of using the Fast Flux network is to make the communication between malware and its command and control server (C\&C) challenging to be discovered by security professionals.&#x20;

So, the primary concept of a Fast Flux network is having multiple IP addresses associated with a domain name, which is constantly changing. Palo Alto created a great fictional scenario to explain Fast Flux: ["](https://unit42.paloaltonetworks.com/fast-flux-101/)[Fast Flux 101: How Cybercriminals Improve the Resilience of Their Infrastructure to Evade Detection and Law Enforcement Takedowns"](https://unit42.paloaltonetworks.com/fast-flux-101/)

An example report where malicious PID 1632 , where we can see how its TRYING to communicate to a domain and an IP. (50.87.136.52,craftingalegacy.com)

[https://assets.tryhackme.com/additional/pyramidofpain/task3-anyrun.pdf](https://assets.tryhackme.com/additional/pyramidofpain/task3-anyrun.pdf)

## Domain Names (Simple)

A domain name can contain a domain and a top-level domain ([evilcorp.com](http://evilcorp.com/)) or a sub-domain followed by a domain and top-level domain ([tryhackme.evilcorp.com](http://tryhackme.evilcorp.com/)).

Domain Names can be a little more of a pain for the attacker to change as they would most likely need to purchase the domain, register it and modify DNS records. Unfortunately for defenders, many DNS providers have loose standards and provide APIs to make it even easier for the attacker to change the domain.

### Puny Code Attack ![](https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/03ad636820590525bdd91e28a04bbec1.png)

Can you spot anything malicious in the above screenshot? Now, compare it to the legitimate website view below:

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/7c4329f6d1d09a739097f818dc42e733.png)\


This is one of the examples of a Punycode attack used by the attackers to redirect users to a malicious domain that seems legitimate at first glance.

What is Punycode? As per [Wandera](https://www.wandera.com/punycode-attacks/), "Punycode is a way of converting words that cannot be written in ASCII, into a Unicode ASCII encoding."

What you saw in the URL above is `adıdas.de` which has the Punycode of `http://xn--addas-o4a.de/`

Internet Explorer, Google Chrome, Microsoft Edge, and Apple Safari are now pretty good at translating the obfuscated characters into the full Punycode domain name.\
To detect the malicious domains, proxy logs or web server logs can be used.\
Attackers usually hide the malicious domains under URL Shorteners. A URL Shortener is a tool that creates a short and unique URL that will redirect to the specific website specified during the initial step of setting up the URL Shortener link. According to [Cofense](https://cofense.com/url-shorteners-fraudsters-friend/), attackers use the following URL Shortening services to generate malicious links: \


* bit.ly
* goo.gl
* ow.ly
* s.id
* smarturl.it
* tiny.pl
* tinyurl.com
* x.co

You can see the actual website the shortened link is redirecting you to by appending "+" to it (see the examples below). Type the shortened URL in the address bar of the web browser and add the above characters to see the redirect URL. \
NOTE: The examples of the shortened links below are non-existent.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5c549500924ec576f953d9fc/room-content/78481d27921134df9daab358a42ff5d0.png)

\
\


### Viewing Connections in Any.run:

Because Any.run is a sandboxing service that executes the sample, we can review any connections such as HTTP requests, DNS requests or processes communicating with an IP address. To do so, we can look at the "networking" tab located just below the snapshot of the machine.

_Please note_: you should be extremely cautious about visiting any of the IP addresses or HTTP requests made in a report. After all, these are behaviours from the malware sample - so they're probably doing something dangerous!

HTTP Requests:

This tab shows the recorded HTTP requests since the detonation of the sample. This can be useful to see what resources are being retrieved from a webserver, such as a dropper or a callback.

![illustrating the HTTP requests in the anyrun view](https://assets.tryhackme.com/additional/pyramidofpain/t4/http%20requests.png)

Connections:

This tab shows any communications made since the detonation of the sample. This can be useful to see if a process communicates with another host. For example, this could be C2 traffic, uploading/downloading files over FTP, etc.

\


<figure><img src="https://assets.tryhackme.com/additional/pyramidofpain/t4/connections.png" alt=""><figcaption></figcaption></figure>

DNS Requests:

This tab shows the DNS requests made since the detonation of the sample. Malware often makes DNS requests to check for internet connectivity (I.e. if It can't reach the internet/call home, then it's probably being sandboxed or is useless).&#x20;

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

[https://app.any.run/tasks/a66178de-7596-4a05-945d-704dbf6b3b90/](https://app.any.run/tasks/a66178de-7596-4a05-945d-704dbf6b3b90/)\
Go to [this report on app.any.run](https://app.any.run/tasks/a66178de-7596-4a05-945d-704dbf6b3b90) and provide the first suspicious URL request you are seeing, you will be using this report to answer the remaining questions of this task.&#x20;

What term refers to an address used to access websites?

Provide the redirected website for the shortened URL&#x20;

using a preview: https://tinyurl.com/bw7t8p4u   (This can be done by adding + sign at the end)

## Host artifacts (Annoying)

On this level, the attacker will feel a little more annoyed and frustrated if you can detect the attack. The attacker would need to circle back at this detection level and change his attack tools and methodologies. This is very time-consuming for the attacker, and probably, he will need to spend more resources on his adversary tools.

Host artifacts are the traces or observables that attackers leave on the system, such as registry values, suspicious process execution, attack patterns or IOCs (Indicators of Compromise), files dropped by malicious applications, or anything exclusive to the current threat.

Suspicious process execution from Word:&#x20;

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/6b91c7de5654b7f285991787cb3bb4fe.png" alt=""><figcaption></figcaption></figure>

Suspicious events followed by opening a malicious application:&#x20;

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/6d742c9c22f99f30e3c8356ef7c36800.png" alt=""><figcaption></figcaption></figure>

The files modified/dropped by the malicious actor:

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5c549500924ec576f953d9fc/room-content/353235afb71be81d56fb079dc7111b15.png" alt=""><figcaption></figcaption></figure>

Answer the questions below

A security vendor has analysed the malicious sample for us. Review the report [here](https://assets.tryhackme.com/additional/pyramidofpain/task5-report.pdf) to answer the following questions.

A process named regidle.exe makes a POST request to an IP address based in the United States (US) on port 8080. What is the IP address? (96.126.101.6)

The actor drops a malicious executable (EXE). What is the name of this executable?(G\_jugk.exe)

Look at this [report](https://assets.tryhackme.com/additional/pyramidofpain/vtotal2.png) by Virustotal. How many vendors determine this host to be malicious?(9)

## Network Artifacts (Annoying)

A network artifact can be a user-agent string, C2 information, or URI patterns followed by the HTTP POST requests.An attacker might use a User-Agent string that hasn’t been observed in your environment before or seems out of the ordinary. The User-Agent is defined by [RFC2616](https://datatracker.ietf.org/doc/html/rfc2616#page-145) as the request-header field that contains the information about the user agent originating the request.

Network artifacts can be detected in Wireshark PCAPs (file that contains the packet data of a network) by using a network protocol analyzer such as [TShark](https://www.wireshark.org/docs/wsug\_html\_chunked/AppToolstshark.html) or exploring IDS (Intrusion Detection System) logging from a source such as [Snort](https://www.snort.org/).\


HTTP POST requests containing suspicious strings:

\


<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/a6e36c7601f7b4ec07ce2a102ffb33ab.png" alt=""><figcaption></figcaption></figure>

Let's use TShark to filter out the User-Agent strings by using the following command:

```
tshark --Y http.request -T fields -e http.host -e http.user_agent -r analysis_file.pcap 
```

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/642cac93b8c5b7bf8c82d448cb48c1d1.png)

These are the most common User-Agent strings found for the [Emotet Downloader Trojan](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/emotet-downloader-trojan-returns-in-force/)

If you can detect the custom User-Agent strings that the attacker is using, you might be able to block them, creating more obstacles and making their attempt to compromise the network more annoying.

Answer the questions below&#x20;

What browser uses the User-Agent string shown in the screenshot above?

Search for parse user agent string and use that tool

How many POST requests are in the screenshot from the pcap file?(6)

## Tools (Challenging)

Attackers would use the utilities to create malicious macro documents (maldocs) for spearphishing attempts, a backdoor that can be used to establish [C2 (Command and Control Infrastructure)](https://www.varonis.com/blog/what-is-c2/), any custom .EXE, and .DLL files, payloads, or password crackers.

A Trojan dropped the suspicious "Stealer.exe" in the Temp folder:

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/20624b49722fd8d0ba062d6206c1d021.png)

The execution of the suspicious binary:

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/60c7fac321aca20049602d2b/room-content/8638b80dc730bfc88e37633f648b15e2.png" alt=""><figcaption></figcaption></figure>

Antivirus signatures, detection rules, and YARA rules can be great weapons for you to use against attackers at this stage.

[MalwareBazaar ](https://bazaar.abuse.ch/)and [Malshare ](https://malshare.com/)are good resources to provide you with access to the samples, malicious feeds, and YARA results - these all can be very helpful when it comes to threat hunting and incident response.&#x20;

For detection rules,[ SOC Prime Threat Detection Marketplace ](https://tdm.socprime.com/)is a great platform, where security professionals share their detection rules for different kinds of threats including the latest CVE's that are being exploited in the wild by adversaries.&#x20;

Fuzzy hashing is also a strong weapon against the attacker's tools. Fuzzy hashing helps you to perform similarity analysis - match two files with minor differences based on the fuzzy hash values. One of the examples of fuzzy hashing is the usage of [SSDeep](https://ssdeep-project.github.io/ssdeep/index.html); on the SSDeep official website, you can also find the complete explanation for fuzzy hashing.&#x20;

Example of SSDeep from VirusTotal:

![](https://i.ibb.co/qnyYHtR/ssdeep.png)

## TTPs (Tough)

TTPs stands for Tactics, Techniques & Procedures. This includes the whole [MITRE ](https://attack.mitre.org/)[ATT\&CK Matrix](https://attack.mitre.org/), which means all the steps taken by an adversary to achieve his goal, starting from phishing attempts to persistence and data exfiltration.&#x20;

If you can detect and respond to the TTPs quickly, you leave the adversaries almost no chance to fight back. For, example if you could detect a [Pass-the-Hash](https://www.beyondtrust.com/resources/glossary/pass-the-hash-pth-attack) attack using Windows Event Log Monitoring and remediate it, you would be able to find the compromised host very quickly and stop the lateral movement inside your network. At this point, the attacker would have two options:

1. Go back, do more research and training, reconfigure their custom tools
2. Give up and find another target

Option 2 definitely sounds less time and resource-consuming.

## Practise?

You can pick any APT (Advanced Persistent Threat Groups) as another exercise. A good place to look at would be [FireEye Advanced Persistent Threat Groups](https://www.fireeye.com/current-threats/apt-groups.html). When you have determined the APT Group you want to research - find their indicators and ask yourself: " What can I do or what detection rules and approach can I create to detect the adversary's activity?", and "Where does this activity or detection fall on the Pyramid of Pain?”\
As David Blanco states, "_the amount of pain you cause an adversary depends on the types of indicators you are able to make use of_".&#x20;
