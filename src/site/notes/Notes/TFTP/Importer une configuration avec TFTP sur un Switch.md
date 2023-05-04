---
{"dg-publish":true,"permalink":"/notes/tftp/importer-une-configuration-avec-tftp-sur-un-switch/"}
---

Pour importer la configuration :
copy tftp running-config 
Address or name of remote host "IP du serveur" 
Source filename  "Nom du fichier dans notre serveur"-confg 
Destination filename running-config? Taper entrer

Puis redémarrer :
reload
Save : Yes

[[Notes/TFTP/Configurer un serveur TFTP\|Configurer un serveur TFTP]]
[[Notes/TFTP/Sauvegarder la configuration d'un Switch avec TFTP\|Sauvegarder la configuration d'un Switch avec TFTP]]
[[Notes/TFTP/Mettre à jour un Switch avec TFTP\|Mettre à jour un Switch avec TFTP]]