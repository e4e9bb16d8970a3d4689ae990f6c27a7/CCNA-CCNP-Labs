# R1
---
```
!
hostname R1      
!         
interface Ethernet0/0
ip address dhcp
!         
interface Ethernet0/1
ip address 154.87.22.1 255.255.255.252
ip ospf 1 area 2
!         
interface Ethernet0/2
ip address 154.87.45.1 255.255.255.0
ip ospf 1 area 0
!
router ospf 1
router-id 0.1.1.1
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 2 stub no-summary
passive-interface Ethernet0/0
default-information originate metric 10 metric-type 1
!
```

# R2
---
```
!
hostname R2      
!         
interface Ethernet0/0
ip address 87.58.45.1 255.255.255.252
ip ospf 1 area 10
!         
interface Ethernet0/1
ip address 87.58.45.5 255.255.255.252
ip ospf 1 area 10
!         
interface Ethernet0/2
ip address 154.87.45.2 255.255.255.0
ip ospf 1 area 0
!         
!
router ospf 1
router-id 0.2.2.2
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 10 nssa no-summary
!
```

# R3
---
```
!
hostname R3       
!         
interface Ethernet0/0
ip address 99.88.9.1 255.255.255.252
ip ospf 1 area 1
!         
interface Ethernet0/1
ip address 154.87.45.3 255.255.255.0
ip ospf 1 area 0
!      
!
router ospf 1
router-id 0.3.3.3
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 1 stub
!
```

# R4
---
```
!
hostname R4
!         
interface Ethernet0/0
ip address 154.87.22.2 255.255.255.252
ip ospf 1 area 2
!         
!         
interface Serial3/0
ip address 10.2.0.1 255.255.255.254
ip ospf 1 area 2
serial restart-delay 0
! 
!
router ospf 1
router-id 2.4.4.4
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 2 stub no-summary
!
```

# R5
---
```
!
hostname R5
!    
!         
interface Serial3/0
ip address 10.2.0.0 255.255.255.254
ip ospf 1 area 2
serial restart-delay 0
!  
!
router ospf 1
router-id 2.5.5.5
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 2 stub no-summary
! 
```

# R6
---
```
!
hostname R6       
!         
interface Ethernet0/0
ip address 87.58.45.2 255.255.255.252
ip ospf 1 area 10
!         
interface Ethernet0/1
ip address 10.10.0.1 255.255.255.0
ip ospf 1 area 10
!         
interface Ethernet0/2
ip address dhcp
!      
!
router ospf 1
router-id 10.6.6.6
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 10 nssa no-summary
redistribute static metric 100 metric-type 1 subnets
default-information originate
!
ip route 99.8.54.0 255.255.255.0 Ethernet0/2
ip route 147.25.123.0 255.255.255.0 Ethernet0/2
!
```

# R7
---
```
!
hostname R7      
!         
interface Ethernet0/0
ip address 87.58.45.6 255.255.255.252
ip ospf 1 area 10
ip ospf cost 150
!         
interface Ethernet0/1
ip address 10.10.0.2 255.255.255.0
ip ospf 1 area 10
!        
!
router ospf 1
router-id 10.7.7.7
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 10 nssa no-summary
!
```

# R8
---
```
!
hostname R8       
!         
interface Ethernet0/0
ip address 99.88.9.2 255.255.255.252
ip ospf 1 area 1
!         
!
router ospf 1
router-id 1.8.8.8
log-adjacency-changes detail
auto-cost reference-bandwidth 1000
area 1 stub
!
```

