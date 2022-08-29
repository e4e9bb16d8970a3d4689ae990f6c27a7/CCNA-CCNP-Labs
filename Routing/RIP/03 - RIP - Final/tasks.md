# Lab RIP - 03 - Final
---

## Technologies covered:
- RIP
- ACL
- IPv6

## Estimated time:
**40 minutes**

## Tasks:
IPv4 and IPv6 addresses are configured (if you apply *initial_config.md*).
Configure RIPv2 and RIPng in whole network (devices in green square are think of as in building one and in blue sqare as in building two), those buildings are interconnected with WAN technologies.
Serial line is leased T1 line with speed of 1.544 Mbps, it is very reliable but since bandwidth is very limited RIP configuration have to be adjusted accordingly.
Second connection between buildings is via ISP where there is created GRE tunnel with IP of 10.255.254.0/30, this connection should be used as backup (due to its inherent insecurity). 

Summarize networks on WAN connections when possible (building one uses 10.255.0.x/30 network and building two 10.254.0.x/30 network).
Secure RIP messages and tune timers for quicker convergence.
Network on SW1 is not to be propagated via WAN links.
R3 is to be configured as default gateways.
Secure edge of the network.
