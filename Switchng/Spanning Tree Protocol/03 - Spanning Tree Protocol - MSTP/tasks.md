# Lab Spanning Tree Protocol - 03 - MSTP
---

## Technologies covered:
- MSTP
- EtherChannel
- RPVSTP+

## Estimated time:
**20 minutes**

## Tasks:

*Switches in red box are in MST Region 1, in green box are in MST Region 2 and in blue box are in MST Region 3. Yellow underlying box represents MSTP Domain, every other switch (those in purple box) is not running MSTP but RPVSTP+*

**(optional) You can run VTPv3 to make the configuration ov VLANs and MSTP easier.**

1. Create VLANs 110,120,130,210,220,230,310,320,330
2. Configure LAG between SW1 and SW7
3. Create MST Regions according to colors with SW1, SW7 and SW5 being CIST Regional Roots and SW5 being CIST Root
4. Incorporate SW10 and SW11 into the network