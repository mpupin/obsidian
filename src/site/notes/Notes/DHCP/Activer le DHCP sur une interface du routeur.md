---
{"dg-publish":true,"permalink":"/notes/dhcp/activer-le-dhcp-sur-une-interface-du-routeur/"}
---

Ici notre serveur DHCP prendra les requêtes sur la sous-interface G0/1.10 qui est la passerelle de notre réseau LAN

```
interface g0/1.10
ip helper-address 10.0.100.150
```

[[Notes/DHCP/Créer un serveur DHCP sous Linux\|Créer un serveur DHCP sous Linux]]
[[Notes/Routage/Configurer un routage on a stick\|Configurer un routage on a stick]]
