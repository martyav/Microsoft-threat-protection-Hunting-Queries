# IcedId Email Delivery

Use this query to locate emails and malicious downloads related to the IcedId activity that can lead to ransomware

## Query
```
EmailUrlInfo 
| where Url matches regex @"\bsites\.google\.com\/view\/(?:id)?\d{9,}\b" 
| join EmailEvents on NetworkMessageId // Note: Replace the following subject lines with the one generated by your website's Contact submission form if no results return initially 
| where Subject has_any('Contact Us', 'New Submission', 'Contact Form', 'Form submission')

```
## Category
This query can be used to detect the following attack techniques and tactics ([see MITRE ATT&CK framework](https://attack.mitre.org/)) or security configuration states.
| Technique, tactic, or state | Covered? (v=yes) | Notes |
|------------------------|----------|-------|
| Initial access | V |  |
| Execution |  |  |
| Persistence |  |  | 
| Privilege escalation |  |  |
| Defense evasion |  |  | 
| Credential Access |  |  | 
| Discovery |  |  | 
| Lateral movement |  |  | 
| Collection |  |  | 
| Command and control |  |  | 
| Exfiltration |  |  | 
| Impact |  |  |
| Vulnerability |  |  |
| Exploit |  |  |
| Misconfiguration |  |  |
| Malware, component |  |  |
| Ransomware |V |  |


## Contributor info
**Contributor:** Microsoft 365 Defender
