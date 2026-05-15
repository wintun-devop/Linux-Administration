### Static Network Address on Ubuntu
-- ubuntu24lts
```
ls /etc/netplan/
```
- backup
```
sudo cp /etc/netplan/50-cloud-init.yaml /etc/netplan/50-cloud-init.yaml.bak
```
- edit for static
```
sudo vi /etc/netplan/50-cloud-init.yaml
```
```
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
      dhcp4: false
      addresses: [192.168.1.71/24]
      routes:
        - to: default
          via: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8,8.8.4.4]
```
```
sudo netplan apply
```
