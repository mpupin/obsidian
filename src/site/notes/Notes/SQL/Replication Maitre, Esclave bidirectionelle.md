---
{"dg-publish":true,"permalink":"/notes/sql/replication-maitre-esclave-bidirectionelle/"}
---

### Configuration du Maitre
GRANT REPLICATION SLAVE ON `*.*` TO 'testrep'@'10.80.64.30' IDENTIFIED BY 'Iroise29';
FLUSH PRIVILEGES;
 USE wp27022023_mathwp;
 FLUSH TABLES WITH READ LOCK;
 SHOW MASTER STATUS;

mysql -u root -p
 USE wp27022023_mathwp; 
 UNLOCK TABLES;
Modifiez le fichier de configuration /etc/mysql/mariadb.conf.d/50-server.cnf


Modifiez ça
bind-address		= 0.0.0.0
server-id		= 1
log-bin                 = /var/log/mysql/mysql-bin.log
binlog_do_db        =wp27022023_mathwp

service mysql restart

mariadb -u root -p
SHOW MASTER STATUS;
Notez le file et la position

Modifiez par ceux notez sur le serveur 2
CHANGE MASTER TO MASTER_HOST='10.80.64.30', MASTER_USER='testrep', MASTER_PASSWORD='Iroise29', MASTER_LOG_FILE='mysql-bin.000003', MASTER_LOG_POS= 342;

### Configuration Esclave
Modifiez le fichier de configuration /etc/mysql/mariadb.conf.d/50-server.cnf
Modifiez ça
bind-address		= 0.0.0.0
server-id		= 2
log-bin                 = /var/log/mysql/mysql-bin.log
binlog_do_db        =wp27022023_mathwp

service mysql restart

mariadb -u root -p

mariadb -u root -p
GRANT REPLICATION SLAVE ON `*.*` TO 'testrep'@'10.80.64.10' IDENTIFIED BY 'Iroise29';
SHOW MASTER STATUS;

Modifiez LOG_FILE et LOG_POS par ceux qu'on a notez

CHANGE MASTER TO MASTER_HOST='10.80.64.10', MASTER_USER='testrep', MASTER_PASSWORD='Iroise29', MASTER_LOG_FILE='mysql-bin.000003', MASTER_LOG_POS= 342;

start slave;

!!!! POUR MODIFIER FAIRE !!!!
STOP SLAVE;

Pour verifier 
SHOW SLAVE STATUS;
**Seconds_behind_master** : Celle-ci doit être à 0. Si elle indique Null, dans ce cas, la réplication ne fonctionne pas.
Vérifiez alors l’information **Last_IO_Error**.

[[Notes/SQL/Replication Maitre, Esclave\|Replication Maitre, Esclave]]

