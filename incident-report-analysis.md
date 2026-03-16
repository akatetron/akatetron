# Incident Report Analysis 🔵

## Objective
Analyze a security incident using the NIST Cybersecurity Framework (CSF)
to identify what happened, contain the damage, and prevent future occurrences.

## Framework Used
- NIST Cybersecurity Framework (CSF)
- 5 Core Functions: Identify → Protect → Detect → Respond → Recover

---

## Incident Summary

| Field | Details |
|---|---|
| **Incident Type** | DDoS Attack / ICMP Flood |
| **Systems Affected** | Internal network |
| **Detection Method** | Network monitoring |
| **Response Time** | Immediate containment applied |

---

## NIST CSF Analysis

### 1️⃣ Identify
- The organization's internal network was disrupted by a flood of ICMP packets
- A malicious actor sent overwhelming ICMP ping requests through an unconfigured firewall
- All internal network services were inaccessible for approximately 2 hours

### 2️⃣ Protect
**Immediate protective measures implemented:**
- New firewall rule added to limit incoming ICMP packet rate
- Source IP address verification enabled on firewall
- Network monitoring software deployed to detect abnormal traffic patterns

### 3️⃣ Detect
- IDS/IPS system configured to filter suspicious ICMP traffic
- Network traffic monitoring tools deployed
- Baseline of normal traffic established for future anomaly detection

### 4️⃣ Respond
- Incident response team activated
- Non-critical network services taken offline during attack
- Critical network services restored in priority order
- Incident documented for post-incident review

### 5️⃣ Recover
- All affected systems restored to normal operation
- Firewall rules updated and hardened
- Staff briefed on updated security procedures
- Post-incident report completed

---

## Key Findings
- Firewall misconfiguration allowed unrestricted ICMP traffic
- Lack of rate limiting enabled flood attack to overwhelm network
- Absence of IDS/IPS delayed initial detection

## Recommendations
1. Implement strict firewall rules for ICMP traffic
2. Deploy IDS/IPS for real-time traffic analysis
3. Establish network traffic baselines for anomaly detection
4. Regular firewall configuration audits

---

## Summary
This incident highlighted the importance of proper firewall configuration
and proactive network monitoring. Applying the NIST CSF framework provided
a structured approach to both responding to the incident and implementing
improvements to prevent recurrence.

**Key takeaway:** A structured incident response framework like NIST CSF
ensures no steps are missed during and after a security incident,
minimizing damage and recovery time.
