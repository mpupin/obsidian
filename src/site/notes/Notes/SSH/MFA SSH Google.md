---
{"dg-publish":true,"permalink":"/notes/ssh/mfa-ssh-google/"}
---

```
apt-get install libpam-google-authenticator

google-authenticator
```

Scanner le QR CODE avec Google Authenticator
Répondre "y" à toutes les questions

```
nano /etc/pam.d/sshd

auth required pam_google_authenticator.so
```

```
nano /etc/ssh/sshd_config

ChallengeResponseAuthentication yes

AuthenticationMethods publickey,keyboard-interactive

PubkeyAuthentication yes

PasswordAuthentication no

systemctl restart sshd
```

[[Notes/SSH/Modifier le port SSH\|Modifier le port SSH]]
[[Notes/SSH/Authentification par clés\|Authentification par clés]]
[[Notes/SSH/Empêcher la connexion de l'utilisateur root en SSH\|Empêcher la connexion de l'utilisateur root en SSH]]
[[Notes/SSH/Configurer le timeout des sessions SSH\|Configurer le timeout des sessions SSH]]
