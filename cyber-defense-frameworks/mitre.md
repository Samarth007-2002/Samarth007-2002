# MITRE

&#x20;The US-based non-profit MITRE Corporation has created for the cybersecurity community, specifically:

* ATT\&CK_®_ (Adversarial Tactics, Techniques, and Common Knowledge) Framework
* CAR (Cyber Analytics Repository) Knowledge Base
* ENGAGE (sorry, not a fancy acronym)
* D3FEND (Detection, Denial, and Disruption Framework Empowering Network Defense)
* AEP (ATT\&CK Emulation Plans)

## Basic Terminology

APT is an acronym for Advanced Persistent Threat.

TTP is an acronym for Tactics, Techniques, and Procedures,

* The Tactic is the adversary's goal or objective.
* The Technique is how the adversary achieves the goal or objective.
* The Procedure is how the technique is executed.

## ATT\&CK® Framework

"MITRE ATT\&CK® is a globally-accessible knowledge base of adversary tactics and techniques based on real-world observations."

In 2013, MITRE began to address the need to record and document common TTPs (Tactics, Techniques, and Procedures) that APT (Advanced Persistent Threat) groups used against enterprise Windows networks. This started with an internal project known as FMX (Fort Meade Experiment). Within this project, selected security professionals were tasked to emulated adversarial TTPs against a network, and data was collected from the attacks on this network. The gathered data helped construct the beginning pieces of what we know today as the ATT\&CK® framework.

