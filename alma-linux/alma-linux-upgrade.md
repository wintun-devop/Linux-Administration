### Alma Linux Upgrade (From 9.6 to 10)
- https://wiki.almalinux.org/elevate/ELevate-quickstart-guide.html#upgrade-steps
```
sudo dnf update -y
```
```
sudo dnf clean all
```
```
sudo reboot
```
### Install ELevate Repositories and Tools
```
sudo yum install -y http://repo.almalinux.org/elevate/elevate-release-latest-el$(rpm --eval %rhel).noarch.rpm
```
```
sudo yum install -y leapp-upgrade leapp-data-almalinux
```
### Run Pre-upgrade Checks
```
sudo leapp preupgrade
```
### Perform the Upgrade
```
sudo leapp upgrade
```
```
sudo reboot
```

### Check Version
```
cat /etc/os-release
```

### Check Installed Kernels
```
rpm -q kernel
```
### Check Current Running Kernel
```
uname -r
```
