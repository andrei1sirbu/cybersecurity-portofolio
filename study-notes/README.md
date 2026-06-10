# Study Notes

Personal notes from three sources compiled during cybersecurity study in early 2026.

---

## CompTIA Security+ (SY0-701)

Notes taken while preparing for the Security+ exam, passed in March 2026. Organised by the five official exam domains.

---

### Domain 1 — Threats, Attacks and Vulnerabilities

#### Threat Actors

- **Capability** — proficiency in devising new exploit techniques
- **Sophistication** — the advancement of a threat actor's methods and tools
- The difference between **Shadow IT** and an **Insider Threat** is malicious intent — Shadow IT is not malicious

#### Social Engineering

- **Pretexting** — making up a scenario to trick users into revealing sensitive data
- **Whaling** — targets high-ranking employees to steal information
- **Phishing campaign** (training) — all employees receive simulated phishing emails
- **Spear phishing campaign** (training) — only a specific group (e.g. managers) receive simulated phishing emails

#### Network Attacks

- **Wiretapping** — attacker physically connects to the network for eavesdropping
- **On-path attack** — attacker intercepts communication between two parties without needing physical access to the network
- **Session hijacking** — attacker intercepts the session ID sent from server to client
- **CSRF (Cross-Site Request Forgery)** — attacker sends a crafted link that, when clicked, initiates an action (e.g. a bank transfer) on behalf of the user without their knowledge
- **Brute-force attack** — tries a wide range of passwords; impacts system performance; uses incremental passwords
- **Dictionary attack** — uses the most common passwords across many accounts to avoid triggering account lockout

#### Malware

- **Spyware** — malware that takes screenshots, activates the camera/microphone, and captures data

#### Indicators of Compromise

- **Concurrent session usage** — an attacker is using an account simultaneously with the legitimate user
- **Impossible travel** — multiple connections from different geographic locations within a short time span
- A **2-hour gap in the logs** is a serious concern and should be investigated

#### Email Security

- **DMARC** — focuses on the authenticity of the sending domain; extends SPF and DKIM; allows you to define what happens to failing emails (e.g. send to spam)
- **DKIM** — validates that the email was sent from the claimed domain's server
- **S/MIME** — signs and encrypts the content of an email
- **SPF** — specifies which email servers are authorised to send on behalf of a domain

#### Ports to Know

- **Microsoft SQL Server** — Port 1433

---

### Domain 2 — Architecture and Design

#### Cryptography

- **Stream cipher** — symmetric encryption best suited for variable-length messages; encrypts data one byte or bit at a time
- **AES** — a block cipher (128-bit or 256-bit); symmetric encryption
- **ECC (Elliptic Curve Cryptography)** — asymmetric algorithm; efficient with shorter keys
- **RSA** — asymmetric encryption algorithm; requires longer keys
- **Digital signatures** — add integrity to data

#### Key and Secret Management

- **HSM (Hardware Security Module)** — hardware that securely stores keys and certificates for all devices across an organisation
- **TPM (Trusted Platform Module)** — a chip on the motherboard used to securely store keys and provide cryptographic functions for that specific device
- **Secure Enclave** — a hardware processor that provides cryptographic functions; common in Apple devices

#### Data Protection

- **Tokenization** — data is paired with a smaller set of symbols; tokens have different sizes and structures than the original data
- **Data masking** — data is hidden using symbols that have the same structure as the original (e.g. a hidden password field)
- **Volume encryption** — encrypts an entire volume or virtual drive; not suited for database operations

#### Zero Trust

- **Control plane** — policy-driven access control
- **Least privilege** — the best way to describe the Zero Trust model

#### Emerging Technologies

- **Blockchain** — can track physical or digital objects; applicable to supply chain monitoring
- **Serverless** — running code without managing the underlying software infrastructure
- **IaC (Infrastructure as Code)** — managing and setting up IT infrastructure through code
- **SDN (Software Defined Networking)** — managing network devices through software

#### Availability

