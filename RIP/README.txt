# RIP Routing Lab – Class A and Class C Networks

### Description

This lab demonstrates the configuration of RIP (Routing Information Protocol) to enable communication between two different networks: a Class A network and a Class C network. The lab is built using Cisco Packet Tracer and simulates departmental segmentation using routers.

The goal is to observe how RIP handles routing updates and enables communication between networks with different IP classes.

### Topology Overview

- **Router 0 (Networking Department)**  
  - Network: 192.168.250.0 (Class C)

- **Router 1 (Cybersecurity Department)**  
  - Network: 25.0.0.0 (Class A)

- **Router Interconnection Link**  
  - Network: 192.168.50.0

### Lab Objectives

- Configure RIP on both routers to advertise their connected networks
- Observe how RIP propagates routing updates across classful networks
- Enable communication between devices in different departments using RIP
- Understand RIP behavior with Class A and Class C addressing

### Tools Used

- Cisco Packet Tracer
- 2 Routers
- PCs for each department
- Static IP addressing
- RIP Version 1 (default)

### Tasks Performed

- Assigned static IP addresses to PCs and router interfaces
- Enabled RIP and advertised networks on both routers
- Verified routing tables and updates using `show ip route`
- Tested connectivity between end devices across both networks using `ping`

### Files Included

- `RIP-Class-A-C.pkt` – Cisco Packet Tracer topology
- `Router0_Config.txt` – RIP and interface configuration for Router 0
- `Router1_Config.txt` – RIP and interface configuration for Router 1
- `PC_Configs.txt` – IP addresses of end devices

### Learning Outcomes

- Understanding of RIP and its limitations with classful routing
- Connecting different IP classes using a dynamic routing protocol
- Practical experience with multi-router setups and route advertisement
- Troubleshooting RIP-based networks
