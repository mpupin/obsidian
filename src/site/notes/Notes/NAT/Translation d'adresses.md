---
{"dg-publish":true,"permalink":"/notes/nat/translation-d-adresses/"}
---

Convertir l'access-list 1 et 2 jusqu'a G0/0 
```
ip nat inside source list 1 interface GigabitEthernet0/0 overload

ip nat inside source list 2 interface GigabitEthernet0/0 overload
```
[[Notes/NAT/Access-list pour le NAT\|Access-list pour le NAT]]
[[Notes/NAT/Vérifier le bon fonctionnement de la translation\|Vérifier le bon fonctionnement de la translation]]