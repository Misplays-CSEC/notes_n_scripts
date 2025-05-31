---
date: 2025-05-07 16:23
tags:
  - redTeam
author: Tryhackme
source:
---

# Source Notes

## Metadata

- **Date/Time**: 2025-05-07 16:23
- **Author**: TryHackMe
- **Source**: https://tryhackme.com/room/nmap04
- **Tags**: [[Red Team]], [[Nmap]]

---
## Service Detection

**Option to use:** -sV  
**Example:** nmap -sV {target}

- **Purpose of Service Detection**:
    
    - After discovering open ports, probing them helps identify running services and potential vulnerabilities.
        
    - Understanding service versions aids in vulnerability research.
        
- **Using `-sV` in Nmap**:
    
    - Enables service and version detection on open ports.
        
    - Requires a **full TCP 3-way handshake**, meaning it’s **not stealthy** (unlike `-sS`).
        
    - Adds a **version column** to output, showing detailed banner info.
        
- **Controlling Intensity**:
    
    - Use `--version-intensity LEVEL` (range: 0–9).
        
        - `--version-light` → Level 2.
            
        - `--version-all` → Level 9.
            
- **Example Output Difference**:
    
    - Without `-sV`: `22/tcp open ssh`
        
    - With `-sV`: `22/tcp open ssh OpenSSH 6.7p1 Debian 5+deb8u8 (protocol 2.0)`
        
    - The **service column** is often guessed; the **version column** is from real interaction.
        
- **Sample Command**:
    
    bash
    
    Copy code
    
    `sudo nmap -sV 10.10.35.188`
    
- **Permissions Note**:
    
    - Some Nmap options (like `-sV`) require root; use `sudo` when running.
        
- **Want to Go Deeper?**
    
    - Explore service vulnerability discovery in **"Vulnerabilities 101"**.

**Run** `nmap -sV --version-light {target}`via the AttackBox. What is the detected version for port 143?

**Answer:** Dovecot imapd

Which service did not have a version detected with --version-light?

**Answer:** rpcbind

---
## OS Detection and Traceroute

- **Enable OS detection** using the `-O` (uppercase letter "O") flag:
    
    `sudo nmap -sS -O 10.10.35.188`
    
- Nmap analyzes network behavior and responses to guess the OS and kernel version.
    
    - Example: Detected Linux 3.X, guessed Linux 3.13.
        
- **Requirements for accurate OS detection**:
    
    - At least **one open and one closed port**.
        
    - Can be affected by virtualization, proxies, or fingerprint obfuscation.
        
- **Accuracy Caveat**:
    
    - Detected OS may be correct, but kernel version can be off.
        
    - Example: A system running kernel 5.13.14 was misidentified as Linux 2.6.X.
        
---

### 🌐 Traceroute with Nmap

- Use `--traceroute` to identify the path (hops/routers) to the target:
    
    bash
    
    Copy code
    
    `sudo nmap -sS --traceroute 10.10.35.188`
    
- **Nmap traceroute method**:
    
    - Starts with **high TTL** and decreases.
        
    - Different from `traceroute` (Linux/macOS) or `tracert` (Windows), which increase TTL.
        
- **Example Result**:
    
    - Only 1 hop → Direct connection to target.
        
- **Limitation**:
    
    - Some routers block ICMP TTL-exceeded responses, hiding their IPs.

---
## Nmap Scripting Engine (NSE)

- 
---
## Saving the Output

---
## Summary
