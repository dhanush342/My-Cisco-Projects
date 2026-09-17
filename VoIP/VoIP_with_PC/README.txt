VoIP with DHCP and SSH – Cisco Packet Tracer Lab

Description
This lab demonstrates configuring a Cisco network with VoIP telephony, automatic IP addressing via DHCP, and secure remote management via SSH.
The setup includes IP phones, PCs, and networking devices connected in a LAN environment to simulate a small office scenario.

Topology Overview
- Router (R1) – Acts as the DHCP server and provides SSH access for remote management.
  LAN Network: 192.168.20.0
  Default Gateway: 192.168.20.1

- Switches – Provide LAN connectivity for phones and PCs.
- IP Phones – Automatically receive IP addresses via DHCP and register with the router’s telephony service.
- PCs – Used for testing network connectivity and SSH access.

Lab Objectives
- Configure DHCP on the router for IP phones and PCs.
- Set up telephony services on the router.
- Automatically assign phone numbers to IP phones.
- Configure SSH for secure management.
- Verify VoIP call functionality and SSH access.

Tools Used
- Cisco Packet Tracer
- Cisco Router (2811/2911 with telephony capability)
- Switches
- IP Phones
- PCs

Tasks Performed
- Assigned IP addresses to router interfaces.
- Configured DHCP pools for LAN devices.
- Enabled and configured router telephony service.
- Configured ephone-dn and ephones for IP phone registration.
- Enabled SSH with local authentication.
- Verified IP phone connectivity and successful voice calls.
- Tested SSH login from a PC.

Files Included
- VoIP-DHCP-SSH.pkt – Cisco Packet Tracer topology file.
- CLI_Commands.txt – Complete router configuration commands.
- outputs/ – Folder containing screenshots of working VoIP calls and SSH sessions.

Learning Outcomes
- How to configure VoIP telephony on Cisco routers.
- DHCP configuration for both PCs and IP phones.
- SSH setup and secure remote access.
- Integrating multiple services in a single network.

