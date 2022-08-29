# Lab VLAN, LAG & FHRPs - 04 - Final
---

## Technologies covered:
- VLAN
- Private VLAN
- Inter-VLAN routing
- FHRP
- ACL
- PortSecurity
- DHCP Snooping
- ARP Snooping
- IP Guard
- LLDP/CDP
- VTP
- DTP
- LAG
- IPv6

## Estimated time:
**120 minutes**

## Tasks:
1. Configure network according to the requirements

### Functionality
- Whole topology is L2 only separated with VLANs and Trunks
- Make use of LAG with correct configuration
- Use VTP for easier administration of VLANs
	- Place VTP server correctly according to Cisco Campus Model
	- Secure protocol
- Configure DTP with security in mind
- Configure CDP/LLDP with security and useability in mind
- Configure Inter-VLAN routing
	- Make use of the best FHRP protocol for both IPv4 & IPv6 (optional)
- DHCP server for all VLANs for IPv4 will be *DHCP* "server" implemented as Cisco router
- Configure VLANs (there can be more VLANs in case other requirements demand them)
	- VLAN 10 (10.0.10.0/24;2001:A:B:10::/64)
	- VLAN 20 (10.0.20.0/24;2001:A:B:20::/64)
	- VLAN 30 (10.0.30.0/24;2001:A:B:30::/64)
	- (optional - Private VLAN) VLAN 100 (10.0.100.0/24;2001:A:B:100::/64)-> VLAN 101 & VLAN 110
	- PC4 -> VLAN10
	- PC1 -> VLAN20
	- PC2 -> VLAN30
	- PC3 -> VLAN10
	- *SRV1x & DHCP -> VLAN100*

### Security
- Secure edge of network (with VTP, DTP & LLDP/CDP in mind)
- Secure edge of network with PortSecurity
- Secure DHCP and ARP functionality with available tools (*Hint: Take a look at technologies covered*)
- Configure ACL acording to following rules (< - > = can connect, other communication is not possible (except for DHCP)):
	- VLAN10 < - > VLAN20
	- VLAN20 < - > VLAN30
	- SRV12 < - > SRV13
- Secure unused edge ports (there are more ways)

### Optional (CCNP-level)
- Make use of *Private VLAN* functionality on DSW-Switch-3 and its connected devices (servers)
- Configuration is described in ACL requirements