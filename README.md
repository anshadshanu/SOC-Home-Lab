# SOC Home Lab – SIEM Monitoring & Attack Detection

![VMware](https://img.shields.io/badge/Platform-VMware-blue)
![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Kali](https://img.shields.io/badge/Attacker-Kali%20Linux-red)
![Status](https://img.shields.io/badge/Status-Completed-green)

---

## Project Overview

This project demonstrates building a Security Operations Center (SOC) home lab 
to simulate real-world cyber attacks and detect them using Splunk SIEM. 
The lab replicates the core workflow of a SOC analyst — monitoring Windows 
security logs, detecting suspicious activity, and investigating threats.

---

## Lab Architecture

| Component | System | IP Address | Role |
|-----------|--------|------------|------|
| Attacker | Kali Linux 2025.2 | 192.168.52.x | Simulate attacks |
| Target | Windows Server 2022 | 192.168.52.136 | Generate security logs |
| SIEM | Splunk Enterprise 10.0.1 | 127.0.0.1:8000 | Log monitoring |
| Virtualization | VMware Workstation Pro 17 | Host Machine | Run VMs |

---

## Lab Flow
```
Kali Linux → Attack Simulation → Windows Server 2022 → Splunk SIEM → Investigation
```

---

## Screenshots

### Network Connectivity Test
![Ping Test](screenshots/4.%20ping_test.png)
*Network connectivity between Kali Linux and Windows Server 2022 verified using ping before beginning attack simulation.*

---

### Splunk SIEM Dashboard
![Splunk Dashboard](screenshots/5.%20splunk_dashboard.png)
*Splunk Enterprise configured to collect and monitor Windows Security, System, and Application logs in real time.*

---

### Attack 1 – Network Scan (Nmap)
![Nmap Attack](screenshots/8.%20attack_nmap_scan.png)
*Nmap scan performed from Kali Linux to identify open ports and services on Windows Server — simulating attacker reconnaissance phase (MITRE ATT&CK T1046).*

---

### Attack 2 – Brute Force Login (Hydra)
![Brute Force](screenshots/9.%20attack_brute_force.png)
*Hydra brute force attack targeting SMB port 445 on Windows Server — generating multiple failed login events in security logs (MITRE ATT&CK T1110).*

---

### SOC Investigation – Attack Detected in Splunk
![Investigation](screenshots/10.%20investigation_results.png)
*Splunk search for EventCode=4625 returned 15 failed logon events — confirming the brute force attack was successfully detected by the SIEM.*

---

## Windows Event IDs Investigated

| Event ID | Name | SOC Relevance |
|----------|------|---------------|
| 4624 | Successful Logon | Monitor for unusual login activity |
| 4625 | Failed Logon | Key indicator of brute force attacks |
| 4688 | Process Creation | Detect suspicious process execution |
| 4672 | Special Privileges | Potential privilege escalation |

---

## Attacks Simulated

| Attack | Tool | MITRE ATT&CK |
|--------|------|--------------|
| Network Scanning | Nmap | T1046 – Network Service Discovery |
| Brute Force Login | Hydra | T1110 – Brute Force |
| SMB Service Attack | Hydra | T1021.002 – SMB/Windows Admin Shares |

---

## Splunk Queries Used
```splunk
index=main
index=main EventCode=4624
index=main EventCode=4625
index=main EventCode=4688
```

---

## Tools Used

| Tool | Version | Purpose |
|------|---------|---------|
| VMware Workstation Pro | 17 | Virtual machine environment |
| Kali Linux | 2025.2 | Attacker machine |
| Windows Server 2022 | Build 20348 | Target machine |
| Splunk Enterprise | 10.0.1 | SIEM platform |
| Nmap | 7.95 | Network reconnaissance |
| Hydra | 9.5 | Brute force simulation |

---

## Author

**Muhammed Anshad**
Certified SOC Analyst (CSA) – EC-Council
[LinkedIn](https://www.linkedin.com/in/muhemmed-a501a0)
[GitHub](https://github.com/anshadshanu)
