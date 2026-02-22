# Defensive Security Intro
Introducing defensive security, what it involves and looks like within the real-world, as well as the technologies involved.

## Task 1 - Introduction to Defensive Security
In this room, we will explore the world of defensive security (also known as blue teaming). We will uncover how defensive security teams play a key role in protecting networks and organisations across the globe, and understand what defensive security looks like in practice.

Unfortunately, headlines show us what happens when defensive security falls short. From large-scale ransomware attacks on healthcare systems to data leaks at major corporations, the impact of poor security can be severe and incredibly costly for an organisation, with fines to follow. Here are some real-world examples:

> **British Airways (2018)**
Personal details such as birth names, addresses, and payment card details of 400,000+ customers were leaked. 
British Airways was fined £20 million for this incident.

> **Marriott International (2020)**
The passport information, payment card details, and names of 334 million customers were leaked, partly due to outdated systems.
Marriott International settled a $52 million lawsuit.

> **Advanced Computer Software Group (2022)**
Medical records and phone numbers for 79,904 people were leaked due to weak security policies.
Government officials fined the organisation £3.07 million.

> **23andMe (2023)**
Over 7 million users' sensitive data, such as names, addresses, health records, and DNA data, was leaked due to poor security policies.
23andMe was fined £2.31 million by government officials.

> **SK Telecom (2024)**
Poorly configured servers led to the personal data of approximately 27 million users being leaked.
SK Telecom were fined $97 million by government officials.

### Answer the questions below 
What is defensive security also known as?
> Blue Teaming


## Task 2 - Responsiblities of Defensive Security
This task will explore defensive security in more depth. You will also meet some of the experts within a defensive security team to learn more about their day-to-day responsibilities.

Let's start by focusing on some key areas of defensive security:

> **Monitoring and Detecting** - 
Continually observing network and system activity to detect suspicious behaviour and events.
These may include, for example, monitoring for logins from another country while the employee is based in the company's London office.

> **Incident Response** - 
The team quickly comes together if suspicious activity is confirmed and alerts are raised.
This is when the Incident Response process begins. The process involves containing and removing the threat and restoring the business back to normality.

> **Threat Intelligence** - 
Gathering and using information about attackers—their latest methods, targets, and trends—can greatly strengthen an organisation’s defences.
For example, understanding that an attacker focuses on a specific software application used within organisations.

> **Vulnerability Management** - 
Fixing software or system flaws is an important preventative measure that can lower the risk of an attack.
Security teams can check which systems attackers are most likely to target. This can be done manually or with the help of automated tools.

> **Investigation and Analysis**
Members of a defensive security team are always monitoring and analysing what’s happening inside an organisation.
They work to separate normal activity from suspicious behaviour, digging into the details like solving a puzzle to uncover valuable insights.

What's more, a defensive security team is made up of a mixture of roles and responsibilities. Below, let's meet some of the highly-skilled individuals you would find within a defensive security team:

> **Bob, SOC Analyst** - 
Bob monitors events on the organisation's network and systems to identify suspicious or expected behaviour.
He is at the frontline of protecting the organisation.

> **Aaliyah, Incident Responder** -
Aaliyah is responsible for investigating and responding to ongoing security incidents within the organisation.
She will monitor and prevent attackers in real time and share lessons learned during the attack to prevent future incidents.

> **Zoe, Security Engineer** - 
Zoe develops and maintains the essential tools and systems that support the defensive security team.
These systems enable the team to monitor, investigate, and explore events within an organisation.

> **Bill, Digital Forensics** - 
Bill will utilise their expertise to understand what occurred during an incident.
They will gather, preserve, and analyse evidence from the network and systems to uncover vital information about the attackers and their methods.

### Answer the questions below
An attack has been detected on an organisation's network. What is the name of the person above who would be responsible for responding to the attack?
> Aaliyah


## Task 3 - Defensive Security in Practice
Now that you’ve been introduced to defensive security and met some key individuals, let's understand how it is applied.

Organisations don’t rely on a single tool or method to stay secure — they build layers of defence, much like an onion or many layers to a castle. We call this "Defence in Depth," meaning that if one security measure fails, we have others to rely upon at various stages.

Examples of these defensive measures include:

> **Employee Training** - 
In today's world, the human factor of cyber security cannot be ignored.
With attacks more often than not targeting employees rather than systems, training employees to be proactive in recognising attempts for things like phishing is essential.

> **Intrusion Detection Systems (IDS)** - 
These devices act as surveillance cameras across the organisation's IT.
They monitor and alert when suspicious behaviour or activity is detected across the network or systems.

> **Firewalls** - 
These devices act as security guards on an organisation's network.
They monitor and determine what traffic is allowed to enter the network, or should be rejected.

> **Security Policies** - 
Security policies help organisations ensure that their systems are used correctly.
They can reduce risk by blocking access to dangerous websites or requiring strong passwords, making it harder for attackers to guess login details.

This means that even if an employee clicks on a dangerous attachment in an email, other protections are in place to prevent the malicious attachment from harming the organisation.

Defensive security teams rely on a wide range of tools and technologies. These tools allow professionals to analyse information and investigate threats more effectively. This section will look at some key technologies commonly used by defensive security teams worldwide.

### Exploring the Security Operations Centre (SOC)
Think of a SOC as the defensive security centre for an organisation's technology. This busy centre is the frontline of protecting an organisation, often operating around the clock, 365 days a year, and employs a variety of security professionals who monitor and protect the organisation's networks, systems, and data.

A typical day in the SOC could look like:

- Reviewing alerts triggered by security tooling
- Investigating anomalies
- Responding to incidents

These professionals are often the eyes and ears on the frontline for protecting an organisation.

### SIEMs: The Defensive Security Radar
Much like a control centre in the real world, SIEMs (Security Information and Event Management) systems are the central place for all data and information collected from security devices, workstations, servers, and more within an organisation.

Much like radar sweeping the digital environment, these systems are an absolutely critical part of any organisation's defensive security, as they offer insight into what is happening within the organisation's IT.

The systems inside an organisation produce a large amount of information. This information needs to be brought together in one central and easy-to-access place to understand what's happening quickly and clearly. This way, several people can review and analyse it quickly.


## Task 4 - Practical: Defend FakeBank
Phew, well done for progressing this far. Now, you will complete a hands-on exercise within a defensive security team to investigate an active attack.

### Scenario
You will be joining the defensive security team for FakeBank, a large financial institution. You will be at the forefront of investigating and resolving suspicious events marked as such by FakeBank's sophisticated "Security Information and Event Management (SIEM)."

It is your duty to protect FakeBank and it's customers. Be proactive and inquisitive. To begin this practical, click on the green "View Site" button located below.

**View Site**

This action will open a "static site" on the right side of your screen. Investigate the "Web Discovery Attack" and perform the necessary, guided, protective measures to stop it from continuing.

### Answer the questions below
What is the flag that you obtained by following along?
> THM{FAKEBANK-SECURED}

---

Ref: [Defensive Security Intro](https://tryhackme.com/room/defensivesecurityintroQR)