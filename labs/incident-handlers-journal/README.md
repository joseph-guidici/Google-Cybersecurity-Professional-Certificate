# 📓 Incident Handler's Journal

## 🔬 Lab Overview

This lab involved documenting four real-world style security incidents using an Incident Handler's Journal — a core artifact that security analysts maintain during and after incident response. Each entry follows the 5W documentation format used in professional SOC environments, capturing the who, what, where, when, and why of each event alongside tools used and key observations.

The scenarios span a range of common attack types: ransomware, phishing/malware delivery, unauthorized data access, and network-based intrusion (DDoS). Working through these entries reinforced how structured documentation supports faster triage, cleaner post-incident reviews, and stronger communication across security teams.

---

## 🛠️ Tools & Methods Reference

| Tool / Method | Purpose |
|---|---|
| `tcpdump` | Captured and analyzed raw network traffic from the command line |
| Wireshark | Performed deep packet inspection and protocol-level traffic analysis |
| VirusTotal | Investigated suspicious file hashes and URLs for known malware indicators |
| 5W Documentation | Structured each incident entry for consistent, reproducible reporting |

---

## 📋 Journal Entries

### Entry 1 — Ransomware Attack on Healthcare Organization

| Field | Details |
|---|---|
| **Date** | Entry 1 |
| **Who** | An organized threat actor group |
| **What** | Ransomware deployed across hospital systems; medical records encrypted and held for ransom |
| **Where** | Healthcare company's internal network and file systems |
| **When** | Discovered Tuesday morning when staff could not access patient records |
| **Why** | Attacker gained access via a phishing email targeting an employee; malicious attachment executed ransomware payload |
| **Tools Used** | Incident response playbook, network logs |

**Key Observations:**
- Initial infection vector was a phishing email with a malicious attachment
- Ransomware propagated laterally across the network after execution
- Highlighted the critical importance of endpoint protection and user security awareness training
- Recovery required isolating affected systems and restoring from clean backups

---

### Entry 2 — Phishing / Malware Investigation

| Field | Details |
|---|---|
| **Date** | Entry 2 |
| **Who** | External attacker, unknown individual |
| **What** | Suspicious file flagged; investigation confirmed malicious software designed to steal credentials |
| **Where** | Employee workstation |
| **When** | Flagged by security tooling; investigated same day |
| **Why** | User downloaded a file from an untrusted source delivered via a phishing email |
| **Tools Used** | VirusTotal (hash and URL analysis) |

**Key Observations:**
- File hash lookup on VirusTotal returned multiple vendor detections, confirming malware
- VirusTotal provided behavioral analysis and known associations with credential-stealing campaigns
- Reinforced why file hash verification is a fast, low-cost first step in malware triage
- Recommended blocking the associated domain and forcing a password reset for the affected user

---

### Entry 3 — Data Breach / Unauthorized Access

| Field | Details |
|---|---|
| **Date** | Entry 3 |
| **Who** | Unauthorized external party |
| **What** | Sensitive customer data accessed and potentially exfiltrated without authorization |
| **Where** | Company database and web-facing application |
| **When** | Discovered during a routine log review |
| **Why** | Attacker exploited a vulnerability in the web application to gain access to backend data |
| **Tools Used** | Manual log analysis, access logs |

**Key Observations:**
- Log review revealed unusual query patterns and access from an unrecognized IP address
- Data accessed included personally identifiable information (PII)
- Incident triggered mandatory breach notification review under applicable compliance requirements
- Remediation involved patching the exploited vulnerability and reviewing access controls

---

### Entry 4 — Network Intrusion (DDoS Attack)

| Field | Details |
|---|---|
| **Date** | Entry 4 |
| **Who** | External attacker(s) |
| **What** | Distributed Denial of Service (DDoS) attack overwhelmed network resources, disrupting services |
| **Where** | Organization's public-facing network infrastructure |
| **When** | During business hours; detected via network monitoring alerts |
| **Why** | High volume of ICMP/UDP packets flooded the network, exhausting bandwidth and server capacity |
| **Tools Used** | tcpdump, Wireshark |

**Key Observations:**
- `tcpdump` captured the flood of incoming packets, confirming abnormal traffic volume
- Wireshark analysis revealed packet characteristics consistent with a DDoS pattern
- Response involved rate-limiting, traffic filtering at the perimeter, and ISP coordination
- Highlighted the value of baseline traffic monitoring for detecting anomalies quickly

---

## 💡 Key Takeaways

- **Documentation discipline matters.** Consistent 5W entries across all four scenarios made it much easier to compare attacker behavior, identify patterns, and think through remediation steps systematically.
- **Tools serve the investigation, not the other way around.** Knowing when to reach for `tcpdump` vs. Wireshark vs. VirusTotal is as important as knowing how to use them.
- **Every incident type has a signature.** Ransomware leaves encryption artifacts. Phishing leaves a delivery chain. DDoS leaves a traffic fingerprint. Recognizing those signatures early compresses response time significantly.
- **The journal is a living document.** In real-world SOC environments, entries like these feed into post-incident reviews, threat intelligence sharing, and playbook improvements.

---

## 🔗 Back to Main Portfolio

[← Return to Google Cybersecurity Certificate Repository](../../README.md)