- **Load balancing** — distributes network traffic across many servers; all servers perform the same task
- **Clustering** — combines servers into a single logical node; servers are assigned different tasks; if one fails, its task is unavailable but others continue

#### Wireless Security

- **WEP** — the weakest wireless security protocol; should never be used
- **TKIP (Temporal Key Integrity Protocol)** — per-packet encryption keys; introduced with WPA

#### Standards

- **ISO/IEC 27001** — requirements for an information security management system
- **NIST SP 800-63** — US government standard for digital identity guidelines

#### Change Management

- **Approval process** — ensures changes are reviewed and approved before implementation
- **Impact analysis** — assesses the potential consequences of a proposed change
- **Maintenance window** — a predefined timeframe for applying system changes
- **Downtime** — a period when a system is unavailable

#### Security Controls

- **Login banner** — a deterrent security control
- **De-authentication attack** — causes loss of connectivity; commonly associated with wireless networks

---

### Domain 3 — Implementation

#### Authentication

- **EAP (Extensible Authentication Protocol)** — handles multiple authentication methods for wired and wireless networks
- **802.1X** — port-based network access control; prevents unauthorised devices from connecting
- **Federation** — organisations share digital identities across systems; enables SSO

#### Mobile Device Management

- **MDM** — helps administrators configure and set policies for all mobile devices in an organisation

#### Cloud

- **Shared responsibility model** — the provider secures infrastructure; the customer secures data and applications
- **Isolation between instances** — prevents lateral movement within a cloud environment

#### Network Security

- **UTM (Unified Threat Management)** — does not provide application layer filtering
- **Securing backups** — encryption is the primary method

#### Data Classification

| Classification                    | Description                                                                     |
| --------------------------------- | ------------------------------------------------------------------------------- |
| Sensitive                         | Data that could affect an individual (health, financial); includes IP, PII, PHI |
| Confidential                      | Very sensitive; must be approved to view                                        |
| Public / Unclassified             | No restrictions on viewing                                                      |
| Private / Classified / Restricted | Restricted access; may require an NDA                                           |
| Critical                          | Data an organisation cannot function without; must always be available          |

- **Regulated data** — a third party sets the rules for how that data is protected (e.g. PCI DSS for card data)
- **Trade secrets** — secret formulas or processes belonging to an organisation
- **Intellectual property** — protected using copyrights
- **Legal data** (e.g. court records) — public data
- **GDPR** — protects personal data including religious beliefs and political opinions

#### Development

- **CI/CD** — integrates code changes regularly into a shared repository; enables seamless collaboration between security and development

---

### Domain 4 — Operations and Incident Response

#### Digital Forensics

- **Legal hold** — securing and preserving evidence related to a security incident
- **E-discovery** — examining drives for electronically stored data to use as evidence
- **Acquisition phase** — imaging a hard drive to create an exact byte-for-byte copy for analysis
- **Chain of custody** — documenting who handles evidence at every step is crucial
- **RFC 3227** — guidelines for Evidence Collection and Archiving
- **Archiving** — ensures long-term secure storage; aids regulatory compliance
- **Data retention** — keeps data for a defined period; must adhere to legal, regulatory, and contractual requirements
- **Audit trails** — detailed sequential activity logs; crucial for detecting and understanding security breaches
- **Security classification status** is NOT included in file metadata

#### Asset Management

- **Enumeration** — does not just count assets; tracks equipment and access controls to hardware, software, and data
- **Inventory** — maintains up-to-date records of all assets
- **Ownership** — establishes accountability; reduces insider threat risk

#### Monitoring and Detection

- **NetFlow** — visualises network flow patterns; the analyst interprets the data
- **Alert tuning** — reduces false positives; improves alerting accuracy
- **SCAP** — automates the validation and patching of security issues
- **Automation** — can recognise security events and escalate tickets to CSIRT

#### Operations

- **Simulation** — interactive drills practising incident response in a controlled environment
- **Guard rails** — boundaries in automation workflows ensuring they stay within designed parameters
- **TCO** — initial purchase cost plus ongoing maintenance costs
- **CAPEX** — the initial purchase cost of an asset
- **Environmental variables** — unique characteristics of an organisation's infrastructure that affect vulnerability assessments

