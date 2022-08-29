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
switchport trunk native vlan 20
switchport mode trunk
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/2
switchport access vlan 10
switchport mode access
negotiation auto
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
switchport trunk native vlan 20
switchport mode trunk
!         
interface Port-channel2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 2 mode on
!         
interface GigabitEthernet0/3
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 2 mode on
!         
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
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
switchport trunk native vlan 20
switchport mode trunk
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport trunk native vlan 20
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
```
# R1
---
```
!
hostname R1
!         
!         
!         
!         
!         
!         
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
no ip address
duplex auto
speed auto
media-type rj45
!
interface GigabitEthernet0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
!
interface GigabitEthernet0/0.20
encapsulation dot1Q 20 native
ip address 192.168.20.1 255.255.255.0
!
```