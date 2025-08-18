# Directory Brute-Frocing Task 5

**Date:** 18 August 2025  
**Internship Program:** Cybersecurity Internship – UJAR TECH  

---

1. **What is a Web Directory?**  
   - Explanation of hierarchical web structures and their role in organizing content.  
   - Difference between directories and search engines .  

2. **What is Directory Brute-forcing?**  
   - Systematic discovery of hidden or unlinked files and folders on a web server.  
   - Purpose: identify sensitive or misconfigured resources.  

3. **How Does the Code Work?**  
   - Tools like Gobuster, Dirb, and FFuF use wordlists and HTTP response codes (200, 403, 404) to identify valid directories .  
   - Use of multi-threading and filters for efficiency.  

4. **What is Gobuster?**  
   - Fast brute-forcing tool for directories, files, DNS, and virtual hosts.  
   - Written in Go; very fast but “loud” and easily detectable by IDS.  
   - Requires manual rerun for recursion.  

5. **Gobuster vs DIRB**  
   - **Gobuster** → Faster, supports DNS/VHosts, best for quick large-scale scans.  
   - **DIRB** → Slower but supports recursive scanning (-r flag), better for deeper exploration.  

6. **How to Install Gobuster?**  
   - Installation via:  

     ```bash
     sudo apt install gobuster
     ```

7. **Wordlists (SecLists)**  
   - Use of SecLists as the primary wordlist for directory brute-forcing.  
   - Importance of selecting appropriate or custom wordlists depending on the target.  

8. **How to Use Gobuster?**  
   - `dir` mode for enumerating URLs of directories and files.  
   - Command example:  
     ```bash

     gobuster dir -u <url> -w <wordlist.txt> -x <file_extensions>
     
     ```
   - Practical demo using Apache server and medium wordlist from SecLists.  
   - Found files with different status codes (403, 301, 200).  

---

[##  References](https://github.com/sarojdsoka/Cybersecurity-Internship-UJAR/blob/main/REFERENCES.md)  
 
---
