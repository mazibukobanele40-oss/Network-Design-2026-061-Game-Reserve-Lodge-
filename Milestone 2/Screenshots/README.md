# CMPG325 Network Design and Implementation

## Project Overview

This project involves the design and implementation of a routed and switched enterprise network using Cisco Packet Tracer.

The network uses VLAN segmentation, inter-VLAN routing, trunk links, static routing, and redundant ISP connections to provide connectivity between internal departments and external servers.

## Milestone 2

Milestone 2 implements the proposed network topology and activates the required network services and routing.

### Main Network Devices

* 1 × CORE-SW – Cisco 3560-24PS Multilayer Switch
* 2 × Access Switches – Cisco 2960-24TT
* 2 × Internal Routers – R1 and R2
* 2 × ISP Routers – ISP1 and ISP2
* 2 × Internet Servers
* Departmental and user devices

## VLAN Configuration

| VLAN | Name               | Network       | Default Gateway |
| ---- | ------------------ | ------------- | --------------- |
| 10   | Management         | 10.28.10.0/24 | 10.28.10.1      |
| 20   | Finance            | 10.28.20.0/24 | 10.28.20.1      |
| 30   | Reception          | 10.28.30.0/24 | 10.28.30.1      |
| 40   | Operations         | 10.28.40.0/24 | 10.28.40.1      |
| 50   | Guest Services     | 10.28.50.0/24 | 10.28.50.1      |
| 99   | Network Management | 10.28.99.0/24 | 10.28.99.1      |

## Routed Links

| Connection      | Network         |
| --------------- | --------------- |
| CORE-SW ↔ R1    | 10.28.254.0/30  |
| R1 ↔ ISP1       | 10.28.254.4/30  |
| CORE-SW ↔ R2    | 10.28.254.8/30  |
| R2 ↔ ISP2       | 10.28.254.12/30 |
| ISP2 ↔ Server 2 | 10.28.254.16/30 |
| ISP1 ↔ Server 1 | 10.28.254.20/30 |

## Core Switch

CORE-SW provides Layer 3 inter-VLAN routing using switched virtual interfaces (SVIs).

Configured gateways:

* VLAN 10: 10.28.10.1
* VLAN 20: 10.28.20.1
* VLAN 30: 10.28.30.1
* VLAN 40: 10.28.40.1
* VLAN 50: 10.28.50.1
* VLAN 99: 10.28.99.1

The access-switch connections use IEEE 802.1Q trunking.

## Static Routing

Static routes were configured between the CORE-SW, R1, R2, ISP1 and ISP2 to provide connectivity between the internal VLANs and the Internet server networks.

The network uses two paths:

**Path 1:**

CORE-SW → R1 → ISP1 → Server 1

**Path 2:**

CORE-SW → R2 → ISP2 → Server 2

## Connectivity Verification

The network was tested using ICMP ping tests.

The following connectivity was successfully verified:

* PC → Default Gateway
* PC → Server 1
* PC → Server 2
* CORE-SW → R1
* CORE-SW → R2
* R1 → ISP1
* R2 → ISP2
* ISP1 → Server 1
* ISP2 → Server 2
* Server 1 → R1
* Server 2 → R2

All final connectivity tests completed successfully with **0% packet loss**.

## Milestone 2 Evidence

The project includes screenshots showing:

1. Complete network topology
2. VLAN configuration
3. SVI configuration
4. Trunk configuration
5. CORE-SW routing table
6. R1 routing table
7. R2 routing table
8. ACCESS-SW1 configuration
9. ACCESS-SW2 configuration
10. End-to-end connectivity tests

## Project File

The final Cisco Packet Tracer project is:

`Milestone2.pkt`

## Conclusion

Milestone 2 successfully implements the proposed enterprise network topology. VLAN segmentation, inter-VLAN routing, trunking, static routing, ISP connectivity and end-to-end communication were configured and verified in Cisco Packet Tracer.

