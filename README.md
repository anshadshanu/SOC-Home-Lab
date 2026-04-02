# SOC Home Lab – SIEM Monitoring & Attack Detection

![VMware](https://img.shields.io/badge/Platform-VMware-blue)
![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

---

## Project Overview

This project demonstrates the creation of a Security Operations Center (SOC) 
home lab environment to simulate real-world cyber attacks and detect malicious 
activity using a SIEM platform.

---

## Lab Architecture

| Component | System | IP Address | Role |
|-----------|--------|------------|------|
| Attacker | Kali Linux 2025.2 | 192.168.52.x | Simulate cyber attacks |
| Target | Windows Server 2022 | 192.168.52.136 | Generate security logs |
| SIEM | Splunk Enterprise 10.0.1 | 127.0.0.1:8000 | Log monitoring & analysis |
| Virtualization | VMware Workstation Pro 17 | Host Machine | Run virtual machines |

---

## Lab Setup

### VMware Workstation – Lab Environment
![VMware Lab](screenshots/1_vmware_lab.png)
*VMware Workstation Pro 17 showing both Kali Linux and Windows Server 2022 virtual machines running simultaneously.*

---

### Kali Linux – Attacker Machine
![Kali Linux](screenshots/2_kali_machine.png)
*Kali Linux 2025.2 configured as the attacker machine used to simulate cyber attacks against the target system.*

---

### Windows Server 2022 – Target Machine
![Windows Server](screenshots/3_windows_server.png)
*Windows Server 2022 configured as the target machine that generates Windows Security Event logs.*

---

### Network Connectivity Test
![Ping Test](screenshots/4_ping_test.png)
*Successful ping from Kali Linux to Windows Server 2022 (192.168.52.136) confirming network connectivity between both machines.*

---

### Splunk SIEM Dashboard
![Splunk Dashboard](screenshots/5_splunk_dashboard.png)
*Splunk Enterprise 10.0.1 dashboard running on Windows Server 2022 at http://localhost:8000 used for real-time log monitoring.*

---

### Windows Log Collection – Success
![Log Collection](screenshots/6_splunk_log_collection.png)
*Splunk confirming successful creation of Windows local event log data input including Security, System and Application logs.*

---

### Splunk Logs Verified
![Logs Verified](screenshots/7_splunk_logs_verified.png)
*Splunk search results confirming Windows Security and Application logs are being collected and indexed in real time.*

---

### Attack Simulation – Nmap Network Scan
![Nmap Attack](screenshots/8_attack_nmap_scan.png)
*Nmap service version scan from Kali Linux identifying open ports 5357 and 5985 on Windows Server 2022 – MITRE ATT&CK T1046.*

---

### Attack Simulation – Hydra Brute Force
![Brute Force](screenshots/9_attack_brute_force.png)
*Hydra brute force attack from Kali Linux targeting SMB port 445 on Windows Server 2022 generating failed login events – MITRE ATT&CK T1110.*

---

### Investigation Results – Attack Detected in Splunk
![Investigation](screenshots/10_investigation_results.png)
*Splunk search showing 15 EventCode=4625 (Failed Logon) events detected from the Hydra brute force attack confirming successful SIEM detection.*

---

## Attacks Simulated

| Attack | Tool | MITRE ATT&CK |
|--------|------|--------------|
| Network Scanning | Nmap | T1046 |
| Brute Force Login | Hydra | T1110 |
| SMB Service Attack | Hydra | T1021.002 |

---

## Splunk Queries Used
```
index=main
index=main EventCode=4624
index=main EventCode=4625
index=main EventCode=4688
```

---

## Windows Event IDs

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

## Author

**Muhammed Anshad**  
Certified SOC Analyst (CSA) – EC-Council  
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)  
[GitHub](https://github.com/anshadshanu)
