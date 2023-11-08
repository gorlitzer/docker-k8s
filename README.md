# Docker

## Running a container
```
# pull and run an nginx server
docker run --publish 80:80 --name webserver nginx

# list rinning containers
docker ps

# stop the container
docker stop webserver

# remove the container
docker rm webserver
```

## Attach Shell - Docker CLI

```
# attach shell
docker run -it nginx -- /bin/bash

# attach powershell
docker run -it -- microsoft/powershell:nanoserver

# attach to a running container
docker container exec -it [containername] -- bash 
```

## Cleaing up - Docker CLI

```
# removes stopped container
docker rm [containername]

# removes all stopped containers
docker rm $(docker ps -a -q)

# list images
docker images

# deletes the image
docker rmi [imagename]

# removes all images not in use by any container
docker system prune -a 
```
