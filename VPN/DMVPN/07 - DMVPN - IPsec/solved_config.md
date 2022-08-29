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
 no ip split-horizon eigrp 65535
 ip nhrp authentication encor
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.2 192.0.2.2
 ip nhrp map multicast 192.0.2.2
 ip nhrp network-id 1
 ip nhrp redirect
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
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
 no ip split-horizon eigrp 65535
 ip nhrp authentication encor
 ip nhrp map multicast dynamic
 ip nhrp map 10.124.124.1 192.0.2.1
 ip nhrp map multicast 192.0.2.1
 ip nhrp network-id 1
 ip nhrp redirect
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
!

```
# R3
```
!
router eigrp 65535
 network 10.12.12.0 0.0.0.255
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
 ip nhrp authentication encor
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip nhrp nhs 10.124.124.2 nbma 192.0.2.2 multicast
 ip nhrp shortcut
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
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
 ip nhrp authentication encor
 ip nhrp network-id 1
 ip nhrp nhs 10.124.124.1 nbma 192.0.2.1 multicast
 ip nhrp nhs 10.124.124.2 nbma 192.0.2.2 multicast
 ip nhrp shortcut
 ip tcp adjust-mss 1360
 tunnel source GigabitEthernet0/0
 tunnel mode gre multipoint
 tunnel protection ipsec profile DMVPN_IPSEC_PROFILE
!
```
# R6
```
!
router eigrp 65535
 network 10.42.42.0 0.0.0.255
!
```