# R1
```
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.1 255.255.255.0
 no ip redirects
 ip mtu 1400
 no ip split-horizon eigrp 1
 ip nhrp authentication encor
 ip nhrp map multicast dynamic
 ip nhrp network-id 1
 ip nhrp holdtime 300
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
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
router eigrp 1
 network 10.12.12.0 0.0.0.255
 network 10.124.124.0 0.0.0.255
!
end
```
# R2
```
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
router eigrp 1
 network 10.12.12.0 0.0.0.255
!
end
```
# R3
```
!
interface GigabitEthernet0/0
 description LAN
 ip address 10.12.12.3 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
router eigrp 1
 network 10.12.12.0 0.0.0.255
!
end
```
# R4
```
!
interface Loopback0
 ip address 10.30.30.1 255.255.255.0
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.4 255.255.255.0
 ip mtu 1400
 ip nhrp authentication encor
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip tcp adjust-mss 1360
 ip ospf network point-to-multipoint non-broadcast
 ip ospf 1 area 0
 tunnel source GigabitEthernet0/0
 tunnel destination 192.0.2.1
!
interface GigabitEthernet0/0
 description WAN
 ip address 192.0.2.4 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
router eigrp 1
 network 10.30.30.0 0.0.0.255
 network 10.124.124.0 0.0.0.255
!
end
```
# R5
```
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.5 255.255.255.0
 ip mtu 1400
 ip nhrp authentication encor
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip tcp adjust-mss 1360
 ip ospf network point-to-multipoint non-broadcast
 ip ospf 1 area 0
 tunnel source GigabitEthernet0/0
 tunnel destination 192.0.2.1
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
 ip ospf 1 area 3
 duplex auto
 speed auto
 media-type rj45
!
router eigrp 1
 network 10.42.42.0 0.0.0.255
 network 10.124.124.0 0.0.0.255
!
end
```
# R6
```
!
interface GigabitEthernet0/0
 description LAN
 ip address 10.42.42.6 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
router eigrp 1
 network 10.42.42.0 0.0.0.255
!
end
```