---
{"dg-publish":true,"permalink":"/notes/xca-certificat/exporter-un-certificat/"}
---

Exporter **la clé privée et le certificat** dans le même fichier :
$ openssl pkcs12 -in certmat.pfx -out keymat.pem -nodes

[[Notes/XCA Certificat/Créer un certificat pour le site web\|Créer un certificat pour le site web]]
[[Notes/XCA Certificat/Signer un certificat avec une CA\|Signer un certificat avec une CA]]
[[Notes/XCA Certificat/Créer une autorité de certification\|Créer une autorité de certification]]