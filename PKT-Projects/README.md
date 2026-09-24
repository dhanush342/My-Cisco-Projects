# 🏢 Enterprise Network Design Projects (`PKT-Projects`)

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco%20Packet%20Tracer-v8.0%2B-049cdb?style=flat-square&logo=cisco&logoColor=white)](https://www.netacad.com/courses/packet-tracer)
[![Category](https://img.shields.io/badge/Domain-Enterprise%20Network%20Architecture-1f8b4c?style=flat-square&logo=wireguard&logoColor=white)](https://github.com/dhanush342/My-Cisco-Projects)
[![Projects Included](https://img.shields.io/badge/Projects-5%20Production%20Designs-blueviolet?style=flat-square)](https://github.com/dhanush342/My-Cisco-Projects)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](../LICENSE)

This directory features five full-scale enterprise network simulation architectures engineered in **Cisco Packet Tracer**. Each project addresses real-world industry scenarios—ranging from branch office inter-VLAN routing to high-availability multi-ISP trading floors, multi-area campus cores, multi-story commercial banking systems, and tiered hospitality infrastructure.

---

## 📑 Projects Matrix

| Project | Target Industry & Scenario | Core Technologies & Protocols | Device Stack | Topology Diagram |
|---|---|---|---|:---:|
| **[Project #1](#project-1-small-office-branch-network-design)** | Food Supply Branch Office (Ridoine Co., Australia) | Router-on-a-Stick, VLANs, DHCP Server, Departmental Wi-Fi APs | 1x Cisco Router, 1x Switch, 3x APs, Endpoints | [View](#project-1-small-office-branch-network-design) |
| **[Project #2](#project-2-multi-area-enterprise-campus-network-design)** | Multi-Site Enterprise Campus (4 Regional Areas) | 4-Router Mesh WAN Backbone, Redundant Links, Dedicated DHCP Servers | 4x Cisco 2911 Routers, 4x 2960 Switches, 4x Servers, 12x Laptops | [View](#project-2-multi-area-enterprise-campus-network-design) |
| **[Project #3](#project-3-4-story-commercial-banking--insurance-system)** | 4-Story Commercial Banking & Insurance (Radeon Bank, Kenya) | OSPF Routing, Sticky Port-Security, SSH Remote Hardening, HTTP & Email Servers | Cisco Routers, Access Switches, Servers, Departmental APs | [View](#project-3-4-story-commercial-banking--insurance-system) |
| **[Project #4](#project-4-high-availability-trading-floor-support-centre)** | Mission-Critical Financial Trading Support Floor (600 Staff) | Dual ISP WAN Redundancy, Multilayer Core Switching, OSPF, NAT/PAT, ACLs | 2x ISP Routers, 2x Edge Routers, 2x Multilayer Switches, Servers | [View](#project-4-high-availability-trading-floor-support-centre) |
| **[Project #5](#project-5-vic-modern-hotel-3-tier-hospitality-network)** | 3-Floor Modern Hotel & Hospitality Facility (Vic Hotel) | 8 Departmental VLANs, Router-on-a-Stick, Multi-Router OSPF, Floor Wi-Fi & DHCP | 3x Cisco Routers, 3x Access Switches, 3x APs, Network Printers | [View](#project-5-vic-modern-hotel-3-tier-hospitality-network) |

---

## 📌 Project Breakdowns

### Project #1: Small Office Branch Network Design
*Directory: [`./Project #1`](./Project%20%231)*

#### Business Scenario
Ridoine Company, a rapidly expanding global food trading corporation based in Eastern Australia with over 2 million customers, established an independent branch facility near Bonalbo. The branch requires departmental traffic segregation, seamless inter-department routing, dynamic IP addressing, and wireless connectivity.

#### Architecture Highlights
- **VLAN Segmentation**: Isolated broadcast domains for **Admin/IT**, **Finance/HR**, and **Customer Service/Reception**.
- **Inter-VLAN Routing**: Configured 802.1Q sub-interfaces using the Router-on-a-Stick (ROAS) methodology on a Cisco router.
- **Dynamic Addressing**: IOS DHCP server configured on the router delivering scoped IP pools, default gateways, and DNS settings.
- **Wireless Coverage**: Cisco Access Points deployed for each department providing cable-free access for mobile client endpoints.
- **Subnet Scheme**: Efficient subnetting based on the parent `192.168.1.0/24` block.

![Project 1 Topology](Project%20%231/Project%20%231.png)

---

### Project #2: Multi-Area Enterprise Campus Network Design
*Directory: [`./Project #2`](./Project%20%232)*

#### Business Scenario
A distributed enterprise organization requiring multi-campus site interconnection across four operational regional divisions (Area 1 through Area 4). The architecture demands robust WAN fault tolerance and localized services to ensure continuous operations in the event of link degradation.

#### Architecture Highlights
- **Redundant Meshed Core**: Four Cisco 2911 ISR routers interconnected via 5 point-to-point WAN links (`192.168.4.0/30`, `192.168.5.0/30`, `192.168.6.0/30`, `192.168.7.0/30`, and diagonal cross-link `192.168.8.0/30`).
- **Campus Area Distribution**:
  - **Area 1 (192.168.0.0/24)**: Cisco 2960 switch, dedicated local DHCP server, and workstation endpoints.
  - **Area 2 (192.169.1.0/24)**: Cisco 2960 switch, dedicated local DHCP server, and workstation endpoints.
  - **Area 3 (192.168.2.0/24)**: Cisco 2960 switch, dedicated local DHCP server, and workstation endpoints.
  - **Area 4 (192.168.3.0/24)**: Cisco 2960 switch, dedicated local DHCP server, and workstation endpoints.
- **Fault-Tolerant Routing**: Alternate path convergence ensuring zero downtime if any single inter-router link fails.

![Project 2 Topology](Project%20%232/Project%20%232.png)

---

### Project #3: 4-Story Commercial Banking & Insurance System
*Directory: [`./Project #3`](./Project%20%233)*

#### Business Scenario
Radeon Company Ltd., a US-owned banking and insurance institution, expanded operations into Africa with a brand-new 4-story commercial building in Nairobi, Kenya. The facility requires high-level security standards, segmented department operations, dynamic routing, and centralized application services.

#### Architecture Highlights
- **Dynamic Routing**: Single-Area OSPF deployed across core routing devices for rapid route convergence and optimal path selection.
- **Layer 2 Security**: Switchport **port-security** configured with sticky MAC address learning (`switchport port-security mac-address sticky`) and violation shutdown mode to prevent rogue device injection.
- **Infrastructure Hardening**: SSH v2 crypto keys configured across all routers, disabling Telnet, enforcing secret passwords, console banners, and disabling DNS lookup timeouts.
- **Application Services**: Dedicated HTTP intranet web server and centralized corporate E-mail server.
- **Wireless Mobility & DHCP**: Departmental wireless access points catering to ~60 users per department with automated DHCP lease management.

![Project 3 Topology](Project%20%233/Project%20%233.png)

---

### Project #4: High-Availability Trading Floor Support Centre
*Directory: [`./Project #4`](./Project%20%234)*

#### Business Scenario
A high-frequency trading floor support facility housing 600 financial operators relocating to a new enterprise building. Any network outage translates directly into financial loss; hence, redundant links, dual ISP uplinks, multilayer switching, and granular traffic controls are paramount.

#### Architecture Highlights
- **High-Availability Hierarchical Model**:
  - **Dual ISP Multihoming**: Redundant WAN links connecting two edge routers to two independent Internet Service Providers via public IP subnets (`195.136.17.0/30`, `195.136.17.4/30`).
  - **Core/Distribution Multilayer Switches**: Dual Layer 3 Catalyst switches performing wire-speed inter-VLAN routing, SVI termination, and hardware-switched packet forwarding.
- **Floor-wise Department Segmentation**:
  - **Floor 1**: Sales & Marketing (120 users), Human Resources & Logistics (120 users).
  - **Floor 2**: Finance & Accounts (120 users), Administration & Public Relations (120 users).
  - **Floor 3**: ICT Department (120 users) and Central Server Room (12 high-density servers).
- **Security & NAT Services**:
  - **Port Address Translation (PAT)**: Outbound address overload mapping private internal subnets (`172.16.1.0` supernet) to ISP routable addresses.
  - **Access Control Lists (ACL)**: Ingress/egress packet filtering protecting server room infrastructure.
  - **Sticky MAC Protection**: Strict port-security enforced on financial workstation access ports.

![Project 4 Topology](Project%20%234/Project%20%234.png)

---

### Project #5: Vic Modern Hotel 3-Tier Hospitality Network
*Directory: [`./Project #5`](./Project%20%235)*

#### Business Scenario
Vic Modern Hotel is a 3-floor luxury hospitality property requiring a converged data, guest Wi-Fi, administrative, and operations network connecting guest reception, point-of-sale store, logistics, finance, HR, executive admin, and IT.

#### Architecture Highlights
- **8 Dedicated Departmental VLANs**:
  - **Floor 1**: Reception (`VLAN 80`, `192.168.8.0/24`), Store (`VLAN 70`, `192.168.7.0/24`), Logistics (`VLAN 60`, `192.168.6.0/24`).
  - **Floor 2**: Finance (`VLAN 50`, `192.168.5.0/24`), HR (`VLAN 40`, `192.168.4.0/24`), Sales/Marketing (`VLAN 30`, `192.168.3.0/24`).
  - **Floor 3**: Admin (`VLAN 20`, `192.168.2.0/24`), IT (`VLAN 10`, `192.168.1.0/24`).
- **Dynamic Inter-Floor Routing**: OSPF configured across routers located in the server room, bridging the three floor switches with sub-second convergence.
- **Peripheral & Hospitality Services**: Dedicated network printers assigned per department, floor-wide guest/staff Wi-Fi coverage, and localized DHCP pools.
- **Physical Port Restriction**: Port security applied on the IT switch (`fa0/1`) locking management access to authorized technician endpoints.

![Project 5 Topology](Project%20%235/Project%20%235.png)

---

## 🛠 Simulation & Execution Guide
1. Launch **Cisco Packet Tracer** (version 8.0 or newer).
2. Open any project folder (e.g. `Project #4/`).
3. Double-click the `.pkt` file (e.g. `Project #4.pkt`).
4. Review the accompanying `README.txt` for the detailed project brief, IP scheme, and configuration commands.
5. Use **Simulation Mode** or terminal commands (`ping`, `traceroute`, `show ip route`) to verify operational behavior.

---

**Author:** [Nagineni Dhanush](https://github.com/dhanush342)  
Part of the [My-Cisco-Projects](https://github.com/dhanush342/My-Cisco-Projects) portfolio.