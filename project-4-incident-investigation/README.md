**Impact:** In the honeypot, nothing real was harmed. On a real server, root access plus a downloaded script would be a serious incident.

---

## Recommendations

1. **Stronger SSH authentication:** use key-based login instead of passwords, and add rate limiting or fail2ban.
2. **Detection:** alert on `wget` or `curl` to external sites right after a login, on reads of `/etc/passwd`, and on successful root logins from unexpected sources.
3. **Network controls:** limit outbound connections from servers and block known bad domains.
4. **Hardening:** disable direct root login, remove unused default accounts, and apply least privilege.

---

## Skills Demonstrated

- Timeline reconstruction from honeypot logs
- Extracting and documenting IOCs
- Mapping activity to MITRE ATT&CK
- Writing an incident report with clear recommendations

---

## Evidence

Cowrie session logs, the command history, and the file download event with its SHA-256 hash. Screenshots of the logs and Splunk results will be added.

**Related:** [Project 1 – Honeypot Lab](../project-1-honeypot-lab) | [Project 3 – Splunk SIEM](../project-3-splunk-siem)

---

*This investigation was done in a controlled home-lab environment for learning and portfolio purposes.*
