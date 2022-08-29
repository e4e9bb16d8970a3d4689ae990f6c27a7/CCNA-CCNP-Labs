# R1
---
```
!
hostname R1       
!         
interface Loopback0
ip address 172.16.1.1 255.255.255.248
!         
interface Ethernet0/0
ip address 10.13.1.1 255.255.0.0
!         
interface Ethernet0/1
ip address 10.14.1.1 255.255.0.0
!         
interface Ethernet0/2
no ip address
shutdown 
!         
interface Ethernet0/3
no ip address
shutdown 
!         
interface Serial1/0
ip address 10.12.1.1 255.255.0.0
serial restart-delay 0
!
```

# R2
---
```
!
hostname R2
!
interface Loopback0
ip address 192.168.0.1 255.255.248.0
!
interface Ethernet0/0
ip address 10.23.2.2 255.255.0.0
!
interface Ethernet0/1
no ip address
shutdown
!
interface Ethernet0/2
no ip address
shutdown
!
interface Ethernet0/3
no ip address
shutdown
!
interface Serial1/0
ip address 10.12.2.2 255.255.0.0
serial restart-delay 0
!
```

# R3
---
```
!
hostname R3
!
interface Loopback0
ip address 154.87.51.2 255.255.255.255
!
interface Ethernet0/0
ip address 10.13.3.3 255.255.0.0
!
interface Ethernet0/1
ip address 10.23.3.3 255.255.0.0
!
interface Ethernet0/2
ip address 10.34.3.3 255.255.0.0
!
```

# R4
---
```
!
hostname R4
!
interface Ethernet0/0
ip address 10.34.4.4 255.255.0.0
!
interface Ethernet0/1
ip address 10.14.4.4 255.255.0.0
!
```

