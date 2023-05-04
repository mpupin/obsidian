---
{"dg-publish":true,"permalink":"/notes/qos/declaration-d-une-priorite-sur-champ-dscp/"}
---

```
MonRouteur (config)#policy-map ma-politique-qos
MonRouteur (config-pmap)#class prio-sur-interface
MonRouteur (config-pmap-c)#set ip dscp cs7
MonRouteur (config-pmap-c)#exit
```

Vérification :
[[Notes/QOS/Vérifier priorité DSCP\|Vérifier priorité DSCP]]
[[Notes/QOS/Verifier classe QOS\|Verifier classe QOS]]
[[Notes/QOS/Priorité sur une bande passante\|Priorité sur une bande passante]]
[[Notes/QOS/Priorité à un protocole\|Priorité à un protocole]]
[[Notes/QOS/Donner une priorité haute à une machine\|Donner une priorité haute à une machine]]
[[Notes/QOS/Appliquer une priorité DSCP à un port\|Appliquer une priorité DSCP à un port]]