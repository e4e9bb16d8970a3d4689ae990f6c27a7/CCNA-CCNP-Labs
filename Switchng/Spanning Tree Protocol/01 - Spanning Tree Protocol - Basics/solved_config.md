# SW1
---
```
!
hostname SW1       
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
spanning-tree vlan 1 priority 36864
!         
!         
!         
!         
!         
!         
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
negotiation auto
spanning-tree vlan 1 cost 10
!
interface GigabitEthernet0/1
negotiation auto
spanning-tree vlan 1 cost 16
!
```

# SW2
---
```
!
hostname SW2       
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
interface GigabitEthernet0/0
negotiation auto
!
interface GigabitEthernet0/1
negotiation auto
!
interface GigabitEthernet0/2
negotiation auto
spanning-tree vlan 1 cost 16
!
```

# SW3
---
```
!
hostname SW3       
!         
!         
spanning-tree mode pvst
spanning-tree extend system-id
spanning-tree vlan 1 priority 28672
!         
!         
!         
!         
!         
!         
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
spanning-tree vlan 1 port-priority 16
!
```

# SW4
---
```
!
hostname SW4
!
```

# SW5
---
```
!
hostname SW5
!
spanning-tree mode pvst
spanning-tree extend system-id
spanning-tree vlan 1 priority 24576
!
```
