# BGP Lab – 2 Router Topology

### Description

This lab demonstrates a basic BGP configuration using two routers in Cisco Packet Tracer. Each router represents a separate network, and BGP is used to exchange routing information between them.

The setup simulates inter-network routing where each router advertises its internal LAN to the other via a WAN link using BGP.

### Topology Overview

- **Router 1 (R1)**  
  - LAN Network: 192.168.10.0
  - WAN IP: `192.168.25.1`

- **Router 2 (R2)**  
  - LAN Network: 192.168.20.0
  - WAN IP: `192.168.25.2`

- **WAN Link Between Routers:**  
  - Network: `192.168.25.0/24`

### Lab Objectives

- Configure BGP on both routers
- Establish a BGP neighbor relationship between R1 and R2
- Advertise each LAN network to the BGP peer
- Verify routing updates and connectivity using BGP

### Tools Used

- Cisco Packet Tracer
- 2 Routers
- PCs in each LAN
- BGP Protocol

### Tasks Performed

- Assigned IP addresses to router interfaces and end devices
- Configured BGP with appropriate AS numbers
- Advertised internal LANs using the `network` command
- Established BGP neighbor relationship over the WAN link
- Verified full connectivity between LAN devices
- Checked routing table and BGP summary for peer status

### Files Included

- `BGP-2Routers.pkt` – Cisco Packet Tracer topology file
- `R1_Config.txt`, `R2_Config.txt` – Router BGP configuration commands

### Learning Outcomes

- Basic BGP configuration and peering process
- Advertising and learning remote networks via BGP
- End-to-end IP connectivity between different LANs
- Real-world simulation of BGP-based inter-network routing
