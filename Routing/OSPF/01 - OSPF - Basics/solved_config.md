# R1
---
```
!
router ospf 1
router-id 1.1.1.1
auto-cost reference-bandwidth 1000
network 10.0.0.0 0.255.255.255 area 0
network 172.16.0.0 0.0.0.7 area 0
!
```

# R2
---
```
!
router ospf 1
router-id 2.2.2.2
auto-cost reference-bandwidth 1000
network 10.0.0.0 0.255.255.255 area 0
network 192.168.0.0 0.0.7.255 area 0
!
```

# R3
---
```
!
hostname R3
!  
ipv6 unicast-routing       
!         
interface Loopback0
ip address 154.87.51.2 255.255.255.255
ospfv3 1 ipv4 area 0
!         
interface Ethernet0/0
ip address 10.13.3.3 255.255.0.0
ospfv3 1 ipv4 area 0
!         
interface Ethernet0/1
ip address 10.23.3.3 255.255.0.0
ospfv3 1 ipv4 area 0
!         
interface Ethernet0/2
ip address 10.34.3.3 255.255.0.0
ospfv3 1 ipv4 area 0
!
interface Ethernet0/3
no ip address
shutdown
!
router ospfv3 1
!
address-family ipv4 unicast
router-id 3.3.3.3
auto-cost reference-bandwidth 1000
exit-address-family
!
```

# R4
---
```
!
hostname R4
!  
ipv6 unicast-routing       
!         
interface Ethernet0/0
ip address 10.34.4.4 255.255.0.0
ospfv3 1 ipv4 area 0
!         
interface Ethernet0/1
ip address 10.14.4.4 255.255.0.0
ospfv3 1 ipv4 area 0
!
interface Ethernet0/2
no ip address
shutdown
!
interface Ethernet0/3
no ip address
shutdown
!
router ospfv3 1
!
address-family ipv4 unicast
auto-cost reference-bandwidth 1000
exit-address-family
!
```