---

### Domain 5 — Governance, Risk and Compliance

#### Agreement Types

| Agreement | Description                                                                                              |
| --------- | -------------------------------------------------------------------------------------------------------- |
| SLA       | Between customer and service provider; defines acceptable downtime and support                           |
| MOU       | Informal partnership; defines broad goals; not a signed contract                                         |
| MOA       | One step above MOU; more detail; can be a legal document but cannot enforce promises like a contract     |
| MSA       | Legal contract between organisations; framework for additional work                                      |
| SOW       | Detailed breakdown of services, scope, and timeline; answers "Was the job done properly?"                |
| NDA       | Confidential agreement; information must not be disclosed; can be unilateral, bilateral, or multilateral |
| BPA       | Formal financial partnership; describes business operations, decision-making, and disaster recovery      |

#### Risk Management

- **Risk threshold** — the limit of acceptable risk
- **Risk tolerance** — willingness to accept risk
- **EF (Exposure Factor)** — fraction of an asset's value at risk
- **SLE** — cost of a single occurrence of a risk event
- **ARO** — expected number of occurrences per year
- **ALE** = SLE × ARO

| Risk Assessment Type | Description                                                 |
| -------------------- | ----------------------------------------------------------- |
| One-time             | Single comprehensive assessment at a specific point in time |
| Ad-hoc               | Performed as needed, in response to an event                |
| Recurring            | Conducted at regular intervals                              |
| Continuous           | Real-time risk analysis                                     |

- **Risk identification** — risks are identified and documented
- **Risk assessment** — evaluating and prioritising risks by impact and likelihood
- **Risk analysis** — determines financial impact using quantitative and qualitative methods
- **Risk register** — comprehensive record of all identified risks, impacts, and mitigations

#### Business Continuity

- **RTO** — amount of time until full business operations are recovered
- **RPO** — maximum tolerable data age for recovery
- **MTTR** — average time to repair a system
- **MTBF** — average time between failures

#### Governance

- **Committees** — support the governance board with recommendations; include representatives from different departments
- **Executive teams / Officers** — hold ultimate decision-making authority
- **Management** — handles day-to-day operations
- **Board governance** — represents the board of directors

#### Compliance Frameworks

| Law / Regulation             | Description                                                                                           |
| ---------------------------- | ----------------------------------------------------------------------------------------------------- |
| GDPR (Europe)                | Protects personal data including religious beliefs and political opinions                             |
| CCPA (USA)                   | US equivalent of GDPR for California residents                                                        |
| Computer Security Act (1987) | Requires US federal agencies to develop policies to secure computer systems                           |
| GLBA                         | Requires financial institutions to secure customers' sensitive data                                   |
| SOX                          | Requires public companies to adhere to strict auditing, reporting, and information security standards |
| HIPAA                        | Standards for the storage, use, and transmission of health care information                           |

#### Physical Security

- Designing sites as security zones maximises access control for the most sensitive areas

#### Software Development

- **SDLC** — divides software creation and maintenance into specific phases

---

## HackTheBox — Junior Cybersecurity Analyst

Notes from the HackTheBox Academy Junior Cybersecurity Analyst learning path.

---

### Introduction to Information Security

#### Core Concepts

- **Risk** — the potential of a malicious event to cause damage; quantified by likelihood and severity; encapsulates both threats and vulnerabilities
- **Threat** — a potential cause of harm; can be a person or a natural disaster; exploits vulnerabilities
- **Vulnerability** — a weakness that can be exploited; software bugs, misconfigurations, weak passwords

#### Security Roles

