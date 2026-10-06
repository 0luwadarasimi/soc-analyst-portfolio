# SOC Analyst Portfolio

**Oluwadarasimi** | Aspiring SOC Analyst | Blue Team | Threat Detection & Incident Response

---

## About Me

Aspiring Security Operations Center (SOC) Analyst focused on threat detection, log analysis, and incident response. I build practical defensive skills through hands-on home labs, honeypot deployments, SIEM analysis, and structured investigation workflows.

This portfolio documents real lab work I have completed — from setting up isolated attack environments to writing detections, reconstructing timelines, extracting IOCs, and performing access reviews.

**Goal:** Secure a Junior / Tier-1 SOC Analyst role where I can contribute to alert triage, investigation, and continuous improvement of detection capabilities.

---

## Skills

| Category              | Skills Demonstrated                                      |
|-----------------------|----------------------------------------------------------|
| **SIEM & Detection**  | Splunk (SPL), log ingestion, dashboard creation, basic correlation |
| **Log Analysis**      | Cowrie honeypot logs, authentication events, command execution |
| **Incident Response** | Timeline reconstruction, IOC extraction, documentation  |
| **Phishing Analysis** | Sender verification, URL inspection, social engineering indicators |
| **Access Control**    | Linux IAM, least privilege auditing, group membership reviews |
| **Networking / Lab**  | VirtualBox networking, Nmap, Wireshark, SSH honeypots   |
| **Frameworks**        | MITRE ATT&CK mapping (in progress)                       |

---

## Featured Projects

| # | Project | Focus | Key Skills | Status |
|---|---------|-------|------------|--------|
| 1 | [Honeypot Lab](./project-1-honeypot-lab) | Network attack detection & reporting | Cowrie, Nmap, Wireshark, lab networking | Completed |
| 2 | [Phishing Analysis](./project-2-phishing-analysis) | Email & SMS phishing investigation | Red flag identification, domain verification, social engineering | Completed |
| 3 | [Splunk SIEM](./project-3-splunk-siem) | SIEM detections on honeypot logs | Splunk Enterprise, SPL queries, dashboards | Completed |
| 4 | [Incident Investigation](./project-4-incident-investigation) | Full investigation workflow | Timeline, IOCs, documentation | Completed |
| 5 | [IAM Access Review](./project-5-iam-access-review) | Least privilege audit | Linux permissions, access reviews, remediation | Completed |

---

## Project Highlights

### 1. Network Attack Detection — Honeypot Lab
Deployed an isolated VirtualBox lab with Kali (attacker) and Ubuntu + Cowrie SSH honeypot (target). Performed reconnaissance with Nmap, captured traffic with Wireshark, and documented the attack path.

### 2. Phishing Email Investigation
Analyzed multiple phishing scenarios (fake document shares, prize scams, 2FA bypass attempts, spoofed security alerts). Documented red flags including domain spoofing, urgency tactics, and social engineering techniques.

### 3. Splunk SIEM on Cowrie Logs
Ingested Cowrie honeypot logs into Splunk, built dashboards for login success/failure and attacker command execution using SPL.

### 4. Incident Investigation
Reconstructed a complete attack timeline from honeypot session logs: successful login with weak credentials → reconnaissance commands → payload download attempt → session close. Extracted and documented IOCs.

### 5. IAM Access Review (Least Privilege)
Simulated a company environment with departmental groups. Planted and then discovered an over-privileged user, proved impact by reading confidential data, remediated the issue, and verified the fix.

---

## Tools & Technologies

- **SIEM:** Splunk Enterprise
- **Honeypot:** Cowrie
- **Analysis:** Wireshark, Nmap
- **OS:** Kali Linux, Ubuntu Server
- **Virtualization:** VirtualBox
- **Other:** Linux user/group management, SPL

---

## Next Steps / Roadmap

- Expand phishing project with full email header analysis and threat intel lookups
- Write additional Splunk correlation searches and alerts
- Add MITRE ATT&CK mappings to all investigation write-ups
- Complete more advanced labs (Sysmon, network forensics, threat hunting)
- Publish detailed incident reports with evidence screenshots

---

## Contact

- **GitHub:** [0luwadarasimi](https://github.com/0luwadarasimi)
- **LinkedIn:** [Oluwadarasimi Silas](https://www.linkedin.com/in/oluwadarasimi-silas-10702835b/)
- **Email:** [ogunbowalesilas@gmail.com](mailto:ogunbowalesilas@gmail.com)

---

*All labs and data in this repository are synthetic and created in controlled home-lab environments for learning purposes.*