navigate to the ATT\&CK® [website](https://attack.mitre.org/).

Direct your attention to the bottom of the page to view the ATT\&CK® Matrix for Enterprise. Across the top of the matrix, there are 14 categories. Each category contains the techniques an adversary could use to perform the tactic. The categories cover the seven-stage Cyber Attack Lifecycle (credit Lockheed Martin for the Cyber Kill Chain).

&#x20;MITRE ATT\&CK® Navigator: "_The ATT\&CK® Navigator is designed to provide basic navigation and annotation of ATT\&CK® matrices, something that people are already doing today in tools like Excel. We've designed it to be simple and generic - you can use the Navigator to visualize your defensive coverage, your red/blue team planning, the frequency of detected techniques, or anything else you want to do_."

You can access the Navigator view when visiting a group or tool page.

## CAR Knowledge Base

official definition of CAR is "_The MITRE Cyber Analytics Repository (CAR) is a knowledge base of analytics developed by MITRE based on the MITRE ATT\&CK_® _adversary model. CAR defines a data model that is leveraged in its pseudocode representations but also includes implementations directly targeted at specific tools (e.g., Splunk, EQL) in its analytics. With respect to coverage, CAR is focused on providing a set of validated and well-explained analytics, in particular with regards to their operating theory and rationale._"

Let's begin our journey by reviewing [CAR-2020-09-001: Scheduled Task - File Access](https://car.mitre.org/analytics/CAR-2020-09-001/).

Upon visiting the page, we're given a brief description of the analytics and references to ATT\&CK (technique, sub-technique, and tactic).

![](https://assets.tryhackme.com/additional/mitre/car1.png)\


![](https://assets.tryhackme.com/additional/mitre/car2.png)\


We're also provided with Pseudocode and a query on how to search for this specific analytic within Splunk. A pseudocode is a plain, human-readable way to describe a set of instructions or algorithms that a program or system will perform.

![](https://assets.tryhackme.com/additional/mitre/car3.png)\


Note the reference to Sysmon. If you're not familiar with Sysmon, check out the Sysmon [room](https://tryhackme.com/room/sysmon).&#x20;

To take full advantage of CAR, we can view the [Full Analytic List](https://car.mitre.org/analytics) or the [CAR ATT\&CK® Navigator layer](https://mitre-attack.github.io/attack-navigator/#layerURL=https://raw.githubusercontent.com/mitre-attack/car/master/docs/coverage/car\_analytic\_coverage\_04\_05\_2022.json) to view all the analytics.

Full Analytic List

![](https://assets.tryhackme.com/additional/mitre/car4.png)\


In the Full Analytic List view, we can see what implementations are available for any given analytic at a single glance, along with what OS platform it applies to.

CAR ATTACK Navigator

![](https://assets.tryhackme.com/additional/mitrev2/t4-car-navigator.png)\


(The techniques highlighted in purple are the analytics currently in CAR)

Let's look at another analytic to see a different implementation, [CAR-2014-11-004: Remote PowerShell Sessions](https://car.mitre.org/analytics/CAR-2014-11-004/).

Under Implementations, a pseudocode is provided and an EQL version of the pseudocode. EQL (pronounced as 'equal'), and it's an acronym for Event Query Language. EQL can be utilized to query, parse, and organize Sysmon event data. You can read more about this [here](https://eql.readthedocs.io/en/latest/).&#x20;

![](https://assets.tryhackme.com/additional/mitrev2/t4-eql-pseudo.png)\


To summarize, CAR is a great place for finding analytics that takes us further than the Mitigation and Detection summaries in the ATT\&CK® framework. This tool is not a replacement for ATT\&CK® but an added resource.

## [MITRE ENGAGE](https://engage.mitre.org/)

"_MITRE Engage is a framework for planning and discussing adversary engagement operations that empowers you to engage your adversaries and achieve your cybersecurity goals._"

MITRE Engage is considered an Adversary Engagement Approach. This is accomplished by the implementation of Cyber Denial and Cyber Deception.

With Cyber Denial we prevent the adversary's ability to conduct their operations and with Cyber Deception we intentionally plant artifacts to mislead the adversary.

Engage website provides a [starter kit](https://engage.mitre.org/starter-kit/) to get you 'started' with the Adversary Engagement Approach. The starter kit is a collection of whitepapers and PDFs explaining various checklists, methodologies, and processes to get you started. \


As with MITRE ATT\&CK, Engage has its own matrix. Below is a visual of the Engage Matrix.

![](https://assets.tryhackme.com/additional/mitrev2/engage-matrix.png)\


(Source: [https://engage.mitre.org](https://engage.mitre.org/))\
Let's quickly explain each of these categories based on the information on the Engage website.

* Prepare the set of operational actions that will lead to your desired outcome (input)
* Expose adversaries when they trigger your deployed deception activities&#x20;
* Affect adversaries by performing actions that will have a negative impact on their operations
* Elicit information by observing the adversary and learn more about their modus operandi (TTPs)
* Understand the outcomes of the operational actions (output)&#x20;

Refer to the [Engage Handbook](https://engage.mitre.org/wp-content/uploads/2022/04/EngageHandbook-v1.0.pdf) to learn more.&#x20;

Interact with the [Engage Matrix Explorer](https://engage.mitre.org/matrix). We can filter by information from [MITRE ATT\&CK](https://attack.mitre.org/). \
Note that by default the matrix focuses on Operate, which entails Expose, Affect, and Elicit.

## MITRE [D3FEND](https://d3fend.mitre.org/)

&#x20;This resource is "_A knowledge graph of cybersecurity countermeasures._"

D3FEND stands for Detection, Denial, and Disruption Framework Empowering Network Defense.

Let's take a quick look at one of the D3FENDs artifacts, such as Decoy File.

As you can see, you're provided with information on what is the technique (definition), how the technique works (how it works), things to think about when implementing the technique (considerations), and how to utilize the technique (example).

## ATT\&CK® Emulation Plans

Incase tools provided to us by MITRE are not enough, under [MITRE ENGENUITY](https://mitre-engenuity.org/), we have CTID, the Adversary Emulation Library, and ATT\&CK® Emulation Plans.

CTID

MITRE formed an organization named The [Center of Threat-Informed Defense](https://mitre-engenuity.org/cybersecurity/center-for-threat-informed-defense/) (CTID). This organization consists of various companies and vendors from around the globe. Their objective is to conduct research on cyber threats and their TTPs and share this research to improve cyber defense for all.&#x20;

Some of the companies and vendors who are participants of CTID:

* AttackIQ (founder)
* Verizon
* Microsoft (founder)
* Red Canary (founder)
* Splunk

Adversary Emulation Library & ATT\&CK® Emulations Plans

The [Adversary Emulation Library](https://medium.com/mitre-engenuity/introducing-the-all-new-adversary-emulation-plan-library-234b1d543f6b) is a public library making adversary emulation plans a free resource for blue/red teamers. The library and the emulations are a contribution from CTID. There are several [ATT\&CK® Emulation Plans](https://github.com/center-for-threat-informed-defense/adversary\_emulation\_library) currently available: [APT3](https://attack.mitre.org/resources/adversary-emulation-plans/), [APT29](https://github.com/center-for-threat-informed-defense/adversary\_emulation\_library/tree/master/apt29), and [FIN6](https://github.com/center-for-threat-informed-defense/adversary\_emulation\_library/tree/master/fin6). The emulation plans are a step-by-step guide on how to mimic the specific threat group.

## ATT\&CK® and Threat Intelligence

Threat Intelligence (TI) or Cyber Threat Intelligence (CTI) is the information, or TTPs, attributed to the adversary. By using threat intelligence, as defenders, we can make better decisions regarding the defensive strategy. Large corporations might have an in-house team whose primary objective is to gather threat intelligence for other teams within the organization, aside from using threat intel already readily available. Some of this threat intel can be open source or through a subscription with a vendor, such as [CrowdStrike](https://www.crowdstrike.com/).

Scenario: You are a security analyst who works in the aviation sector. Your organization is moving their infrastructure to the cloud. Your goal is to use the ATT\&CK® Matrix to gather threat intelligence on APT groups who might target this particular sector and use techniques targeting your areas of concern. You are checking to see if there are any gaps in coverage. After selecting a group, look over the selected group's information and their tactics, techniques, etc.

