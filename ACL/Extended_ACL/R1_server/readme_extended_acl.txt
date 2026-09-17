# Extended Access Control List (ACL) Lab – Class C Network with Server Control

### Description

This lab demonstrates the implementation of **Extended ACLs** in a Class C network environment to control inter-departmental access using Cisco Packet Tracer. The setup includes a server in the cybersecurity department, and the goal is to restrict or allow access to it from selected hosts in the networking department.

This simulates real-world security policy enforcement at the network edge.

### Topology Overview

- **Router 0 (R0) – Networking Department**  
  - Network: `192.168.70.0/24`  
  - Devices: 3 Laptops, 1 PC

- **Router 1 (R1) – Cybersecurity Department**  
  - Network: `192.168.61.0`
  - Devices: 1 Laptop, 1 PC, 1 Server  
  - Server IP: `192.168.61.4`

- **WAN Link Between Routers**  
  - R0 (WAN): `192.168.41.1`  
  - R1 (WAN): `192.168.41.2`  
  - Network: 192.168.41.0

### Lab Objectives

- Configure Extended ACLs to control access from networking to cybersecurity department
- Restrict access to the server based on IP and protocol (e.g., allow HTTP, block ICMP)
- Apply ACLs correctly on router interfaces (inbound/outbound)
- Analyze and verify access control behavior before and after applying ACLs

### Tools Used

- Cisco Packet Tracer
- 2 Routers
- Switches
- 3 Laptops and 1 PC (Networking Dept)
- 1 Laptop, 1 PC, and 1 Server (Cybersecurity Dept)

### Tasks Performed

- Assigned IP addresses to all end devices and router interfaces
- Verified full connectivity between departments
- Configured an Extended ACL (e.g., access-list 100) to:
  - Block or allow specific traffic to the server at `192.168.61.4`
  - Control access by protocol (ICMP, TCP, HTTP)
- Applied the ACL on R1's WAN interface in the correct direction
- Verified results using:
  - `ping` and browser tests from laptops and PCs
  - `show access-lists` and interface ACL debugging

### Files Included

- `Extended-ACL-ClassC.pkt` – Cisco Packet Tracer topology
- `R0_Config.txt` – Configuration for Router 0
- `R1_Config.txt` – ACL and interface configuration for Router 1
- `Device_Configs.txt` – IP details and testing logs for all end devices

### Learning Outcomes

- Understanding of extended ACLs for network access restriction
- Filtering traffic with precision using IP, port, and protocol
- Identifying the right placement and direction for ACLs
- Realistic enterprise-grade traffic control practice
