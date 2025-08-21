# Wireshark – Cybersecurity Internship Task 6

**Date:** 21 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

##  Overview
---
**Wireshark** is a free, open-source network packet analyzer widely used by security professionals, penetration testers, and system administrators. It helps in analyzing network protocols, capturing live traffic, and detecting potential security issues.  
Unlike `tcpdump`, Wireshark provides a **graphical user interface (GUI)** with advanced filtering and visualization features.  
A command-line alternative, **Tshark**, also exists for terminal users.

---

##  Installation
---
### On Linux (Debian/Ubuntu/Kali)
```bash
sudo apt install wireshark
```
##How to Use Wireshark
---
1. Launch Wireshark.
2. Choose a network interface (e.g., Wi-Fi or Ethernet).
3. Start capturing packets.
4. Apply filters to narrow down useful traffic.
5. Analyze packets in detail using the Packet List, Tree View, and Byte View panes.

##Packet Capturing
---
Wireshark uses two types of filters:
### 1. Capture Filters
---
Applied before capturing packets to limit data collection.
Examples:
```bash
host 192.168.1.10          # Capture traffic from/to specific host
net 192.168.0.0/24         # Capture all traffic in a subnet
dst host 10.0.0.5          # Capture traffic sent to host
port 53                    # Capture DNS traffic only
port not 53 and not arp    # Capture all except DNS & ARP
```
### 2. Display Filters
---
Applied after capturing packets to filter what is shown in the interface.
Examples:
```bash
tcp                    # Show only TCP packets
http                   # Show HTTP traffic
ip.addr==10.96.200.253 # Show packets to/from a specific IP
http.request           # Show all HTTP POST requests
http.response          # Show HTTP responses
```
##Packet Coloring in Wireshark
---

Wireshark color-codes packets to make analysis easier:

Gray → TCP packets
Black (red text) → TCP packets with errors
Green → HTTP packets
Light Blue → UDP packets
Pale Blue → ARP packets
Lavender → ICMP packets
Black (green text) → ICMP errors
Custom coloring rules can be set via:
View → Coloring Rules

[# REFERENCES](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
