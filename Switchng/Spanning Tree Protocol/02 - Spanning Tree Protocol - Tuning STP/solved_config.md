# DSW1
---
```
!
hostname DSW1       
!         
spanning-tree mode rapid-pvst
spanning-tree extend system-id
spanning-tree backbonefast
spanning-tree vlan 1,10,20 priority 24576
!         
!         
!         
!         
!         
!         
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
spanning-tree portfast network
!
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
spanning-tree portfast network
!
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
spanning-tree portfast network
!
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode active
!
interface GigabitEthernet0/3
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode active
!
```

# DSW2
---
```
!
hostname DSW2       
!         
spanning-tree mode rapid-pvst
spanning-tree extend system-id
spanning-tree backbonefast
spanning-tree vlan 1,10,20 priority 28672
!         
!         
!         
!         
!         
!         
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
spanning-tree portfast network
!
interface GigabitEthernet0/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
spanning-tree portfast network
!
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode dynamic desirable
negotiation auto
spanning-tree portfast network
!
interface GigabitEthernet0/2
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode active
!
interface GigabitEthernet0/3
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode active
!
```

# SW1
---
```
!
hostname SW1       
!         
spanning-tree mode rapid-pvst
spanning-tree portfast edge default
spanning-tree portfast edge bpduguard default
spanning-tree extend system-id
spanning-tree backbonefast
!         
!         
!         
!         
!         
!         
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
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/2
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet0/3
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet1/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet1/1
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/2
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/3
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
```

# SW2
---
```
!
hostname SW2        
!         
spanning-tree mode rapid-pvst
spanning-tree portfast edge default
spanning-tree portfast edge bpduguard default
spanning-tree extend system-id
spanning-tree backbonefast
!         
!         
!         
!         
!         
!         
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
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/2
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet0/3
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/0
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/1
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/2
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/3
switchport access vlan 20
switchport mode access
negotiation auto
spanning-tree guard root
!
```

# SW3
---
```
!
hostname SW3       
!         
spanning-tree mode rapid-pvst
spanning-tree portfast edge default
spanning-tree portfast edge bpduguard default
spanning-tree extend system-id
spanning-tree backbonefast
!         
!         
!         
!         
!         
!         
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
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/2
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet0/3
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet1/0
switchport access vlan 10
switchport mode access
negotiation auto
!         
interface GigabitEthernet1/1
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet1/2
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet1/3
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!   
```

# SW4
---
```
!
hostname SW4       
!         
spanning-tree mode rapid-pvst
spanning-tree portfast edge default
spanning-tree portfast edge bpduguard default
spanning-tree extend system-id
spanning-tree backbonefast
!         
!         
!         
!         
!         
!         
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
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/1
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!         
interface GigabitEthernet0/2
description Edge
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet0/3
description Edge
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!         
interface GigabitEthernet1/0
switchport trunk allowed vlan 10,20
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
spanning-tree portfast network
!
interface GigabitEthernet1/1
description Edge
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/2
description Edge
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!
interface GigabitEthernet1/3
description Edge
switchport access vlan 10
switchport mode access
negotiation auto
spanning-tree guard root
!
```

