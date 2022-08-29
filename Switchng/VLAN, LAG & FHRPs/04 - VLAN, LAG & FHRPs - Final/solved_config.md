# Core-Switch
---
```
!
hostname Core-Switch
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
no ip domain-lookup
ip cef    
no ipv6 cef
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
!         
lldp run  
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
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode trunk
switchport nonegotiate
negotiation auto
!         
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode trunk
switchport nonegotiate
negotiation auto
!         
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20,30,100
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode trunk
switchport nonegotiate
negotiation auto
!      
```

# DST-Switch-1
---
```
!
hostname DST-Switch-1
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
vtp file vtp.vlan.conf
!         
!         
!         
no ip domain-lookup
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
!         
lldp run  
!         
track 10 interface GigabitEthernet0/0 line-protocol
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
interface Port-channel1
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode trunk
negotiation auto
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
negotiation auto
channel-group 1 mode active
!         
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
negotiation auto
channel-group 1 mode active
!         
interface GigabitEthernet0/3
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
negotiation auto
!         
interface GigabitEthernet1/0
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
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
interface Vlan10
ip address 10.0.10.1 255.255.255.0
ip access-group 110 in
ip helper-address 10.0.100.10 
standby version 2
standby 10 ipv6 FE80::FFFF
standby 10 ipv6 2001:A:B:10::FFFF/64
standby 10 priority 110
standby 10 preempt
standby 10 authentication md5 key-string 7 045802150C2E404F0B0A
standby 10 track 10 decrement 10
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:10::1/64
ipv6 traffic-filter VLAN10 in
glbp 10 ip 10.0.10.254
glbp 10 priority 110
glbp 10 preempt
glbp 10 authentication md5 key-string 7 02050D48080903204E5D
glbp 10 weighting track 10
!         
interface Vlan20
ip address 10.0.20.1 255.255.255.0
ip access-group 120 in
ip helper-address 10.0.100.10 
standby version 2
standby 20 ipv6 FE80::FFFF
standby 20 ipv6 2001:A:B:20::FFFF/64
standby 20 priority 110
standby 20 preempt
standby 20 authentication md5 key-string 7 104D000A06181E0A0E17
standby 20 track 10 decrement 10
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:20::1/64
ipv6 traffic-filter VLAN20 in
glbp 20 ip 10.0.20.254
glbp 20 priority 110
glbp 20 preempt
glbp 20 authentication md5 key-string 7 110A1016141D070D0639
glbp 20 weighting track 10
!         
interface Vlan30
ip address 10.0.30.1 255.255.255.0
ip access-group 130 in
ip helper-address 10.0.100.10 
standby version 2
standby 30 ipv6 FE80::FFFF
standby 30 ipv6 2001:A:B:30::FFFF/64
standby 30 priority 120
standby 30 preempt
standby 30 authentication md5 key-string 7 104D000A06181E0A0E17
standby 30 track 10 decrement 10
ipv6 address FE80::1 link-local
ipv6 address 2001:A:B:30::1/64
ipv6 traffic-filter VLAN30 in
glbp 30 ip 10.0.30.254
glbp 30 preempt
glbp 30 authentication md5 key-string 7 13061E010803082B2937
glbp 30 weighting track 10
!         
interface Vlan100
ip address 10.0.100.51 255.255.255.0
ipv6 address 2001:A:B:100::51/64
!         
ip forward-protocol nd
!         
ip http server
!         
ip ssh server algorithm encryption aes128-ctr aes192-ctr aes256-ctr
ip ssh client algorithm encryption aes128-ctr aes192-ctr aes256-ctr
!         
!         
access-list 110 permit ip 10.0.10.0 0.0.0.255 host 10.0.10.254
access-list 110 permit udp any any eq bootps
access-list 110 permit udp any any eq bootpc
access-list 110 permit ip 10.0.10.0 0.0.0.255 10.0.10.0 0.0.0.255
access-list 110 permit ip 10.0.10.0 0.0.0.255 host 224.0.0.102
access-list 110 permit ip 10.0.10.0 0.0.0.255 10.0.20.0 0.0.0.255
access-list 110 permit ip 10.0.10.0 0.0.0.255 host 10.0.100.10
access-list 110 deny   ip any any
access-list 120 permit ip 10.0.20.0 0.0.0.255 host 10.0.20.254
access-list 120 permit udp any any eq bootps
access-list 120 permit udp any any eq bootpc
access-list 120 permit ip 10.0.20.0 0.0.0.255 10.0.20.0 0.0.0.255
access-list 120 permit ip 10.0.20.0 0.0.0.255 host 224.0.0.102
access-list 120 permit ip 10.0.20.0 0.0.0.255 10.0.10.0 0.0.0.255
access-list 120 permit ip 10.0.20.0 0.0.0.255 host 10.0.100.10
access-list 120 permit ip 10.0.20.0 0.0.0.255 10.0.30.0 0.0.0.255
access-list 120 deny   ip any any
access-list 130 permit ip 10.0.30.0 0.0.0.255 host 10.0.20.254
access-list 130 permit udp any any eq bootps
access-list 130 permit udp any any eq bootpc
access-list 130 permit ip 10.0.30.0 0.0.0.255 host 224.0.0.102
access-list 130 permit ip 10.0.30.0 0.0.0.255 10.0.20.0 0.0.0.255
access-list 130 permit ip 10.0.30.0 0.0.0.255 host 10.0.100.10
access-list 130 deny   ip any any
!         
!         
!         
!         
ipv6 access-list VLAN10
sequence 1 permit icmp any any nd-ns
sequence 2 permit icmp any any nd-na
sequence 3 permit icmp any any router-solicitation
sequence 4 permit icmp any any router-advertisement
sequence 5 permit ipv6 FE80::/16 FE80::/16
sequence 7 permit ipv6 FE80::/16 FF02::/16
sequence 10 permit ipv6 2001:A:B:10::/64 2001:A:B:20::/64
permit ipv6 2001:A:B:10::/64 host 2001:A:B:100::10
sequence 100 deny ipv6 any any
!         
ipv6 access-list VLAN20
sequence 1 permit icmp any any nd-ns
sequence 2 permit icmp any any nd-na
sequence 3 permit icmp any any router-solicitation
sequence 4 permit icmp any any router-advertisement
sequence 5 permit ipv6 FE80::/16 FE80::/16
sequence 7 permit ipv6 FE80::/16 FF02::/16
sequence 10 permit ipv6 2001:A:B:20::/64 2001:A:B:10::/64
permit ipv6 2001:A:B:20::/64 host 2001:A:B:100::10
permit ipv6 2001:A:B:20::/64 2001:A:B:30::/64
sequence 100 deny ipv6 any any
!         
ipv6 access-list VLAN30
sequence 1 permit icmp any any nd-ns
sequence 2 permit icmp any any nd-na
sequence 3 permit icmp any any router-solicitation
sequence 4 permit icmp any any router-advertisement
sequence 5 permit ipv6 FE80::/16 FE80::/16
sequence 7 permit ipv6 FE80::/16 FF02::/16
sequence 10 permit ipv6 2001:A:B:30::/64 2001:A:B:20::/64
permit ipv6 2001:A:B:30::/64 host 2001:A:B:100::10
sequence 100 deny ipv6 any any
!
```

