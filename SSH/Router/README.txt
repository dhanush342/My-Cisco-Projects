# Router SSH Lab – Multi-Device Network

Description:
# This lab demonstrates configuring a Cisco router to provide
# SSH-based remote management access and DHCP-based automatic
# IP assignment for multiple devices. PCs connect through a
# switch to a central router. The goal is to simulate secure
# device management in a small enterprise network environment.

Topology Overview:
# Router (R1)      - DHCP and SSH access
#                    LAN Network: 192.168.50.0/24
#                    Router IP: 192.168.50.1
# Switch           - Connects all client devices
# PCs (Clients)    - SSH clients and DHCP clients

 Lab Objectives:
1. Configure DHCP on the router to assign IP addresses automatically
2. Enable SSH access for secure remote CLI management
3. Test SSH connectivity from multiple PCs
4. Verify interface configuration and device communication

 Tools Used:
# Cisco Packet Tracer
# Router (Cisco 2911 or similar)
# Switch
# PCs

#Tasks Performed:
# Configured router hostname and interface IP
# Set up DHCP pool to provide IPs to clients
# Enabled SSH:
#     - Configured domain name
#     - Created local username and password
#     - Generated RSA key
#     - Configured VTY lines for SSH login
# Tested SSH connectivity from multiple PCs
# Verified interface status using `show ip interface brief`
# -hecked SSH configuration using `show ssh`
# Saved running configuration to startup configuration

# Files Included:
# - Router-SSH-Lab.pkt      # Cisco Packet Tracer topology
# - CLI_Commands.txt        # Complete router configuration commands
# - Outputs/                # Screenshots of SSH login & interface verification

Learning Outcomes:
# Configure DHCP on Cisco routers
# Enable secure SSH access on network devices
# Test remote connectivity in a LAN
# Understand router-based service hosting

