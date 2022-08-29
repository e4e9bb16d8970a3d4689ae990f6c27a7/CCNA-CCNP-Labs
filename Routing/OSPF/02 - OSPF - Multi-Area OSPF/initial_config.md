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
!         
interface Ethernet0/2
ip address 154.87.45.1 255.255.255.0
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
!
interface Ethernet0/1
ip address 87.58.45.5 255.255.255.252
!
interface Ethernet0/2
ip address 154.87.45.2 255.255.255.0
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
!
interface Ethernet0/1
ip address 154.87.45.3 255.255.255.0
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
interface Ethernet1/0
no ip address
shutdown 
!         
interface Ethernet1/1
no ip address
shutdown 
!         
interface Ethernet1/2
no ip address
shutdown 
!         
interface Ethernet1/3
no ip address
shutdown 
!         
interface Ethernet2/0
no ip address
shutdown 
!         
interface Ethernet2/1
no ip address
shutdown 
!         
interface Ethernet2/2
no ip address
shutdown
!
interface Ethernet2/3
no ip address
shutdown
!
interface Serial3/0
ip address 10.2.0.1 255.255.255.254
serial restart-delay 0
!
```

# R5
---
```
!
hostname R5        
!         
interface Ethernet0/0
no ip address
shutdown 
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
interface Ethernet1/0
no ip address
shutdown 
!         
interface Ethernet1/1
no ip address
shutdown 
!         
interface Ethernet1/2
no ip address
shutdown 
!         
interface Ethernet1/3
no ip address
shutdown 
!         
interface Ethernet2/0
no ip address
shutdown 
!         
interface Ethernet2/1
no ip address
shutdown 
!         
interface Ethernet2/2
no ip address
shutdown 
!         
interface Ethernet2/3
no ip address
shutdown 
!         
interface Serial3/0
ip address 10.2.0.0 255.255.255.254
serial restart-delay 0
!         
```

# R6
---
```
!
hostname R6      
!
ip route 99.8.54.0 255.255.255.0 e0/2  
ip route 147.25.123.0 255.255.255.0 e0/2   
!      
interface Ethernet0/0
ip address 87.58.45.2 255.255.255.252
!         
interface Ethernet0/1
ip address 10.10.0.1 255.255.255.0
!         
interface Ethernet0/2
ip address dhcp
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
!         
interface Ethernet0/1
ip address 10.10.0.2 255.255.255.0
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
!
```