# DST-Switch-2
---
```
!
hostname DST-Switch-2
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
no ip domain-lookup
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
!         
lldp run  
!         
track 10 interface GigabitEthernet0/0 line-protocol
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
interface Port-channel1
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode trunk
negotiation auto
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
negotiation auto
channel-group 1 mode active
!         
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
negotiation auto
channel-group 1 mode active
!         
interface GigabitEthernet0/3
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
negotiation auto
!         
interface GigabitEthernet1/0
switchport trunk allowed vlan 10,20,30,100,2048
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport mode dynamic desirable
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
interface Vlan10
ip address 10.0.10.2 255.255.255.0
ip access-group 110 in
ip helper-address 10.0.100.10 
standby version 2
standby 10 ipv6 FE80::FFFF
standby 10 ipv6 2001:A:B:10::FFFF/64
standby 10 preempt
standby 10 authentication md5 key-string 7 070C285F4D0615041501
standby 10 track 10 decrement 10
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:10::2/64
ipv6 traffic-filter VLAN10 in
glbp 10 ip 10.0.10.254
glbp 10 preempt
glbp 10 authentication md5 key-string 7 070C285F4D0615041501
glbp 10 weighting track 10
!         
interface Vlan20
ip address 10.0.20.2 255.255.255.0
ip access-group 120 in
ip helper-address 10.0.100.10 
standby version 2
standby 20 ipv6 FE80::FFFF
standby 20 ipv6 2001:A:B:20::FFFF/64
standby 20 preempt
standby 20 authentication md5 key-string 7 045802150C2E404F0B0A
standby 20 track 10 decrement 10
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:20::2/64
ipv6 traffic-filter VLAN20 in
glbp 20 ip 10.0.20.254
glbp 20 preempt
glbp 20 authentication md5 key-string 7 02050D48080903204E5D
glbp 20 weighting track 10
!         
interface Vlan30
ip address 10.0.30.2 255.255.255.0
ip access-group 130 in
ip helper-address 10.0.100.10 
standby version 2
standby 30 ipv6 FE80::FFFF
standby 30 ipv6 2001:A:B:30::FFFF/64
standby 30 priority 110
standby 30 preempt
standby 30 authentication md5 key-string 7 00071A15075407070D32
standby 30 track 10 decrement 10
ipv6 address FE80::2 link-local
ipv6 address 2001:A:B:30::2/64
ipv6 traffic-filter VLAN30 in
glbp 30 ip 10.0.30.254
glbp 30 priority 110
glbp 30 preempt
glbp 30 authentication md5 key-string 7 121A0C04110400052838
glbp 30 weighting track 10
!         
interface Vlan100
ip address 10.0.100.52 255.255.255.0
ipv6 address 2001:A:B:100::52/64
!         
ip forward-protocol nd
!         
ip http server
!         
ip ssh server algorithm encryption aes128-ctr aes192-ctr aes256-ctr
ip ssh client algorithm encryption aes128-ctr aes192-ctr aes256-ctr
!         
!         
access-list 110 permit ip 10.0.10.0 0.0.0.255 host 10.0.10.254
access-list 110 permit udp any any eq bootps
access-list 110 permit udp any any eq bootpc
access-list 110 permit ip 10.0.10.0 0.0.0.255 10.0.10.0 0.0.0.255
access-list 110 permit ip 10.0.10.0 0.0.0.255 host 224.0.0.102
access-list 110 permit ip 10.0.10.0 0.0.0.255 10.0.20.0 0.0.0.255
access-list 110 permit ip 10.0.10.0 0.0.0.255 host 10.0.100.10
access-list 110 deny   ip any any
access-list 120 permit ip 10.0.20.0 0.0.0.255 host 10.0.20.254
access-list 120 permit udp any any eq bootps
access-list 120 permit udp any any eq bootpc
access-list 120 permit ip 10.0.20.0 0.0.0.255 10.0.20.0 0.0.0.255
access-list 120 permit ip 10.0.20.0 0.0.0.255 host 224.0.0.102
access-list 120 permit ip 10.0.20.0 0.0.0.255 10.0.10.0 0.0.0.255
access-list 120 permit ip 10.0.20.0 0.0.0.255 host 10.0.100.10
access-list 120 permit ip 10.0.20.0 0.0.0.255 10.0.30.0 0.0.0.255
access-list 120 deny   ip any any
access-list 130 permit ip 10.0.30.0 0.0.0.255 host 10.0.20.254
access-list 130 permit udp any any eq bootps
access-list 130 permit udp any any eq bootpc
access-list 130 permit ip 10.0.30.0 0.0.0.255 host 224.0.0.102
access-list 130 permit ip 10.0.30.0 0.0.0.255 10.0.20.0 0.0.0.255
access-list 130 permit ip 10.0.30.0 0.0.0.255 host 10.0.100.10
access-list 130 deny   ip any any
!         
!         
!         
!         
ipv6 access-list VLAN10
sequence 1 permit icmp any any nd-ns
sequence 2 permit icmp any any nd-na
sequence 3 permit icmp any any router-solicitation
sequence 4 permit icmp any any router-advertisement
sequence 5 permit ipv6 FE80::/16 FE80::/16
sequence 7 permit ipv6 FE80::/16 FF02::/16
sequence 10 permit ipv6 2001:A:B:10::/64 2001:A:B:20::/64
permit ipv6 2001:A:B:10::/64 host 2001:A:B:100::10
sequence 100 deny ipv6 any any
!         
ipv6 access-list VLAN20
sequence 1 permit icmp any any nd-ns
sequence 2 permit icmp any any nd-na
sequence 3 permit icmp any any router-solicitation
sequence 4 permit icmp any any router-advertisement
sequence 5 permit ipv6 FE80::/16 FE80::/16
sequence 7 permit ipv6 FE80::/16 FF02::/16
sequence 10 permit ipv6 2001:A:B:20::/64 2001:A:B:10::/64
permit ipv6 2001:A:B:20::/64 host 2001:A:B:100::10
permit ipv6 2001:A:B:20::/64 2001:A:B:30::/64
sequence 100 deny ipv6 any any
!         
ipv6 access-list VLAN30
sequence 1 permit icmp any any nd-ns
sequence 2 permit icmp any any nd-na
sequence 3 permit icmp any any router-solicitation
sequence 4 permit icmp any any router-advertisement
sequence 5 permit ipv6 FE80::/16 FE80::/16
sequence 7 permit ipv6 FE80::/16 FF02::/16
sequence 10 permit ipv6 2001:A:B:30::/64 2001:A:B:20::/64
permit ipv6 2001:A:B:30::/64 host 2001:A:B:100::10
sequence 100 deny ipv6 any any
!
```

