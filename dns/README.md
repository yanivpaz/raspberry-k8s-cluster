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




## Install bind
```
sudo apt install -y bind9 bind9utils bind9-doc dnsutils
```


## check status 
```
resolvectl status 
```

source:
https://computingforgeeks.com/configure-master-bind-dns-server-on-ubuntu/
