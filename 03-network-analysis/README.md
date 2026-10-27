# Network Incident Analysis — ICMP Ping Flood (DoS Attack)

## Overview
This write-up covers an incident response scenario from Course 3 of the Google Cybersecurity Certificate. The scenario involved an unconfigured network firewall being targeted by a heavy ICMP flood, causing an internal denial of service (DoS).

---

## Breakdown by NIST Framework

### 1. Identify
* **Root Cause:** A threat actor took advantage of a misconfigured perimeter firewall to launch an ICMP ping flood.
* **Impact:** High incoming packet volume saturated network bandwidth and system memory, taking down core internal services.

### 2. Protect
* **Fixes Implemented:**
  * Added firewall rules to rate-limit inbound ICMP traffic.
  * Turned on source IP address verification to block spoofed packets.
  * Updated IDS/IPS signatures to automatically drop suspicious ICMP patterns moving forward.

### 3. Detect
* **How it was caught:** Network monitoring tools flagged massive spikes in traffic alongside user tickets reporting unresponsive internal systems.

### 4. Respond
* **Containment:** Immediately blocked incoming ICMP packets at the network edge to stabilize the connection and isolated non-critical systems to analyze the attack safely.

### 5. Recover
* **Restoration:** Checked SIEM log data to confirm the flood had completely stopped, confirmed firewall rules were holding, and brought core systems back online safely.

---

## Key Lessons Learned
Leaving ICMP completely unrestricted at the perimeter is a huge risk. Simple rate-limiting rules and source IP checks at the edge firewall are essential for stopping ping floods before they starve internal network resources.