# DSW-Switch-3
---
```
!
hostname DSW-Switch-3
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
vtp domain ciscolabs
vtp mode off
!         
!         
!         
no ip domain-lookup
ip cef    
ipv6 unicast-routing
ipv6 cef  
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
!         
!         
vlan 10,20,30 
!         
vlan 100  
private-vlan primary
private-vlan association 101,110
!         
vlan 101  
private-vlan community
!         
vlan 110  
private-vlan isolated
lldp run  
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
switchport trunk allowed vlan 10,20,30,100
switchport trunk encapsulation dot1q
switchport trunk native vlan 2048
switchport private-vlan trunk allowed vlan 10,20,30,100
switchport mode trunk
negotiation auto
!         
interface GigabitEthernet0/1
switchport private-vlan host-association 100 101
switchport mode private-vlan host
negotiation auto
!         
interface GigabitEthernet0/2
switchport private-vlan host-association 100 110
switchport mode private-vlan host
negotiation auto
!         
interface GigabitEthernet0/3
switchport private-vlan host-association 100 101
switchport mode private-vlan host
negotiation auto
!         
interface GigabitEthernet1/0
switchport access vlan 100
switchport private-vlan mapping 100 101,110
switchport mode private-vlan promiscuous
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
interface Vlan10
ip address 10.0.10.3 255.255.255.0
ipv6 address autoconfig
!         
interface Vlan20
ip address 10.0.20.3 255.255.255.0
ipv6 address autoconfig
!         
interface Vlan30
ip address 10.0.30.3 255.255.255.0
ipv6 address autoconfig
!         
interface Vlan100
ip address 10.0.100.1 255.255.255.0
ipv6 address 2001:A:B:100::FFFF/64
private-vlan mapping 101,110
!    
```

