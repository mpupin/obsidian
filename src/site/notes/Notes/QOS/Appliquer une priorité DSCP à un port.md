---
{"dg-publish":true,"permalink":"/notes/qos/appliquer-une-priorite-dscp-a-un-port/"}
---

En sortie
```
MonRouteur(config)#interface g0/2
MonRouteur(config-if)#service-policy output ma-politique-qos
MonRouteur(config-if)#exit
```

[[Notes/QOS/Declaration d'une priorité sur champ DSCP\|Declaration d'une priorité sur champ DSCP]]
[[Notes/QOS/Donner une priorité haute à une machine\|Donner une priorité haute à une machine]]
[[Notes/QOS/Priorité à un protocole\|Priorité à un protocole]]
[[Notes/QOS/Priorité sur une bande passante\|Priorité sur une bande passante]]
[[Notes/QOS/Verifier classe QOS\|Verifier classe QOS]]
[[Notes/QOS/Vérifier priorité DSCP\|Vérifier priorité DSCP]]