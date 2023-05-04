---
{"dg-publish":true,"permalink":"/notes/dns/faire-un-simple-serveur-dns/"}
---

named.conf :
include "/etc/bind/named.conf.log";

acl goodclients {
    10.0.0.0/8;
    192.168.0.0/16;
    172.16.0.0/12;
        172.25.0.0/16;
    localhost;
    localnets;
};

options {
    directory "/var/cache/bind";

    dnssec-validation no;
    dnssec-enable no;

        // recursion : le serveur est-il récursif ? Répondre aux résolveurs pour les zones dont il n'a pas autorité.
    recursion yes;
    allow-recursion { goodclients; };
    allow-query     { any; };

        // Interdit les transferts de zone par défaut (requetes AXFR)
        allow-transfer {"none";};

    listen-on-v6 { none; };

    forwarders {
        172.25.254.12;
        172.25.254.15;
    };
};
zone "M2L.com" {
        type master;
        file "/etc/bind/db.M2L.com";
};

db.M2L.com :

;
; BIND data file for m2l.com
;
$TTL    604800
@       IN      SOA     m2l.com. root.m2l.com. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
        IN      A       10.80.64.20
;
@       IN      NS      ns.m2l.com.
ns      IN      A       10.80.64.20
serv   IN      A       10.80.64.20

[[Notes/HAPROXY/Backend\|Backend]]
[[Notes/HAPROXY/FrontEND HTTP et HTTPS\|FrontEND HTTP et HTTPS]]
