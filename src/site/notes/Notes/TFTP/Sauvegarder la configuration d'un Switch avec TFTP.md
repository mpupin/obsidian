---
{"dg-publish":true,"permalink":"/notes/tftp/sauvegarder-la-configuration-d-un-switch-avec-tftp/"}
---

Pour commencer sur le switch :
copy running-config tftp

Quand Address or name of remote host apparait ecrire l'IP de notre serveur.
Dans destination file vérifier que ce soit bien le nom qu'on a entrer dans notre serveur
Puis valider

On peut maintenant aller voir la config sur notre serveur avec :
cat /tftpboot/"Nom du switch"-confg

[[Notes/TFTP/Configurer un serveur TFTP\|Configurer un serveur TFTP]]
[[Notes/TFTP/Importer une configuration avec TFTP sur un Switch\|Importer une configuration avec TFTP sur un Switch]]
[[Notes/TFTP/Mettre à jour un Switch avec TFTP\|Mettre à jour un Switch avec TFTP]]