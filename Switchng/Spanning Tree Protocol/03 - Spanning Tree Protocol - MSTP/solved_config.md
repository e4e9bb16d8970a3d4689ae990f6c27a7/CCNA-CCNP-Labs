# SW1
---
```
!
hostname SW1       
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R1
revision 1
instance 1 vlan 110
instance 2 vlan 120
instance 3 vlan 130
instance 20 vlan 210, 220, 230
instance 30 vlan 310, 320, 330
!         
!         
!         
!         
!         
!         
!         
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
switchport trunk encapsulation dot1q
switchport mode trunk
!         
interface GigabitEthernet0/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode active
!
```

# SW2
---
```
!
hostname SW2        
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R1
revision 1
instance 1 vlan 110
instance 2 vlan 120
instance 3 vlan 130
instance 20 vlan 210, 220, 230
instance 30 vlan 310, 320, 330
!         
!         
!         
!         
!         
!         
!         
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
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW3
---
```
!
hostname SW3        
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R1
revision 1
instance 1 vlan 110
instance 2 vlan 120
instance 3 vlan 130
instance 20 vlan 210, 220, 230
instance 30 vlan 310, 320, 330
!         
!         
!         
!         
!         
!         
!         
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
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW4
---
```
!
hostname SW4       
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R2
revision 1
instance 1 vlan 210
instance 2 vlan 220
instance 3 vlan 230
instance 10 vlan 110, 120, 130
instance 30 vlan 310, 320, 330
!         
!         
!         
!
!
!
!
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
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW5
---
```
!
hostname SW5        
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R2
revision 1
instance 1 vlan 210
instance 2 vlan 220
instance 3 vlan 230
instance 10 vlan 110, 120, 130
instance 30 vlan 310, 320, 330
!         
spanning-tree mst 0-3,10,30 priority 24576
!         
!         
!         
!
!
!
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
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW6
---
```
!
hostname SW6        
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R2
revision 1
instance 1 vlan 210
instance 2 vlan 220
instance 3 vlan 230
instance 10 vlan 110, 120, 130
instance 30 vlan 310, 320, 330
!         
!         
!         
!         
!         
!         
!         
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
switchport mode trunk
negotiation auto
!         
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!         
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!         
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW7
---
```
!
hostname SW7       
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R2
revision 1
instance 1 vlan 310
instance 2 vlan 320
instance 3 vlan 330
instance 10 vlan 110, 120, 130
instance 20 vlan 210, 220, 230
!         
!         
!         
!         
!         
!         
!         
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
switchport trunk encapsulation dot1q
switchport mode trunk
!
interface GigabitEthernet0/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode active
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
channel-group 1 mode active
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW8
---
```
!
hostname SW8       
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R2
revision 1
instance 1 vlan 310
instance 2 vlan 320
instance 3 vlan 330
instance 10 vlan 110, 120, 130
instance 20 vlan 210, 220, 230
!         
!         
!         
!         
!         
!         
!         
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
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW9
---
```
!
hostname SW9        
!         
spanning-tree mode mst
spanning-tree extend system-id
!         
spanning-tree mst configuration
name LAB-MSTP-R3
revision 1
instance 1 vlan 310
instance 2 vlan 320
instance 3 vlan 330
instance 10 vlan 110, 120, 130
instance 20 vlan 210, 220, 230
!         
!         
!         
!         
!         
!         
!         
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
switchport mode trunk
negotiation auto
!         
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW10
---
```
!
hostname SW10       
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
interface GigabitEthernet0/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

# SW11
---
```
!
hostname SW11
       
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
interface GigabitEthernet0/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/1
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/2
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet0/3
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
interface GigabitEthernet1/0
switchport trunk encapsulation dot1q
switchport mode trunk
negotiation auto
!
```

