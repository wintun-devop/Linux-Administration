### ssh tunnel
- ssh tunnel with key
```
sudo chmod 600 newkey.pem
```
```
ssh -i newkey.pem -D 1080 -C -N username@host_address
```
- ssh tunnel with username and password
```
ssh -D 1080 -C -N user@remote_host
```
- check
```
sudo netstat -tunlp
```

- export before use
```
export ALL_PROXY=socks5h://127.0.0.1:1080
```
```
export HTTPS_PROXY=socks5h://127.0.0.1:1080
```
```
export HTTP_PROXY=socks5h://127.0.0.1:1080
```

- Persistance Process
```
sudo vi /etc/systemd/system/ssh-tunnel.service
```
- run with correct key and host address
```
[Unit]
Description=Persistent SSH SOCKS Tunnel
After=network.target

[Service]
ExecStart=/usr/bin/ssh -i /home/sysadmin/ssh-tunnel/newkey.pem -D 1080 -C -N username@host_address
Restart=always
User=sysadmin

[Install]
WantedBy=multi-user.target
```
```
sudo systemctl enable ssh-tunnel
```
```
sudo systemctl start ssh-tunnel
```
