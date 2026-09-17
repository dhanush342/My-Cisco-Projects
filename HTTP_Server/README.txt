# HTTP Server with DHCP Lab – Multi-Device Network

### Description

This lab demonstrates configuring a Cisco network to provide **automatic IP addressing via DHCP** and **web-based management access using HTTP/HTTPS**. The network includes multiple end devices such as laptops, printers, tablets, and smartphones, all connected through switches to a central router and server. The goal is to simulate real-world enterprise network services and device connectivity in Cisco Packet Tracer.

### Topology Overview

- **Router (R1)** – Provides DHCP service and HTTP/HTTPS access  
  - LAN Network: 192.168.170.0/24  
  - Router IP: 192.168.170.25  

- **Server** – HTTP/HTTPS service enabled

- **Switches** – Provide LAN connectivity for all devices

- **End Devices** – Laptops, Printers, Tablets, Smartphones (DHCP clients)

### Lab Objectives

- Configure DHCP on the router to assign IP addresses automatically
- Enable HTTP and HTTPS services for router GUI access
- Test connectivity between all devices in the LAN
- Access the router GUI from multiple devices using a web browser

### Tools Used

- Cisco Packet Tracer
- Router (Cisco 2911 with HTTP server support)
- Switches
- Server
- End Devices (Laptops, Printer, Tablets, Smartphones)

### Tasks Performed

- Assigned IP address to the router interface
- Configured DHCP pool to provide IPs to all clients
- Enabled HTTP and HTTPS services on the router
- (Optional) Configured local authentication for web access
- Verified automatic IP allocation for all devices
- Tested HTTP/HTTPS access from multiple devices
- Verified connectivity using `ping`

### Files Included

- HTTP-DHCP-Lab.pkt – Cisco Packet Tracer topology
- CLI_Commands.txt – Complete router configuration commands

### Learning Outcomes

- How to configure DHCP on Cisco routers
- Enabling and securing HTTP/HTTPS services on network devices
- Testing multi-device connectivity in a LAN
- Understanding router-based service hosting
