##E-mail Analysis **This folder contains E-mail Analysis for E-mail spoofing. ##Tools Used MXToolbox.com → delivery information, SPF and DKIM information and relay information.
📌Maltego Graph: (./screenshots/MALTEGOGRAPH2.PNG)
📌E-mail: (E-mail.jpg) 
📌Observations: 1.Email headers showed SPF, DKIM, DMARC passed, but this only proves the email came from an authorized server, not that it was legitimate.
2.The Message-ID belonged to the fraudster’s server.
3.The domain used was a lookalike hosted on Hostinger.
4.WHOIS checks revealed several suspicious domains (e.g., hclteam.com, hcltec.com, hcltech.ai) that are not owned by HCL but mimic the brand.
5.Even when authentication checks (SPF/DKIM/DMARC) pass, a scam email can still be delivered if the domain itself is fraudulent but well-configured. Scammers increasingly use cheap providers (like Hostinger) to host lookalike domains and bypass filters.
6.Domain has DMARC but policy is set to p=none (monitoring only, no enforcement). This allows spoofing attempts to pass without being blocked.
7.Domain Legitimacy: The domain hclteams.com is not the official HCL domain (hcl.com / hcltech.com), indicating potential abuse for impersonation.
📌Attack:
1.Phishing/Job Scam Email impersonating HCL Technologies.
2.Uses a lookalike domain (hclteams.com) instead of the legitimate (hcl.com / hcltech.com).
3.Social engineering tactics include urgency (“last date to apply”) and authority (fake HCL branding).
📌Exploit:
1.SPF & DKIM correctly configured for hclteams.com, giving the email legitimacy even though the domain itself is malicious.
2.DMARC policy set to p=none → no enforcement, allowing spoofed/abusive emails to pass through.
3.Victim tricked into:
->Paying money via bank transfer.
->Sharing sensitive personal documents (ID, address, qualifications).
📌Mitigation:
1.Technical Controls:
->Domain owners should set DMARC to reject or quarantine to prevent abuse.
->Security teams must monitor lookalike domains (typosquatting) and take them down.
->Email providers should flag suspicious recruitment emails that request payments.
2.User Awareness
->Legitimate companies like HCL never charge candidates for recruitment or training.
->Always verify sender’s domain (@hcltech.com, not @hclteams.com).
->Cross-check job postings on official careers websites before responding.
