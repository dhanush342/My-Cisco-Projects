# Static Routing Lab – Interdepartmental Communication

### Description

This lab demonstrates **static IP routing** between two departmental networks using Cisco Packet Tracer. The goal is to manually configure routing tables on each router to enable communication between the Networking and Cybersecurity departments without using any dynamic routing protocols.

### Topology Overview

- **Router 0 (R0) – Networking Department**  
  - LAN Network: 165.10.0.0

- **Router 1 (R1) – Cybersecurity Department**  
  - LAN Network: 165.25.0.0

- **WAN Link Between Routers**  
  - R0 WAN IP: 165.15.10.1  
  - R1 WAN IP: 165.15.10.2  
  - WAN Network: 165.15.10.0

### Lab Objectives

- Configure static routes on each router to reach remote networks
- Understand next-hop IP vs exit interface in static routing
- Test and verify connectivity between end devices across networks

### Tools Used

- Cisco Packet Tracer
- 2 Routers
- Switches
- End Devices (PCs/Laptops)

### Tasks Performed

- Assigned static IP addresses to all devices and interfaces
- Verified local LAN connectivity
- Configured static routes:
  - On R0: route to 165.25.0.0/24 via 165.15.10.2
  - On R1: route to 165.10.0.0/24 via 165.15.10.1
- Tested full connectivity using `ping`
- Verified routing tables using `show ip route` and `show run`

### Files Included

- Static-Routing.pkt – Cisco Packet Tracer topology
- R0_Config.txt – Configuration for Router 0
- R1_Config.txt – Configuration for Router 1
- PC_Configs.txt – IP addresses and ping results from end devices

### Learning Outcomes

- Fundamentals of static routing in IP networks
- How to route packets manually using next-hop or interface method
- How routers handle forwarding decisions without dynamic protocols
- CLI practice for configuring and verifying static routes
