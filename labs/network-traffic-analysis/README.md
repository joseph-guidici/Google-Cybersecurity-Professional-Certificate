# Lab 02 - Network Traffic Analysis

## Scenario Overview

This lab presented a real-world-style incident scenario in which a multimedia company experienced a DDoS (Distributed Denial of Service) attack that disrupted internal network services for two hours. ICMP flood packets overwhelmed the network, blocking legitimate traffic from reaching internal resources.

My role was to act as a cybersecurity analyst responding to the incident, applying the **NIST Cybersecurity Framework** to analyze what happened and build a structured incident response plan across all five core functions.

## Skills Demonstrated

- Applying the NIST CSF to a real-world network incident
- Identifying attack vectors and affected assets
- Developing actionable security controls and response procedures
- Documenting a structured incident response plan
- Understanding DDoS attack mechanics and network-layer defenses

## NIST CSF Breakdown

### Identify
This company had experienced an ICMP flood attack performed by a malicious actor. This attack affected the entire internal network. All critical network resources needed to be secured and restored to a functioning state.

### Protect
In respond to this attack, the following implementations have been made
- New firewall rules to limit rate of incoming ICMP packets
- Installed an Intrusion Detection System (IDS)
- Installed an Intrusion Prevention System (IPS)

### Detect
Firewall has been configured with source IP address verification to check for spoofed IP addresses on incoming ICMP packets.

### Respond
Outlined the incident response procedures taken during and after the attack:
- Isolate affected systems to prevent further disruption
- Restore critical systems and services
- Analyze network logs to check for suspiciour activity
- Reported the incident to relevant stakeholders and upper management

### Recover
Defined recovery steps to return operations to normal and prevent recurrence:
- Restored all affected internal systems and services to full operation
- Conducted a post-incident review to evaluate the effectiveness of the response
- Updated firewall rules and IDS signatures based on lessons learned
- Scheduled future security training to improve team response time


## Lessons Learned

Working through this scenario reinforced how the NIST CSF functions as more than just a checklist, but a structured way of thinking through an incident from all angles. The identify and protect phases are where a lot of future incidents are actually prevented, not just the respond phase where most attention tends to go during an active attack.

This lab also made the relationship between network-layer attacks and organizational risk very concrete. A two-hour service outage from an ICMP flood has real downstream consequences — lost revenue, damaged trust, and potential SLA violations — which is exactly why having a documented response plan before an incident occurs matters.
