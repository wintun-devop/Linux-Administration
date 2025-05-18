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
### Copy file between host using scp
```
sudo scp -i your_key_pairs.pem your_path -r ec2-user@your_destination_host_ip:/home/ec2-user
```
### Disk Management
```

```

### Dir Management
- Check Permission for /opt
```
ls -ld /opt
```
```
id
```
- Change Permission for /opt
```
sudo chown <your_username>:<your_username> /opt
```
