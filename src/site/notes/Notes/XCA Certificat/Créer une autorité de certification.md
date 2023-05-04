---
{"dg-publish":true,"permalink":"/notes/xca-certificat/creer-une-autorite-de-certification/"}
---

# Création de la paire de clé


On commence par créer une nouvelle paire de clés : **Clés privés > Nouvelle clé**

![start_image_1.png](/img/user/Notes/XCA%20Certificat/Images/start_image_1.png)

Puisque c’est la clé de l’AC, la taille de la clé sera plus importante afin d’augmenter sa sécurité.

Une fois créée, la clé est disponible dans l’onglet clés privées.

# Création du certificat

Une fois la paire de clés créée, c'est au tour du certificat. **Certificats > Nouveau Certificat**

**Dans l’onglet Source**, la sécurité sera également accrue en modifiant le type de l’empreinte.

Dans la liste déroulante « Modèle pour le nouveau certificat » choisir `[default] CA` pour que les paramètres du certificat soit modifier en conséquence.

Cliquer sur le bouton « Appliquer tout ».
![20200122-121446.png](/img/user/Notes/XCA%20Certificat/Images/20200122-121446.png)

Remplir les informations concernant l'identité :
 ![20200122-131354.png](/img/user/Notes/XCA%20Certificat/Images/20200122-131354.png)
[[Notes/XCA Certificat/Créer un certificat pour le site web\|Créer un certificat pour le site web]]
[[Notes/XCA Certificat/Exporter un certificat\|Exporter un certificat]]
[[Notes/XCA Certificat/Signer un certificat avec une CA\|Signer un certificat avec une CA]]
