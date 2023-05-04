---
{"dg-publish":true,"permalink":"/notes/qos/priorite-a-un-protocole/"}
---

```
MonRouteur (config)#policy-map ma-politique-qos
MonRouteur (config-pmap)#class prio-sur-ftp
MonRouteur (config-pmap-c)#set ip dscp cs1
MonRouteur (config-pmap-c)#exit
```
[[Notes/QOS/Appliquer une priorité DSCP à un port\|Appliquer une priorité DSCP à un port]]
[[Notes/QOS/Declaration d'une priorité sur champ DSCP\|Declaration d'une priorité sur champ DSCP]]
[[Notes/QOS/Donner une priorité haute à une machine\|Donner une priorité haute à une machine]]
[[Notes/QOS/Priorité à un protocole\|Priorité à un protocole]]
[[Notes/QOS/Priorité sur une bande passante\|Priorité sur une bande passante]]
[[Notes/QOS/Verifier classe QOS\|Verifier classe QOS]]
[[Notes/QOS/Vérifier priorité DSCP\|Vérifier priorité DSCP]]