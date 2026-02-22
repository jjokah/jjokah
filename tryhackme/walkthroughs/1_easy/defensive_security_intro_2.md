# Defensive Security Intro
Introducing defensive security and related topics, such as Threat Intelligence, SOC, DFIR, Malware Analysis, and SIEM.

## Task 1 - Introduction to Defensive Security

In this room, we will explore the world of defensive security. We will uncover how defensive security teams play a pivotal role in protecting networks and organisations across the globe.

Defensive security, **known as the blue team**, is used to prepare and proactively protect an organisation's IT infrastructure.  It is concerned with two main tasks:

1. Preventing intrusions from occurring
2. Detecting intrusions when they occur and responding properly

Some of the tasks that are involved in defensive security include:

> **Cyber Security Awareness** - 
Training users about cyber security attacks, such as phishing and social engineering.

> **Documenting & Managing Assets** - 
We must know the systems within the organisation to adequately protect them.

> **Preventative Security** - 
Firewalls and Intrusion Prevention Systems are the first line of defence. These devices control what traffic is allowed to enter and leave the network and prevents malicious traffic from entering the network.

> **Logging & Monitoring** - 
Comprehensive logging of the network and system activity is essential in detecting a threat or unauthorised activity.

> **Frameworks, Policies & Procedures** - 
Creating robust security policies helps ensure that the organisation's devices are used appropriately.

Answer the question below before proceeding onto the next task, where we explore what defensive security looks like within an organisation.

### Answer the questions below
Which team focuses on defensive security?
> Blue Team


## Task 2 - Exploring the SOC

The following tasks will explore the variety of areas within defensive security that work together to protect an organisation's digital assets. Let's begin with one of the core elements that make up a defensive security team.

### Security Operations Centre (SOC)
A Security Operations Centre (SOC) is a team of cyber security professionals that monitors the network and its systems to detect malicious cyber security events. Some of the main areas of interest for a SOC are:

> **Trends & Vulnerability Awareness** -
Keeping up to date with the latest trends and vulnerabilities in the industry is an essential skill to help understand the risks an organisation faces.

> **Policy Violations** -
A security policy is a set of rules that outline how an organisation's assets are to be used and protected. The SOC team monitors for adherence to these policies.

> **Unauthorised & Illegal Activity** -
The SOC team establishes a baseline of acceptable behaviour and activity. Any deviation from this baseline is investigated. Illegal activity exposes the organisation to higher risk.

> **Intrusion & Breach Detection** - 
No matter how well protected an organisation is, there is always a risk of a breach. The SOC team is responsible for detecting and responding to these breaches.

### Answer the questions below
What would you call a team of cyber security professionals that monitors a network and its systems for malicious events?
> Security Operations Centre


## Task 3 - Digital Forensics

### Digital Forensics
Digital forensics is the application of traditional forensic science processes to digital devices. Digital forensics is used to preserve and analyse digital evidence to aide in the investigation of incidents, such as a breach. This may involve looking at information from:

> **File System** -
Analysing a low-level copy of a system's storage reveals much information, such as installed programs, created, partially overwritten and deleted files.

> **System Memory** - If an attacker runs a malicious program within the memory without saving it to the disk, the memory can be analysed to uncover details about how the program operates.

> **System Logs** - Log files provide plenty of information about what happened on a system. Even if the attacker tries to clear their traces, some traces will remain.

> **Network Logs** - Logs of the network traffic that have traversed a network would help answer more questions about whether an attack is occurring and what it entails.


### Answer the questions below
An attacker deploys a piece of malicious code that does not save to the disk. What digital forensics technique would we use in this instance?

> System Memory


## Task 4 - Incident Response

### Incident Response
Incident Response is how organisations manage security events such as breaches, data leaks and cyber attacks. An incident response process is a defined set of stages to minimise damage, contain the threat and recover fast. The process will look like so:

![Incident Response Process](https://tryhackme-images.s3.amazonaws.com/user-uploads/5f04259cf9bf5b57aed2c476/room-content/b162600f5990f249d921aa0e8b7822f7.png)

Let's explore these in a bit further detail:

> **Preparation** - Creating the necessary resources and frameworks to handle an incident. This includes creating incident response teams, infrastructure to support in the incident response process, as well anything to help prevent the incidents, such as providing phishing awareness training.

> **Detection & Analysis** - Using tooling and processes to detect incidents and assess their scope (reach) and severity. Logs can be analysed for suspicious events.

> **Containment, Eradication, and Recovery** - Limiting the impact of the incident, such as preventing a virus from spreading and eliminate the cause and restore affected systems.

> **Post-Incident Activity** - Review the incident overall, how it was handled and could've been prevented. What were the learning points throughout the process? Do we need to provide further cyber awareness training?

### Answer the questions below
What phase of the incident response process involves providing "cyber awareness" training to employees?

> Preparation


## Task 5 - Practical Example of Defensive Security

### The Scenario
Let us pretend you are a Security Operations Center (SOC) analyst for an organisation. You have been given access to the organisation's internal Security Information and Event Management (SIEM) tool, which gathers security-related information and events from various sources and presents them in one dashboard. If the SIEM finds something suspicious, an alert will be generated.

![SIEM Dashboard](https://tryhackme-images.s3.amazonaws.com/user-uploads/63588b5ef586912c7d03c4f0/room-content/63588b5ef586912c7d03c4f0-1715343494201)

### Simulating a SIEM

We have prepared a simplified, interactive simulation of a SIEM system to provide you with a hands-on experience similar to what cyber security analysts encounter.

To start this simulation, please click the "View Site" button below.

View Site
This action will open a "static site" on the right side of your screen. Follow the step-by-step instructions provided within the simulation to navigate through the events and locate the "flag." The flag will popup once you have completed all necessary steps.

### Answer the questions below
What is the flag that you obtained by following along?

> THREAT-BLOCKED


---

Ref:
[Defensive Security Intro](https://tryhackme.com/room/defensivesecurityintroqW)