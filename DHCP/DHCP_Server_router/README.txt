# DHCP Lab – Server and Router Based Configuration

### Description

This lab demonstrates two DHCP configuration methods using Cisco Packet Tracer. Both setups are included in a single `.pkt` file to compare how IP addresses can be dynamically assigned using a dedicated DHCP server or a router.

### Topology Overview

#### 1. DHCP with Server
- **Network:** 192.168.20.0
- A dedicated DHCP server is used to assign IP addresses to clients
- PCs are connected through a switch to the DHCP server

#### 2. DHCP with Router (DHCP Relay)
- **Network:** 192.168.50.0
- The router is configured to act as the DHCP server
- End devices receive IPs directly from the router's DHCP pool

### Lab Objectives

- Configure a DHCP server with appropriate pools and exclusions
- Enable DHCP relay through a router using the `ip helper-address` command
- Observe dynamic IP assignment in both scenarios
- Verify successful address leasing and connectivity using `ipconfig` and `ping`

### Tools Used

- Cisco Packet Tracer
- Switches
- DHCP Server
- Routers
- PCs

### Tasks Performed

- Configured DHCP server with address pool, default gateway, and DNS (optional)
- Set up router DHCP pool with `ip dhcp pool` and excluded-addresses
- Connected end devices and enabled DHCP on PCs
- Verified successful lease assignment
- Used `ipconfig` to verify IPs and `ping` to test connectivity

### Files Included

- `DHCP-Lab.pkt` – Topology file containing both DHCP methods
- `Router_Config.txt` – DHCP pool and relay commands
- `Server_Config.txt` – DHCP scope setup
- `PC_Configs.txt` – Expected IP assignments and outputs

### Learning Outcomes

- Difference between server-based and router-based DHCP
- Configuration of DHCP server and DHCP pool on a router
- Use of `ip helper-address` in router-based DHCP relay
- Dynamic IP management in enterprise networks
