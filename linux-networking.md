### Visual Command Linke Network Editor
```
nmtui
```
### list available devices and their status on Linux
```
nmcli device status
```
```
nmcli connection show
```
### ip command
```
ip addr
```
###
```
lshw -class network
```
### Interfaces and their packets
```
netstat -i
```
### Check Listing Ports
```
sudo netstat -tunlp
```
```
netstat -plant | grep 3000
```
### check services
```
sudo systemctl list-units --type=service | grep postgres
```

### firewalld configuration (Redhat,Cent,Alma,Fedora)
- http service add
```
sudo firewall-cmd --add-service=http --permanent
```
- https service add
```
sudo firewall-cmd --add-service=https --permanent
```
- tcp port service add
```
sudo firewall-cmd --add-port=5432/tcp --permanent
```
```
sudo firewall-cmd --reload
```
### selinux management (redhat,alma,rocky,cent)
- se-linux status check
```
sudo sestatus
```
- se-linux network connection for nginx reverse proxy
```
sudo setsebool -P httpd_can_network_connect 1
```
- Temporary Disable SE-Linux if necessary
```
sudo setenforce 0
```

