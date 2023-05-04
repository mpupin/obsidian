---
{"dg-publish":true,"permalink":"/notes/tftp/configurer-un-serveur-tftp/"}
---

apt-get install xinetd tftpd tftp

Nous allons configurer notre serveur TFTP. Pour cela créer le fichier suivant :
nano /etc/xinetd.d/tftp

Copier/Coller cette configuration à l'interieur :
service tftp 
{ 
protocol                 = udp 
port                        = 69 
socket_type            = dgram 
wait                        = yes 
user                        = nobody 
server                     = /usr/sbin/in.tftpd 
server_args             = /tftpboot
disable                    = no 
}

Créons ensuite le répertoire **/tftpboot** à la racine : 
sudo mkdir /tftpboot

Appliquer ces droits :
sudo chmod -R 777 /tftpboot 
sudo chown -R nobody /tftpboot

Relancer le service xinetd :
sudo /etc/init.d/xinetd restart

touch "Nom du switch"-confg (dans le répertoire /tftpboot/)

Appliquer ces droits à votre fichier :
chmod 777 "Nom du fichier"-confg

[[Notes/TFTP/Sauvegarder la configuration d'un Switch avec TFTP\|Sauvegarder la configuration d'un Switch avec TFTP]]
[[Notes/TFTP/Importer une configuration avec TFTP sur un Switch\|Importer une configuration avec TFTP sur un Switch]]
[[Notes/TFTP/Mettre à jour un Switch avec TFTP\|Mettre à jour un Switch avec TFTP]]


