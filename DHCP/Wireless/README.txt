# DHCP Wireless Lab – Access Point Based IP Assignment

### Description

This lab demonstrates dynamic IP address assignment to wireless clients using a DHCP server in a Class B network. It simulates an enterprise wireless setup where Access Points (APs) broadcast SSIDs and wireless clients like smartphones and tablets receive IPs automatically.

The lab is built using Cisco Packet Tracer and showcases realistic DHCP and wireless configurations.

### Network Overview

- **Network Used**: 172.16.0.0 (Class B)
- **DHCP Server**: Provides IP addresses dynamically to wireless devices
- **Access Points**
  - Access Point 0 – SSID: accenture
  - Access Point 1 – SSID: Accenture Banglore
- **Wireless Devices**: Tablets and Smartphones

### Lab Objectives

- Configure a DHCP server with the correct IP scope
- Set up wireless access points with custom SSIDs
- Connect wireless clients to access points and verify DHCP assignment
- Observe dynamic IP lease behavior in wireless environments

### Tools Used

- Cisco Packet Tracer
- Wireless Access Points
- DHCP Server
- Switches
- Wireless Tablets
- Wireless Smartphones

### Tasks Performed

- Configured a DHCP server with a valid IP pool for the `172.16.0.0/16` network
- Set SSIDs on Access Points
- Connected wireless clients (smartphones/tablets) to access points
- Verified IP address assignment using DHCP
- Tested network connectivity using `ping` between devices

### Files Included

- DHCP-Wireless.pkt – Cisco Packet Tracer lab file
- Server_Config.txt – DHCP server pool and settings

### Learning Outcomes

- How DHCP works in a wireless network
- Setting up enterprise-style SSIDs on Access Points
- Managing Class B IP address distribution via DHCP
- Real-world simulation of wireless connectivity and dynamic IP management
