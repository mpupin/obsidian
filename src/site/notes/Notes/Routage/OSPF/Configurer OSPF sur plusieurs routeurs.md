---
{"dg-publish":true,"permalink":"/notes/routage/ospf/configurer-ospf-sur-plusieurs-routeurs/"}
---

Routeur 1 :
```
routeur ospf 1
network 172.16.0.0 0.0.255.255 area 0
network 10.50.100.0 0.0.0.255 area 0
network 10.100.50.0 0.0.0.255 area 0
```
Routeur 2 :
```
routeur ospf 1
network 172.25.0.0 0.0.255.255 area 0
network 10.50.100.0 0.0.0.255 area 0
network 10.100.50.0 0.0.0.255 area 0
```
Routeur 3 :
```
routeur ospf 1
network 172.25.0.0 0.0.255.255 area 0
network 172.16.0.0 0.0.255.255 area 0
network 10.100.50.0 0.0.0.255 area 0
```
Routeur 4 :
```
routeur ospf 1
network 172.25.0.0 0.0.255.255 area 0
network 172.16.0.0 0.0.255.255 area 0
network 10.50.100.0 0.0.0.255 area 0
```
[[Notes/Routage/OSPF/Configuration des IDs routeurs OSPF\|Configuration des IDs routeurs OSPF]]
[[Notes/Routage/OSPF/Verifier les voisins OSPF\|Verifier les voisins OSPF]]
[[Notes/Routage/OSPF/Afficher les réseaux appris\|Afficher les réseaux appris]]