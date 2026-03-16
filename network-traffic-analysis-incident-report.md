# Cybersecurity Incident Report: Network Traffic Analysis 🌐

## Objective
Analyze DNS and ICMP traffic logs using tcpdump to identify the cause
of a network connectivity issue affecting a client website.

## Tools Used
- `tcpdump` — network packet analyzer
- DNS/ICMP protocol analysis

---

## Incident Summary

| Field | Details |
|---|---|
| **Time Reported** | 1:24 PM |
| **Affected Service** | yummyrecipesforme.com |
| **Error Message** | "destination port unreachable" |
| **Protocols Involved** | UDP, DNS, ICMP |
| **Suspected Cause** | DNS server DoS attack or firewall misconfiguration |

---

## Part 1: DNS and ICMP Traffic Log Analysis

### Protocols Identified
- **UDP** — used by browser to send DNS queries to the DNS server
- **DNS** — used to resolve domain name to IP address
- **ICMP** — used to return error responses back to the client

### Log Findings
- UDP packets were sent from source computer to DNS server at `203.0.113.2` on **port 53**
- ICMP error responses returned with message: **"udp port 53 unreachable"**
- Query ID `35084` showed a `+` flag indicating issues with the UDP message
- `A?` symbol indicated flags with DNS A record lookup operations

### Interpretation
Since **port 53 is the standard DNS port**, receiving "port 53 unreachable"
confirms the DNS server is not responding to queries. This prevents domain
name resolution, making the website inaccessible to users.

---

## Part 2: Incident Analysis

### Timeline
```
13:24:32 — Customers begin reporting "destination port unreachable" error
13:24:32 — Security team notified, investigation begins
13:24:32 — tcpdump packet capture initiated
13:24:32 — DNS port 53 unreachable confirmed in logs
```

### Investigation Steps
1. Visited affected website — received "destination port unreachable" error
2. Loaded tcpdump network analyzer
3. Reloaded webpage while capturing traffic
4. Analyzed captured packets — identified UDP/ICMP exchange
5. Confirmed port 53 unreachable in all log events

### Root Cause Analysis
Two possible causes identified:

| Cause | Likelihood |
|---|---|
| DoS attack against DNS server | High |
| Firewall misconfiguration blocking port 53 | Medium |

### Next Steps
- [ ] Verify DNS server operational status
- [ ] Check firewall rules for port 53 blocking
- [ ] If DoS confirmed — implement rate limiting and traffic filtering
- [ ] Restore DNS service and verify website accessibility

---

## Summary
A network traffic analysis using tcpdump identified that DNS port 53 was
unreachable, preventing domain name resolution for the client website.
The most likely cause is a DoS attack against the DNS server or a firewall
misconfiguration blocking DNS traffic.

**Key takeaway:** tcpdump is a powerful tool for identifying network-level
issues. Understanding protocol behavior (UDP/DNS/ICMP) is essential for
rapid incident diagnosis in a SOC environment.
