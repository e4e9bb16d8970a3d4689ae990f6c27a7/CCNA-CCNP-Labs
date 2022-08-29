# Lab DMVPN - 09 - Final
---

## Technologies covered:
- GRE tunnels
- DMVPN Phase 3
- NHRP
- IPsec
- NAT
- IGP
- IPv6

## Estimated time:
**120 minutes**

## Tasks:
1. Apply initial config
2. Configure DMVPN Phase 3 with
	- Core-Hub as NHS for Layer and Region-1-Hub, Region-2-Hub as NCs
	- Region-1-Hub as NHS for Region 1 and Region-1-R1, Region-1-R2 as NCs
	- Region-2-Hub as NHS for Region 2 and Region-2-R1, Region-2-R2 as NCs
3. Allow multicast communication
4. Secure connections with authentication and encryption
5. Run IGP of your selection with summarization for Region-1 and Region-2
	- Configure with regards to logical topology
	- Secure protocol
6. Connect Region-3-R1 (behind NAT) to Core-Hub via DMVPN and fully secure connection
7. (optional) If possible (based on your EVE-NG/GNS-3 config) make it possible for whole network to access Internet
8. (optional) Run IPv6 in DMVPN
	- Work with fact that your ISP does not support IPv6
	- Use IPv6 addressing in regards of IPv4 addressing (10.x.x.x = 2001:10x:x:x::/64)