# Lab VLAN, LAG & FHRPs - 01 - Basics
---

## Technologies covered:
- LAG
- VLAN
- Trunk

## Estimated time:
**10 minutes**

## Tasks:

1. Configure manual LAGs between ACCS-Switch-1 <-> DST-Switch <-> ACCS-Switch-2
2. Configure VLANs:
	- VLAN 10 (192.168.10.0/24)
	- VLAN 20 (192.168.20.0/24)
3. Configure access ports:
	- ACCS-Switch-1) Gi0/2 -> VLAN 10
	- ACCS-Switch-2) Gi0/2 -> VLAN 10;Gi0/3 -> VLAN 20
4. Configure trunks on LAGs between ACCS-Switch-1 <-> DST-Switch <-> ACCS-Switch-2
5. (optional) Configure IP addresses on end devices and check whether VLANs are working correctly