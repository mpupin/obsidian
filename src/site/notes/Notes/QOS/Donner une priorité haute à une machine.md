---
{"dg-publish":true,"permalink":"/notes/qos/donner-une-priorite-haute-a-une-machine/"}
---

```
MonRouteur#configure terminal
MonRouteur(config)#class-map match-all prio-sur-interface
MonRouteur(config-cmap)#match input-interface g0/0
MonRouteur(config-cmap)#exit
```
[[Notes/QOS/Appliquer une priorité DSCP à un port\|Appliquer une priorité DSCP à un port]]
[[Notes/QOS/Declaration d'une priorité sur champ DSCP\|Declaration d'une priorité sur champ DSCP]]
[[Notes/QOS/Priorité à un protocole\|Priorité à un protocole]]
[[Notes/QOS/Priorité sur une bande passante\|Priorité sur une bande passante]]
[[Notes/QOS/Verifier classe QOS\|Verifier classe QOS]]
[[Notes/QOS/Vérifier priorité DSCP\|Vérifier priorité DSCP]]