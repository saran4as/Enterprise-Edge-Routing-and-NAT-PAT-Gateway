# Multi-VLAN Enterprise Edge & NAT/PAT Gateway Using Cisco Packet Tracer

## Project Overview
Designed and implemented an enterprise-grade network simulation connecting multiple departmental VLANs to a public WAN gateway using Cisco Packet Tracer. The project demonstrates Layer 2/Layer 3 VLAN segmentation, Router-on-a-Stick routing, static IP configuration, and Port Address Translation (PAT/Overload) for outbound internet access.

## Key Features
- VLAN-based network segmentation for departmental isolation
- Inter-VLAN Routing using Router-on-a-Stick (802.1Q trunking)
- Static IP addressing and default gateway configuration
- Perimeter NAT/PAT (NAT Overload) sharing a single public WAN IP
- Trunk and Access Port Configuration on Cisco Catalyst switches
- End-to-End Connectivity Testing between internal hosts and an external ISP server
- Network troubleshooting and translation table verification

## Network Architecture
- **VLAN 10 (Sales):** `192.168.10.0/24`
- **VLAN 20 (Engineering):** `192.168.20.0/24`
- **WAN / ISP Link:** `203.0.113.0/30` (Point-to-point connection to external Server)

All internal subnets connect through Cisco Catalyst switches via an 802.1Q trunk link to an edge router, which routes traffic between VLANs and translates private IPs to public space.

## NAT/PAT & Routing Configuration
Configured perimeter security and edge translation rules:
- Static Default Routing (`0.0.0.0/0`) directing traffic to the external ISP next-hop gateway (`203.0.113.2`).
- Standard Access Control List (ACL) to permit internal private subnets (`192.168.10.0/24` and `192.168.20.0/24`).
- Port Address Translation (PAT / NAT Overload) mapped to the external WAN interface (`203.0.113.1`) to enable multi-subnet internet egress.

## Technologies Used
- Cisco Packet Tracer
- VLANs & 802.1Q Trunking
- Router-on-a-Stick Inter-VLAN Routing
- NAT / PAT (Network Address Translation Overload)
- IPv4 Addressing & Static Routing
- Cisco Switching & Routing
- Network Troubleshooting & Verification

## Result
Successfully built a secure and functional enterprise edge network where isolated departmental subnets can seamlessly communicate internally and access external WAN destinations through centralized translation and routing.
