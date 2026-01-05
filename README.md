# AIG Shields Up (Forage) — Security Operations Simulation: Log4j Zero-Day Response + Ransomware Recovery Exercise

## Author
**Ruchi Giradkar**  
Security Operations | Incident Response | Vulnerability Management | Threat Analysis

---

## Overview

This repository contains my completed deliverables for the **AIG “Shields Up” Cybersecurity Job Simulation** hosted on **Forage** (January 2026). The program simulates real-world work performed by an **Information Security Analyst** in a Cyber & Information Security team.

The simulation is split into practical tasks that test:
- **Zero-day vulnerability triage and response** using **CISA advisories** (Apache Log4j / Log4Shell scenario)
- **Infrastructure impact analysis** (identify affected systems + ownership)
- **Enterprise-grade security communication** (targeted remediation email)
- **Ransomware recovery thinking** via a controlled **encrypted file pack** exercise using Python
- **Professional articulation** (resume snippet + interview “Why AIG / Why this role?”)

---

## Repository Contents

### Key folders/files (as provided in the ZIP)
- `Task One/` — Log4j zero-day response workflow, screenshots, and written outputs
- `Task Two/` — Ransomware-related exercise + encrypted file pack (Python starter template, encrypted ZIP, wordlist)
- `Task Three/` — Resume snippet and interview tip writeups
- `completion_certificate.pdf` — Certificate of completion (included)

---

## Task One — Responding to a Zero-Day Vulnerability (Apache Log4j / CISA Advisory)

### Objective
Respond to a newly published **CISA alert** on a **zero-day vulnerability in Apache Log4j**, identify which enterprise infrastructure is affected, determine ownership, and draft a professional security advisory email with remediation steps.

### What I did (technical workflow)
1. **Threat intake & validation**
   - Reviewed CISA-published advisories provided in the simulation.
   - Identified the vulnerability class as **Apache Log4j RCE (Log4Shell-like scenario)**.
   - Mapped impact to likely real-world outcomes: **unauthenticated remote code execution**, common post-exploitation actions, and ransomware risk.

2. **Infrastructure impact analysis (inventory-driven triage)**
   - Reviewed the provided **Infrastructure List** and validated which systems had Log4j installed.
   - Avoided false positives by distinguishing between:
     - **Apache httpd** (web server)
     - **Log4j** (Java logging library; the actual vulnerable component)
   - Result: **Only systems explicitly listing Log4j were treated as in-scope**.

3. **Affected infrastructure identified**
   - **System impacted:** *Product Development Staging Environment*
   - **Reason:** Services installed include **Log4j** (explicitly listed).
   - **Ownership:** *Product Development team* (Team lead listed in the exercise).

4. **Security advisory drafting (enterprise tone + actionable remediation)**
   - Drafted a targeted email to the owning team (instead of broadcasting to the whole org).
   - Included:
     - concise vulnerability description
     - business risk framing (ransomware relevance)
     - remediation and mitigation actions
     - request for confirmation and escalation instructions

### Key technical points included in the advisory
- Threat class: **RCE** enabling attacker-controlled code execution
- Attack vector context: **malicious input reaching logging paths**
- Mitigation strategy:
  - upgrade to fixed Log4j versions where possible
  - temporary mitigations when patching is delayed
  - monitoring guidance for signs of exploitation
- IR awareness: escalate if exploitation indicators are observed

---

## Task Two — “Bypassing Ransomware” (Controlled Recovery Exercise using Encrypted File Pack)

### Objective
Simulate defensive recovery steps in a controlled environment by recovering access to encrypted content using:
- an **encrypted ZIP file** (`enc.zip`)
- a provided **wordlist subset** (`rockyou.txt`)
- a **Python starter template** (`bruteforce.py`) using the `zipfile/ZipFile` library

This task tests:
- understanding of weak attacker operational security (weak passwords)
- ability to write practical automation in Python
- disciplined handling of recovery steps (recover file, document method)

### What I did (technical workflow)
1. **Reviewed the supplied recovery package**
   - `EncryptedFilePack/enc.zip` — password-protected archive (simulated “encrypted payload”)
   - `EncryptedFilePack/rockyou.txt` — common password list subset
   - `EncryptedFilePack/bruteforce.py` — starter template requiring implementation

2. **Implemented a controlled password discovery routine in Python (defensive lab context)**
   - Used Python’s `zipfile.ZipFile` to attempt extraction using candidate passwords from the wordlist.
   - The logic pattern is:
     - iterate candidate passwords
     - attempt `extractall()` with current password (byte-encoded)
     - handle failure via exceptions
     - stop immediately when extraction succeeds
   - Result: recovered access to the protected archive content (as required by the simulation).

3. **Documented outcome as part of the task submission**
   - After successful decryption/extraction, followed the exercise instruction to include evidence of completion (per the Forage workflow).

### Python implementation notes (what’s in this repo)
- The repository includes the **starter template** (`bruteforce.py`) that uses:
  - `from zipfile import ZipFile`
  - wordlist opened in **binary mode** (`rb`) in the template
- The missing portion is the loop + extraction attempts + success/failure handling, which is the core of the exercise.

> **Important**: This exercise was performed in a controlled educational setting. It demonstrates defensive recovery automation skills and does not involve targeting real systems.

---

## Task Three — Professional Artifacts (Resume Snippet + Interview “Why AIG / Why this role?”)

### Resume snippet produced
- Focused on:
  - threat analysis aligned to **CISA publications**
  - vulnerability research and impact assessment
  - drafting actionable remediation guidance
  - applying Python in an ethical, controlled environment for recovery-oriented tasks

### Interview answer produced (“Why are you interested in this role / AIG?”)
- Emphasized:
  - interest in enterprise security operations
  - experience translating technical findings into action
  - motivation to contribute to real-world cyber defense

---

## Skills Demonstrated (ATS + Hiring Manager Keywords)

- **Security Operations (SOC)**
- **Incident Response (IR) workflow awareness**
- **Zero-day vulnerability triage**
- **Vulnerability management & remediation prioritization**
- **Threat intelligence consumption (CISA advisories)**
- **Risk communication to technical and non-technical stakeholders**
- **Python automation for defensive security tasks**
- **Ransomware recovery mindset (containment + recovery orientation)**

---

## Certificate

AIG Shields Up: Cybersecurity Job Simulation — Certificate of Completion is included in this repository.

---

## Ethical & Legal Disclaimer

All work in this repository reflects an **educational simulation** completed in a controlled environment.  
No real-world systems were targeted, and no malicious activity was conducted.

---

## How to Navigate This Repo (Quick Start)

- Start with **Task One** to see the Log4j triage + infrastructure impact analysis + advisory output.
- Then review **Task Two** for the encrypted file pack and the Python automation context.
- Use **Task Three** for recruiter-facing artifacts (resume snippet + interview response).
