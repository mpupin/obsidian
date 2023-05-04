---
{"dg-publish":true,"permalink":"/notes/tftp/mettre-a-jour-un-switch-avec-tftp/"}
---

Télécharger le fichier IOS de la nouvelle version IOS qu'on le souhaite et l'ajouter sur notre serveur grâce à MobaXterm.
Ajouter le fichier dans sysadmin ou l'emplacement ou nous avons les droits
Puis faire un mv "nom du fichier" vers le dossier souhaité

Switch# enable
Switch # archive download-sw /overwrite tftp://"Adresse IP du serveur TFTP"/"Nom du fichier IOS qui est dans notre serveur"
puis vérifier avec "show boot"

[[Notes/TFTP/Configurer un serveur TFTP\|Configurer un serveur TFTP]]
[[Notes/TFTP/Importer une configuration avec TFTP sur un Switch\|Importer une configuration avec TFTP sur un Switch]]
[[Notes/TFTP/Sauvegarder la configuration d'un Switch avec TFTP\|Sauvegarder la configuration d'un Switch avec TFTP]]