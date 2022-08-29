# Core-Hub
---
!
hostname Core-Hub
!
ip nat source list 1 interface GigabitEthernet0/0 overload
ip nat inside source list 1 interface GigabitEthernet0/0 overload
!
!
!
access-list 1 permit any
!
!
interface GigabitEthernet0/0
 description WAN
 ip address dhcp
 ip nat outside
 ip virtual-reassembly in
 duplex auto
 speed auto
 media-type rj45
!
!
interface GigabitEthernet0/1
 description ISP-DMVPN
 ip address 15.20.30.1 255.255.255.0
 ip nat inside
 ip virtual-reassembly in
 duplex auto
 speed auto
 media-type rj45
!

# Region-1-Hub
---
!
hostname Region-1-Hub
!
!
interface GigabitEthernet0/0
 description ISP-DMVPN
 ip address 15.20.30.2 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!

# Region-2-Hub
---
!
hostname Region-2-Hub
!
!
interface GigabitEthernet0/0
 description ISP-DMVPN
 ip address 15.20.30.3 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!

# Region-1-R1
---
!
hostname Region-1-R1
!
!
interface GigabitEthernet0/0
 description ISP-DMVPN
 ip address 15.20.30.4 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!

# Region-1-R2
---
!
hostname Region-1-R2
!
!
interface GigabitEthernet0/0
 description ISP-DMVPN
 ip address 15.20.30.5 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!

# Region-2-R1
---
!
hostname Region-2-R1
!
!
interface GigabitEthernet0/0
 description ISP-DMVPN
 ip address 15.20.30.6 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!

# Region-2-R2
---
!
hostname Region-2-R2
!
!
interface GigabitEthernet0/0
 ip address 15.20.30.7 255.255.255.0
 duplex auto
 speed auto
 media-type rj45
!

# Region-3-R1
---
!
hostname Region-3-R1
!
!
interface GigabitEthernet0/0
 description ISP-DMVPN-NAT
 ip address dhcp
 duplex auto
 speed auto
 media-type rj45
!
