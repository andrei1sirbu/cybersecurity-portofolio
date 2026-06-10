# Forage Job Simulations

Four cybersecurity job simulations completed in March 2026 on the Forage platform. Each simulation was designed by the company and involved completing real-world tasks reviewed against model answers from industry professionals.

---

## Mastercard — Cybersecurity

**Tasks:** 2 · **Duration:** ~1-2 hours

### Task 1 — Phishing Email Simulation Design

**Brief:** Design a realistic phishing email to be used in an employee awareness campaign. The task involved analysing an obviously fake phishing email and improving it to make it convincing enough to be a genuine test.

**Approach:** I analysed the characteristics that make phishing emails effective — sender spoofing that mimics a trusted source, urgency-driven subject lines, familiar branding, and calls to action leading to credential harvesting. I applied these to craft a believable simulation email while understanding why each element works psychologically.

**Deliverable:** In-platform submission.

**Takeaways:**

- Effective phishing exploits trust and urgency rather than technical vulnerabilities — it targets human psychology
- A phishing simulation is only useful if it is realistic enough to be a genuine test; obvious fakes do not build awareness
- Immediate feedback and targeted training for employees who clicked significantly improves programme effectiveness

---

### Task 2 — Security Awareness Presentation

**Brief:** Analyse phishing campaign results across Mastercard departments and create a security awareness training presentation for the teams identified as most at risk (HR and Marketing).

**Approach:** I built a presentation covering what phishing is, the tactics attackers use, how to recognise suspicious emails, and concrete prevention steps. The material was aimed at non-technical employees, so the focus was on practical guidance rather than technical detail.

**Deliverable:** [`mastercard-cybersecurity/mastercard-task-2.pdf`](./mastercard-cybersecurity/mastercard-task-2.pdf)

**Takeaways:**

- Security awareness training is most effective when grounded in real campaign data — knowing which teams clicked most directs the training where it is needed
- Non-technical audiences need clear, jargon-free guidance focused on what to do rather than how attacks work

---

## Commonwealth Bank — Introduction to Cybersecurity

**Tasks:** 4 · **Duration:** ~3-4 hours

### Task 1 — Splunk Data Analysis and Visualisation

**Brief:** Install and configure Splunk Enterprise, import a provided fraud-related dataset, and build a dashboard with charts and tables to visualise key trends and patterns in the data.

**Approach:** I set up Splunk, explored the dataset fields to understand the data structure, and built visualisations to surface fraud-related patterns. The task focused on translating raw log data into a readable format that could inform a security or fraud team.

**Deliverable:** In-platform submission (Splunk dashboard — no export available).

**Takeaways:**

- SIEM tools like Splunk turn raw log data into actionable intelligence; the value is in knowing which fields and patterns to look for
- Building dashboards requires understanding both the data and the questions the audience needs answered

---

### Task 2 — Data Reporting

**Brief:** Interpret the visualised data from Task 1 and present findings to stakeholders, identifying key insights from the fraud dataset.

**Approach:** I identified the most significant trends from the Splunk dashboard and structured a clear summary of findings, focusing on what the data indicated about fraud patterns and what actions it suggested.

**Deliverable:** In-platform submission.

**Takeaways:**

- Communicating data findings to stakeholders requires translating technical observations into business-relevant conclusions
- The ability to prioritise insights — focusing on what matters most — is as important as the analysis itself

---

### Task 3 — Security Awareness Infographic

**Brief:** Design an infographic to raise password security awareness among Commonwealth Bank employees, based on Australian Cyber Security Centre (ACSC) guidelines. Target audience: non-technical staff. Format: PDF.

**Approach:** I researched ACSC recommendations and structured the infographic as a five-step visual guide using a numbered roadmap layout, covering the most important concepts in order of complexity.

**Topics covered:**

1. Passphrases — what they are and why they are harder to crack than passwords
2. Strong passphrases — minimum 15 characters, random words, unique per account
3. Password managers — secure storage, auto-fill, and strong password generation
4. MFA — hardware keys, biometrics, authenticator apps, passkeys, and SMS
5. Passkeys — how they work and why they provide stronger protection than traditional passwords

**Deliverable:** [`commonwealth-bank-cybersecurity/common-wealth-task-3.pdf`](./commonwealth-bank-cybersecurity/common-wealth-task-3.pdf)

**Takeaways:**

- Security awareness materials must balance accuracy with accessibility — the goal is behaviour change, not technical education
- Passphrases and passkeys represent a meaningful evolution beyond traditional passwords and are increasingly recommended by standards bodies

---

### Task 4 — Penetration Testing

**Brief:** Complete the first 10 basic web challenges on HackThisSite.org and document findings in a professional penetration testing report. All work was completed within the browser environment without external tools.

**Approach:** I worked through each challenge methodically, starting with client-side code analysis and progressively applying input manipulation, HTML modification, directory traversal, command injection, and cookie editing as difficulty increased. For each level I documented the vulnerability category, description, impact, exploit procedure, evidence, risk rating, and recommendation — following standard pentest report structure.

**Vulnerability types encountered:**

- Client-side credential exposure (hardcoded password in HTML source)
- Authentication logic flaw (empty password accepted)
- Directory traversal and improper file permissions
- Client-side trust — manipulable form actions and form fields
- Weak reversible cryptography
- Command injection via unsanitised input
- Server-side script execution (SHTML)
- Directory breakout beyond web root
- Insecure cookie handling (plaintext, modifiable without detection)

