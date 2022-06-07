# Lab setup

## High level design 
https://datatracker.ietf.org/doc/html/rfc1918
192.168.1.231 - Switch 
192.168.1.232 - DNS  
192.168.1.235 - 192.168.1.250 - nodes   

## Router setup
Configure DHCP to use only below 
192.168.1.2-192.168.1.230


## Cisco setup
1. Change defualt password

2. Enable ssh  ( from console ) 
3. Update device IP to be 192.168.1.231
4. Enable dhcp  
5. Create DHCP network pool 
range should be 192.168.1.235 - 192.168.1.250

6. define DNS server 192.168.1.232
 


## Windows setup
Set static ip to the machine
192.168.1.232


C:\WINDOWS\system32>route add 0.0.0.0 mask 0.0.0.0 192.168.1.1 metric 30
 OK!



## Raspberry setup

install desktop version 64 bit
named nodes as node[01-03]
using networkmanager 

```
sudo apt install net-tools 
sudo apt install openssh-server
```

### Default route 
TODO: persist
nmcli connection modify <name> +ipv4.routes <destination> ipv4.gateway <gateway>

```
route add default gw 192.168.1.1 eth0
```

### DNS option 1
```
systemctl stop systemd-resolved  
systemctl disable systemd-resolved 
change nameserver 192.168.1.232 in /etc/resolv.conf
```


### DNS option 2 - to check not working 
/etc/systemd/resolved.conf
```
[Resolve]
DNS=192.168.1.232
FallbackDNS=8.8.8.8
```

run 
```
sudo resolvectl status
```

## DNS server setup

see [here](dns/README.md)
