---
{"dg-publish":true,"permalink":"/notes/routage/configurer-un-routage-on-a-stick/"}
---

### Configuration "trunk" côté commutateur
Switch>
Switch>en
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#int G0/1
Switch(config-if)#switchport mode trunk 

### Configuration "trunk" côté routeur

Router>en
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#int G0/1
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

Router(config-if)#exit
Router(config)#int G0/1.10
Router(config-subif)#encapsulation dot1Q 10
Router(config-subif)#ip address 192.168.10.254 255.255.255.0
Router(config-subif)#exit
Router(config)#interface G0/1.20
Router(config-subif)#encapsulation dot1Q 20
Router(config-subif)#ip address 192.168.20.254 255.255.255.0

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

### Configuration des ports "access" du switch

Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#int F0/1
Switch(config-if)#switchport mode access 
Switch(config-if)#switchport access vlan 10
Switch(config-if)#exit
Switch(config)#int F0/2
Switch(config-if)#switchport mode access 
Switch(config-if)#switchport access vlan 20
Switch(config-if)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

