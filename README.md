#elasticsearch-docker-cluster

## Prerequisites
``` 
$ grep vm.max_map_count /etc/sysctl.conf

and set the line :
vm.max_map_count=262144
```
or 
```
$ sysctl -w vm.max_map_count=262144
```
## Start the containers
``` 
$ docker-compose up -d
```
