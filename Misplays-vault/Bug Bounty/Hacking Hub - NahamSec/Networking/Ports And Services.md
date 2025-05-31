---
tags: #networking #services #ports #study_notes
---
## Topic: What is a Service and a Port?  


---

### Cues / Questions

- What is a service in networking?  
- What are some examples of services?  
- What is a port?  
- How are IP addresses and ports related?  
- What are some common port numbers and their associated services?

---

### Notes

- **What is a Service?**  
  - A service is a computer program that:
    - Accepts connections  
    - Sends and receives specific data  
  - Examples of internet services:
    - **Web servers** – Host websites (HTTP/HTTPS)  
    - **Mail servers** – Send/receive emails (SMTP/POP3/IMAP)  
    - **FTP/SFTP** – Transfer files  
    - **SSH/Telnet** – Remote terminal access

- **What is a Port?**  
  - A port is a number used to identify a specific service on a device  
  - Works with IP addresses:
    - IP = the address of the building  
    - Port = the apartment number  
  - Port numbers range from **1 to 65535**  
    - Applications can bind to any of them  
    - Some ports are **commonly used** for specific services

- **Common Port Numbers**  
  - **21** – FTP  
  - **22** – SSH  
  - **23** – Telnet  
  - **25** – SMTP (email sending)  
  - **80** – HTTP (web traffic)  
  - **110** – POP3 (email receiving)

- More port numbers listed here:  
  - [Wikipedia - TCP/UDP Ports](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers)

- Future topic preview:  
  - How to **scan an IP address** to find open ports and identify listening services

---

### Summary  
Services are programs that handle connections and data over a network. Each runs on a specific port, which works in combination with the device's IP address to direct traffic to the correct application. Common ports like 80 for HTTP and 22 for SSH help standardize communication. Ports range from 1–65535, and discovering which are open helps identify active services on a system.
![[Icons and Title Slides II-11.png]]
