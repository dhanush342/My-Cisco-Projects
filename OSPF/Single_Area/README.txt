# OSPF Single Area Routing Lab using Cisco Routers

This project demonstrates a Single Area OSPF routing setup using Cisco routers in Cisco Packet Tracer. The lab simulates routing between three departments across three routers, configured under Area 0.

## Topology Overview

- All routers operate under **OSPF Area 0**
- **Router0** (HR department): 192.168.10.0
- **Router1** (Marketing department): 192.168.20.0
- **Router2** (Customer Support): 192.168.30.0
- Each router is connected via serial links forming a full mesh topology

## IP Addressing Scheme

| Device       | Interface     | IP Address         | Description       |
|--------------|---------------|--------------------|-------------------|
| Router0      | LAN (G0/0)    | 192.168.10.1       | HR LAN            |
| Router0      | S0/0/0        | 192.168.40.1       | Link to Router1   |
| Router0      | S0/0/1        | 192.168.60.1       | Link to Router2   |
| Router1      | LAN (G0/0)    | 192.168.20.1       | Marketing LAN     |
| Router1      | S0/0/0        | 192.168.40.2       | Link to Router0   |
| Router1      | S0/0/1        | 192.168.50.1       | Link to Router2   |
| Router2      | LAN (G0/0)    | 192.168.30.1       | Customer Support  |
| Router2      | S0/0/0        | 192.168.50.2       | Link to Router1   |
| Router2      | S0/0/1        | 192.168.60.2       | Link to Router0   |

## OSPF Configuration (Sample)

```bash
Router(config)# router ospf 1
Router(config-router)# network 192.168.10.0 0.0.0.255 area 0
Router(config-router)# network 192.168.40.0 0.0.0.3 area 0
Router(config-router)# network 192.168.60.0 0.0.0.3 area 0
