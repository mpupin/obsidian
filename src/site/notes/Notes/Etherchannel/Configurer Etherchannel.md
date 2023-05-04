---
{"dg-publish":true,"permalink":"/notes/etherchannel/configurer-etherchannel/"}
---

### Configuration de Spanning-Tree

Sur SW0 :

```
SW0(config)#spanning-tree vlan 10 root primary
SW0(config)#spanning-tree vlan 20 root secondary
```

Sur SW1 :

```
SW1(config)#spanning-tree vlan 20 root primary
SW1(config)#spanning-tree vlan 10 root secondary
```

### Configuration Etherchannel

Sur SW0 et sur SW1 :
```
(config)#interface range G0/0-1
(config-if-range)#shutdown
(config-if-range)#switchport trunk encapsulation dot1q
(config-if-range)#switchport mode trunk
(config-if-range)#channel-group 1 mode auto
(config-if-range)#no shutdown
(config-if-range)#exit
(config)#interface Po1
(config-if)#switchport trunk encapsulation dot1q
(config-if)#switchport mode trunk
(config-if)#exit
```

[[__VLAN\|__VLAN]]
[[__CONFIGURATION INTERFACE\|__CONFIGURATION INTERFACE]]
