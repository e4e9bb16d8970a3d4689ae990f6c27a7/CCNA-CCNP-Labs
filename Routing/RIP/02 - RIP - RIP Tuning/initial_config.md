# R1
---
```
!
hostname R1        
!         
interface GigabitEthernet0/0
ip address 172.16.0.1 255.255.255.252
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/1
ip address 172.16.0.5 255.255.255.252
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/2
ip address 172.16.0.9 255.255.255.252
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
interface GigabitEthernet0/0
ip address 172.16.0.18 255.255.255.252
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
interface GigabitEthernet0/2
ip address 172.16.0.14 255.255.255.252
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
interface GigabitEthernet0/0
ip address 172.16.0.17 255.255.255.252
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/1
ip address 172.16.0.21 255.255.255.252
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/2
ip address 172.16.0.10 255.255.255.252
duplex auto
speed auto
media-type rj45
!
```

# R4
---
```
!
hostname R4
!
interface GigabitEthernet0/0
ip address 172.16.0.13 255.255.255.252
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/1
ip address 172.16.0.6 255.255.255.252
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/2
ip address 172.16.0.26 255.255.255.252
duplex auto
speed auto
media-type rj45
!
```

# Switch1
---
```
!
hostname Switch1
!
interface Loopback0
ip address 192.168.1.1 255.255.255.0
!
interface Loopback1
ip address 10.10.0.1 255.255.255.0
!
interface GigabitEthernet0/0
no switchport
ip address 172.16.0.22 255.255.255.252
negotiation auto
!
```

# Switch2
---
```
!
hostname Switch2
!
interface Loopback0
ip address 10.20.1.1 255.255.255.0
!
interface Loopback1
ip address 172.16.0.254 255.255.255.255
!
interface GigabitEthernet0/0
no switchport
ip address 172.16.0.25 255.255.255.252
negotiation auto
!
```

