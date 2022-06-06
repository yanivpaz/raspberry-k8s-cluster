## DNS setup 



## Install packages 
```
sudo apt install net-tools # ifconfig 
sudo apt install openssh-server #  enable ssh 
sudo apt install network-manager  #  nmcli
sudo hostnamectl set-hostname dns 
```

```
git clone https://github.com/yanivpaz/raspberry-k8s-cluster.git
sudo cp  ~/raspberry-k8s-cluster/dns/netplan.yaml /etc/netplan/50-cloud-init.yaml
```

## Open firewall 
```
sudo ufw allow 53/tcp
sudo ufw allow 53/udp
```

## Install bind
```
sudo apt install -y bind9 bind9utils bind9-doc dnsutils
```

source:
https://computingforgeeks.com/configure-master-bind-dns-server-on-ubuntu/


## check status 
```
resolvectl status 
```

## Troubleshooting
sshd server can not start 
```
sshd: no hostkeys available -- exiting
```
solution : run ssh-keygen -A
