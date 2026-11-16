Cisco Packet Tracer Enterprise Network Labs 🌐

This repository showcases practical networking labs, topologies, and configurations built in **Cisco Packet Tracer** as part of my CCNA certification preparation. Each folder contains the original `.pkt` simulation file alongside full documentation, configuration snippets, and verification screenshots.

Lab Directory

1. **[Lab 01: Inter-VLAN Routing & DHCP Configuration](./Lab01-InterVLAN-Routing)**

 Featured Lab: Inter-VLAN Routing & DHCP

 Objective
Design and configure a segmented small-office network across three departments (IT, HR, and Sales) using Router-on-a-Stick (ROAS) to enable inter-VLAN communication and centralized DHCP IP address allocation.

Network Topology
![Inter-VLAN Topology Diagram]
<img width="1408" height="658" alt="image 1" src="https://github.com/user-attachments/assets/f3f4e2b8-0450-465c-8a30-99c25b46c010" />

*(Tip: Upload your screenshot into an `images` folder in your repo and match the filename above)*

 Key Skills & Protocols Demonstrated
* **Subnetting (VLSM):** Calculated subnet masks for 3 distinct departmental VLANs (`VLAN 10`, `VLAN 20`, `VLAN 30`).
* **Switch Configuration:** Configured access ports, 802.1Q trunking, and native VLAN security.
* **Router-on-a-Stick (ROAS):** Configured sub-interfaces (`Gig0/0.10`, `Gig0/0.20`, `Gig0/0.30`) with dot1Q encapsulation.
* **DHCP Pools:** Configured automated IP assignment and excluded static gateway addresses.

Key Configuration Snippet
```ios
! Router Sub-Interface & DHCP Configuration
interface GigabitEthernet0/0.10
 description IT_Department_VLAN10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
!
ip dhcp excluded-address 192.168.10.1 192.168.10.10
ip dhcp pool IT_POOL
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 8.8.8.8
