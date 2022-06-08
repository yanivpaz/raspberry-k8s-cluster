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


```
route add 0.0.0.0 mask 0.0.0.0 192.168.1.1 
```



## Raspberry setup

install desktop version 64 bit
named nodes as node[01-03] # hostnamectl set-hostname 
using networkmanager 


Networkmanager update systemed-resolved using dbus 
( no need to update /etc/systemd/resolved.conf which is global configuration - see https://youtu.be/DtFjrJdnWAU?t=1399 ) 
see also : https://unix.stackexchange.com/questions/612416/why-does-etc-resolv-conf-point-at-127-0-0-53

### packages 
```
sudo apt install net-tools 
sudo apt install openssh-server
```

### Default route 

```
sudo nmcli connection modify "Wired connection 1" ipv4.adress 0.0.0.0/0
sudo nmcli connection modify "Wired connection 1" ipv4.gateway 192.168.1.1
sudo nmcli connection modify "Wired connection 1" ipv4.dns 192.168.1.232
```


## DNS server setup
see [here](dns/README.md)










### Not needed 

```
route add default gw 192.168.1.1 eth0
systemctl stop systemd-resolved  
systemctl disable systemd-resolved 
change nameserver 192.168.1.232 in /etc/resolv.conf


-- DNS option 2 - to check not working 
/etc/systemd/resolved.conf

[Resolve]
DNS=192.168.1.232
FallbackDNS=8.8.8.8
run 
sudo resolvectl status # its acutally systemed-resolved ?
```


