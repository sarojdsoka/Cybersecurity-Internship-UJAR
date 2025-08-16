#  OWASP ZAP – Vulnerability Scanner Task 4
**Date:** 16 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

--- 	

##  Overview
**OWASP ZAP (Zed Attack Proxy)** is a free, open-source web application security scanner maintained by the [OWASP Foundation](https://owasp.org/).  
It is widely used by penetration testers, bug bounty hunters, and developers to **identify and exploit security vulnerabilities** in websites and applications.

ZAP works as a **proxy** between your browser and the target application, intercepting all requests and responses. This makes it easier to analyze, manipulate, and detect potential weaknesses in real time.

---

##  Features of OWASP ZAP
- **Intercepting Proxy** – Capture and modify HTTP/S requests & responses.  
- **Automated Scanning** – Perform quick security scans to find vulnerabilities.  
- **Spidering & Crawling** – Discover hidden endpoints and pages.  
- **Active & Passive Scans** – Identify vulnerabilities without/with sending malicious requests.  
- **Fuzzer** – Test application inputs with large payload sets.  
- **Plug-in Extensibility** – Add custom scripts and extensions.

---

##  How ZAP Works
1. Configure your browser to route traffic through **ZAP Proxy**.  
2. All **requests from the browser** and **responses from the server** pass through ZAP.  
3. ZAP records and analyzes them, highlighting potential vulnerabilities.  
4. The tester can **manually manipulate requests** (e.g., change parameters, cookies, headers) to test application security.  

---

##  Common Use Cases
- **Finding XSS (Cross-Site Scripting) vulnerabilities.**    
- **Checking authentication & session management weaknesses.**  
- **Identifying insecure HTTP headers.**  
---

##  Basic Workflow
1. **Start ZAP** → Launch ZAP and configure your browser proxy to `127.0.0.1:8080`.  
2. **Intercept Traffic** → Browse the target application and allow ZAP to capture requests.  
3. **Spider the Site** → Use ZAP’s spider to discover hidden paths & endpoints.  
4. **Run Active Scan** → Perform automated vulnerability scanning.  
5. **Analyze Results** → Review alerts (categorized as high, medium, low risk).  
6. **Report Findings** → Export results in formats like HTML, XML, or Markdown.  

---

## Example Security Issues Found by ZAP
- Reflected & Stored **XSS attacks**.  
- **Insecure HTTP Headers** (missing CSP, HSTS, X-Frame-Options, etc.).  
- **Session fixation** & authentication flaws.  
- **Insecure cookie flags** (HttpOnly, Secure).  

---

[## References](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
