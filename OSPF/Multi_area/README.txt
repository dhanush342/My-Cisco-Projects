# OSPF Multi-Area Routing Lab using Cisco Routers

This project demonstrates a Multi-Area OSPF configuration using Cisco routers in Cisco Packet Tracer. The lab simulates inter-area routing with proper area segmentation, full connectivity, and efficient routing.

## Topology Overview

- Area 0 (Backbone):
  - Router2

- Area 1:
  - Router0 (with LAN: 192.168.41.0/24)
  - Router1 (Area Border Router)

- Area 2:
  - Router4 (with LAN: 192.168.35.0/24)
  - Router3 (Area Border Router)

- End Devices:
  - PC0–PC2 in Area 1
  - PC3–PC5 in Area 2

- Switches:
  - One switch in each LAN

## IP Addressing Scheme

| Device       | Interface     | IP Address         | Area     |
|--------------|---------------|--------------------|----------|
| Router0      | LAN (G0/0)    | 192.168.41.1       | Area 1   |
| Router0      | S0/0/0        | 10.1.0.1           | Area 1   |
| Router1      | S0/0/0        | 10.1.0.2           | Area 1   |
| Router1      | S0/0/1        | 172.17.10.1        | Area 0   |
| Router2      | S0/0/0        | 172.17.10.2        | Area 0   |
| Router2      | S0/0/1        | 172.18.10.1        | Area 0   |
| Router3      | S0/0/0        | 172.18.10.2        | Area 0   |
| Router3      | S0/0/1        | 172.19.10.1        | Area 2   |
| Router4      | S0/0/0        | 172.19.10.2        | Area 2   |
| Router4      | LAN (G0/0)    | 192.168.35.1       | Area 2   |

## OSPF Configuration

Below is a sample OSPF configuration used on one of the routers:

```bash
Router(config)# router ospf 1
Router(config-router)# network 192.168.41.0 0.0.0.255 area 1
Router(config-router)# network 10.1.0.0 0.0.0.255 area 1
