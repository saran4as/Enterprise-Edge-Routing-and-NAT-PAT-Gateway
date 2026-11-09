# Multi-VLAN Office Network with Inter-VLAN Routing and PAT

A small office network I built in Cisco Packet Tracer. Sales and Engineering are on separate VLANs, one router connects them, and the same router does PAT so both VLANs can reach an outside server through a single public IP.

![Topology](Topology diagram.png)

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

