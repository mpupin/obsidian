---
{"dg-publish":true,"permalink":"/notes/cisco/reintialiser-le-mot-de-passe-d-un-routeur/"}
---

1.  Éteindre et rallumer le routeur
2.  Pendant le démarrage appuyer sur **Ctrl + Pause** (sous Windows, pour les autres OS voir le document Standard Break) ou pour arriver au prompt « > »
3.  Entrer la commande: **confreg 0×2142**
4.  Entrer la commande: **reset**
5.  Au re-démarrage, le routeur va ignorer les fichiers de configuration: Répondez **no** aux 2 questions qu’il va poser.
6.  Entrer en mode privilégié par la commande: **enable**
7.  En mode configuration, supprimer le mot de passe enable avec la configuration suivante :
    -   **no enable password**
    -   **no enable secret**
8.  Entrez la commande suivante : **confreg 0x2102**
9.  Enregistrer la configuration: **copy run start**

[[Notes/CISCO/Reintialiser les mots de passe d'un Switch Cisco\|Reintialiser les mots de passe d'un Switch Cisco]]
[[Notes/CISCO/Sécurisation des ports d'un switch\|Sécurisation des ports d'un switch]]
[[Notes/SSH/Configurer SSH sur équipement CISCO\|Configurer SSH sur équipement CISCO]]
[[Notes/TFTP/Importer une configuration avec TFTP sur un Switch\|Importer une configuration avec TFTP sur un Switch]]