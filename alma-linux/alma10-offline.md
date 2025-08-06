### Enable Persistent Caching
```
ls /etc/dnf/
```
- add keepcache=True on dnf.conf
```
sudo vi /etc/dnf/dnf.conf
```
```
keepcache=True
```

### dnf-plugins-core installation
```
sudo dnf install dnf-plugins-core -y
```

### Update Packages(1)
```
mkdir alma10-offline-updates
```
```
cd alma10-offline-updates
```
```
sudo dnf update --downloadonly --downloaddir=/home/sysadmin/alma10-offline-updates
```
```
sudo dnf upgrade --downloadonly --downloaddir=/home/sysadmin/alma10-offline-updates
```
- install update offline
```
cd alma10-offline-updates
```
```
sudo dnf install *.rpm --disablerepo=* --nogpgcheck
```

### Basic necessary packages(2)
```
mkdir alma10-necessary-packages
```
```
cd alma10-necessary-packages
```
```
dnf download --resolve gcc net-tools curl wget unzip make git openssl glibc-devel openssl-devel
```
- install Basic necessary packages(2) offline
```
cd alma10-necessary-packages
```
```
sudo dnf install *.rpm --disablerepo=* --nogpgcheck  --skip-broken
```

### dotnet8-nginx(3)
```
mkdir dotnet-nginx
```
```
cd dotnet-nginx
```
```
dnf download --resolve dotnet-sdk-8.0 nginx
```
- install dotnet8-nginx(3) offline
```
cd dotnet-nginx
```
```
sudo dnf install *.rpm --disablerepo=* --nogpgcheck
```

### postgresql17(4)
```
sudo dnf install -y wget
```
```
mkdir postgresql-17-server-installer
```
```
cd postgresql-17-server-installer
```
```
wget https://download.postgresql.org/pub/repos/yum/reporpms/EL-9-x86_64/pgdg-redhat-repo-latest.noarch.rpm
```
```
sudo dnf install -y ./pgdg-redhat-repo-latest.noarch.rpm
```
```
sudo dnf -qy module disable postgresql
```
```
dnf download --resolve postgresql17-server
```
- install postgresql17(4) on offline machine (customer side)
```
sudo dnf install *.rpm --disablerepo=* --nogpgcheck
```
# Optionally initialize the database and enable automatic start:
```
sudo /usr/pgsql-17/bin/postgresql-17-setup initdb
```
```
sudo systemctl enable postgresql-17
```
```
sudo systemctl start postgresql-17
```

- transfer usb stick
``` 
cp -r /home/win/offline-updates /run/media/$USER/YourUSB/
```
```
cd /run/media/$USER/YourUSB/offline-updates
```

```
sudo dnf install *.rpm --disablerepo=* --nogpgcheck
```

### Offline(nginx-postgresql-enable)
```
sudo systemctl enable nginx
```
```
sudo systemctl start nginx
```
```
sudo /usr/pgsql-17/bin/postgresql-17-setup initdb
```
```
sudo systemctl enable postgresql-17
```
```
sudo systemctl start postgresql-17
```
### status check
```
sudo systemctl status nginx
```
```
sudo systemctl status postgresql-17
```
```
sudo netstat -tunlp
```
