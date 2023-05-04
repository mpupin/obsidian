---
{"dg-publish":true,"permalink":"/notes/rsyslog/configurer-un-serveur-rsyslog/"}
---

Pour activer rsyslog, il faut tout simplement décommenter les lignes 16,17,20,21, du fichier de configuration dans 
/etc/rsyslog.conf de manière à ce que ça ressemble à cela:
```shell
provides UDP syslog reception
module(load="imudp")
input(type="imudp" port="514")``
provides TCP syslog reception
module(load="imtcp")
input(type="imtcp" port="514")
```

Rsyslog est alors activé et prêt à recevoir des logs.

On peut stocker des logs extérieur au client (ceux d'un routeur par exemple) dans un dossier précis (exemple avec un routeur
qui s'appelle RouteurToto). Il suffit de rentrer la ligne (toujours dans le fichier /etc/rsyslog.conf): 
```
$template DynamicFile,"/var/log/RouterToto/forwarded-logs.log"
*.* -?DynamicFile
```


⚠ On pensera à remplacer "RouteurToto" par le nom désiré.
⚠Il faut mettre cette ligne AVANT la section "Rules" du fichier de configuration.

 [[Notes/RSYSLOG/Configurer rsyslog sur un switch cisco\|Configurer rsyslog sur un switch cisco]]