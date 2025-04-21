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