# R1
```
!
crypto ikev2 keyring DMVPN_KEYRING
 peer DMVPN_PEER
  address 192.0.2.0 255.255.255.0
  pre-shared-key encor
 !
!
!
crypto ikev2 profile DMVPN_IKEv2_PROFILE
 match identity remote address 192.0.2.0 255.255.255.0
 identity local address 192.0.2.1
 authentication local pre-share
 authentication remote pre-share
 keyring local DMVPN_KEYRING
!
!
!
crypto ipsec transform-set DMVPN_TS esp-aes 256 esp-sha512-hmac
 mode tunnel
!
crypto ipsec profile DMVPN_IPSEC_PROFILE
 set transform-set DMVPN_TS
 set ikev2-profile DMVPN_IKEv2_PROFILE
!
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.1 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.2 192.0.2.2
 ip nhrp map multicast 192.0.2.2
 ip nhrp network-id 1
 ip nhrp redirect
 ip tcp adjust-mss 1360
 ipv6 address 2001:10:124:124::1/64
 ipv6 nhrp map multicast dynamic
 ipv6 nhrp map multicast 192.0.2.2
 ipv6 nhrp map 2001:10:124:124::2/128 192.0.2.2
 ipv6 nhrp network-id 1
 ipv6 nhrp redirect
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
!
!
router eigrp DMVPN
 !
 address-family ipv4 unicast autonomous-system 65535
  !
  af-interface Tunnel1
   no split-horizon
  exit-af-interface
  !
  topology base
  exit-af-topology
  network 10.12.12.0 0.0.0.255
  network 10.124.124.0 0.0.0.255
 exit-address-family
 !
 address-family ipv6 unicast autonomous-system 65535
  !
  af-interface Tunnel1
   no split-horizon
  exit-af-interface
  !
  topology base
  exit-af-topology
 exit-address-family
!
```
# R2
```
!
crypto ikev2 keyring DMVPN_KEYRING
 peer DMVPN_PEER
  address 192.0.2.0 255.255.255.0
  pre-shared-key encor
 !
!
!
crypto ikev2 profile DMVPN_IKEv2_PROFILE
 match identity remote address 192.0.2.0 255.255.255.0
 identity local address 192.0.2.2
 authentication local pre-share
 authentication remote pre-share
 keyring local DMVPN_KEYRING
!
!
!
crypto ipsec transform-set DMVPN_TS esp-aes 256 esp-sha512-hmac
 mode tunnel
!
crypto ipsec profile DMVPN_IPSEC_PROFILE
 set transform-set DMVPN_TS
 set ikev2-profile DMVPN_IKEv2_PROFILE
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.2 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.1 192.0.2.1
 ip nhrp map multicast 192.0.2.1
 ip nhrp network-id 1
 ip nhrp redirect
 ipv6 address 2001:10:124:124::2/64
 ipv6 nhrp map multicast dynamic
 ipv6 nhrp map multicast 192.0.2.2
 ipv6 nhrp map 2001:10:124:124::1/128 192.0.2.1
 ipv6 nhrp network-id 1
 ipv6 nhrp redirect
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
!
!
router eigrp DMVPN
 !
 address-family ipv4 unicast autonomous-system 65535
  !
  af-interface Tunnel1
   no split-horizon
  exit-af-interface
  !
  topology base
  exit-af-topology
  network 10.12.12.0 0.0.0.255
  network 10.124.124.0 0.0.0.255
 exit-address-family
 !
 address-family ipv6 unicast autonomous-system 65535
  !
  af-interface Tunnel1
   no split-horizon
  exit-af-interface
  !
  topology base
  exit-af-topology
 exit-address-family
!
```
# R3
```
!
router eigrp DMVPN
 !
 address-family ipv4 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
  network 10.12.12.0 0.0.0.255
 exit-address-family
 !
 address-family ipv6 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
 exit-address-family
!
```
# R4
```
!
crypto ikev2 keyring DMVPN_KEYRING
 peer DMVPN_PEER
  address 192.0.2.0 255.255.255.0
  pre-shared-key encor
 !
!
!
crypto ikev2 profile DMVPN_IKEv2_PROFILE
 match identity remote address 192.0.2.0 255.255.255.0
 identity local address 192.0.2.4
 authentication local pre-share
 authentication remote pre-share
 keyring local DMVPN_KEYRING
!
!
!
crypto ipsec transform-set DMVPN_TS esp-aes 256 esp-sha512-hmac
 mode tunnel
!
crypto ipsec profile DMVPN_IPSEC_PROFILE
 set transform-set DMVPN_TS
 set ikev2-profile DMVPN_IKEv2_PROFILE
!
!
!
!
!
!
!
interface Loopback0
 ip address 10.30.30.1 255.255.255.0
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.4 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip nhrp nhs 10.124.124.2 nbma 192.0.2.2 multicast
 ip nhrp shortcut
 ip tcp adjust-mss 1360
 ipv6 address 2001:10:124:124::4/64
 ipv6 nhrp network-id 1
 ipv6 nhrp nhs 2001:10:124:124::1 nbma 192.0.2.1 multicast
 ipv6 nhrp nhs 2001:10:124:124::2 nbma 192.0.2.2 multicast
 ipv6 nhrp shortcut
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
!
!
router eigrp DMVPN
 !
 address-family ipv4 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
  network 10.30.30.0 0.0.0.255
  network 10.124.124.0 0.0.0.255
 exit-address-family
 !
 address-family ipv6 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
 exit-address-family
!
```
# R5
```
!
crypto ikev2 keyring DMVPN_KEYRING
 peer DMVPN_PEER
  address 192.0.2.0 255.255.255.0
  pre-shared-key encor
 !
!
!
crypto ikev2 profile DMVPN_IKEv2_PROFILE
 match identity remote address 192.0.2.0 255.255.255.0
 identity local address 192.0.2.5
 authentication local pre-share
 authentication remote pre-share
 keyring local DMVPN_KEYRING
!
!
!
crypto ipsec transform-set DMVPN_TS esp-aes 256 esp-sha512-hmac
 mode tunnel
!
crypto ipsec profile DMVPN_IPSEC_PROFILE
 set transform-set DMVPN_TS
 set ikev2-profile DMVPN_IKEv2_PROFILE
!
!
!
!
!
!
!
interface Tunnel1
 bandwidth 1000000
 ip address 10.124.124.5 255.255.255.0
 no ip redirects
 ip mtu 1400
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip nhrp nhs 10.124.124.2 nbma 192.0.2.2 multicast
 ip nhrp shortcut
 ip tcp adjust-mss 1360
 ipv6 address 2001:10:124:124::5/64
 ipv6 nhrp network-id 1
 ipv6 nhrp nhs 2001:10:124:124::2 nbma 192.0.2.2 multicast
 ipv6 nhrp nhs 2001:10:124:124::1 nbma 192.0.2.1 multicast
 ipv6 nhrp shortcut
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
!
!
router eigrp DMVPN
 !
 address-family ipv4 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
  network 10.42.42.0 0.0.0.255
  network 10.124.124.0 0.0.0.255
 exit-address-family
 !
 address-family ipv6 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
 exit-address-family
!
```
# R6
```
!
router eigrp DMVPN
 !
 address-family ipv4 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
  network 10.42.42.0 0.0.0.255
 exit-address-family
 !
 address-family ipv6 unicast autonomous-system 65535
  !
  topology base
  exit-af-topology
 exit-address-family
!
```