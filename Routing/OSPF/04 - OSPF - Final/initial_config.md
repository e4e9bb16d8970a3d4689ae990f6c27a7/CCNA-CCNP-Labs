# R1
---
```
!
hostname R1       
!         
ip cef    
ipv6 unicast-routing       
!         
interface Ethernet0/0
ip address dhcp
ipv6 address FE80::1 link-local
ipv6 address autoconfig
!         
interface Ethernet0/1
ip address 172.16.1.1 255.255.255.252
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:FFFD::1/64
!         
interface Ethernet0/2
ip address 172.16.1.5 255.255.255.252
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:FFFC::1/64
!         
interface Ethernet0/3
ip address 172.16.1.9 255.255.255.252
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:FFFB::1/64
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
interface Serial2/0
ip address 172.16.0.0 255.255.255.254
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:FFFF::1/64
serial restart-delay 0
!         
interface Serial2/1
ip address 172.16.0.2 255.255.255.254
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:FFFE::1/64
serial restart-delay 0
!
```

# R2
---
```
!
hostname R2
!  
ipv6 unicast-routing      
!         
interface Ethernet0/0
ip address 172.16.2.9 255.255.255.252
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:FFF8::2/64
!         
interface Ethernet0/1
ip address 172.16.2.5 255.255.255.252
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:FFF9::2/64
!         
interface Ethernet0/2
ip address 172.16.2.13 255.255.255.252
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:FFF7::2/64
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
interface Serial2/0
ip address 172.16.0.1 255.255.255.254
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:FFFF::2/64
serial restart-delay 0
!
interface Serial2/1
ip address 172.16.2.1 255.255.255.252
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:FFFA::2/64
serial restart-delay 0
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
interface Ethernet0/0
ip address 172.16.3.1 255.255.255.252
ipv6 address FE80::3 link-local
ipv6 address 2001:A:B:FFF6::3/64
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
interface Serial2/0
ip address 172.16.0.3 255.255.255.254
ipv6 address FE80::3 link-local
ipv6 address 2001:A:B:FFFE::3/64
serial restart-delay 0
!
interface Serial2/1
ip address 172.16.2.2 255.255.255.252
ipv6 address FE80::3 link-local
ipv6 address 2001:A:B:FFFA::3/64
serial restart-delay 0
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
ip address 172.16.1.2 255.255.255.252
ipv6 address FE80::4 link-local
ipv6 address 2001:A:B:FFFD::4/64
!         
interface Ethernet0/1
ip address 172.16.2.6 255.255.255.252
ipv6 address FE80::4 link-local
ipv6 address 2001:A:B:FFF9::4/64
!         
interface Ethernet0/2
ip address 172.16.4.5 255.255.255.252
ipv6 address FE80::4 link-local
ipv6 address 2001:A:B:FFF4::4/64
!         
interface Ethernet0/3
ip address 172.16.4.1 255.255.255.252
ipv6 address FE80::4 link-local
ipv6 address 2001:A:B:FFF5::4/64
!         
```

# R5
---
```
!
hostname R5
!  
ipv6 unicast-routing     
!         
interface Ethernet0/0
ip address 172.16.2.10 255.255.255.252
ipv6 address FE80::5 link-local
ipv6 address 2001:A:B:FFF8::5/64
!         
interface Ethernet0/1
ip address 172.16.1.6 255.255.255.252
ipv6 address FE80::5 link-local
ipv6 address 2001:A:B:FFFC::5/64
!         
interface Ethernet0/2
ip address 172.16.5.1 255.255.255.252
ipv6 address FE80::5 link-local
ipv6 address 2001:A:B:FFF3::5/64
!         
interface Ethernet0/3
ip address 172.16.4.2 255.255.255.252
ipv6 address FE80::5 link-local
ipv6 address 2001:A:B:FFF5::5/64
!
```

