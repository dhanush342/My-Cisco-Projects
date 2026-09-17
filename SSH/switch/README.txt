# Cisco Switch SSH Configuration Lab – Secure Remote Access

### Description
This lab demonstrates configuring a Cisco switch for secure remote access using SSH. 
The configuration includes setting up a management VLAN, assigning an IP address, 
creating local user accounts, and enabling SSH version 2 with encrypted credentials. 
The goal is to provide secure command-line management of the switch, avoiding insecure 
protocols like Telnet.

### Topology Overview
- Switch (SW1) – Configured for SSH remote management
  - Management VLAN: VLAN 1
  - Switch IP: 192.168.52.1

- PC – Used as the SSH client to access the switch

### Lab Objectives
- Assign a hostname to the switch
- Configure an encrypted enable password
- Create a local user account with encrypted password
- Assign an IP address to the management VLAN
- Generate RSA keys for SSH
- Enable SSH version 2 and restrict remote access to SSH only
- Save configuration to NVRAM

### Tools Used
- Cisco Packet Tracer
- Cisco Switch (IOS-based)
- PC for SSH client access

### Tasks Performed
- Set the switch hostname
- Configured `enable secret` for privileged EXEC mode
- Created a local user account with `secret` password
- Assigned IP address to VLAN 1 and enabled the interface
- Set domain name for RSA key generation
- Generated 2048-bit RSA keys
- Enabled SSH version 2
- Restricted VTY lines to SSH access only
- Saved configuration to NVRAM

### Files Included
- Switch-SSH-Lab.pkt – Cisco Packet Tracer topology
- CLI_Commands.txt – Complete switch configuration commands (sanitized with placeholders for passwords)

### Learning Outcomes
- How to configure SSH on Cisco switches
- Importance of using `enable secret` instead of `enable password`
- Restricting remote access to SSH only
- Managing devices securely over a network
- Understanding key generation and encryption in Cisco IOS
