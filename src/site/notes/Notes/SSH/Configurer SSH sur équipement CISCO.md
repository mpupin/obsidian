---
{"dg-publish":true,"permalink":"/notes/ssh/configurer-ssh-sur-equipement-cisco/"}
---

hostname routeurmat
ip domain-name btssiosecurity.com
username matheo privilege 15 secret topsecret
line vty 0 4
 login local 
transport input ssh
crypto key zeroize rsa
crypto key generate rsa
ip ssh version 2