| Role                         | Description                                          | Relevance to Penetration Testing                         |
| ---------------------------- | ---------------------------------------------------- | -------------------------------------------------------- |
| CISO                         | Oversees the entire information security program     | Sets the security strategy that pen testers evaluate     |
| Security Architect           | Designs secure systems and networks                  | Creates the systems pen testers attempt to breach        |
| Penetration Tester           | Identifies vulnerabilities through simulated attacks | Finds and exploits vulnerabilities legally and ethically |
| Incident Response Specialist | Manages and responds to security incidents           | Works alongside pen testers; shares lessons learned      |
| Security Analyst             | Monitors systems for threats                         | Uses pen test results to improve monitoring              |
| Compliance Specialist        | Ensures adherence to security standards              | Pen test reports often support compliance efforts        |

#### CIA Triad and Core Principles

Confidentiality · Integrity · Availability · Non-repudiation · Authentication · Privacy

#### Security Processes

1. Risk Assessment
2. Security Planning
3. Implementation of Security Controls
4. Monitoring and Detection (SOC)
5. Incident Response (Containment, Eradication and Recovery)
6. Disaster Recovery
7. Continuous Improvement

#### Common Tools

- **Nmap** — network scanning
- **Wireshark** — packet analysis
- **Metasploit** — exploitation framework
- **Burp Suite** — web application security testing
- **John the Ripper** — password cracking
- Firewalls, IPS/IDS, SIEM, Vulnerability Scanners, Encryption Tools

---

### Operational Security

1. **Asset Identification** — identify critical information assets
2. **Threat Identification** — determine what could go wrong
3. **Vulnerability Identification** — identify weaknesses
4. **Access Control** — determine who has access to sensitive data
5. **Monitoring** — continuously look for alerts and suspicious activity

- **Asset management** — tracks what assets exist, where they are, and how important they are
- **Change management** — changes must be controlled, tested, and approved

---

### Disaster Recovery and Business Continuity

- **Disaster Recovery** — restores critical systems after failure
- **Business Continuity** — ensures the organisation can keep operating regardless of what happens
- Define RTO and RPO for all critical systems

---

### Cloud Security

Follows a **shared responsibility model** — the provider secures infrastructure; the customer secures data and applications.

- Encrypt data at rest and in transit
- Apply IAM — only authorised individuals can access cloud resources
- Follow compliance and governance requirements

---

### Physical Security Vulnerabilities

| Vulnerability                 | Description                                                       |
| ----------------------------- | ----------------------------------------------------------------- |
| Unsecured access points       | Doors or windows left unlocked or easily bypassed                 |
| Weak locks                    | Outdated locks that can be picked or broken                       |
| Inadequate perimeter security | Lack of fencing, barriers, or surveillance                        |
| Poor key management           | Improper handling of keys, access cards, or credentials           |
| Insufficient lighting         | Dark areas that could conceal intruders                           |
| Exposed IT infrastructure     | Servers or network devices accessible to unauthorised individuals |
| Lack of visitor management    | Weak protocols for monitoring visitors                            |
| Unattended workstations       | Computers left unlocked in shared spaces                          |

---

### Mobile and IoT Security

- **Mobile** — passwords, remote wipe, encryption, VPNs, app vetting, permission management
- **IoT** — network segmentation limits what IoT devices can access on the network

---

### Cybersecurity Teams

- **Red Team** — simulates real-world attacks; identifies vulnerabilities; produces detailed reports
- **Blue Team** — SOC analysts, incident responders, threat hunters, security engineers, security analysts
- **Purple Team** — red and blue teams working together and sharing knowledge

---

### Networking Fundamentals

| Architecture  | Description                                                                                         | Examples            |
| ------------- | --------------------------------------------------------------------------------------------------- | ------------------- |
| P2P           | Each node acts as both client and server; no centralised server                                     | BitTorrent          |
| Client-Server | Centralised server responds to clients; single/two/three/N-tier variants                            | Web servers         |
| Hybrid        | Combines P2P and client-server; central server handles authentication; data transfers between peers | Skype               |
| Cloud         | Third-party provides the architecture; scalable; no direct hardware access                          | iCloud              |
| SDN           | Control plane managed by a software controller; devices execute software commands                   | Enterprise networks |

---

## DNSC SOC Analyst Exam Preparation

