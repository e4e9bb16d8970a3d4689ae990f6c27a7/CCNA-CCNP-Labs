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
vlan 10
vlan 20        
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
switchport mode trunk
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
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
vlan 10
vlan 20         
!         
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
switchport mode trunk
!         
interface Port-channel2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 2 mode on
!         
interface GigabitEthernet0/3
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 2 mode on
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
vlan 10
vlan 20     
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
switchport mode trunk
!         
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode on
!         
interface GigabitEthernet0/2
switchport access vlan 10
switchport mode access
negotiation auto
!         
interface GigabitEthernet0/3
switchport access vlan 20
switchport mode access
negotiation auto
!  
```