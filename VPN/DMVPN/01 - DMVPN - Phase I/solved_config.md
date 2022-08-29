# R1
```
!
interface Tunnel1
 description DMVPN_CORE
 bandwidth 1000000
 ip address 10.124.124.1 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp authentication encor
 ip nhrp map multicast dynamic
 ip nhrp network-id 1
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
!
end
```
# R2
```
!
interface Tunnel1
 description DMVPN_CORE
 bandwidth 1000000
 ip address 10.124.124.2 255.255.255.0
 ip mtu 1400
 ip nhrp authentication encor
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel destination 192.0.2.1
!
end
```
# R4
```
!
interface Tunnel1
 description DMVPN_CORE
 bandwidth 1000000
 ip address 10.124.124.4 255.255.255.0
 ip mtu 1400
 ip nhrp authentication encor
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel destination 192.0.2.1
!
end
```
# R5
```
!
interface Tunnel1
 description DMVPN_CORE
 bandwidth 1000000
 ip address 10.124.124.5 255.255.255.0
 ip mtu 1400
 ip nhrp authentication encor
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel destination 192.0.2.1
!
end
```