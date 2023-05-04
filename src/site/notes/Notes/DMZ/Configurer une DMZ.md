---
{"dg-publish":true,"permalink":"/notes/dmz/configurer-une-dmz/"}
---

## Notre DMZ autorise uniquement les protocoles HTTP/HTTPS, DNS, SSH, ICMP
Le SSH est en local.
Ne pas oubliez de mettre les ports en inside/outside, ACL en entrant ou sortant (entrant = entre dans le routeur, outside = sort du routeur )

ip nat inside source list 1 interface GigabitEthernet0/0 overload

ip nat inside source list 2 interface GigabitEthernet0/0 overload

ip nat inside source static tcp 10.80.64.20 53 172.25.100.10 53 extendable

ip nat inside source static udp 10.80.64.20 53 172.25.100.10 53 extendable

ip nat inside source static tcp 10.80.64.20 80 172.25.100.10 80 extendable

ip nat inside source static tcp 10.80.64.20 443 172.25.100.10 443 extendable

ip route 0.0.0.0 0.0.0.0 172.25.254.254
!
access-list 1 permit 172.16.0.0 0.0.255.255

access-list 2 permit 10.0.0.0 0.255.255.255

access-list 101 permit tcp 10.80.64.0 0.0.0.255 any eq www

access-list 101 permit tcp 10.80.64.0 0.0.0.255 any eq 443

access-list 101 permit tcp 10.80.64.0 0.0.0.255 any eq 123

access-list 101 permit tcp 10.80.64.0 0.0.0.255 any eq domain

access-list 101 permit icmp any any

access-list 101 permit udp 10.80.64.0 0.0.0.255 any eq domain

access-list 101 permit udp 10.80.64.0 0.0.0.255 eq domain any

access-list 101 permit tcp 10.80.64.0 0.0.0.255 eq www any

access-list 101 permit tcp 10.80.64.0 0.0.0.255 eq 443 any

access-list 101 permit tcp 10.80.64.0 0.0.0.255 eq 2222 172.16.0.0 0.0.255.255

access-list 102 permit tcp 172.16.0.0 0.0.255.255 any eq 22

access-list 102 permit tcp 172.16.0.0 0.0.255.255 any eq www

access-list 102 permit tcp 172.16.0.0 0.0.255.255 any eq 443

access-list 102 permit tcp 172.16.0.0 0.0.255.255 any eq 123

access-list 102 permit tcp 172.16.0.0 0.0.255.255 any eq domain

access-list 102 permit udp 172.16.0.0 0.0.255.255 any eq domain

access-list 102 permit icmp any any

access-list 102 permit tcp 172.16.0.0 0.0.255.255 any eq 2222

access-list 104 permit tcp any any established

access-list 104 permit udp any eq domain any

access-list 104 permit tcp any 172.25.0.0 0.0.255.255 eq www

access-list 104 permit icmp any any
