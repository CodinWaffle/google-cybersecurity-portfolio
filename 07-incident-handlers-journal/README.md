# Incident Handler's Journal: Network Security & Traffic Analysis

## Project Overview
This Incident Handler's Journal documents network security analysis, traffic monitoring, and attack mitigation procedures completed as part of the Google Cybersecurity Professional Certificate portfolio[cite: 10]. The entries capture incident handling activities across five key network security domains[cite: 10].

---

## Incident Journal Entries

### Journal Entry 1: TCP/IP Model & Network Layer Analysis
* **Date:** October 2024
* **Request Description:** Analysis of network traffic protocols and TCP/IP model communications.
* **Prior State:** Standard unmonitored traffic flowing through local network interfaces.
* **Actions Taken:** Analyzed packet flow across the 4 TCP/IP layers to trace network activity and verify security boundaries.
* **The 5 W's:**
  * **What caused the incident?** Routine network traffic baseline analysis to detect potential protocol anomalies.
  * **Where did the incident occur?** Across local subnets and gateway interfaces within the TCP/IP layers.
  * **When did it occur?** During baseline network security monitoring.
  * **What details pertain to the incident?** Analyzed packet header encapsulation across Network Access, Internet, Transport, and Application layers.
  * **How will the incident be addressed?** Established a standard traffic baseline to easily flag unauthorized network protocols.
* **Additional Notes:** Understanding layer interactions helps isolate where malicious packets enter the network.

---

### Journal Entry 2: Wireshark Packet Sniffing & Traffic Analysis
* **Date:** October 2024
* **Request Description:** Packet sniffing and unencrypted traffic analysis using Wireshark.
* **Prior State:** Raw network capture file containing unfiltered protocol traffic.
* **Actions Taken:** Applied Wireshark display filters (`http`, `dns`, `ip.addr`) to inspect packet headers and cleartext payloads.
* **The 5 W's:**
  * **What caused the incident?** Transmission of unencrypted HTTP traffic across the internal network.
  * **Where did the incident occur?** Local network interface card (NIC) capturing live subnet traffic.
  * **When did it occur?** During packet analysis lab execution.
  * **What details pertain to the incident?** Unencrypted HTTP and DNS queries revealed cleartext payload data in Wireshark captures.
  * **How will the incident be addressed?** Filter cleartext traffic with Wireshark and enforce HTTPS/TLS across all host connections.
* **Additional Notes:** Wireshark display filters isolate targeted traffic patterns immediately.

---

### Journal Entry 3: TCP 3-Way Handshake Connection Auditing
* **Date:** October 2024
* **Request Description:** TCP 3-way handshake connection auditing.
* **Prior State:** Client-server network connection setup phase.
* **Actions Taken:** Traced `SYN`, `SYN-ACK`, and `ACK` packet sequences in packet captures to verify connection validity.
* **The 5 W's:**
  * **What caused the incident?** Verification of stateful TCP connection setups between clients and internal servers.
  * **Where did the incident occur?** Transport layer (TCP) connection ports.
  * **When did it occur?** During stateful session connection auditing.
  * **What details pertain to the incident?** Identified standard `SYN` -> `SYN-ACK` -> `ACK` packet sequences alongside incomplete connection attempts.
  * **How will the incident be addressed?** Monitor stateful handshakes to identify and drop incomplete SYN flood DoS patterns.
* **Additional Notes:** Incomplete handshakes are key indicators of SYN flood attacks.

---

### Journal Entry 4: Network Attack Analysis (DDoS & IP Spoofing)
* **Date:** October 2024
* **Request Description:** Network attack investigation involving DDoS and IP spoofing.
* **Prior State:** Target server experiencing high latency and service degradation.
* **Actions Taken:** Analyzed high-volume traffic patterns, identified spoofed source IPs, and recommended blocking rules.
* **The 5 W's:**
  * **What caused the incident?** A simulated Denial of Service (DoS) attack using spoofed IP addresses.
  * **Where did the incident occur?** External network gateway and public web server.
  * **When did it occur?** During simulated incident response scenario execution.
  * **What details pertain to the incident?** Massive traffic spikes from forged source IP addresses flooded server bandwidth.
  * **How will the incident be addressed?** Implement rate-limiting and configure firewall access control lists (ACLs) to drop spoofed IP traffic.
* **Additional Notes:** Combining traffic filters with rate-limiting rapidly restores service availability.

---

### Journal Entry 5: Defensive Hardening & System Remediation
* **Date:** October 2024
* **Request Description:** Network defense strategy and system hardening implementation.
* **Prior State:** Network with unsegmented subnets and unnecessary open ports.
* **Actions Taken:** Configured firewall rules, restricted unused ports, and established intrusion detection rules.
* **The 5 W's:**
  * **What caused the incident?** Post-incident remediation to reduce system vulnerabilities and attack surface area.
  * **Where did the incident occur?** Internal firewalls, routers, and host operating systems.
  * **When did it occur?** During system hardening and remediation phase.
  * **What details pertain to the incident?** Identified open ports and default configurations that allowed unrestricted lateral traffic.
  * **How will the incident be addressed?** Close unnecessary open ports, deploy stateful firewall rules, and implement subnet isolation.
* **Additional Notes:** Combining strict firewall rules with network segmentation enforces defense-in-depth.

---

## Reflection & Workflow Application
This Incident Handler's Journal serves as a structured framework for documenting future security investigations. By capturing the initial state, technical actions taken, the 5 W's, and remediation steps, I can maintain an accurate audit trail, analyze recurring threat patterns, and streamline reporting during live incident handling.