Notes prepared for the cybersecurity entrance exam for a SOC Analyst position at the Romanian National Directorate of Cyber Security (DNSC). Originally written in Romanian; translated to English here.

---

### Core Terminology

| Term                  | Description                                                                                                                                                            |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **SIEM**              | Aggregates logs from across a network; enables real-time detection, analysis, and response                                                                             |
| **Firewall**          | Operates at OSI layers 3 and 4; filters traffic by IP and port using ACLs; implicit deny by default                                                                    |
| **NGFW**              | Operates at layer 7; integrates DPI, IPS, and Application Awareness; inspects payloads, not just headers; can block traffic for a specific user rather than just an IP |
| **IPS**               | Blocks traffic matching known or custom malware signatures; can only prevent known malware                                                                             |
| **IDS**               | Alerts when traffic matches a malware signature; does not block — monitoring only                                                                                      |
| **EDR**               | Real-time monitoring and detection; uses behavioural analysis; can detect unknown malware                                                                              |
| **Antivirus**         | Detects, quarantines, or removes malware based on signatures; can only handle known malware                                                                            |
| **Content Filtering** | Ad blockers, spam email filters, reputation services                                                                                                                   |

---

### Malware Types

| Malware    | Description                                                     |
| ---------- | --------------------------------------------------------------- |
| Worm       | Replicates without user execution; spreads via USB AutoRun      |
| Virus      | Requires user execution to activate                             |
| Trojan     | Disguised as legitimate software                                |
| Ransomware | Encrypts host data; typically stores keys in RAM                |
| Spyware    | Captures screenshots, activates camera/microphone, records data |

---

### Attack Techniques

| Technique            | Description                                                                  |
| -------------------- | ---------------------------------------------------------------------------- |
| DoS / DDoS           | Overwhelms system resources, forcing it offline                              |
| C2 and Beaconing     | Infected system signals attacker's C2 server; establishes persistent control |
| Botnet               | Network of infected systems; commonly used for DDoS                          |
| XSS — Persistent     | Script injected into unsanitised input; runs for all users who view it       |
| XSS — Non-Persistent | Crafted link with embedded script sent to a single target                    |
| Drive-by Target      | Legitimate website compromised with malicious content                        |
| Drive-by Compromise  | Malicious code executes in the victim's browser without their knowledge      |
| Web Shell            | Malicious script uploaded to a web server for remote attacker access         |
| Fileless Execution   | Code executes directly in RAM; no file written to disk; harder to detect     |
| RCE                  | Attacker runs code on the infected system without local access               |
| Obfuscated Files     | Zip/RAR or encrypted files used to conceal malware from detection tools      |

---

### MITRE ATT&CK Framework

#### Initial Access

| Technique                           | Description                                                    |
| ----------------------------------- | -------------------------------------------------------------- |
| Content Injection                   | SQL injection, XSS, XML injection                              |
| Exploit Public-Facing Application   | Compromises a publicly accessible server to gain network entry |
| External Remote Services            | Exploits services such as VPNs                                 |
| Hardware Additions                  | Adds a rogue device to the network or a workstation            |
| Phishing                            | Tricks users via email or phone                                |
| Replication Through Removable Media | Exploits USB AutoRun to spread malware                         |
| Supply Chain Compromise             | Tampered hardware or software                                  |
| Trusted Relationships               | Compromises a partner network to access the target             |
| Valid Accounts                      | Uses legitimate credentials                                    |
| Wi-Fi Networks                      | Exploits a vulnerable or compromised Wi-Fi network             |

#### Execution

