### ufw installation
```
sudo apt install ufw -y
```
```
sudo ufw allow 22/tcp
```
```
sudo ufw allow 80/tcp
```
```
sudo ufw allow 443/tcp
```
```
sudo ufw allow 9505
```
```
sudo ufw enable
```

### check status
```
sudo iptables -L -n -v
```
```
sudo nft list ruleset
```
```
sudo ss -tlnp | egrep ':(22|80|443)\s'
```
```
sudo ufw status verbose
```