# ACCS-Switch-1
---
```
!
hostname ACCS-Switch-1
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
ip arp inspection vlan 10,20,30
!         
!         
!         
ip dhcp snooping vlan 10,20,30
no ip dhcp snooping information option
ip dhcp snooping database flash:dhcp.dat
ip dhcp snooping
no ip domain-lookup
ip cef    
no ipv6 cef
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
!         
lldp run  
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
description DST-Switch-1
switchport trunk allowed vlan 10,20,30
switchport trunk native vlan 2048
ip arp inspection trust
negotiation auto
ip dhcp snooping trust
!         
interface GigabitEthernet0/1
description DST-Switch-2
switchport trunk allowed vlan 10,20,30
switchport trunk native vlan 2048
ip arp inspection trust
negotiation auto
ip dhcp snooping trust
!         
interface GigabitEthernet0/2
description Edge
switchport access vlan 10
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security mac-address sticky 0050.7966.680a
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
!         
interface GigabitEthernet0/3
description Edge
switchport access vlan 20
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security mac-address sticky 0050.7966.6804
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
interface GigabitEthernet1/0
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
interface GigabitEthernet1/1
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
interface GigabitEthernet1/2
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
interface GigabitEthernet1/3
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
```

# ACCS-Switch-2
---
```
!
hostname ACCS-Switch-2
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
ip arp inspection vlan 10,20,30
!         
!         
!         
ip dhcp snooping vlan 10,20,30
no ip dhcp snooping information option
ip dhcp snooping database flash:dhcp.dat
ip dhcp snooping
no ip domain-lookup
ip cef    
no ipv6 cef
!         
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
!         
lldp run  
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
description DST-Switch-1
switchport trunk allowed vlan 10,20,30
switchport trunk native vlan 2048
ip arp inspection trust
negotiation auto
ip dhcp snooping trust
!         
interface GigabitEthernet0/1
description DST-Switch-2
switchport trunk allowed vlan 10,20,30
switchport trunk native vlan 2048
ip arp inspection trust
negotiation auto
ip dhcp snooping trust
!         
interface GigabitEthernet0/2
description Edge
switchport access vlan 10
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security mac-address sticky 0050.7966.6806
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
!         
interface GigabitEthernet0/3
description Edge
switchport access vlan 30
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security mac-address sticky 0050.7966.6805
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
interface GigabitEthernet1/0
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
interface GigabitEthernet1/1
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!         
interface GigabitEthernet1/2
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!
interface GigabitEthernet1/3
description Edge
switchport access vlan 2048
switchport mode access
switchport nonegotiate
switchport port-security violation restrict
switchport port-security mac-address sticky
switchport port-security
negotiation auto
no lldp transmit
no cdp enable
ip verify source port-security
ip dhcp snooping limit rate 10
!
```

