# CAMPUS-NETWORK-vLAN-ROUTING
A simulated enterprise campus network designed and tested in *Cisco Packet Tracer*. This project demonstrates how to segment network traffic using Virtual LANs (VLANs), configure 802.1Q trunking, and enable cross-subnet communication using Router-on-a-Stick (Inter-VLAN Routing).

📄 *[Read the Full Case Study & Test Evidence (PDF)]([Campus_Network_Project_Case_Study (2).pdf](https://github.com/user-attachments/files/35109392/Campus_Network_Project_Case_Study.2.pdf)
)*

---

## 🎯 Project Overview
Flat networks suffer from excessive broadcast traffic and lack department-level security isolation. In this lab, I segmented a multi-department campus network into three isolated VLANs and configured a central router to manage controlled traffic between them.

### Key Technologies & Concepts
* *Network Simulation:* Cisco Packet Tracer
* *Switching:* VLAN creation (VLAN 10, 20, 30), Access port assignment, 802.1Q Trunking (Fa0/24)
* *Routing:* Inter-VLAN Routing (Router-on-a-Stick) using subinterfaces
* *Verification & Troubleshooting:* Cisco IOS CLI (show vlan brief, show interfaces trunk, show ip route, ICMP ping)

---

## 🏗️ Network Architecture
* *Switch (SW1):* Manages local host access ports and forwards tagged multi-VLAN traffic over uplink port Fa0/24.
* *Router (R1):* Acts as the default gateway for all three VLANs via virtual subinterfaces.
* *End Devices (PC1 – PC4):* Distributed across separate VLANs to test intra-VLAN isolation and inter-VLAN reachability.

| VLAN ID | Department / Role | Subnet / Gateway | Assigned Ports |
| :--- | :--- | :--- | :--- |
| *VLAN 10* | [e.g., Admin / Staff] | [e.g., 192.168.10.0/24] | [e.g., Fa0/1 - Fa0/5] |
| *VLAN 20* | [e.g., Students / HR] | [e.g., 192.168.20.0/24] | [e.g., Fa0/6 - Fa0/10] |
| *VLAN 30* | [e.g., IT / Servers] | [e.g., 192.168.30.0/24] | [e.g., Fa0/11 - Fa0/15] |

---

## ✅ Testing & Verification Summary
To validate the configuration, I executed structured baseline and post-routing tests:

1. *VLAN & Trunk Verification (SW1):* Verified active VLAN assignments with show vlan brief and confirmed Fa0/24 was actively trunking VLANs 10, 20, 30 via show interfaces trunk.
2. *Pre-Routing Isolation Test:* Confirmed that intra-VLAN pings succeeded (PC1 -> PC2), while cross-VLAN pings failed prior to router configuration.
3. *Routing Table Check (R1):* Confirmed all 3 directly connected VLAN subinterfaces appeared in the routing table via show ip route.
4. *Post-Routing Connectivity:* Verified full end-to-end reachability across different VLANs (PC1 -> PC3 and PC4).

---

## 📂 Repository Contents
* Campus_Network_Case_Study.pdf — Complete documentation including topology diagrams, CLI configurations, test evidence screenshots, and troubleshooting notes.
* Campus_Network_Topology.pkt — Interactive Cisco Packet Tracer lab file.

---

## 🚀 How to Run the Lab
1. Download Campus_Network_Topology.pkt from this repository.
2. Open the file using *Cisco Packet Tracer* (v8.0 or newer recommended).
3. Open any PC desktop terminal and run ping commands across subnets to test live packet flow.

---

## 👤 Author
* *[RAHUL CHAUHAN]* — [Your LinkedIn Profile URL]
*
