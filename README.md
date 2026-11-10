# Enterprise-Edge-Routing-and-NAT-PAT-Gateway

Built an enterprise-grade network simulation in Cisco Packet Tracer to demonstrate core routing, Layer 2/Layer 3 segmentation, and perimeter NAT/PAT services. This project models a corporate branch office environment where multiple internal departments share a single public WAN interface to reach an external ISP server.


## Addressing

| Network | Subnet | Gateway |
|---|---|---|
| VLAN 10 (Sales) | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 (Engineering) | 192.168.20.0/24 | 192.168.20.1 |
| WAN link | 203.0.113.0/30 | Router0 is .1, Server0 is .2 |

## Configured:
- Created VLANs 10 and 20 on the switch and made the port to the router a trunk.
- Used router-on-a-stick: subinterfaces Gig0/0.10 and Gig0/0.20 act as the gateways.
- Set up PAT with an ACL for both subnets and `overload` on the WAN interface, so everything shows up as 203.0.113.1.
- Added a default route to the server.

## Test and Verified: 
- Pinged PCs in the same VLAN, then across VLANs.
- Pinged the server from both VLANs.
- Checked `show interfaces trunk` and `show ip nat translations` on the router and switch.

