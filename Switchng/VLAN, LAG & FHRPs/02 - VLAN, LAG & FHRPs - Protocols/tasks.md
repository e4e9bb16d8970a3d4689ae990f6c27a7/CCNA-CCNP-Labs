# Lab VLAN, LAG & FHRPs - 02 - Protocols
---

## Technologies covered:
- VLAN
- VTP
- DTP
- LAG
	- LACP
	- PaGP
- HSRP

## Estimated time:
**20 minutes**

## Tasks:

1. Configure LACP LAG between ACCS-Switch-1 <-> DST-Switch with ACCS-Switch-1 being pro-active
2. Configure PaGP LAG between ACCS-Switch-2 <-> DST-Switch with ACCS-Switch-2 being pro-active
3. Configure VTP:
	- DST-Switch will be **Server** & ACCS-Switch-x will be **Clients**
	- VTP domain name will be *ciscolabs* with same password
	- Create VLANS:
		- VLAN 10 (192.168.10.0/24)
		- VLAN 20 (192.168.20.0/24)
3. Configure access ports:
	- ACCS-Switch-1) Gi0/2 -> VLAN 10
	- ACCS-Switch-2) Gi0/2 -> VLAN 10;Gi0/3 -> VLAN 20
	- Secure end ports (DTP & VTP)
4. Configure trunks on LAGs between ACCS-Switch-1 <-> DST-Switch <-> ACCS-Switch-2
	- via DTP (DST-Switch will be pro-active)
5. Configure Inter-VLAN routing:
	- Use SVIs
	- ACCS-Switch-x will be DG with IP of 192.168.x.1
		- Use FHRP protocol of your selection (optionally try all of them)
	- (optional) Take advantage of load-balancing between VLANs that is provided with use of FHRP