# 🔍 Introduction to Nmap – Cybersecurity Internship Task 2

**Date:** 12 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

## Overview
Nmap (Network Mapper) is a powerful open-source tool used by penetration testers, network administrators, and cybersecurity professionals for network discovery and security auditing. It can identify hosts, services, operating systems, versions, firewalls, and vulnerabilities using a variety of scanning techniques.

This report covers:
- Installation steps
- How Nmap works
- Practical scanning examples
- Advanced usage for CVE detection and aggressive scanning
- Tips for saving scan outputs

---

##  Installation Guide

### **Linux**
```bash
# CentOS / Fedora
sudo dnf install nmap

# Ubuntu / Debian
sudo apt-get install nmap
````

### **Windows**

1. Download the Nmap installer from [nmap.org](https://nmap.org/download.html).
2. Run the `.exe` installer and follow the steps.

### **MacOS**

1. Download the `Nmap-mpkg` installer.
2. Run the installer and wait a few seconds for setup.

---

## ⚙ How Nmap Works

* **Open Ports:** Nmap sends a SYN packet; the server responds with SYN+ACK; Nmap sends RST to mark the port as open.
* **Closed Ports:** Server replies with RST.
* **Filtered Ports:** No response (likely due to firewall rules).

**Example:**

* Port 800, 1234 → Open
* Port 80 → Closed
* 456 ports → Filtered

---

## Common Nmap Commands

### Basic Scan

```bash
nmap scanme.nmap.org
nmap scanme.nmap.org 1.1.1.1 8.8.8.8
```

### Scan Specific Ports / Ranges

```bash
nmap -p 80,443 localhost scanme.nmap.org
nmap -p 1-65535 localhost
```

### Top Ports Scan

```bash
nmap --top-ports 100 scanme.nmap.org
```

###  Service Detection

```bash
nmap -sV scanme.nmap.org
```

### TCP / UDP Scans

```bash
# TCP SYN Scan
nmap -sS scanme.nmap.org

# TCP Connect Scan
nmap -sT scanme.nmap.org

# UDP Scan
nmap -sU scanme.nmap.org
```

Other specialized scans: `-sA` (ACK), `-sF` (FIN), `-sN` (NULL), `-sX` (Xmas).

### CVE & Vulnerability Scanning

```bash
nmap --script vuln scanme.nmap.org
```

You can also create custom NSE scripts in Lua.

### Aggressive Scan + Speed

```bash
# Default speed (T3)
nmap -A scanme.nmap.org

# Faster scan (T4)
nmap -A -T4 scanme.nmap.org
```

### Save Output

```bash
# Normal, XML, Script, Grepable
nmap -oN result.txt scanme.nmap.org
nmap -oX result.xml scanme.nmap.org
nmap -oS result.skr scanme.nmap.org
nmap -oG result.grep scanme.nmap.org

# All formats at once
nmap -oA scan_results scanme.nmap.org
```

---

## Key Insights

* Nmap is more effective when combined with OSINT for targeted scanning.
* Knowing the difference between TCP and UDP scanning is crucial.
* Aggressive scanning provides detailed results but may increase detection risk.
* NSE scripts significantly enhance vulnerability detection.

---

[** References**]

