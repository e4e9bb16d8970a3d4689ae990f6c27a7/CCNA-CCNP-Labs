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
key chain RIP
key 10   
key-string ciscolabs
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
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
ipv6 address FD00:AC45:AC45:1::1/64
ipv6 rip RIP enable
!         
interface Ethernet0/1
ip address 10.255.0.5 255.255.255.252
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
ipv6 address FD00:AC45:AC45:2::1/64
ipv6 rip RIP enable
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
ip rip triggered
ip rip authentication mode md5
ip rip authentication key-chain RIP
encapsulation ppp
ip summary-address rip 10.255.0.0 255.255.0.0
ipv6 address FD00:AC45:84CD:FFFF::1/64
ipv6 rip RIP enable
serial restart-delay 0
!         
interface Serial2/1
no ip address
shutdown 
serial restart-delay 0
!         
interface Serial2/2
no ip address
shutdown 
serial restart-delay 0
!         
interface Serial2/3
no ip address
shutdown 
serial restart-delay 0
!         
router rip
version 2
timers basic 3 18 18 24
passive-interface default
no passive-interface Ethernet0/0
no passive-interface Ethernet0/1
network 10.0.0.0
network 172.16.0.0
neighbor 172.16.0.1
distribute-list RIP_WAN out Ethernet0/0
distribute-list RIP_WAN out Ethernet0/1
distribute-list RIP out Serial2/0
no auto-summary
!         
ip forward-protocol nd
!
!
no ip http server
no ip http secure-server
!
ip access-list standard RIP
deny   192.168.0.0 0.0.0.255
permit any
ip access-list standard RIP_WAN
deny   172.16.0.0 0.0.0.1
permit any
!
ipv6 router rip RIP
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
key chain RIP
key 1    
key-string ciscolabs
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
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
ipv6 address FD00:84CD:84CD:1::1/64
ipv6 rip RIP enable
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
ip rip triggered
ip rip authentication mode md5
ip rip authentication key-chain RIP
encapsulation ppp
ip summary-address rip 10.254.0.0 255.255.0.0
ipv6 address FD00:AC45:84CD:FFFF::2/64
ipv6 rip RIP enable
serial restart-delay 0
!         
interface Serial2/1
no ip address
shutdown 
serial restart-delay 0
!         
interface Serial2/2
no ip address
shutdown
serial restart-delay 0
!
interface Serial2/3
no ip address
shutdown
serial restart-delay 0
!
router rip
version 2
timers basic 3 18 18 24
passive-interface default
no passive-interface Ethernet0/0
network 10.0.0.0
network 172.16.0.0
neighbor 172.16.0.0
distribute-list RIP_WAN out Ethernet0/0
no auto-summary
!
ip forward-protocol nd
!
!
no ip http server
no ip http secure-server
!
ip access-list standard RIP_WAN
deny   172.16.0.0 0.0.0.1
permit any
!
ipv6 router rip RIP
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
key chain RIP
key 1    
key-string ciscolabs
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
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
ip summary-address rip 10.255.0.0 255.255.0.0
tunnel source Ethernet0/1
tunnel mode ipip
tunnel destination 142.158.41.57
!         
interface Tunnel2
no ip address
ipv6 address FD00:AC45:84CD:FFFE::1/64
ipv6 rip RIP enable
ipv6 rip RIP metric-offset 5
tunnel source Ethernet0/1
tunnel mode ipv6ip
tunnel destination 142.158.41.57
!         
interface Ethernet0/0
ip address 10.255.0.2 255.255.255.252
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
ipv6 address FD00:AC45:AC45:1::2/64
ipv6 rip RIP enable
!         
interface Ethernet0/1
ip address 142.158.41.58 255.255.255.252
duplex auto
!         
interface Ethernet0/2
ip address 192.168.0.1 255.255.255.0
ip rip advertise 3
duplex auto
ipv6 address FE80::FFFF link-local
ipv6 address FD00:AC45:AC45:F001::FFFF/64
ipv6 rip RIP enable
!
interface Ethernet0/3
no ip address
shutdown
duplex auto
!
router rip
version 2
timers basic 3 18 18 24
passive-interface default
no passive-interface Ethernet0/0
offset-list RIP_OFFSET out 5 Tunnel1
network 10.0.0.0
network 192.168.0.0
neighbor 10.255.254.2
distribute-list RIP out Tunnel1
no auto-summary
!
ip forward-protocol nd
!
!
no ip http server
no ip http secure-server
!
ip access-list standard RIP
deny   192.168.0.0 0.0.0.255
permit any
ip access-list standard RIP_OFFSET
permit any
!
ipv6 router rip RIP
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
key chain RIP
key 10   
key-string ciscolabs
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
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
ipv6 address FD00:AC45:AC45:2::2/64
ipv6 rip RIP enable
!         
interface Ethernet0/1
ip address 192.168.1.1 255.255.255.0
ip rip advertise 3
duplex auto
ipv6 address FE80::FFFF link-local
ipv6 address FD00:AC45:AC45:F002::FFFF/64
ipv6 rip RIP enable
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
router rip
version 2
timers basic 3 18 18 24
passive-interface default
no passive-interface Ethernet0/0
network 10.0.0.0
network 192.168.1.0
no auto-summary
!
ip forward-protocol nd
!
!
no ip http server
no ip http secure-server
!
ipv6 router rip RIP
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
key chain RIP
key 1    
key-string ciscolabs
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
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
ip summary-address rip 10.254.0.0 255.255.0.0
tunnel source Ethernet0/1
tunnel mode ipip
tunnel destination 142.158.41.58
!         
interface Tunnel2
no ip address
ipv6 address FD00:AC45:84CD:FFFE::2/64
ipv6 rip RIP enable
ipv6 rip RIP metric-offset 5
tunnel source Ethernet0/1
tunnel mode ipv6ip
tunnel destination 142.158.41.58
!         
interface Ethernet0/0
ip address 10.254.0.2 255.255.255.252
ip rip advertise 3
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
ipv6 address FD00:84CD:84CD:1::2/64
ipv6 rip RIP enable
!         
interface Ethernet0/1
ip address 142.158.41.57 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
!         
interface Ethernet0/2
ip address 192.168.3.1 255.255.255.0
ip rip advertise 3
duplex auto
ipv6 address FE80::FFFF link-local
ipv6 address FD00:84CD:84CD:F001::FFFF/64
ipv6 rip RIP enable
!
interface Ethernet0/3
no ip address
shutdown
duplex auto
!
router rip
version 2
timers basic 3 18 18 24
passive-interface default
no passive-interface Ethernet0/0
offset-list RIP_OFFSET out 5 Tunnel1
network 10.0.0.0
network 192.168.3.0
neighbor 10.255.254.1
default-information originate
no auto-summary
!
ip forward-protocol nd
!
!
no ip http server
no ip http secure-server
!
ip access-list standard RIP_OFFSET
permit any
!
ipv6 router rip RIP
!
```


