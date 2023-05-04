---
{"dg-publish":true,"permalink":"/notes/ssh/authentification-par-cles/"}
---

Depuis la machine cliente :
```
ssh-keygen -b 2048

ssh-copy-id sysadmin@172.25.192.7
```
Sur la serveur : 
```
 nano /etc/ssh/sshd_config

PasswordAuthentication no
```

[[Notes/SSH/Empêcher la connexion de l'utilisateur root en SSH\|Empêcher la connexion de l'utilisateur root en SSH]]
[[Notes/SSH/Configurer le timeout des sessions SSH\|Configurer le timeout des sessions SSH]]
[[Notes/SSH/MFA SSH Google\|MFA SSH Google]]
[[Notes/SSH/Modifier le port SSH\|Modifier le port SSH]]
