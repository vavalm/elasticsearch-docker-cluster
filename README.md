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

### References
[How elastic search works](https://hub.packtpub.com/how-does-elasticsearch-work-tutorial/)
[Elastic search official benchmarks](https://elasticsearch-benchmarks.elastic.co/)
[Rally](https://github.com/elastic/rally)