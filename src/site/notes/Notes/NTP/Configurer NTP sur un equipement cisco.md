---
{"dg-publish":true,"permalink":"/notes/ntp/configurer-ntp-sur-un-equipement-cisco/"}
---

Pour le moment, le routeur n’est pas synchronisé via le serveur NTP, on peut consulter l’heure actuelle grâce à la commande “show clock”, on remarque que l’heure n’est pas bonne du tout…

```console
SwitchToto#show clock
*0:8:8.942 UTC Mon Mar 1 1993
```

Il faut que l'équipement soit proche de l'heure où nous sommes
```
Switch#clock set 21:40:00 Sept 25 2012
```

Passons à la configuration, très simple puisqu’il suffit d’indiquer l’adresse du serveur NTP. Voici la procédure de configuration :

```console
SwitchToto#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
SwitchToto(config)#ntp server 192.168.1.10
SwitchToto(config)#exit
```

On peut vérifier que notre switch est bien associé au serveur ntp:

```console
SwitchToto#show ntp association
```

Affichez à nouveau la date et l’heure, normalement elle doit être actualisée :

```console
Router#show clock
*11:51:11.134 UTC Fri Jan 1 2023
```

Et vos équipements sont bien synchronisé entre eux!

[[Notes/NTP/Installer un serveur NTP\|Installer un serveur NTP]]
