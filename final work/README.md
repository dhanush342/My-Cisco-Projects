# 🏢 Small-Scale Enterprise Office Network Design & Implementation
### 🎓 Final Capstone Networking Lab Project (Team Collaboration)

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco%20Packet%20Tracer-v8.0%2B-049cdb?style=for-the-badge&logo=cisco&logoColor=white)](https://www.netacad.com/courses/packet-tracer)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](../LICENSE)
[![Topology](https://img.shields.io/badge/Architecture-Dual--Router%20WAN%20Interconnect-1f8b4c?style=for-the-badge)](./SmallOfficeNetwork.pkt)

---

## 📌 Project Overview

This capstone project showcases the design, addressing, configuration, and verification of a **Small-Scale Enterprise Office Network** simulated in **Cisco Packet Tracer**. Completed as a collaborative final laboratory project with my team, this project integrates multiple functional departments and a dedicated server room interconnected across two enterprise routers via a high-speed Serial WAN link.

The project demonstrates real-world networking principles including **hierarchical departmental design**, **static routing across point-to-point serial interfaces**, **default gateway path resolution**, **dedicated network printer sharing**, and **end-to-end multi-subnet connectivity**.

---

## 🖼️ Network Topology Diagram

![Small Office Network Topology](final%20output.png)

---

## 🏛️ Network Architecture & Departmental Layout

The office network is divided into four distinct organizational zones spanning two routers connected via a Serial WAN connection:

```
                                  [ Serial WAN Link (10.0.0.0/8) ]
                               Se2/0 (10.0.0.1) <========> Se2/0 (10.0.0.2)
                            +--------------------+        +--------------------+
                            |   Router-PT Main   |        |  Router-PT Router-1|
                            +---------+----------+        +----------+---------+
                                      |                              |
                   +------------------+--------------+   +-----------+--------------------+
                   |                                 |   |                                |
             Fa1/0 (192.168.3.1)           Fa0/0 (1.0.0.1)  Fa1/0 (192.168.2.1)    Fa0/0 (192.168.1.1)
                   |                                 |   |                                |
        [ Computer Department Switch ]          [ Switch 1 ] [ IT Department Switch ]   [ Chairman Switch ]
                   |                                 |   |                                |
        - Employee Computers 1, 2, 3           - Server0   - Employee Computers 4, 5      - Chairman PC
        - Manager Computer 1                   - Laptop0   - Manager Computer 2           - VC Computer
        - Dept Network Printer                             - IT Network Printer
```

---

## 📊 Comprehensive IP Addressing & Port Allocation Matrix

| Department / Zone | Device Name | Device Type | Interface | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|---|---|---|
| **Computer Department** (`192.168.3.0/24`) | **Router-PT Main** | Cisco Router | `Fa1/0` | `192.168.3.1` | `255.255.255.0` | N/A |
| | Computer Dept Switch | Catalyst Switch | `Fa0/1` | Unmanaged L2 | `255.255.255.0` | N/A |
| | Employee Computer 1 | Desktop PC | `Fa0` | `192.168.3.2` | `255.255.255.0` | `192.168.3.1` |
| | Employee Computer 2 | Desktop PC | `Fa0` | `192.168.3.3` | `255.255.255.0` | `192.168.3.1` |
| | Employee Computer 3 | Desktop PC | `Fa0` | `192.168.3.4` | `255.255.255.0` | `192.168.3.1` |
| | Manager Computer 1 | Desktop PC | `Fa0` | `192.168.3.5` | `255.255.255.0` | `192.168.3.1` |
| | Computer Dept Printer | Network Printer | `Fa0` | `192.168.3.6` | `255.255.255.0` | `192.168.3.1` |
| **Server Room** (`1.0.0.0/8`) | **Router-PT Main** | Cisco Router | `Fa0/0` | `1.0.0.1` | `255.0.0.0` | N/A |
| | Switch 1 | Catalyst Switch | `Fa0/1` | Unmanaged L2 | `255.0.0.0` | N/A |
| | Server0 | Enterprise Server | `Fa0` | `1.0.0.2` | `255.0.0.0` | `1.0.0.1` |
| | Laptop0 | Admin Laptop | `Fa0` | `1.0.0.3` | `255.0.0.0` | `1.0.0.1` |
| **IT Department** (`192.168.2.0/24`) | **Router-PT Router-1** | Cisco Router | `Fa1/0` | `192.168.2.1` | `255.255.255.0` | N/A |
| | IT Dept Switch | Catalyst Switch | `Fa0/1` | Unmanaged L2 | `255.255.255.0` | N/A |
| | Employee Computer 4 | Desktop PC | `Fa0` | `192.168.2.2` | `255.255.255.0` | `192.168.2.1` |
| | Employee Computer 5 | Desktop PC | `Fa0` | `192.168.2.3` | `255.255.255.0` | `192.168.2.1` |
| | Manager Computer 2 | Desktop PC | `Fa0` | `192.168.2.4` | `255.255.255.0` | `192.168.2.1` |
| | IT Dept Printer | Network Printer | `Fa0` | `192.168.2.5` | `255.255.255.0` | `192.168.2.1` |
| **Chairman Room** (`192.168.1.0/24`) | **Router-PT Router-1** | Cisco Router | `Fa0/0` | `192.168.1.1` | `255.255.255.0` | N/A |
| | Chairman Switch | Catalyst Switch | `Fa0/1` | Unmanaged L2 | `255.255.255.0` | N/A |
| | Chairman Computer | Executive PC | `Fa0` | `192.168.1.2` | `255.255.255.0` | `192.168.1.1` |
| | VC Computer | Executive PC | `Fa0` | `192.168.1.3` | `255.255.255.0` | `192.168.1.1` |
| **Serial WAN Interconnect** (`10.0.0.0/8`) | **Router-PT Main** | Cisco Router | `Se2/0` | `10.0.0.1` | `255.0.0.0` | N/A |
| | **Router-PT Router-1** | Cisco Router | `Se2/0` | `10.0.0.2` | `255.0.0.0` | N/A |

---

## ⚙️ Router Configuration & Static Routing Implementation

### 1. Router-PT Main Configuration
```cisco
Router> enable
Router# configure terminal
Router(config)# hostname Router-Main

! Configure FastEthernet 0/0 (Server Room)
Router-Main(config)# interface FastEthernet 0/0
Router-Main(config-if)# ip address 1.0.0.1 255.0.0.0
Router-Main(config-if)# no shutdown
Router-Main(config-if)# exit

! Configure FastEthernet 1/0 (Computer Department)
Router-Main(config)# interface FastEthernet 1/0
Router-Main(config-if)# ip address 192.168.3.1 255.255.255.0
Router-Main(config-if)# no shutdown
Router-Main(config-if)# exit

! Configure Serial 2/0 (WAN Interconnect DCE)
Router-Main(config)# interface Serial 2/0
Router-Main(config-if)# ip address 10.0.0.1 255.0.0.0
Router-Main(config-if)# clock rate 64000
Router-Main(config-if)# no shutdown
Router-Main(config-if)# exit

! Configure Static Routes to Router-1's subnets
Router-Main(config)# ip route 192.168.1.0 255.255.255.0 10.0.0.2
Router-Main(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2
Router-Main(config)# exit
Router-Main# write memory
```

### 2. Router-PT Router-1 Configuration
```cisco
Router> enable
Router# configure terminal
Router(config)# hostname Router-1

! Configure FastEthernet 0/0 (Chairman Room)
Router-1(config)# interface FastEthernet 0/0
Router-1(config-if)# ip address 192.168.1.1 255.255.255.0
Router-1(config-if)# no shutdown
Router-1(config-if)# exit

! Configure FastEthernet 1/0 (IT Department)
Router-1(config)# interface FastEthernet 1/0
Router-1(config-if)# ip address 192.168.2.1 255.255.255.0
Router-1(config-if)# no shutdown
Router-1(config-if)# exit

! Configure Serial 2/0 (WAN Interconnect DTE)
Router-1(config)# interface Serial 2/0
Router-1(config-if)# ip address 10.0.0.2 255.0.0.0
Router-1(config-if)# no shutdown
Router-1(config-if)# exit

! Configure Static Routes to Router-Main's subnets
Router-1(config)# ip route 192.168.3.0 255.255.255.0 10.0.0.1
Router-1(config)# ip route 1.0.0.0 255.0.0.0 10.0.0.1
Router-1(config)# exit
Router-1# write memory
```

---

## 🧪 Testing & Verification

1. **Intra-Subnet Verification (Same Department):**
   - Ping between `Employee Computer 1` (`192.168.3.2`) and `Manager Computer 1` (`192.168.3.5`): **0% packet loss**.
   - Printing job test from `Employee Computer 2` to `Computer Dept Printer` (`192.168.3.6`): **Successful**.

2. **Inter-Department Gateway Verification:**
   - Workstation ping to default gateway (`192.168.3.1` or `192.168.2.1`): **Successful**.

3. **Cross-WAN End-to-End Connectivity:**
   - Chairman PC (`192.168.1.2`) to Server0 (`1.0.0.2`): **Successful**.
   - IT Manager Computer 2 (`192.168.2.4`) to Employee Computer 1 (`192.168.3.2`): **Successful**.
   - Admin Laptop (`1.0.0.3`) to IT Department Printer (`192.168.2.5`): **Successful**.

4. **Routing Table Inspection:**
   ```cisco
   Router-Main# show ip route
   Codes: C - connected, S - static, R - RIP, M - mobile, B - BGP
   Gateway of last resort is not set

   C    1.0.0.0/8 is directly connected, FastEthernet0/0
   C    10.0.0.0/8 is directly connected, Serial2/0
   S    192.168.1.0/24 [1/0] via 10.0.0.2
   S    192.168.2.0/24 [1/0] via 10.0.0.2
   C    192.168.3.0/24 is directly connected, FastEthernet1/0
   ```

---

## 🚀 How to Run This Project

1. Install **Cisco Packet Tracer** (version 8.0 or newer).
2. Open the project file: [`SmallOfficeNetwork.pkt`](./SmallOfficeNetwork.pkt).
3. Switch between **Realtime Mode** and **Simulation Mode** (bottom right toolbar) to trace packet flow (ICMP PDUs).
4. Click on any PC -> Open **Command Prompt** -> Execute `ping 1.0.0.2` or `ping 192.168.1.2` to observe the round-trip replies.

---

## 👥 Project Team & Contributors

- **Nagineni Dhanush** (Team Lead & Network Architect)
- **Collaborating Team Members** (Academic Capstone Group)
- **Institution:** Department of Computer Science & Engineering / Information Technology
- **Mentorship:** Coursework Faculty & Networking Lab Instructors

---

## 📜 License

This capstone project is licensed under the [MIT License](../LICENSE). Feel free to reference this topology and configuration for academic study and network architecture practice.
