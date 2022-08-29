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
end
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
end
```
# R3
```
hostname R3
!
interface GigabitEthernet0/0
 description LAN
 ip address 10.12.12.3 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
end
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
end
```
# R5
```
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
end
```
# R6
```
hostname R6
!
interface GigabitEthernet0/0
 description LAN
 ip address 10.42.42.6 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!
end
```