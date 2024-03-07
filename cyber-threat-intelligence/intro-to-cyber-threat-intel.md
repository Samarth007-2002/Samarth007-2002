# Intro to Cyber Threat Intel

## Cyberthreat Intelligence

Cyber Threat Intelligence (CTI) can be defined as evidence-based knowledge about adversaries, including their indicators, tactics, motivations, and actionable advice against them.

**Data:** Discrete indicators associated with an adversary, such as IP addresses, URLs or hashes.

**Information:** A combination of multiple data points that answer questions such as “How many times have employees accessed tryhackme.com within the month?”

**Intelligence:** The correlation of data and information to extract patterns of actions based on contextual analysis.

The primary goal of CTI is to understand the relationship between your operational environment and your adversary and how to defend your environment against any attacks. You would seek this goal by developing your cyber threat context by trying to answer the following questions:

* Who’s attacking you?
* What are their motivations?
* What are their capabilities?
* What artefacts and indicators of compromise (IOCs) should you look out for?

With these questions, threat intelligence would be gathered from different sources under the following categories:

* **Internal:**
  * Corporate security events such as vulnerability assessments and incident response reports.
  * Cyber awareness training reports.
  * System logs and events.
* **Community:**
  * Open web forums.
  * Dark web communities for cybercriminals.
* **External**
  * Threat intel feeds (Commercial & Open-source)
  * Online marketplaces.
  * Public sources include government data, publications, social media, financial and industrial assessments.

### Threat Intelligence Classifications

* **Strategic Intel:** High-level intel that looks into the organisation’s threat landscape and maps out the risk areas based on trends, patterns and emerging threats that may impact business decisions.
* **Technical Intel:** Looks into evidence and artefacts of attack used by an adversary. Incident Response teams can use this intel to create a baseline attack surface to analyse and develop defence mechanisms.
* **Tactical Intel:** Assesses adversaries’ tactics, techniques, and procedures (TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations.
* **Operational Intel:** Looks into an adversary’s specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organisation (people, processes and technologies) that may be targeted.

## CTI Lifecycle

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Threat intel is obtained from a data-churning process that transforms raw data into contextualised and action-oriented insights geared towards triaging security incidents. The transformational process follows a six-phase cycle:

### Direction

Every threat intel program requires to have objectives and goals defined, involving identifying the following parameters:

* Information assets and business processes that require defending.
* Potential impact to be experienced on losing the assets or through process interruptions.
* Sources of data and intel to be used towards protection.
* Tools and resources that are required to defend the assets.

This phase also allows security analysts to pose questions related to investigating incidents.

### Collection

Once objectives have been defined, security analysts will gather the required data to address them. Analysts will do this by using commercial, private and open-source resources available. Due to the volume of data analysts usually face, it is recommended to automate this phase to provide time for triaging incidents.

### Processing

Raw logs, vulnerability information, malware and network traffic usually come in different formats and may be disconnected when used to investigate an incident. This phase ensures that the data is extracted, sorted, organized, correlated with appropriate tags and presented visually in a usable and understandable format to the analysts. SIEMs are valuable tools for achieving this and allow quick parsing of data.

### Analysis

Once the information aggregation is complete, security analysts must derive insights. Decisions to be made may involve:

* Investigating a potential threat through uncovering indicators and attack patterns.
* Defining an action plan to avert an attack and defend the infrastructure.
* Strengthening security controls or justifying investment for additional resources.

### Dissemination

Different organizational stakeholders will consume the intelligence in varying languages and formats. For example, C-suite members will require a concise report covering trends in adversary activities, financial implications and strategic recommendations. At the same time, analysts will more likely inform the technical team about the threat IOCs, adversary TTPs and tactical action plans.

### Feedback

The final phase covers the most crucial part, as analysts rely on the responses provided by stakeholders to improve the threat intelligence process and implementation of security controls. Feedback should be regular interaction between teams to keep the lifecycle working.

## CTI Standards & Frameworks

#### MITRE ATT\&CK

#### TAXII

[The Trusted Automated eXchange of Indicator Information (TAXII)](https://oasis-open.github.io/cti-documentation/taxii/intro) defines protocols for securely exchanging threat intel to have near real-time detection, prevention and mitigation of threats. The protocol supports two sharing models:

* Collection: Threat intel is collected and hosted by a producer upon request by users using a request-response model.
* Channel: Threat intel is pushed to users from a central server through a publish-subscribe model.

#### STIX

[Structured Threat Information Expression (STIX)](https://oasis-open.github.io/cti-documentation/stix/intro) is a language developed for the "specification, capture, characterisation and communication of standardised cyber threat information". It provides defined relationships between sets of threat info such as observables, indicators, adversary TTPs, attack campaigns, and more.

#### Cyber Kill Chain

#### The Diamond Model

## Practical Analysis

As part of the dissemination phase of the lifecycle, CTI is also distributed to organisations using published threat reports. These reports come from technology and security companies that research emerging and actively used threat vectors. They are valuable for consolidating information presented to all suitable stakeholders. Some notable threat reports come from [Mandiant](https://www.mandiant.com/resources), [Recorded Future](https://www.recordedfuture.com/resources/global-issues) and [AT\&TCybersecurity](https://cybersecurity.att.com).
