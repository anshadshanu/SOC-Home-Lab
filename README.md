# SOC Home Lab
## SIEM Monitoring & Attack Detection

![VMware](https://img.shields.io/badge/Platform-VMware-blue)
![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)
![Difficulty](https://img.shields.io/badge/Level-Intermediate-yellow)

---

## Project Overview

This project demonstrates the creation of a Security Operations Center (SOC) 
home lab environment to simulate real-world cyber attacks and detect malicious 
activity using a SIEM platform.

The lab consists of an attacker machine running Kali Linux and a target machine 
running Windows Server 2022, both connected through a virtualized network inside 
VMware Workstation Pro 17. Splunk Enterprise was configured to collect and analyze 
Windows security logs in real time.

---

## Lab Architecture

| Component | System | IP Address | Role |
|-----------|--------|------------|------|
| Attacker | Kali Linux 2025.2 | 192.168.52.x | Simulate cyber attacks |
| Target | Windows Server 2022 | 192.168.52.136 | Generate security logs |
| SIEM | Splunk Enterprise 10.0.1 | 127.0.0.1:8000 | Log monitoring & analysis |
| Virtualization | VMware Workstation Pro 17 | Host Machine | Run virtual machines |

---

## Lab Flow
```
Kali Linux → Attack Simulation → Windows Server 2022 → Splunk SIEM → Log Investigation
```

---

## Attacks Simulated

| Attack | Tool | Command | MITRE ATT&CK |
|--------|------|---------|--------------|
| Network Scanning | Nmap | nmap -sV 192.168.52.136 | T1046 |
| Brute Force Login | Hydra | hydra -l administrator -P rockyou.txt 192.168.52.136 smb | T1110 |

---

## Detection Results

| Finding | Evidence | MITRE ATT&CK |
|---------|----------|--------------|
| Network Reconnaissance | Open ports 5357 and 5985 identified | T1046 |
| Brute Force Attack | 15 EventCode=4625 failed login events in Splunk | T1110 |
| SMB Service Targeted | Hydra attack on SMB port 445 | T1021.002 |

---

## Windows Event IDs Used

| Event ID | Name | Description |
|----------|------|-------------|
| 4624 | Successful Logon | User successfully logged on |
| 4625 | Failed Logon | Failed login – brute force indicator |
| 4688 | Process Creation | New process created |
| 4672 | Special Privileges | Privilege escalation indicator |

---

## Skills Demonstrated

- Building and configuring a virtualized SOC lab using VMware
- Installing and configuring Splunk SIEM for Windows log collection
- Simulating cyber attacks using Kali Linux tools (Nmap, Hydra)
- Detecting attacks using Splunk search queries and Windows Event IDs
- Mapping attack techniques to the MITRE ATT&CK framework
- Documenting findings in a professional SOC investigation report

---

## Tools Used

| Tool | Version | Purpose |
|------|---------|---------|
| VMware Workstation Pro | 17 | Virtual machine environment |
| Kali Linux | 2025.2 | Attacker machine |
| Windows Server 2022 | Build 20348 | Target machine |
| Splunk Enterprise | 10.0.1 | SIEM platform |
| Nmap | 7.95 | Network scanning |
| Hydra | 9.5 | Brute force simulation |

---

## Splunk Queries Used
```
index=main
index=main EventCode=4625
index=main EventCode=4624
```

---

## Project Report

Full investigation report with screenshots is available in this repository.

---

## Author

**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)
[GitHub](https://github.com/anshadshanu)
