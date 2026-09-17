# Extended Access Control List (ACL) Lab – Departmental Access Control

### Description

This lab demonstrates the use of **Extended ACLs** to control traffic between departments in a simulated enterprise network. Using Cisco Packet Tracer, the topology includes routers for two departments (Marketing and HR) and a shared server in the Marketing network. Extended ACLs are configured to restrict or permit access based on IP addresses, protocols, and services.

### Topology Overview

- **Router 0 (R0) – Marketing Department**  
  - LAN: 192.168.50.0/24  
  - Includes a Server: 192.168.50.2

- **Router 1 (R1) – HR Department**  
  - LAN: 192.168.10.0/24

- **Inter-router WAN Link**  
  - Network: 192.168.18.0

### Lab Objectives

- Create and apply Extended ACLs to control access to specific resources (e.g., the server)
- Allow or deny traffic based on source/destination IP and protocol (e.g., HTTP, ICMP)
- Protect the Marketing server from unauthorized access
- Verify ACL effectiveness with `ping` and browser tests

### Tools Used

- Cisco Packet Tracer
- Routers
- Switches
- PCs
- Server

### Tasks Performed

- Assigned IP addresses to all PCs, server, and router interfaces
- Verified full connectivity before applying ACLs
- Configured extended ACL using `access-list 100` (or named ACL)
- Applied ACL in the correct direction (inbound/outbound on WAN-facing interface)
- Example ACL actions:
  - Allow HTTP (port 80) from HR to Marketing server
  - Deny ICMP (ping) from HR to Marketing
- Verified functionality using:
  - `ping` from HR PCs to Server
  - Browser access from HR PCs to Server (HTTP)
  - `show access-lists` to confirm hit counts

### Files Included

- `Extended-ACL-Server.pkt` – Cisco Packet Tracer topology file
- `R0_Config.txt` – ACL rules and interface settings for Router 0
- `R1_Config.txt` – Config for Router 1
- `PC_Configs.txt` – IP settings and expected test results

### Learning Outcomes

- Understand how extended ACLs work for protocol and port filtering
- Learn to protect specific resources (e.g., servers) using ACLs
- Practice placing ACLs in the correct direction and location
- Develop CLI confidence for configuring, applying, and verifying ACLs
