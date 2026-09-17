# VLAN Network Lab (Single and Dual VLAN - Switch-Based)

### Description

This lab demonstrates two VLAN topologies using only Layer 2 switches in Cisco Packet Tracer:

1. **Single VLAN Setup** – All devices are part of the same VLAN and can communicate freely.
2. **Dual VLAN Setup** – Devices are placed in two separate VLANs to simulate network segmentation. Communication between VLANs is restricted by design.

This lab helps visualize how VLANs isolate broadcast domains and enhance network security and structure.

### Lab Objectives

- Understand the difference between single and multiple VLAN configurations
- Learn how to create VLANs and assign ports on a switch
- Observe communication behavior within and across VLANs
- Practice static IP addressing and ping testing

### Tools Used

- Cisco Packet Tracer
- Layer 2 Switches
- PCs

### Tasks Performed

#### Single VLAN:
- All switch ports were assigned to a single VLAN, used by three departments: Customer Support, Product Development, and Sales
- Devices were configured with static IPs in the same subnet
- Verified full connectivity between all devices

#### Dual VLAN:
- Two VLANs were created for three departments: HR, Marketing, and Sales
  - One VLAN was dedicated to the Executive Team
  - One VLAN was dedicated to the Associate Team
- Assigned switch ports to their respective VLANs
- Configured static IPs in separate subnets
- Verified communication within the same VLAN
- Confirmed isolation between devices in different VLANs

### Files Included

- `VLAN.pkt` – Cisco Packet Tracer topology with both Single and Dual VLAN setups
- `Switch_Config.txt` – VLAN creation and port assignments
- `PC_Configs.txt` – IP details for each host

### Learning Outcomes

- Understanding VLANs in Layer 2 networks
- Difference between flat networks and segmented networks
- Impact of VLANs on traffic isolation and broadcast control
- Improved hands-on CLI practice with switch configuration

