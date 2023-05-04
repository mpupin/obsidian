---
{"dg-publish":true,"permalink":"/notes/haproxy/front-end-http-et-https/"}
---

frontend http-in
    bind 10.80.64.20:80
    mode http
    option httplog
    acl pupin1 hdr(host) serv.m2l.com
    acl pupin2 hdr(host) 172.25.100.10
    redirect scheme https code 301 if !{ ssl_fc } pupin1 
    use_backend backend1 if pupin1 or pupin2



frontend lehttps
    bind 10.80.64.20:443 ssl crt /etc/haproxy/cert/ no-sslv3
    mode http
    option httplog
    acl pupin1 hdr(host) serv.m2l.com
    use_backend backend1 if pupin1

[[Notes/HAPROXY/Backend\|Backend]]
[[Notes/XCA Certificat/Exporter un certificat\|Exporter un certificat]]
[[Notes/XCA Certificat/Signer un certificat avec une CA\|Signer un certificat avec une CA]]
[[Notes/XCA Certificat/Créer un certificat pour le site web\|Créer un certificat pour le site web]]
[[Notes/XCA Certificat/Créer une autorité de certification\|Créer une autorité de certification]]
