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
ethernet lmi ce
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
ip cef    
no ipv6 cef
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
interface GigabitEthernet0/0
ip address 172.16.0.1 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/1
ip address 172.16.0.5 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/2
ip address 172.16.0.9 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/3
no ip address
shutdown 
duplex auto
speed auto
media-type rj45
!         
router rip
version 2
passive-interface default
network 172.16.0.0
neighbor 172.16.0.2
neighbor 172.16.0.6
neighbor 172.16.0.10
distribute-list gateway RIP_DSTL in GigabitEthernet0/2
no auto-summary
!
ip forward-protocol nd
!
!
no ip http server
no ip http secure-server
!
ip access-list standard RIP_DSTL
permit 172.16.0.22
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
ethernet lmi ce
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
ip cef    
no ipv6 cef
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
interface GigabitEthernet0/0
ip address 172.16.0.18 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/1
ip address 172.16.0.2 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/2
ip address 172.16.0.14 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/3
no ip address
shutdown
duplex auto
speed auto
media-type rj45
!
router rip
version 2
passive-interface default
no passive-interface GigabitEthernet0/1
network 172.16.0.0
neighbor 172.16.0.17
neighbor 172.16.0.1
neighbor 172.16.0.13
distribute-list gateway RIP_DSTL in GigabitEthernet0/0
no auto-summary
!
ip forward-protocol nd
!
!
no ip http server
no ip http secure-server
!
ip access-list standard RIP_DSTL
permit 172.16.0.22
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
ethernet lmi ce
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
ip cef    
no ipv6 cef
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
interface GigabitEthernet0/0
ip address 172.16.0.17 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/1
ip address 172.16.0.21 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/2
ip address 172.16.0.10 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/3
no ip address
shutdown
duplex auto
speed auto
media-type rj45
!
router rip
version 2
passive-interface default
offset-list RIP_OFFSET in 5 GigabitEthernet0/2
network 172.16.0.0
neighbor 172.16.0.16
neighbor 172.16.0.9
neighbor 172.16.0.22
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
```

# R4
---
```
!
hostname R4
!
boot-start-marker
boot-end-marker
!
!
!
no aaa new-model
ethernet lmi ce
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
ip cef    
no ipv6 cef
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
interface GigabitEthernet0/0
ip address 172.16.0.13 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/1
ip address 172.16.0.6 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/2
ip address 172.16.0.26 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/3
no ip address
shutdown
duplex auto
speed auto
media-type rj45
!
router rip
version 2
passive-interface default
network 172.16.0.0
neighbor 172.16.0.14
neighbor 172.16.0.5
neighbor 172.16.0.25
no auto-summary
!
```

# Switch1
---
```
!
hostname Switch1
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
!
!         
!         
!         
!         
ip cef    
no ipv6 cef
!         
key chain RIP
key 1    
key-string ciscolabs
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
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
interface Loopback0
ip address 192.168.1.1 255.255.255.0
!         
interface Loopback1
ip address 10.10.0.1 255.255.255.0
!         
interface GigabitEthernet0/0
no switchport
ip address 172.16.0.22 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
negotiation auto
!
interface GigabitEthernet0/1
negotiation auto
!
interface GigabitEthernet0/2
negotiation auto
!
interface GigabitEthernet0/3
negotiation auto
!
interface GigabitEthernet1/0
negotiation auto
!
interface GigabitEthernet1/1
negotiation auto
!
interface GigabitEthernet1/2
negotiation auto
!
interface GigabitEthernet1/3
negotiation auto
!
router rip
version 2
network 10.0.0.0
network 172.16.0.0
network 192.168.1.0
neighbor 172.16.0.21
no auto-summary
!
```

# Switch2
---
```
!
hostname Switch2
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
!
!         
!         
!         
!         
ip cef    
no ipv6 cef
!         
key chain RIP
key 1    
key-string ciscolabs
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
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
interface Loopback0
ip address 10.20.1.1 255.255.255.0
!         
interface Loopback1
ip address 172.16.0.254 255.255.255.255
!         
interface GigabitEthernet0/0
no switchport
ip address 172.16.0.25 255.255.255.252
ip rip authentication mode md5
ip rip authentication key-chain RIP
negotiation auto
!         
interface GigabitEthernet0/1
negotiation auto
!         
interface GigabitEthernet0/2
negotiation auto
!         
interface GigabitEthernet0/3
negotiation auto
!         
interface GigabitEthernet1/0
negotiation auto
!         
interface GigabitEthernet1/1
negotiation auto
!         
interface GigabitEthernet1/2
negotiation auto
!         
interface GigabitEthernet1/3
negotiation auto
!         
router rip
version 2
network 10.0.0.0
network 172.16.0.0
neighbor 172.16.0.26
no auto-summary
!    
```


