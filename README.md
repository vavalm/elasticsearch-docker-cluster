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
### Start 4 slaves
To launch the 4 slaves containers you can do:
``` 
$ docker-compose up -d
```
Then wait a minute to let the cluster being intialized and run:
``` 
$ docker-compose up rally
```
To watch the test

### Start less than 4 slaves
To launch the 4 slaves containers you can do:
``` 
$ docker-compose up -f docker-compose-<nb_of_slaves>slaves.yml -d
```
To choose the right file corresponding to the number of slaves you want (with -f option)

As previously, wait a minute to let the cluster being intialized and run:
``` 
$ docker-compose up rally
```
To watch the test

## Results
The results are stored in the file [rally/benchmarks/results/display_result.html](rally/benchmarks/results/display_result.html)
You can also open the jupyter notebook (.ipynb) to see all the output results

## Results interpretation

On the [elasticsearch website](https://esrally.readthedocs.io/en/stable/metrics.html), the output metrics of rally are explained.
The main metrics for us are:
* latency: Time period between submission of a request and receiving the complete response. It also includes wait time, i.e. the time the request spends waiting until it is ready to be serviced by Elasticsearch.
* service_time: Time period between start of request processing and receiving the complete response. This metric can easily be mixed up with latency but does not include waiting time. This is what most load testing tools refer to as “latency” (although it is incorrect).
* throughput: Number of operations that Elasticsearch can perform within a certain time period, usually per second. See the track reference for a definition of what is meant by one “operation” for each operation type.

### References
[How elastic search works](https://hub.packtpub.com/how-does-elasticsearch-work-tutorial/)
[Elastic search official benchmarks](https://elasticsearch-benchmarks.elastic.co/)
[Rally](https://github.com/elastic/rally)