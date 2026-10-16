CMPG325 — Mafikeng Game Reserve Lodges Network

Project ID:CMPG325-2026-061  
Client ID:CLI-061  
Assigned technical challenge:IEEE 802.1Q VLAN trunking  
Addressing block: `10.28.0.0/16`

Project overview

This repository contains the Cisco Packet Tracer implementation, technical report, and evidence for the Mafikeng Game Reserve Lodges network project. The design uses departmental VLANs, 802.1Q trunks between switches, a multilayer core switch for inter-VLAN routing, and two simulated external routing paths.

Repository contents

- `Milestone 2.pkt` — Cisco Packet Tracer project file.
- `Technical_Documentation.docx` — technical implementation report.
- `Evidence_Audit.docx` — audit of the existing 12 screenshots and the remaining proof needed.

Verified configuration evidence

The CLI outputs reviewed during final preparation showed:

- Core `Fa0/1` and `Fa0/2`, and access-switch trunks, operating with `802.1q` encapsulation and status `trunking`.
- VLANs `10`, `20`, `30`, `40`, `50`, and `99` active and forwarding on the observed trunk links.
- Core SVIs `10.28.10.1`, `10.28.20.1`, `10.28.30.1`, `10.28.40.1`, `10.28.50.1`, and `10.28.99.1` reporting `up/up`.
- A default route on the core via `10.28.254.1`.

These outputs verify the displayed switch/trunk and core-routing configuration. They do **not** alone prove all endpoint paths or successful failover. See the report for limitations and evidence notes.

 VLAN and addressing summary

| VLAN | Observed label | Gateway | Subnet |
|---:|---|---|---|
| 10 | Management | `10.28.10.1` | `10.28.10.0/24` |
| 20 | Finance | `10.28.20.1` | `10.28.20.0/24` |
| 30 | Sales | `10.28.30.1` | `10.28.30.0/24` |
| 40 | `VLAN0040` on core/ACCESS-SW1; `HR` on ACCESS-SW2 | `10.28.40.1` | `10.28.40.0/24` |
| 50 | Guest_Services | `10.28.50.1` | `10.28.50.0/24` |
| 99 | Network_Management | `10.28.99.1` | `10.28.99.0/24` |

