---
{"dg-publish":true,"permalink":"/notes/ssh/configurer-le-timeout-des-sessions-ssh/"}
---

```
nano /etc/ssh/sshd_config

ClientAliveInterval 600
ClientAliveCountMax 0
```


-   **ClientAliveInterval** - ceci indique le délai d'attente en secondes. Après x secondes, le serveur SSH enverra un message au client demandant une réponse.

-   **ClientAliveCountMax** - ceci indique le nombre total de messages de vérification envoyés par le serveur SSH sans obtenir de réponse du client SSH.

[[Notes/SSH/Authentification par clés\|Authentification par clés]]
[[Notes/SSH/Empêcher la connexion de l'utilisateur root en SSH\|Empêcher la connexion de l'utilisateur root en SSH]]
[[Notes/SSH/MFA SSH Google\|MFA SSH Google]]
[[Notes/SSH/Modifier le port SSH\|Modifier le port SSH]]
