# Extended Access Control List (ACL) Lab

### Description

This lab demonstrates the use of **Extended Access Control Lists (ACLs)** in Cisco Packet Tracer. Extended ACLs allow filtering of traffic based on **source and destination IP addresses, protocols, and port numbers**. The lab simulates a scenario where network access between two departments is controlled for security.

### Topology Overview

- **Router 0 (Cybersecurity Department)**  
  - LAN: 192.168.10.0/24

- **Router 1 (Networking Department)**  
  - LAN: 192.168.20.0/24

- **WAN link Between Routers**  
  - R0: 192.168.30.1 
  - R1: 192.168.30.2`

### Lab Objectives

- Configure extended ACLs to allow or deny specific traffic between departments
- Apply the ACL on the correct interface and in the proper direction
- Use specific protocols (e.g., ICMP, TCP, HTTP) in access rules
- Observe how extended ACLs enhance network security and control

### Tools Used

- Cisco Packet Tracer
- Routers
- Switches
- PCs

### Tasks Performed

- Assigned IPs to PCs and router interfaces
- Verified full connectivity before applying ACL
- Configured extended ACL using `access-list 100` (or named ACLs)
- Applied ACL to WAN-facing interface (either inbound or outbound)
- Used commands like `permit tcp`, `deny icmp`, etc. for filtering
- Verified behavior using `ping`, `telnet`, and browser (if HTTP configured)
- Confirmed ACL hit counts using `show access-lists`

### Files Included

- `Extended-ACL.pkt` – Cisco Packet Tracer topology
- `Router0_Config.txt` – ACL rules and interface setup for Router 0
- `Router1_Config.txt` – Interface settings for Router 1
- `PC_Configs.txt` – IP settings and test results

### Learning Outcomes

- Deep understanding of extended ACL logic
- Ability to control traffic with precision (protocol, port, IP)
- Correct placement and direction of ACLs on router interfaces
- Real-world simulation of inter-departmental traffic restrictions
