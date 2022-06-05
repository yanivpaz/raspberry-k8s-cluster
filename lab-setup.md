# Lab setup

## Cisco setup
1. Change defualt password

2. Enable ssh  ( from console ) 
3. Enable dhcp  
3.1 ssh switch and run   
```
configure terminal
interface vlan1
ip add 192.168.1.250 255.255.255.0
```
3.2 from switch UI enable DHCP   

## Raspberrys setup

Ubuntu 22.04
Run wizard Ubuntu - named nodes as node01
```
sudo apt install net-tools
sudo apt install openssh-server
```
