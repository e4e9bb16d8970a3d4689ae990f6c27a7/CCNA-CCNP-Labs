# R1
```
hostname R1
!
interface GigabitEthernet0/0
 description WAN
 ip address 192.0.2.1 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
interface GigabitEthernet0/1
 description LAN
 ip address 10.12.12.1 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.1 255.255.255.0
 no ip redirects
 ip mtu 1400
 no ip split-horizon eigrp 65535
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.2 192.0.2.2
 ip nhrp map multicast 192.0.2.2
 ip nhrp network-id 1
 ip nhrp redirect
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
hostname R2
!
interface GigabitEthernet0/0
 description WAN
 ip address 192.0.2.2 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
interface GigabitEthernet0/1
 description LAN
 ip address 10.12.12.2 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.2 255.255.255.0
 no ip redirects
 ip mtu 1400
 no ip split-horizon eigrp 65535
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.1 192.0.2.1
 ip nhrp map multicast 192.0.2.1
 ip nhrp network-id 1
 ip nhrp redirect
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
hostname R3
!
interface GigabitEthernet0/0
 description LAN
 ip address 10.12.12.3 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
router eigrp 65535
 network 10.12.12.0 0.0.0.255
!
```
# R4
```
hostname R4
!
interface Loopback0
 ip address 10.30.30.1 255.255.255.0
!
interface GigabitEthernet0/0
 description WAN
 ip address 192.0.2.4 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
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
hostname R5
!
interface GigabitEthernet0/0
 description WAN
 ip address 192.0.2.5 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
interface GigabitEthernet0/1
 description LAN
 ip address 10.42.42.5 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
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
hostname R6
!
interface GigabitEthernet0/0
 description LAN
 ip address 10.42.42.6 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
router eigrp 65535
 network 10.42.42.0 0.0.0.255
!
```