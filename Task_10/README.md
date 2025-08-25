# Linux Firewall with Iptables - Task 10

**Date:** 26 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

## Overview
A **firewall** is a security system that controls incoming and outgoing network traffic based on predefined security rules.  
On Linux, the most common firewall management tool is **iptables**, which operates at the kernel level to filter packets and enforce rules.  

Iptables allows administrators to define rules for:
- Accepting or dropping traffic  
- Redirecting packets  
- Enforcing security policies  

---

## ⚙ Installation
Most Linux distributions come with iptables pre-installed.  
Check version:

```bash
iptables --version
```
Install (if missing):

```bash
sudo apt update
sudo apt install iptables
```

---

## Architecture of Iptables

Iptables operates with **tables** and **chains**:

* **Filter table** → Default packet filtering

  * `INPUT` (incoming traffic)
  * `OUTPUT` (outgoing traffic)
  * `FORWARD` (traffic being routed)

* **NAT table** → Network Address Translation, port forwarding.

* **Mangle table** → Special packet alterations (QoS, TTL, etc.).

### Chains & Rules

* A **chain** is a list of rules applied to packets.
* Each **rule** specifies a condition and an action (`ACCEPT`, `DROP`, `REJECT`, etc.).

---

## Common Commands

```bash
iptables [options] [CHAIN] [RULES]
```

* `-A` → Append rule
* `-D` → Delete rule
* `-L` → List rules
* `-F` → Flush rules
* `-P` → Set default policy

---

## Basic Firewall Configurations

### 1 Default Policies

```bash
sudo iptables -P INPUT DROP     # Deny all incoming requests
sudo iptables -P OUTPUT ACCEPT  # Allow all outgoing requests
sudo iptables -P FORWARD DROP   # Deny forwarded requests
```

### 2 Allow Established Connections

```bash
sudo iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
```

### 3 Allow SSH (Port 22)

```bash
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

### 4 Allow HTTP & HTTPS

```bash
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
```

### 5 Allow ICMP (Ping)

```bash
sudo iptables -A INPUT -p icmp --icmp-type echo-request -j ACCEPT
```

### 6 Save Rules

```bash
sudo iptables-save > /etc/iptables/rules.v4
```

### 7 Port Forwarding

Forward external port 80 → internal server `192.168.1.100:80`:

```bash
sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j DNAT --to-destination 192.168.1.100:80
sudo iptables -A FORWARD -p tcp -d 192.168.1.100 --dport 80 -j ACCEPT
```

### 8 Rate Limiting (Prevent DoS)

Limit SSH to 5 attempts/minute:

```bash
sudo iptables -A INPUT -p tcp --dport 22 -i eth0 -m state --state NEW -m recent --set
sudo iptables -A INPUT -p tcp --dport 22 -i eth0 -m state --state NEW -m recent --update --seconds 60 --hitcount 5 -j DROP
```

### 9 Logging Dropped Packets

```bash
sudo iptables -A INPUT -j LOG --log-prefix "Dropped Packet: " --log-level 4
sudo tail -f /var/log/syslog
```

---

[## References](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
