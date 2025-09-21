This folder contains DNS record enumeration using *nslookup* (Linux + nslookup.io) and *dig* (Linux + digtool online).  
All work is *passive reconnaissance only* no active exploitation was performed.
---
## Tools / Commands Used:
  - nslookup (Linux)
  - nslookup -type=MX <domain>  
  - nslookup -type=TXT <domain>  
  - nslookup -type=A <domain>  
  - nslookup.io (online) — collected: A, AAAA, TXT, SPF, Other TXT, NS, MX, SOA  
  - dig (Linux)  
  - dig ANY <domain> +noall +answer  
  - dig axfr @<nameserver> <domain> (zone transfer test)  
  - digtool (online)** — collected: A, MX, NS, SOA, TXT
---
📌Observations (example summary)
- A / AAAA records → show IP addresses for the domain and subdomains (hosts).  
- MX records → mail servers responsible for email delivery.  
- NS records → authoritative name servers (where DNS is hosted).  
- SOA record → administrative details, serial number, refresh/expiry times.  
- TXT / SPF / Other TXT → SPF and other policies present (check for properly configured SPF/DKIM/DMARC).  
- Online tools (nslookup.io, digtool) confirmed Linux outputs and provided extra TXT/SPF details.
---
📌Attack (information an attacker could gather)
- Discover mail servers (MX) to target phishing or SMTP-based attacks.  
- Enumerate subdomain IPs (A/AAAA) to find exposed services.  
- Identify authoritative NS and SOA info to map DNS infrastructure and maintenance windows.  
- Weak or missing SPF/DKIM/DMARC entries increase success of email spoofing.
---
📌Exploit (theoretical(not performed))
- Email spoofing / phishing if SPF/DKIM/DMARC misconfigured.  
- Service targeting on discovered IPs (scanning for vulnerable services).  
- Zone transfer (AXFR) disclosure (if a nameserver allows AXFR, an attacker can obtain the full DNS zone) (all records and subdomains).
---
📌Mitigation
- Implement and enforce SPF, DKIM, DMARC for email protection.  
- Restrict zone transfers (AXFR) to authorized management IPs only.  
- Regularly audit A/AAAA/MX/NS/TXT records and remove unused entries.  
- Monitor DNS changes and SOA serial for unexpected updates.  
- Use DNSSEC where applicable to protect against spoofing.






