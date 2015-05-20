## Handy Dockerfiles for testing and experimenting

**Dependecies: boot2docker**

### Create your image
First install boot2docker on your Mac then run the following commands ONCE.
```
boot2docker up
eval "$(boot2docker shellinit)"
echo $DOCKER_HOST   # verify environment vars were set
docker build -t elasticsearch ./dockerfiles/
```


### Running/starting an instance
```
docker run -it -p 9200:9200 -p 9300:9300 elasticsearch bash
service elasticsearch start
```

### Stopping your instance
Type **exit** into window with shell connected to the running Docker instance
or terminate it from another window...
```
docker ps
docker kill CONTAINER-ID
```

### ElasticSearch access
Access your ES through the usual means on ports 9200 and 9300 under the IP returned by `boot2docker ip`

- To access ES' head plugin, run the following in the terminal and cut-n-paste the output URL into your browser:
```
echo "http://`boot2docker ip`:9200/_plugin/head" 
```


