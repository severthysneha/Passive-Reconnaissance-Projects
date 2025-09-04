##DNS Enumeration
**This folder contains DNS enumeration work using Whois, Censys and Maltego.
##Tools Used
Whois → Domain details, Registrar info, Name servers, Registrant/technical contact info.
Censys → host, service, software, port, ASN, location, and technology fingerprinting data, IP addresses of the discovered hosts along with metadata.
🔹 Screenshots
📌 Maltego Graph:
(./screenshots/MALTEGOGRAPH.png)
 📌 Observations:
 1.The domain openai.com is registered with MarkMonitor Inc., a well-known registrar for large organizations.
 2.The domain has been active since 2007 and is renewed until 2029 → shows long-term ownership.
 3.DNS servers are hosted on Azure DNS → indicates Microsoft cloud infrastructure usage.
4.Domain status is set to client/server delete/transfer/update prohibited → strong protections enabled at the registrar level.
5.DNSSEC is not enabled → this could leave the domain vulnerable to DNS spoofing.
 6.Publicly visible WHOIS contact details are protected (emails hidden behind MarkMonitor’s web form).
 7.From Censys search, infrastructure/services linked to the domain were found, useful for attacker mapping.
 📌 Attack:
 1.Identify the DNS provider and try targeted social engineering.
 2.Track domain expiry for potential hijacking.
 3.Map infrastructure (Azure DNS in this case) for further reconnaissance.
 **Note: This was gathered using only passive reconnaissance techniques (WHOIS lookups & Censys search).
 📌 Exploit:
 **Possible exploitation paths (theoretical, not performed here):
 1.DNS Hijacking → If attackers compromise registrar or DNS account.
 2.Phishing / Spoofing → Using domain similarity or misconfigured subdomains.
 3.Domain Takeover → If domain renewal is missed.
 📌 Mitigation
 1.Enable DNSSEC to prevent DNS spoofing.
