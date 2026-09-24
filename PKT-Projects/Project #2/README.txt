================================================================================
PROJECT #2: MULTI-AREA ENTERPRISE CAMPUS NETWORK DESIGN
================================================================================

OVERVIEW:
This project simulates a resilient, multi-site enterprise campus network spanning 
four regional operational zones (Area 1, Area 2, Area 3, Area 4) interconnected by a 
high-availability 4-router meshed core backbone. Each area operates its own localized 
access switch, dedicated DHCP server, and departmental workstation endpoints.

NETWORK ARCHITECTURE & TOPOLOGY:
1. Core Mesh WAN Backbone:
   - 4x Cisco 2911 Integrated Services Routers (ISR):
     * Router3 (South-West Core)
     * Router3(1) (South-East Core)
     * Router3(2) (North-West Core)
     * Router3(1)(1) (North-East Core)
   - Redundant point-to-point interconnect subnets:
     * WAN Link 1: 192.168.4.0/30 (Router3(2) <-> Router3(1)(1))
     * WAN Link 2: 192.168.5.0/30 (Router3(2) <-> Router3)
     * WAN Link 3: 192.168.6.0/30 (Router3 <-> Router3(1))
     * WAN Link 4: 192.168.7.0/30 (Router3(1) <-> Router3(1)(1))
     * WAN Link 5 (Diagonal Cross-Mesh): 192.168.8.0/30 (Router3(2) <-> Router3(1))

2. Regional Enterprise Campus Areas:
   - Area 1 (South-West Campus):
     * Subnet: 192.168.0.0/24
     * Gateway: Router3 FastEthernet/Gigabit interface
     * Switch: Cisco Catalyst 2960-24TT (Switch0)
     * End Devices: Laptop 1A1, Laptop 2A1, Laptop 3A1
     * Local Server: Server-PT (DHCP 1) providing dynamic addressing
   - Area 2 (North-West Campus):
     * Subnet: 192.169.1.0/24
     * Gateway: Router3(2) FastEthernet/Gigabit interface
     * Switch: Cisco Catalyst 2960-24TT (Switch0(2))
     * End Devices: Laptop 1A2, Laptop 2A2, Laptop 3A2
     * Local Server: Server-PT (DHCP 2) providing dynamic addressing
   - Area 3 (South-East Campus):
     * Subnet: 192.168.2.0/24
     * Gateway: Router3(1) FastEthernet/Gigabit interface
     * Switch: Cisco Catalyst 2960-24TT (Switch0(1))
     * End Devices: Laptop 1A3, Laptop 2A3, Laptop 3A3
     * Local Server: Server-PT (DHCP 3) providing dynamic addressing
   - Area 4 (North-East Campus):
     * Subnet: 192.168.3.0/24
     * Gateway: Router3(1)(1) FastEthernet/Gigabit interface
     * Switch: Cisco Catalyst 2960-24TT (Switch0(1)(1))
     * End Devices: Laptop 1A4, Laptop 2A4, Laptop 3A4
     * Local Server: Server-PT (DHCP 4) providing dynamic addressing

KEY TECHNICAL COMPETENCIES:
- Redundant multi-path core topology preventing single points of failure (SPOF)
- Dynamic route convergence across primary and alternate WAN links
- Subnet planning and localized DHCP infrastructure
- End-to-end Layer 3 inter-campus connectivity verification
================================================================================
