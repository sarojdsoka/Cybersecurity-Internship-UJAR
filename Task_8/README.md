# Password Cracking – Task 8
  
**Date:** 24 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

## Overview
Password cracking is the process of recovering passwords from stored data, often hashes, using different attack methods.  
It is one of the most common techniques used in cybersecurity attacks and penetration testing, often after credentials are stolen from databases or configuration files.  

The most popular techniques are:  
- **Brute-force attacks** → Tries all possible combinations.  
- **Dictionary attacks** → Tries a list of known/common passwords.  

The success of password cracking depends on **password strength**, **length**, and **hashing algorithm** used.

---

##  What is a Hash?
A **hash** is a one-way cryptographic function that converts input data (like a password) into a fixed-length string.  
- Hashes are **irreversible** by design.  
- But weak/short passwords can be cracked using tools and wordlists.  

### Common Hash Types
- **MD5** – Very fast, broken, found in old apps.  
- **SHA1** – Slightly better, but insecure.  
- **bcrypt** – Strong, designed to be slow.  
- **NTLM** – Windows authentication hashes.  
- **SHA512 (crypt)** – Used in Linux `/etc/shadow` password files.  

 Use tools like `hashid` to identify unknown hashes.  
```bash
sudo apt install hashid
hashid hash.txt
```
⚙ Installing John the Ripper (JtR)

On Kali Linux (pre-installed or via apt):
```bash
sudo apt install john
```
Install latest Jumbo version (from source):
```bash
git clone https://github.com/openwall/john.git
cd john/src
./configure && make -s clean && make -sj4
```
Binaries will be available inside the run/ directory.
Cracking Linux Hashes
1. Create a test hash

```bash
echo -n 'rakesh' | openssl passwd -1 -stdin > hash.txt
```

This generates an MD5-based hash and saves it in hash.txt.
2. Crack the hash with John

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```
3. John compares the hash against the wordlist until it finds the matching password.
In this case, it successfully cracked the hash of "rakesh" within seconds.
    Password length is more important than complexity.
    Short and weak passwords are cracked quickly with tools like John the Ripper.
    Always use strong, unique passwords combined with secure hashing algorithms (e.g., bcrypt, argon2).
    Never store passwords in plain text.

[References](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