| Technique                          | Description                                                               |
| ---------------------------------- | ------------------------------------------------------------------------- |
| Command and Scripting Interpreters | Runs commands via PowerShell, CMD, Bash, etc.                             |
| Docker / Kubernetes Exec           | Runs commands inside active containers                                    |
| Exploitation for Client Execution  | Executes code in vulnerable client apps (browsers, Office, PDF readers)   |
| Native API                         | Executes through low-level OS functions                                   |
| Scheduled Tasks                    | Creates or modifies scheduled tasks for persistence (schtasks.exe, cron)  |
| Process Injection                  | Inserts code (e.g. DLL) into a legitimate process                         |
| Reflective Code Loading            | Executes code directly in RAM without a file on disk; very hard to detect |
| WMI                                | Used for persistence, RCE, and lateral movement                           |
| Remote Services                    | Uses SSH to execute code remotely                                         |
| Ingress Tool Transfer              | Transfers files or scripts to the victim system via C2                    |
| Input Capture                      | Keylogger                                                                 |

---

### FIRST Framework — SIEM Services

#### Monitoring and Detection

- Uses AV, IDS/IPS alerts, and application logs to identify potential incidents
- Reduces false positives before escalation
- Functions: log and sensor management, detection use case management, contextual data management

#### Event Analysis

- Determines whether an event is a valid incident or false alarm
- Prioritises more important incidents
- Functions: **Correlation** (groups related incidents as one) · **Qualification** (triages as TP or FP)

---

### FIRST Framework — CSIRT Services

| Service                                 | Purpose                                                                                       |
| --------------------------------------- | --------------------------------------------------------------------------------------------- |
| Incident Report Acceptance              | Receives reports from SOC teams; standardises reporting                                       |
| Incident Analysis                       | Triage → information collection → detailed analysis → root cause → cross-incident correlation |
| Artefact and Forensic Evidence Analysis | Artefact preservation; reverse engineering; dynamic analysis; comparative analysis            |
| Mitigation and Recovery                 | Containment → system restoration → support for other security entities                        |
| Incident Coordination                   | Timely notifications and accurate information distribution                                    |
| Crisis Management Support               | Assists other CSIRTs; senior personnel take responsibility for escalation                     |

---

### NIST — Malware Incident Prevention

#### Policy

- Mandatory scanning of files, links, and USB drives
- Prohibition on sending/receiving .exe files by email
- Restriction of USB drive usage
- Prohibition of unnecessary software installation
- Specified antivirus requirements per device category

#### Awareness

- Do not open suspicious emails, websites, or files
- Do not disable security tools on workstations
- Do not use administrator accounts for routine tasks

#### Vulnerability Mitigation

- Disable unnecessary services and systems
- Change default credentials
- Disable AutoRun
- Apply the principle of least privilege
- Automate host configuration using checklists

#### Threat Mitigation Controls

| Control                    | Description                                             |
| -------------------------- | ------------------------------------------------------- |
| Antivirus                  | Real-time scanning; quarantine and disinfect            |
| Network/Host IPS           | Blocks known malware signatures                         |
| Network Behaviour Analysis | Analyses traffic and establishes baselines              |
| Network/Host Firewalls     | Deny by default                                         |
| Content Filtering          | Ad blockers, spam filters, reputation services          |
| Application Whitelisting   | Allows only approved applications; use audit mode first |

#### Defensive Architecture

- **BIOS protection**
- **Sandboxing** — isolates applications; restricts resource access
- **Browser Segregation** — separate browsers for corporate and personal use
- **Virtualisation** — multiple VMs for different purposes

---

### NIST — Malware Incident Response

#### 1. Preparation

- IR teams must understand how malware infects and spreads
- Maintain a designated point of contact (help desk IT)
- Ensure all response tools are available and ready

#### 2. Detection and Analysis

- Confirm whether the incident is valid; when in doubt, treat it as real
- Examine detection sources: AV, IPS/IDS, SIEM
- Automate infected host detection where possible
- Place malware in a sandbox to analyse behaviour
- Prioritise incident response based on severity

#### 3. Containment, Eradication and Recovery

- **Containment** — shut down affected services; isolate infected hosts from the network
- **Eradication** — remove malware; mitigate host weaknesses; rebuild OS images where necessary
- **Recovery** — remove containment measures; restore data and functionality

#### 4. Lessons Learned

- Update security policies and awareness training programmes
- Reconfigure software and antivirus tools based on findings
- Deploy any missing detection tools identified during the incident
