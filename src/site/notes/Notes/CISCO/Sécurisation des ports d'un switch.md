---
{"dg-publish":true,"permalink":"/notes/cisco/securisation-des-ports-d-un-switch/"}
---

Si sur ce port du switch l'adresse MAC qui a envoyé le premier paquet change alors le port se désactive
```
Switch(config)#interface FastEthernet 0/3
Switch(config-if)#switchport mode access
Switch(config-if)#switchport port-security
Switch(config-if)#switchport port-security mac-address sticky
Switch(config-if)#switchport port-security violation shutdown
```

[[Notes/SSH/Configurer SSH sur équipement CISCO\|Configurer SSH sur équipement CISCO]]
[[Notes/CISCO/Reintialiser le mot de passe d'un routeur\|Reintialiser le mot de passe d'un routeur]]
[[Notes/CISCO/Reintialiser les mots de passe d'un Switch Cisco\|Reintialiser les mots de passe d'un Switch Cisco]]
[[Notes/CISCO/Configurer l'interface WEB SF500\|Configurer l'interface WEB SF500]]
