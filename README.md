# SOC Home Lab – SIEM Monitoring & Attack Detection

## Project Overview
Built a SOC home lab environment to simulate real-world cyber attacks and detect them using Splunk SIEM. The lab includes an attacker machine (Kali Linux) and a target machine (Windows Server 2022) connected in a virtualized network.

## Tools Used
| Tool | Purpose |
|------|---------|
| VMware Workstation Pro 17 | Virtualization platform |
| Kali Linux 2025.2 | Attacker machine |
| Windows Server 2022 | Target/victim machine |
| Splunk Enterprise 10.0.1 | SIEM – log collection & analysis |
| Nmap 7.95 | Network scanning attack |
| Hydra 9.5 | Brute force login attack |

## Attacks Simulated
- Network Scanning using Nmap – MITRE ATT&CK T1046
- Brute Force Login using Hydra – MITRE ATT&CK T1110

## Detection Results
- 15 failed login events (EventCode=4625) detected in Splunk
- Network scan activity identified from attacker machine

## Lab Architecture
Kali Linux → Attack Simulation → Windows Server 2022 → Splunk SIEM → Investigation

## Author
**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
