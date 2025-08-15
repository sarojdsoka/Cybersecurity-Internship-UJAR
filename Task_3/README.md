# Introduction to HTTP Headers – Cybersecurity Internship Task 3

**Date:** 15 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

##  Overview
HTTP Headers are additional instructions sent by a server along with its response, telling the browser **how to handle and display content**, what is allowed, and what is blocked. They play a vital role in improving security, preventing attacks, and controlling the behavior of web pages.

---

##  What are HTTP Headers?
HTTP Headers:
- Define **how pages should load** and behave.
- Control **permissions** and restrictions.
- Protect against attacks such as XSS, Clickjacking, and data leaks.

Example:  
If multiple websites share the same IP address, the `Host` header tells the server exactly which website is being requested.

---

##  How to Check HTTP Headers

### 1️⃣ Using Browser Developer Tools
1. Open your target website in a browser.
2. Press **CTRL+Shift+I** → Go to **Network tab**.
3. Reload the page, click on a request, and view the **Headers** section.

### 2️⃣ Using Command-Line Tools
```bash
# Using Nmap
nmap -p 80 --script http-headers testphp.vulnweb.com
````

### 3️⃣ Using Online Tools

* [Mozilla Observatory](https://observatory.mozilla.org/)
* [SecurityHeaders.com](https://securityheaders.com/)

These tools show **missing security headers** and provide a **security score** from A+ to F.

---

## Risks of Missing Security Headers

### 1. Missing **Content-Security-Policy (CSP)**

* **Risk:** Allows malicious script injection (XSS).
* **Example:** Injecting payloads on vulnerable sites without CSP.
* **Fix:**

```bash
Content-Security-Policy: default-src 'self';
```

### 2. Missing **X-Frame-Options**

* **Risk:** Clickjacking attacks using invisible overlays.
* **Fix:**

```bash
X-Frame-Options: DENY
```

### 3. Missing **X-Content-Type-Options**

* **Risk:** MIME type sniffing leading to executable file attacks.
* **Fix:**

```bash
X-Content-Type-Options: nosniff
```

### 4. Missing **Strict-Transport-Security (HSTS)**

* **Risk:** SSL stripping, MITM attacks.
* **Fix:**

```bash
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

### 5. Missing **Referrer-Policy**

* **Risk:** Sensitive data leaks in the HTTP `Referer` header.
* **Fix:**

```bash
Referrer-Policy: strict-origin-when-cross-origin
```

---

##  Preventing HTTP Header Attacks

| Problem                 | Fix                                                                 |
| ----------------------- | ------------------------------------------------------------------- |
| Clickjacking            | `X-Frame-Options: DENY` or `frame-ancestors 'none'` in CSP          |
| SSL Stripping           | Enable HSTS and HTTPS everywhere                                    |
| MIME Type Spoofing      | `X-Content-Type-Options: nosniff`                                   |
| Data Leak via Referrer  | `Referrer-Policy: no-referrer` or `strict-origin-when-cross-origin` |
| XSS & Content Injection | Strong CSP + avoid inline JavaScript                                |
| Server Info Disclosure  | Remove/modify `Server` and `X-Powered-By` headers                   |

---

##  Conclusion

HTTP Security Headers act as the **first line of defense** against many common web attacks.
Properly configured headers:

* Enforce HTTPS connections.
* Prevent unauthorized framing of pages.
* Stop MIME sniffing attacks.
* Protect against data leaks.
* Reduce XSS and injection risks.

When implemented carefully, they **significantly improve web application security** without breaking site functionality.

---

[## References](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)
---

