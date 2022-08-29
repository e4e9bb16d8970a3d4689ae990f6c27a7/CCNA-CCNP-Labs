# R1
```
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.1 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.2 192.0.2.2
 ip nhrp map multicast 192.0.2.2
 ip nhrp network-id 1
 ip nhrp redirect
 ip tcp adjust-mss 1360
 ip ospf network point-to-multipoint
 ip ospf 1 area 0
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router ospf 1
 router-id 1.1.1.1
 log-adjacency-changes detail
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
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.1 192.0.2.1
 ip nhrp map multicast 192.0.2.1
 ip nhrp network-id 1
 ip nhrp redirect
 ip tcp adjust-mss 1360
 ip ospf network point-to-multipoint
 ip ospf 1 area 0
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router ospf 1
 router-id 2.2.2.2
 log-adjacency-changes detail
!
```
# R3
```
!
router ospf 1
 router-id 3.3.3.3
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
 ip nhrp shortcut
 ip tcp adjust-mss 1360
 ip ospf network point-to-multipoint
 ip ospf 1 area 0
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router ospf 1
 router-id 4.4.4.4
 log-adjacency-changes detail
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
 ip nhrp shortcut
 ip tcp adjust-mss 1360
 ip ospf network point-to-multipoint
 ip ospf 1 area 0
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
router ospf 1
 router-id 5.5.5.5
 log-adjacency-changes detail
!
```
# R6
```
!
router ospf 1
 router-id 6.6.6.6
!
```