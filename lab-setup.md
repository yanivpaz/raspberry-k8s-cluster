# Lab setup

## High level design 
https://datatracker.ietf.org/doc/html/rfc1918
10.0.0.1 - 10.0.0.100
10.0.0.100 - 10.0.0.250

## Windows setup
set static ip to the machine
10.0.0.2

## Cisco setup
1. Change defualt password

2. Enable ssh  ( from console ) 
3. Enable dhcp  
3.1 ssh switch and run   
```
configure terminal
interface vlan1
ip add 10.0.0.1 255.255.255.0
```
3.2 from switch UI enable DHCP  

4. Create DHCP network pool 
range should be 10.0.0.100 - 10.0.0.250 

## Raspberry setup

install desktop version 64 bit
named nodes as node[01-03]

```
sudo apt install net-tools 
sudo apt install openssh-server
```


## DNS setup

install server version 32 bit

```
sudo apt install net-tools # ifconfig 
sudo apt install openssh-server #  enable ssh 
sudo apt install network-manager  #  nmcli
sudo hostnamectl set-hostname dns 
```
