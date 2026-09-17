# BGP Lab – 3 Router Topology

### Description

This lab demonstrates the configuration of Border Gateway Protocol (BGP) using three routers in Cisco Packet Tracer. Each router represents a separate network (or autonomous system), and BGP is used to establish neighbor relationships and exchange routing information.

The topology simulates inter-network routing between different networks using BGP, commonly used in large-scale enterprise and ISP environments.

### Topology Overview

- **Router 1 (R1)**  
  - LAN Network: 192.168.10.0  
  - WAN Link to R2: 192.168.1.1

- **Router 2 (R2)**  
  - LAN Network: 192.168.20.0  
  - WAN Links:  
    - To R1: `192.168.1.2`  
    - To R3: `192.168.2.1`

- **Router 3 (R3)**  
  - LAN Network: 192.168.30.0  
  - WAN Link to R2: `192.168.2.2`

### Lab Objectives

- Configure BGP on all three routers
- Establish neighbor relationships between directly connected routers
- Advertise internal LAN networks via BGP
- Use `next-hop-self` on R2 to allow full connectivity
- Verify BGP peering and routing tables

### Tools Used

- Cisco Packet Tracer
- 3 Routers
- PCs in each LAN
- Static IP addressing for testing
- BGP protocol

### Tasks Performed

- Assigned IP addresses to all router interfaces and PCs
- Configured BGP `router` process with respective AS numbers
- Established BGP neighbor relationships:
  - R1 ↔ R2  
  - R2 ↔ R3
- Advertised internal LAN networks using the `network` command
- Used `next-hop-self` on R2 to resolve next-hop reachability
- Verified full connectivity across all LANs using `ping`
- Checked BGP tables using `show ip bgp summary` and `show ip route`

### Files Included

- `BGP-3Routers.pkt` – Cisco Packet Tracer topology file
- `R1_Config.txt`, `R2_Config.txt`, `R3_Config.txt` – Router BGP configs

### Learning Outcomes

- Understanding BGP neighbor formation and advertisement
- Importance of `next-hop-self` in BGP transit scenarios
- Hands-on experience with multi-router BGP topologies
- BGP’s role in large-scale and inter-AS routing
