# Corporate LAN Architecture & Automated DHCP Implementation

## Overview
This project demonstrates the design and deployment of a small corporate Local Area Network (LAN) using Cisco Packet Tracer. The infrastructure provides dynamic IP addressing via a centralized router configured with DHCP services, enabling automatic network integration and client-to-gateway connectivity.

## Network Topology & Components
* **Router:** Cisco 1921 (Gateway & DHCP Server)
* **Switch:** Cisco Catalyst 2960
* **End Devices:** PC Workstations
* **Addressing Scheme:** `192.168.1.0/24` (Gateway: `192.168.1.1`)

---

## Technical Configuration (Cisco CLI)

### 1. Interface Gateway Setup
```text
Router> enable
Router# configure terminal
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
