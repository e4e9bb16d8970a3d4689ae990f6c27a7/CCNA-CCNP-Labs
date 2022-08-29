# R1
---
```
!
router rip
version 2
network 10.0.0.0
network 172.16.0.0
no auto-summary
!
```

# R2
---
```
!
router rip
version 2
network 10.0.0.0
network 192.168.0.0
no auto-summary
!
```

# R3
---
```
!
router rip
version 2
network 10.0.0.0
network 172.16.0.0
no auto-summary
!
```