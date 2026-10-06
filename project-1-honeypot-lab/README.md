# Network Attack Detection & Reporting — Honeypot Lab

**Type:** Detection Lab / Attack Simulation  
**Status:** Completed

---

## 1. Overview

This project simulates an attacker scanning and targeting a vulnerable SSH service. All activity is captured and analyzed using a Cowrie honeypot and packet capture tools inside an isolated lab environment.

The goal is to practice network reconnaissance detection, traffic analysis, and basic incident documentation.

---

## 2. Lab Environment

| Role              | System                          | Purpose                          |
|-------------------|---------------------------------|----------------------------------|
| Attacker          | Kali Linux VM                   | Reconnaissance & attack simulation |
| Target            | Ubuntu Server + Cowrie          | SSH honeypot                     |
| Networking        | VirtualBox Host-Only Adapter    | Isolated lab network             |
| Capture / Analysis| Wireshark + Nmap                | Traffic capture & scanning       |

---

## 3. Objectives

- Configure an isolated lab network
- Deploy and run a Cowrie SSH honeypot
- Perform reconnaissance (Nmap) from the attacker machine
- Capture and analyze malicious traffic with Wireshark
- Document findings in a structured report

---

## 4. High-Level Attack Flow

1. Attacker (Kali) discovers the target on the host-only network.
2. Nmap scan identifies open SSH port.
3. Connection attempts are made against the Cowrie honeypot.
4. All interaction is logged by Cowrie and captured at the packet level with Wireshark.
5. Findings are documented (see related Project 4 – Incident Investigation for full timeline & IOCs).

---

## 5. Skills Demonstrated

- Building isolated virtual lab environments
- Deploying and operating an SSH honeypot (Cowrie)
- Network reconnaissance with Nmap
- Packet capture and traffic analysis with Wireshark
- Reading honeypot logs to identify attacker activity
- Documenting findings in a structured report

---

## 6. Related Projects

- [Project 3 – Splunk SIEM](../project-3-splunk-siem): Cowrie logs from this lab analyzed in Splunk
- [Project 4 – Incident Investigation](../project-4-incident-investigation): full timeline and IOCs

---

*All activity in this lab is synthetic and was performed in a controlled home-lab environment for learning purposes.*