# DHCP
---
```
!
hostname DHCP
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
ip dhcp excluded-address 10.0.10.1 10.0.10.10
ip dhcp excluded-address 10.0.10.250 10.0.10.254
ip dhcp excluded-address 10.0.20.1 10.0.20.10
ip dhcp excluded-address 10.0.20.250 10.0.20.254
ip dhcp excluded-address 10.0.30.1 10.0.30.10
ip dhcp excluded-address 10.0.30.250 10.0.30.254
ip dhcp excluded-address 10.0.100.1 10.0.100.128
!         
ip dhcp pool VLAN10
network 10.0.10.0 255.255.255.0
default-router 10.0.10.254 
dns-server 10.0.100.100 
domain-name ciscolabs
!         
ip dhcp pool VLAN20
network 10.0.20.0 255.255.255.0
default-router 10.0.20.254 
dns-server 10.0.100.100 
domain-name ciscolabs
!         
ip dhcp pool VLAN30
network 10.0.30.0 255.255.255.0
default-router 10.0.30.254 
dns-server 10.0.100.100 
domain-name ciscolabs
!         
ip dhcp pool VLAN100
network 10.0.100.0 255.255.255.0
default-router 10.0.100.1 
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
ip address 10.0.100.10 255.255.255.0
duplex auto
speed auto
media-type rj45
ipv6 address 2001:A:B:100::10/64
ipv6 nd other-config-flag
!         
interface GigabitEthernet0/1
no ip address
shutdown 
duplex auto
speed auto
media-type rj45
!         
interface GigabitEthernet0/2
no ip address
shutdown 
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
ip forward-protocol nd
!         
!         
no ip http server
no ip http secure-server
ip route 0.0.0.0 0.0.0.0 10.0.100.1
!         
ipv6 route ::/0 2001:A:B:100::FFFF
!   
```

