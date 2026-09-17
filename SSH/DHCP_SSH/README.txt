# DHCP & SSH Lab – Single LAN with Wired and Wireless Devices

## Description
This lab demonstrates the configuration of DHCP for both wired and wireless devices and enabling SSH (Secure Shell) access on the router. 
The lab is built using Cisco Packet Tracer and simulates a departmental LAN with both PCs and smartphones connected through a switch and an access point (AP).

The goal is to provide automatic IP addressing (DHCP) for all devices and ensure secure remote management (SSH) of the router.

## Topology Overview
- Router (DHCP + SSH enabled)
  - Provides IP addresses to LAN devices
  - Acts as the default gateway
- Switch
  - Connects wired devices to the LAN
- Access Point (AP)
  - Provides wireless access for smartphones/laptops
  - WPA2-PSK security enabled
- Devices
  - 2 PCs (wired, DHCP enabled)
  - 1 Smartphone (wireless, WPA2 + DHCP enabled)

## Lab Objectives
- Configure a DHCP server on the router to assign IP addresses dynamically
- Enable SSH for secure remote access to the router
- Configure wireless access point (AP) with WPA2-PSK for smartphone connectivity
- Verify DHCP works on both wired and wireless clients

## Tools Used
- Cisco Packet Tracer
- 1 Router (Cisco 4331)
- 1 Switch
- 1 Access Point (AP-PT)
- PCs and Smartphone

## Tasks Performed
1. Basic Router Configuration
   - Assigned IP address to router interface (default gateway)
   - Enabled SSH login (username, password, domain, RSA key)

2. DHCP Configuration
   - Defined DHCP pool for LAN
   - Configured default gateway and DNS server
   - Verified IP assignment for PCs and smartphone

3. Access Point Setup
   - Configured SSID: NATSSH10
   - Enabled WPA2-PSK with pre-shared key
   - Connected smartphone using wireless

4. Verification
   - Used ipconfig on PCs and smartphone to confirm DHCP lease
   - Tested connectivity via ping
   - Verified secure remote login using: ssh -l admin <router-ip>

## Files Included
- DHCP-SSH-LAN.pkt – Cisco Packet Tracer topology
- Router_Config.txt – DHCP and SSH configuration for router
- PC_Configs.txt – Wired PC settings (DHCP assigned)
- Wireless_Config.txt – AP + smartphone settings

## Learning Outcomes
- How to configure DHCP for mixed wired + wireless networks
- Secure router management using SSH instead of Telnet
- Setting up wireless access with WPA2-PSK
- Troubleshooting DHCP and wireless connectivity issues
