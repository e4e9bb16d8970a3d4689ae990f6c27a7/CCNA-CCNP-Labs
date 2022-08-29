# Lab OSPF - 03 - Tuning
---

## Technologies covered:
- OSPF
- ACL

## Estimated time:
**30 minutes**

## Tasks:
- Resume configuration on previus lab (OSPF 02)
1. Add loopback interface with network 192.168.2.0/24 on R5
	- This network will be accesable only within Area 2
2. Enable prefix suppression in backbone
3. Enable iSPF in whole network
4. Configure authentication with MD5
5. Implement summarization for each area (networks are 10.x.0.0/16 where x is area number)
6. Implement TTL Security