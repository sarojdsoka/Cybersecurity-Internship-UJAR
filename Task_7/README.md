#  DIRB – Cybersecurity Internship Task 7

**Date:** 23 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

##  Overview
**DIRB** is a web content scanner used for discovering hidden directories and files on a web server.  
It works by launching dictionary-based brute-force attacks against a target and analyzing the server’s responses.  

Unlike a typical vulnerability scanner, **DIRB does not scan for vulnerabilities directly**. Instead, it helps penetration testers and auditors find **hidden web objects** (like directories, scripts, or files) that may otherwise remain unnoticed.

---

##  Key Features
- Comes **pre-installed in Kali Linux**.  
- Uses built-in wordlists (e.g., `common.txt`) but supports **custom wordlists**.  
- Supports scanning for **specific file extensions**.  
- Can save output to a file for later analysis.  
- Supports **recursive or non-recursive scans**.  

---

##  Basic Usage

### 1️⃣ Default Scan

By default, DIRB uses the `common.txt` wordlist:

```bash
dirb http://testphp.vulnweb.com/
```
This scans the target for common directories and displays results in real-time.

### 2 Scan for Specific File Extensions

The -X flag allows scanning for specific file extensions:

```bash
dirb http://testphp.vulnweb.com/ -X .php
```
This extracts all PHP files/directories from the target.

### 3  Save Output to File

To store results for record-keeping and reporting:

```bash
dirb http://testphp.vulnweb.com/ -o commonScan.txt
```

The output will be saved in commonScan.txt.

### 4 Disable Recursive Scanning

By default, DIRB scans subdirectories recursively. To save time, disable recursion using -r:

```bash
dirb http://127.0.0.1:42001/index.php -r
```
### Use Cases

1. Enumerating hidden admin panels or login pages.
2. Discovering unlinked files like backup configs or test scripts.
3. Mapping web application directory structures.
4. Supporting manual penetration tests with targeted wordlists.


[# REFERENCE](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
