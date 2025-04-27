### Change the hostname
```
sudo hostnamectl set-hostname <new-hostname>
```

### Permission for  current directory
```
ls -ld $(pwd)
```
```
sudo chown -R $(whoami) $(pwd)
```
### Check Specific Port Running
```
netstat -tulpn | grep :8443
```
### Kill Speciic Port If necessary
```
sudo fuser -k 8443/tcp
```