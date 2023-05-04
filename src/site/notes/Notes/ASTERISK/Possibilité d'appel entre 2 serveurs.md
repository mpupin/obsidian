---
{"dg-publish":true,"permalink":"/notes/asterisk/possibilite-d-appel-entre-2-serveurs/"}
---

Ajouter dans extensions.conf :
```
[finance]
exten => _1XXX,1,Dial(IAX2/thomas/${EXTEN}) # si le numéro commence par 1 alors rediriger vers le contexte thomas dans iax.conf

[liaison-thomas]
;routage des appels sortants vers le site distant
exten => _2XXX,1,Goto(finance,${EXTEN},1) #permettre que les appels entrent dans le contexte finance du serveur distant

```

Ajouter dans iax.conf
```
[general]
register => matheo:1234@172.25.117.1 #ce sont les logins qui vont nous permettre de nous connecter au serveur distant

[thomas]
type = friend ;voir explication dans l’activité 1.
host = dynamic ;ip fixe (static) ou dynamique pour le serveur distant.
trunk = yes
secret = 1234
context = liaison-thomas ;contexte associé à la gestion des appels distants.
qualify = yes
```
[[Notes/ASTERISK/Ajouter un utilisateur\|Ajouter un utilisateur]]
[[Notes/ASTERISK/Configuration de base extensions.conf\|Configuration de base extensions.conf]]
[[Notes/ASTERISK/Configuration de base voicemail.conf\|Configuration de base voicemail.conf]]
[[Notes/ASTERISK/Configuration de base users.conf\|Configuration de base users.conf]]
[[Notes/ASTERISK/Configurer Téléphone IP DE410\|Configurer Téléphone IP DE410]]
[[Notes/ASTERISK/Créer un template\|Créer un template]]
