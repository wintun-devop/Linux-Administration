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
