# R1
---
```
!
hostname R1
!      
!         
!         
interface Loopback0
ip address 10.1.0.1 255.255.255.0
!         
interface GigabitEthernet0/0
ip address 172.16.0.5 255.255.255.252
duplex auto
speed auto
media-type rj45
!    
```

# R2
---
```
!
hostname R2      
!         
!         
!
interface Loopback0
ip address 192.168.0.1 255.255.255.0
!
interface GigabitEthernet0/0
ip address 172.16.0.6 255.255.255.252
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/1
ip address 172.16.0.2 255.255.255.252
duplex auto
speed auto
media-type rj45
!
```

# R3
---
```
!
hostname R3
!
!
!
interface Loopback0
ip address 10.2.0.1 255.255.255.0
!
interface GigabitEthernet0/0
ip address 172.16.0.1 255.255.255.252
duplex auto
speed auto
media-type rj45
!
```