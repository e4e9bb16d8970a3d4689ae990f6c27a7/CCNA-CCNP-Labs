# ER1
---
```
!
hostname ER1
!
boot-start-marker
boot-end-marker
!
!
!
no aaa new-model
!
!
!
mmi polling-interval 60
no mmi auto-configure
no mmi pvc
mmi snmp-timeout 180
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         


!         
!         
!         
!         
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
multilink bundle-name authenticated
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
redundancy
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
interface Ethernet0/0
ip address 10.255.0.1 255.255.255.252
duplex auto
ipv6 address FD00:AC45:AC45:1::1/64
!         
interface Ethernet0/1
ip address 10.255.0.5 255.255.255.252
duplex auto
ipv6 address FD00:AC45:AC45:2::1/64
!         
interface Ethernet0/2
no ip address
shutdown 
duplex auto
!         
interface Ethernet0/3
no ip address
shutdown 
duplex auto
!         
interface Ethernet1/0
no ip address
shutdown 
duplex auto
!         
interface Ethernet1/1
no ip address
shutdown 
duplex auto
!         
interface Ethernet1/2
no ip address
shutdown 
duplex auto
!         
interface Ethernet1/3
no ip address
shutdown 
duplex auto
!         
interface Serial2/0
description T1WAN-ER2
ip address 172.16.0.0 255.255.255.254
encapsulation ppp
ipv6 address FD00:AC45:84CD:FFFF::1/64
serial restart-delay 0
!
```

# ER2
---
```
!
hostname ER2
!
boot-start-marker
boot-end-marker
!
!
!
no aaa new-model
!
!
!
mmi polling-interval 60
no mmi auto-configure
no mmi pvc
mmi snmp-timeout 180
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         


!         
!         
!         
!         
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
multilink bundle-name authenticated
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
redundancy
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
interface Ethernet0/0
ip address 10.254.0.1 255.255.255.252
duplex auto
ipv6 address FD00:84CD:84CD:1::1/64
!         
interface Ethernet0/1
no ip address
shutdown
duplex auto
!
interface Ethernet0/2
no ip address
shutdown
duplex auto
!
interface Ethernet0/3
no ip address
shutdown
duplex auto
!
interface Ethernet1/0
no ip address
shutdown
duplex auto
!
interface Ethernet1/1
no ip address
shutdown
duplex auto
!
interface Ethernet1/2
no ip address
shutdown
duplex auto
!
interface Ethernet1/3
no ip address
shutdown
duplex auto
!
interface Serial2/0
description T1WAN-ER1
ip address 172.16.0.1 255.255.255.254
encapsulation ppp
ipv6 address FD00:AC45:84CD:FFFF::2/64
serial restart-delay 0
!
```

# R1
---
```
!
hostname R1
!
boot-start-marker
boot-end-marker
!
!
!
no aaa new-model
!
!
!
mmi polling-interval 60
no mmi auto-configure
no mmi pvc
mmi snmp-timeout 180
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         


!         
!         
!         
!         
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
multilink bundle-name authenticated
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
redundancy
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!
interface Tunnel1
ip address 10.255.254.1 255.255.255.252
tunnel source Ethernet0/1
tunnel mode ipip
tunnel destination 142.158.41.57
!
interface Tunnel2
no ip address
ipv6 address FD00:AC45:84CD:FFFE::1/64
tunnel source Ethernet0/1
tunnel mode ipv6ip
tunnel destination 142.158.41.57
!
interface Ethernet0/0
ip address 10.255.0.2 255.255.255.252
duplex auto
ipv6 address FD00:AC45:AC45:1::2/64
!
interface Ethernet0/1
ip address 142.158.41.58 255.255.255.252
duplex auto
!
interface Ethernet0/2
ip address 192.168.0.1 255.255.255.0
duplex auto
ipv6 address FE80::FFFF link-local
ipv6 address FD00:AC45:AC45:F001::FFFF/64
!
```

# R2
---
```
!
hostname R2
!
boot-start-marker
boot-end-marker
!
!
!
no aaa new-model
!
!
!
mmi polling-interval 60
no mmi auto-configure
no mmi pvc
mmi snmp-timeout 180
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         


!         
!         
!         
!         
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
multilink bundle-name authenticated
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
redundancy
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!
interface Ethernet0/0
ip address 10.255.0.6 255.255.255.252
duplex auto
ipv6 address FD00:AC45:AC45:2::2/64
!
interface Ethernet0/1
ip address 192.168.1.1 255.255.255.0
duplex auto
ipv6 address FE80::FFFF link-local
ipv6 address FD00:AC45:AC45:F002::FFFF/64
!
```

# R3
---
```
!
hostname R3
!
boot-start-marker
boot-end-marker
!
!
!
no aaa new-model
!
!
!
mmi polling-interval 60
no mmi auto-configure
no mmi pvc
mmi snmp-timeout 180
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         


!         
!         
!         
!         
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
multilink bundle-name authenticated
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
redundancy
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
!         
interface Tunnel1
ip address 10.255.254.2 255.255.255.252
tunnel source Ethernet0/1
tunnel mode ipip
tunnel destination 142.158.41.58
!
interface Tunnel2
no ip address
ipv6 address FD00:AC45:84CD:FFFE::2/64
tunnel source Ethernet0/1
tunnel mode ipv6ip
tunnel destination 142.158.41.58
!
interface Ethernet0/0
ip address 10.254.0.2 255.255.255.252
duplex auto
ipv6 address FD00:84CD:84CD:1::2/64
!
interface Ethernet0/1
ip address 142.158.41.57 255.255.255.252
duplex auto
!
interface Ethernet0/2
ip address 192.168.3.1 255.255.255.0
duplex auto
ipv6 address FE80::FFFF link-local
ipv6 address FD00:84CD:84CD:F001::FFFF/64
!
```
