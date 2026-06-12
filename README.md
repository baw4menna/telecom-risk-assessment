# Telecom Critical Infrastructure Risk Assessment



> ⚠️ **Note:** All scanning was performed with explicit written permission from the target organization as part of an authorized security assessment. Client identity has been anonymized for confidentiality.



## Client

A major telecommunications operator (anonymized for confidentiality)



## My Role

**Technical Risk Assessment** – External port scanning, vulnerability identification, MITRE ATT&CK mapping.



## Methodology

- External port scanning using Nmap on authorized public-facing IP ranges

- TCP SYN scan with version detection (`-sS -sV -Pn --top-ports 20`)

- UDP scan for DNS, DHCP, NTP, SNMP services (`-sU -p 53,67,68,123,161`)



## Key Findings



| Port | Service | Risk Level | MITRE ATT\&CK Technique |
|------|---------|------------|------------------------|
| 21/tcp | FTP | HIGH | T1110, T1078 |
| 53/udp | DNS | HIGH | T1071.004 |
| 123/udp | NTP | MEDIUM | T1498 |
| 161/udp | SNMP | MEDIUM | T1046 |


## Analysis Summary

- **FTP (Port 21):** Plaintext protocol – credentials vulnerable to interception

- **DNS (Port 53):** Open resolver – potential for DNS amplification attacks

- **NTP (Port 123):** Potential vector for DDoS amplification

- **SNMP (Port 161):** Information disclosure risk for network mapping



## Files

- `/reports/` – Full risk assessment report (anonymized)



## Tools Used

- Nmap

- MITRE ATT\&CK Framework
