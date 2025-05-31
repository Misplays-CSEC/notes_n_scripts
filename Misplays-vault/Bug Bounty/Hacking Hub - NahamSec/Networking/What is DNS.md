---
tags:
  - Networking
  - ipaddress
  - network_basics
  - NahamSec
  - cybersecurity
---
## Topic: Understanding IP Addresses  

---

### Cues / Questions

- What is an IP address?  
- What are the types of IP addresses?  
- How do public and private IPs differ?  
- How do devices communicate locally?  
- What role do MAC addresses and ARP play?  
- How do devices communicate across the internet?  
- What is DHCP and what does it assign?

---

### Notes

- **Definition of IP Address**  
  - Used to identify and communicate with other devices  
  - Two main versions: IPv4 (covered here) and IPv6  
  - IPv4 format: Four decimal blocks (0–255), e.g. `192.168.1.1`

- **Types of IP Addresses**  
  - **Private IPs** (used within local networks)  
    - Not routable over the public internet  
    - Reserved ranges:
      - `192.168.0.0 – 192.168.255.255` (65,536 addresses)  
      - `172.16.0.0 – 172.31.255.255` (1,048,576 addresses)  
      - `10.0.0.0 – 10.255.255.255` (16,777,216 addresses)  
    - Common in home networks (e.g., routers often use `192.168.1.1`)
  
  - **Public IPs** (assigned by ISPs)  
    - Routable over the internet  
    - Used by websites, routers, and internet-facing services

- **Local Communication**  
  - Devices use **MAC addresses** (unique hardware IDs)  
    - First 3 blocks = manufacturer, last 3 = unique identifier  
  - **ARP (Address Resolution Protocol)**  
    - Resolves IP → MAC address  
    - Device broadcasts ARP request  
    - Target replies with MAC  
    - Stored in ARP cache for future use

- **Remote/Internet Communication**  
  - Devices use a **default gateway** (usually router)  
  - Router performs **NAT (Network Address Translation)**  
    - Public IP of router receives responses from internet  
    - Forwards responses to correct device inside network  
  - **Subnet masks** help determine if an IP is local or remote  

- **DHCP (Dynamic Host Configuration Protocol)**  
  - Automatically assigns network settings:  
    - IP address  
    - Subnet mask  
    - Default gateway  
    - DNS server  

---

### Summary  
IP addresses allow devices to communicate on both local and remote networks. Private IPs are used within local networks, while public IPs are used to communicate over the internet. MAC addresses and ARP help devices find each other locally. Routers, through NAT, handle external communication. DHCP simplifies device setup by automatically providing necessary network details.

![[Icons and Title Slides II_1.png]]
