## Handy Dockerfiles for testing and experimenting

**Dependecies: boot2docker**

First install boot2docker on your Mac then run the following commands ONCE.
```
boot2docker up
eval "$(boot2docker shellinit)"
echo $DOCKER_HOST   # verify environment vars were set
docker build -t elasticsearch ./dockerfiles/
```


Running your image
```
docker run -it -p 9200:9200 -p 9300:9300 elasticsearch bash
docker ps
docker kill CONTAINER-ID
```
