tags: #BugBounty #Networking #cybersecurity 

## Topic: Understanding IP Addresses  
---

### Cues / Questions

- What is an IP address?  
- What are the types of IP addresses?  
- What is the difference between public and private IPs?  
- How do devices communicate using IPs?  
- What role does ARP play in communication?  
- What happens when devices communicate over the internet?  
- What is DHCP?

---
### Notes

- **What is an IP Address?**  
  - IP = Internet Protocol  
  - Used to locate and communicate with other devices  
  - Two versions: IPv4 and IPv6 (only IPv4 covered here)  
  - Format: Four numbers between 0–255 (e.g. `192.168.1.1`)

- **Types of IP Addresses**  
  - **Private IPs**:  
    - Only accessible within local networks (LANs)  
    - Common ranges:  
      - `192.168.0.0 – 192.168.255.255` → 65,536 devices  
      - `172.16.0.0 – 172.31.255.255` → 1,048,576 devices  
      - `10.0.0.0 – 10.255.255.255` → 16,777,216 devices  
    - Example: Home router often uses `192.168.1.1`  
  - **Public IPs**:  
    - Assigned by ISPs  
    - Used for internet-facing devices  
    - Examples: Web servers, your home router’s external IP

- **Device Communication – Local**  
  - Devices also have a **MAC address** (unique hardware ID)  
  - Format: `44:F2:1B:83:11:7A`  
    - First 3 blocks = manufacturer  
    - Last 3 blocks = unique identifier  
  - **ARP (Address Resolution Protocol)**  
    - Device sends ARP request to learn MAC of another IP  
    - Reply received → stored in ARP Cache  

- **Device Communication – Remote / Internet**  
  - If destination is outside local network → sent to **default gateway** (router)  
  - Router forwards request using **NAT (Network Address Translation)**  
  - Reply returns to **public IP of router**, then forwarded to the device  
  - Device uses a **subnet mask** to determine if an IP is local or remote  
    - (Details of subnetting are beyond this lesson)

- **How Devices Get IPs**  
  - Most home routers use **DHCP** (Dynamic Host Configuration Protocol)  
  - Automatically assigns:
    - IP address  
    - Subnet mask  
    - Default gateway  
    - DNS server address  

---

### Summary  
IP addresses allow devices to communicate across local and global networks. Private IPs are used within LANs, while public IPs connect to the internet. Devices use MAC addresses and ARP for local communication, while NAT and gateways enable communication over the internet. DHCP simplifies network configuration by auto-assigning network settings.

