# Splunk SIEM — Cowrie Honeypot Log Analysis

**Type:** SIEM Detection & Dashboarding | **Platform:** Splunk Enterprise 10.4.2 on Ubuntu Server | **Status:** Completed

---

## Overview

I ingested Cowrie SSH honeypot logs into Splunk, wrote SPL searches for key attacker behavior, and built a dashboard around them. The goal was to practice core SOC skills: log onboarding, search, visualization, and basic detection logic.

**Setup:** Splunk on an Ubuntu Server VM (VirtualBox), a dedicated `cowrie` index, and synthetic localhost SSH sessions as the data source.

---

## Dashboard Panels

**1. Login attempts: success vs failed** (authentication volume and success rate)
```spl
index=cowrie (eventid=cowrie.login.success OR eventid=cowrie.login.failed)
| stats count by eventid
```

**2. Attacker commands** (every command run in the honeypot, newest first)
```spl
index=cowrie eventid=cowrie.command.input
| table _time, session, input
| sort -_time
```

**3. Successful logins** (source IP, username, and session ID for each login)
```spl
index=cowrie eventid=cowrie.login.success
| table _time, src_ip, username, session
```

**4. File downloads** (URL and hash of files the attacker tried to download, usable as IOCs)
```spl
index=cowrie eventid=cowrie.session.file_download
| table _time, session, url, shasum
```

---

## Skills Demonstrated

- SIEM log ingestion and index configuration
- Writing practical SPL queries for security use cases
- Building operational dashboards
- Analyzing attacker behavior from honeypot telemetry
- Correlating events by session ID and extracting IOCs

---

## Limitations & Next Steps

- Data is synthetic and from a single source.
- Add real multi-source attack traffic.
- Build correlation alerts (e.g. successful login followed by an immediate `wget`).
- Map high-value events to MITRE ATT&CK.
- Add dashboard screenshots to this README.

**Related:** [Project 1 – Honeypot Lab](../project-1-honeypot-lab) | [Project 4 – Incident Investigation](../project-4-incident-investigation)

---

*All data is synthetic and was created in a controlled home-lab environment for learning purposes.*
