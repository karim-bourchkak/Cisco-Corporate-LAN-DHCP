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
### 2. DHCP Pool Deployment
```text
Router(config)# ip dhcp pool LAN-POOL
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.1.1
Router(dhcp-config)# exit
Router(config)# do write memory
```
---

## Proof of Work & Verification
- **DHCP Leasing:** Client PCs automatically requested and obtained valid network configurations within the `192.168.1.0/24` scope.
- **ICMP Reachability:** Successful `ping` tests confirmed full layer 3 connectivity between end devices and the default gateway (`192.168.1.1`).

### Network Topology & Verification Screenshots
![Network Topology](Screenshot%202026-09-25%20143504.png)
![Ping Test Verification](Screenshot%202026-09-25%20143530.png)
