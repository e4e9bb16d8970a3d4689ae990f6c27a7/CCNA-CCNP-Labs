# R1
```
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.1 255.255.255.0
 no ip redirects
 ip mtu 1400
 no ip next-hop-self eigrp 65535
 no ip split-horizon eigrp 65535
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.2 192.0.2.2
 ip nhrp map multicast 192.0.2.2
 ip nhrp network-id 1
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router eigrp 65535
 network 10.12.12.0 0.0.0.255
 network 10.124.124.0 0.0.0.255
!
```
# R2
```
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.2 255.255.255.0
 no ip redirects
 ip mtu 1400
 no ip next-hop-self eigrp 65535
 no ip split-horizon eigrp 65535
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.1 192.0.2.1
 ip nhrp map multicast 192.0.2.1
 ip nhrp network-id 1
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router eigrp 65535
 network 10.12.12.0 0.0.0.255
 network 10.124.124.0 0.0.0.255
!
```
# R3
```
!
router eigrp 65535
 network 10.12.12.0 0.0.0.255
!
```
# R4
```
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.4 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip nhrp nhs 10.124.124.2 nbma 192.0.2.2 multicast
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router eigrp 65535
 network 10.30.30.0 0.0.0.255
 network 10.124.124.0 0.0.0.255
!
```
# R5
```
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.5 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip nhrp nhs 10.124.124.2 nbma 192.0.2.2 multicast
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router eigrp 65535
 network 10.42.42.0 0.0.0.255
 network 10.124.124.0 0.0.0.255
!
```
# R6
```
!
router eigrp 65535
 network 10.42.42.0 0.0.0.255
!
```