# R6
---
```
!
hostname R6
! 
ipv6 unicast-routing       
!         
interface Loopback0
ip address 10.20.0.2 255.255.255.0
ipv6 address 2001:A:B:102::1/64
!         
interface Loopback1
ip address 192.168.15.1 255.255.252.0
ipv6 address 2001:A:B:1105::/64 eui-64
!         
interface Ethernet0/0
ip address 172.16.4.6 255.255.255.252
ipv6 address FE80::6 link-local
ipv6 address 2001:A:B:FFF4::6/64
!         
interface Ethernet0/1
ip address 172.16.5.2 255.255.255.252
ipv6 address FE80::6 link-local
ipv6 address 2001:A:B:FFF3::6/64
!         
```

# R7
---
```
!
hostname R7
!
ipv6 unicast-routing       
!         
interface Ethernet0/0
ip address 172.16.2.14 255.255.255.252
ipv6 address FE80::7 link-local
ipv6 address 2001:A:B:FFF7::7/64
!         
interface Ethernet0/1
ip address 172.16.7.1 255.255.255.252
ipv6 address FE80::7 link-local
ipv6 address 2001:A:B:FFF0::7/64
ipv6 rip RIP enable
!         
interface Ethernet0/2
ip address 172.16.9.2 255.255.255.252
ipv6 address FE80::7 link-local
ipv6 address 2001:A:B:FFF1::7/64
!         
!
router rip
version 2
passive-interface Ethernet0/0
passive-interface Ethernet0/2
network 172.16.0.0
no auto-summary
!
```

# R8
---
```
!
hostname R8
!
ipv6 unicast-routing       
!         
interface Loopback0
ip address 192.168.0.1 255.255.255.0
ipv6 address 2001:A:B:2::1/64
!         
interface Loopback1
ip address 10.4.0.1 255.255.255.248
ipv6 address 2001:A:B:21::1/64
ipv6 rip RIP enable
!         
interface Loopback2
no ip address
!         
interface Loopback3
ip address 187.45.12.2 255.255.255.252
ipv6 address 2001:748:44:23A::/64 eui-64
ipv6 rip RIP enable
!         
interface Ethernet0/0
ip address 172.16.7.2 255.255.255.252
ipv6 address FE80::8 link-local
ipv6 address 2001:A:B:FFF0::8/64
ipv6 rip RIP enable
!         
!
router rip
version 2
network 10.0.0.0
network 172.16.0.0
network 187.45.0.0
network 192.168.0.0
no auto-summary
!
```

# R9
---
```
!
hostname R9
!  
ipv6 unicast-routing       
!         
interface Loopback0
ip address 10.1.0.1 255.255.255.0
ipv6 address 2001:A:B:10::1/64
!         
interface Loopback1
ip address 10.1.1.1 255.255.255.0
ipv6 address 2001:A:B:11::1/64
!         
interface Loopback3
ip address 10.1.2.1 255.255.255.0
ipv6 address 2001:A:B:12::1/64
!         
interface Ethernet0/0
ip address 172.16.9.1 255.255.255.252
ipv6 address FE80::9 link-local
ipv6 address 2001:A:B:FFF1::9/64
!         
interface Ethernet0/1
ip address 172.16.10.2 255.255.255.252
ipv6 address FE80::9 link-local
ipv6 address 2001:A:B:FFF2::9/64
!         
```

# R10
---
```
!
hostname R10
!   
ipv6 unicast-routing       
!         
interface Ethernet0/0
ip address 172.16.1.10 255.255.255.252
ipv6 address FE80::10 link-local
ipv6 address 2001:A:B:FFFB::10/64
!         
interface Ethernet0/1
ip address 172.16.3.2 255.255.255.252
ipv6 address FE80::10 link-local
ipv6 address 2001:A:B:FFF6::10/64
!         
interface Ethernet0/2
ip address 172.16.10.1 255.255.255.252
ipv6 address FE80::10 link-local
ipv6 address 2001:A:B:FFF2::10/64
!         
```

