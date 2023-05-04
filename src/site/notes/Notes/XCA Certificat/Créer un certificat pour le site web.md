---
{"dg-publish":true,"permalink":"/notes/xca-certificat/creer-un-certificat-pour-le-site-web/"}
---

# Créer une demande de certificat pour le site web

Dans XCA, créer une requête :

Requêtes de signature de certificat > Nouvelle requête

Choisir le modèle pour un serveur HTTPS et appliquer le modèle :

![20200122-141305.png](/img/user/Notes/XCA%20Certificat/Images/20200122-141305.png)

Dans l'onglet « Sujet », remplir les informations relatives à l'identité et générer une nouvelle clé : 

![20200122-141437.png](/img/user/Notes/XCA%20Certificat/Images/20200122-141437.png)

Le « commonName » doit correspondre au nom du domaine FQDN du site web.

Dans l'onglet « Extensions », renseigner le nom du domaine FQDN du site web ainsi que les adresses IP utilisées pour y accéder :
![20200122-143345.png](/img/user/Notes/XCA%20Certificat/Images/20200122-143345.png)

[[Notes/XCA Certificat/Créer une autorité de certification\|Créer une autorité de certification]]
[[Notes/XCA Certificat/Signer un certificat avec une CA\|Signer un certificat avec une CA]]
[[Notes/XCA Certificat/Exporter un certificat\|Exporter un certificat]]