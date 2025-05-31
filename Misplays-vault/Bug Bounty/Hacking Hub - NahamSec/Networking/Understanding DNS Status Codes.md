---
tags:
  - dns
  - Networking
---
## Topic: Understanding DNS Status Codes  

---

### Cues / Questions
- What does NOERROR mean in DNS?
- When do you get an NXDOMAIN error?
- What causes a SERVFAIL status?
- Why would a DNS query be REFUSED?
- What are the differences among DNS status codes?

---

### Notes

- **DNS (Domain Name System)**  
  - Translates domain names (e.g., `example.com`) into IP addresses  
  - DNS status codes inform you of the result of a DNS query  

- **NOERROR (No Error)**  
  - Query completed successfully  
  - Requested record found and returned  
  - Example: `A record` for a valid domain returns an IP address  

- **NXDOMAIN (Non-Existent Domain)**  
  - The domain name queried does not exist  
  - Common causes:
    - Typos in the domain  
    - Domain has been deleted or never existed  

- **SERVFAIL (Server Failure)**  
  - DNS server couldn’t complete the query due to internal error  
  - Possible causes:
    - Timeout
    - Misconfiguration
    - Failure to query upstream servers  
  - Indicates uncertainty — server couldn’t process the request reliably

- **REFUSED (Query Refused)**  
  - DNS server refuses to answer the query  
  - Typically due to:
    - Security policies
    - Query restrictions
    - Unauthorized access attempt  
  - Response means server is unwilling to respond, not that domain doesn't exist

---

### Summary  
DNS status codes help identify the result of a domain lookup. **NOERROR** means success, **NXDOMAIN** means the domain doesn't exist, **SERVFAIL** indicates a problem with the server, and **REFUSED** means the query was rejected—usually for policy or access reasons.