**Deliverable:** [`commonwealth-bank-cybersecurity/common-wealth-task-4.pdf`](./commonwealth-bank-cybersecurity/common-wealth-task-4.pdf)

**Takeaways:**

- All 10 vulnerabilities share a common root cause: over-reliance on client-supplied data and insufficient server-side validation
- Command injection and directory traversal are among the most impactful web vulnerabilities because they provide direct access to the underlying system
- Cookie manipulation is an underestimated attack vector — signing and encrypting cookies server-side is a straightforward mitigation

---

## Datacom — Cyber Security Operations

**Tasks:** 2 · **Duration:** ~3 hours

Both tasks were based on a ransomware incident affecting a fictional healthcare client, Orion Health Services — a mid-sized healthcare technology provider with 250 employees managing sensitive patient data and cloud-based clinic software across Australia and New Zealand.

> **Note:** Datacom has since updated their Task 2 brief to use a different client scenario. Both deliverables in this repository reflect the original brief completed in March 2026.

---

### Task 1 — Security Breach Impact Analysis

**Brief:** Acting as a junior cybersecurity consultant, investigate the ransomware incident and prepare an executive report covering the nature of the breach, affected systems, business impact, and recommendations.

**Given information:**

- Incident type: Ransomware attack
- Initial entry point: Phishing email with a malicious Excel attachment sent to a finance team member
- Compromised data: Employee payroll records, patient appointment schedules, internal system credentials
- Affected systems: File server, HR and finance systems, backup server (partially encrypted)
- IOCs: Suspicious overseas IP login, Mimikatz credential harvesting, files encrypted with `.orionlock` extension

**Approach:** I structured the report around a standard incident response narrative: executive summary → incident timeline → kill chain → affected assets → data impact classification → operational impact → IOCs → root cause analysis → containment actions → recovery steps → lessons learned.

For the kill chain I mapped the attack as: phishing email → malicious Excel execution → Mimikatz credential harvesting → privilege escalation → lateral movement to shared drive and backup server → ransomware encryption.

I classified compromised data into sensitive (PII: payroll records, appointment schedules) and critical (system credentials) categories, and recommended DMARC, MFA, EDR/XDR, and geographic access restrictions as key controls.

**Deliverable:** [`datacom-cybersecurity/datacom-task-1.pdf`](./datacom-cybersecurity/datacom-task-1.pdf)

**Takeaways:**

- Phishing remains one of the most effective initial access vectors precisely because it bypasses technical controls by targeting people — it requires both technical mitigations (email security) and non-technical ones (training)
- Mimikatz appearing in logs is a strong indicator of privilege escalation and should be treated as a high-severity finding
- Partially encrypted backups drastically reduce recovery options — backup isolation and immutability are critical controls

---

### Task 2 — Cybersecurity Risk Assessment

**Brief:** Conduct a formal risk assessment for the client, identifying the key risks exposed by the incident, scoring them using a likelihood × consequence matrix, and recommending mitigations.

**Approach:** I identified three risks mapped directly to the stages of the attack chain from Task 1, ensuring the assessment reflected the actual threat landscape rather than generic risks:

| Risk ID  | Title                                      | Inherent Rating | Residual Rating |
| -------- | ------------------------------------------ | --------------- | --------------- |
| DTCOM001 | Phishing-Driven Initial Compromise         | High            | High            |
| DTCOM002 | Credential Harvesting and Lateral Movement | Extreme         | High            |
| DTCOM003 | Backup Server Encryption                   | High            | Medium          |

DTCOM002 carried the highest inherent risk (Extreme) because the combination of likely exploitation and extreme consequence — domain-wide credential compromise — represents the most dangerous phase of the attack.

**Deliverable:** [`datacom-cybersecurity/datacom-task-2.pdf`](./datacom-cybersecurity/datacom-task-2.pdf)

**Takeaways:**

- Mapping risks to observed attack stages produces a more actionable risk register than generic assessments disconnected from real events
- MFA and EDR deployment are the two controls with the highest impact on reducing residual risk across all three identified risks
- Offline and immutable backups are a critical and often overlooked control against ransomware that directly reduces recovery time and negotiation pressure

---

## Deloitte Australia — Cyber

**Tasks:** 1 · **Duration:** ~30-60 minutes

### Task 1 — Web Activity Log Analysis

**Brief:** A client suffered a leak of private company information. Analyse the provided web activity logs to identify the source of the breach by identifying suspicious user behaviour.

**Approach:** I worked through the log data systematically, answering questions designed to test log reading ability and anomaly identification. The analysis focused on identifying unusual access times, unexpected resource access, and suspicious IP addresses to pinpoint the responsible user.

**Deliverable:** In-platform submission (quiz format — no file export available).

**Takeaways:**

- Web activity logs are a primary source of evidence in breach investigations; reading them quickly and accurately is a core SOC skill
- Anomalous behaviour is often identifiable without advanced tooling when logs are examined with the right questions in mind — unusual times, unexpected resources, and unfamiliar IPs are the main signals
- Manual log analysis builds the foundational intuition needed to configure and tune automated detection tools effectively
