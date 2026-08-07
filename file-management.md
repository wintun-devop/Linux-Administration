### Zip file with maximum compression
```
zip -r -9 nodejs.zip nodejs/
```
### unzip
```
unzip nodejs.zip
```

### list the Dir
- total dir
```
ls -l | grep -c '^d'
```
- total file
```
ls -l | grep -c '^-'
```
- total file and dir
```
echo "Dirs: $(ls -l | grep -c '^d') Files: $(ls -l | grep -c '^-') Total: $(($(ls -l | wc -l)-1))"
```
### check your folder size
```
du -sh your_folder
```
