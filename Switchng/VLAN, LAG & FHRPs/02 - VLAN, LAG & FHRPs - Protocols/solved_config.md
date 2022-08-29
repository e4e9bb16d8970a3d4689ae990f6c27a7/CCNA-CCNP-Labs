# ACCS-Switch-1
---
```
!
hostname ACCS-Switch-1
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
interface Port-channel1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
negotiation auto
channel-group 1 mode active
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
negotiation auto
channel-group 1 mode active
!         
interface GigabitEthernet0/2
switchport access vlan 10
switchport mode access
switchport nonegotiate
negotiation auto
no vtp   
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
interface Vlan10
ip address 192.168.10.2 255.255.255.0
standby version 2
standby 10 ip 192.168.10.1
standby 10 priority 110
standby 10 preempt
!         
interface Vlan20
ip address 192.168.20.2 255.255.255.0
standby 20 ip 192.168.20.1
standby 20 preempt
!   
```

# DST-Switch
---
```
!
hostname DST-Switch
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
interface Port-channel1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
!         
interface Port-channel2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
channel-group 1 mode passive
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
channel-group 1 mode passive
!         
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
channel-group 2 mode auto
!         
interface GigabitEthernet0/3
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
channel-group 2 mode auto
!    
```

# ACCS-Switch-2
---
```
!
hostname ACCS-Switch-2
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
interface Port-channel1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
negotiation auto
channel-group 1 mode desirable
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
negotiation auto
channel-group 1 mode desirable
!         
interface GigabitEthernet0/2
switchport access vlan 10
switchport mode access
switchport nonegotiate
negotiation auto
no vtp   
!         
interface GigabitEthernet0/3
switchport access vlan 20
switchport mode access
switchport nonegotiate
negotiation auto
no vtp   
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
interface Vlan10
ip address 192.168.10.3 255.255.255.0
standby version 2
standby 10 ip 192.168.10.1
standby 10 preempt
!         
interface Vlan20
ip address 192.168.20.3 255.255.255.0
standby 20 ip 192.168.20.1
standby 20 priority 110
standby 20 preempt
!    
```
