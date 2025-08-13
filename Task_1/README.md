**CIA Triad – Cybersecurity Internship Task 1**
---

Date: 11 August 2025  

## Overview
The **CIA Triad** is a fundamental model in cybersecurity that ensures data is protected through three key principles:  
- **Confidentiality** – Ensuring only authorized users can access data.  
- **Integrity** – Ensuring data remains accurate and unaltered.  
- **Availability** – Ensuring data and systems are accessible when needed.  

This document explores the CIA Triad, its components, real-world case studies, and how Linux file permissions can support these principles.

---

## CIA Triad Components & Case Studies

### 1. Confidentiality
**Definition:** Keeping information private so only intended parties can access it.  
**Example:** WhatsApp's end-to-end encryption ensures messages are visible only to sender and receiver.  

**Case Study:** *Aadhaar Data Breach (2018)*  
- Over 1.1 billion Indian citizens’ personal data leaked.  
- Unauthorized access by ex-government employees.  
- Data was being sold via WhatsApp.  
- Highlights the need for strict confidentiality controls.

---

### 2. Integrity
**Definition:** Ensuring data is not altered during storage or transfer.  
**Example:** Bank balances or messages must remain unchanged in transit.  

**Case Study:** *Stuxnet Worm (2010)*  
- Targeted Iran’s Natanz nuclear facility.  
- Altered industrial control systems’ data.  
- Damaged 984 centrifuges, reducing uranium enrichment efficiency by 30%.  
- Demonstrated how compromised integrity can lead to critical failures.

---

### 3. Availability
**Definition:** Ensuring resources and data are accessible when needed.  
**Example:** Online services like maps or messaging must be operational during emergencies.  

**Case Study:** *Microsoft Outage due to CrowdStrike (2024)*  
- Faulty software update caused global Windows crash.  
- Affected airlines, healthcare, finance, and public services.  
- Cost US Fortune 500 companies $5.4 billion.  
- Showed the importance of redundancy and disaster recovery planning.

---

##  How the CIA Triad is Maintained

### Confidentiality
- **Methods:** Access control (passwords, biometrics, OTP), encryption (AES, TLS, HTTPS), secure networks (VPNs, SSH).  
- **Example:** Gmail uses TLS encryption + 2FA.

### Integrity
- **Methods:** Hashing (SHA256, MD5), digital signatures, audit logs, version control.  
- **Example:** Banking systems store transaction hashes to detect tampering.

### Availability
- **Methods:** Redundant servers, load balancing, backups, disaster recovery plans.  
- **Example:** Netflix uses multiple data centers for uninterrupted service.

---

## Linux File Permissions & the CIA Triad

- **Confidentiality:**  
  `chmod 600 secrets.txt` – Only owner can read/write.  
- **Integrity:**  
  `chmod 644 config.cfg` – Only owner can modify, others can read.  
- **Availability:**  
  `chmod 755 script.sh` – Owner full access, others read & execute to ensure availability.

---

[## References](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
