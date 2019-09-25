# GRUPO-6-SCRIPT-ROUTER

enable
configure terminal
hostname RT-06
banner motd "ACESSO APENAS PARA O GRUPO 6"
enable secret senha6
security passwords min-length 8
login block-for 180 attempts 3 within 60
username erick privilege 15 secret senha6
username ruth privilege 15 secret senha6
username guilherme privilege 15 secret senha6
username cleiton priviliege 15 secret senha6
username vinicius privilege 15 secret senha6
line console 0
login local
exec-timeout 10
line vty 0 15
transport input ssh
login local
exec-timeout 10
exit
service password-encryption
interface gigabitethernet 0/1
no shutdown
description CONEXAO COM SWITCH 6
exit
interface gigabitethernet 0/1.10
encapsulation dot1q 10
ip address 192.168.6.129 255.255.255.192
description SUBINTERFACE VLAN 10
exit
interface gigabitethernet 0/1.20
encapsulation dot1q 20
ip address 192.168.6.1 255.255.255.128
description SUBINTERFACE VLAN 20 
exit
interface gigabitethernet 0/1.30
encapsulation dot1q 30
ip address 192.168.7.1 255.255.255.240
description SUBINTERFACE VLAN 30 
do wr
