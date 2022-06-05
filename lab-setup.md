# Lab setup

## High level design 
https://datatracker.ietf.org/doc/html/rfc1918
192.168.1.231 - Switch 
192.168.1.232 - DNS  
192.168.1.235 - 192.168.1.250 - nodes   

## Router setup
Configure DHCP to use only below 
192.168.1.2-192.168.1.230

## Windows setup
Set static ip to the machine
192.168.1.232


C:\WINDOWS\system32>route add 0.0.0.0 mask 0.0.0.0 192.168.1.1 metric 30
 OK!


## Cisco setup
1. Change defualt password

2. Enable ssh  ( from console ) 
3. Update device IP to be 192.168.1.231
4. Enable dhcp  


4. Create DHCP network pool 
range should be 192.168.1.235 - 192.168.1.250

## Raspberry setup

install desktop version 64 bit
named nodes as node[01-03]

```
sudo apt install net-tools 
sudo apt install openssh-server
```


## DNS setup

install server version 32 bit
sudo netplan apply dns/netplan.yaml
```
sudo ip route add default via 192.168.1.1 
```

```
sudo apt install net-tools # ifconfig 
sudo apt install openssh-server #  enable ssh 
sudo apt install network-manager  #  nmcli
sudo hostnamectl set-hostname dns 
```
