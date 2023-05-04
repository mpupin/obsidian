---
{"dg-publish":true,"permalink":"/notes/haproxy/backend/"}
---

backend backend1
    mode http
    option httpchk
    option forwardfor except 127.0.0.1
    http-request add-header X-Forwarded-Proto https if { ssl_fc }
    cookie SERVERUSED insert indirect nocache
    balance roundrobin
    server web-server1 10.80.64.10:80 maxconn 32 cookie web-server1
    server web-server2 10.80.64.30:80 maxconn 32 cookie web-server2

!! COOKIE sert à ce que le client connecté sur le serveur reste sur le même serveur, même apres un refresh de la page !!
[[Notes/HAPROXY/FrontEND HTTP et HTTPS\|FrontEND HTTP et HTTPS]]
[[Notes/XCA Certificat/Exporter un certificat\|Exporter un certificat]]
[[Notes/XCA Certificat/Signer un certificat avec une CA\|Signer un certificat avec une CA]]
[[Notes/XCA Certificat/Créer un certificat pour le site web\|Créer un certificat pour le site web]]
[[Notes/XCA Certificat/Créer une autorité de certification\|Créer une autorité de certification]]
