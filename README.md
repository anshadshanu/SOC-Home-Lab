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

## Lab Flow
```
Kali Linux → Attack Simulation → Windows Server 2022 → Splunk SIEM → Log Investigation
```

---

## Screenshots

### Network Connectivity Test
![Ping Test](screenshots/4.%20ping_test.png)
*Successful ping from Kali Linux to Windows Server 2022 confirming lab network is working.*

---

### Splunk SIEM Dashboard
![Splunk Dashboard](screenshots/5.%20splunk_dashboard.png)
*Splunk Enterprise dashboard configured to collect and monitor Windows Security logs in real time.*

---

### Attack Simulation – Nmap Network Scan
![Nmap Attack](screenshots/8.%20attack_nmap_scan.png)
*Nmap scan from Kali Linux identifying open ports on Windows Server 2022 – MITRE ATT&CK T1046.*

---

### Attack Simulation – Hydra Brute Force
![Brute Force](screenshots/9.%20attack_brute_force.png)
*Hydra brute force attack targeting SMB port 445 generating failed login events – MITRE ATT&CK T1110.*

---

### Investigation Results – Attack Detected in Splunk
![Investigation](screenshots/10.%20investigation_results.png)
*Splunk detecting 15 EventCode=4625 Failed Logon events from the Hydra brute force attack.*

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
