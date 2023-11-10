# Docker

## Running a container
```bash
# pull and run an nginx server
docker run --publish 80:80 --name webserver nginx

docker run --rm -d -p 3000:3000/tcp [containername]:[tag]

# list rinning containers
docker ps

# stop the container
docker stop webserver

# remove the container
docker rm webserver
```

## Attach Shell - Docker CLI

```bash
# attach shell
docker run -it nginx -- /bin/bash

# attach powershell
docker run -it -- microsoft/powershell:nanoserver

# attach to a running container
docker container exec -it [containername] bash

# To copy a file from the local file system to a container
docker cp <src-path> <container>:<dest-path> 
```

## Cleaing up - Docker CLI

```bash
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

## Building - Docker CLI

```bash
# build image using Dockerfile located in the same folder
docker build -t [name:tag] .

# build image using Dockerfile located in a different folder
docker build -t [name:tag] -f [filename]

# tag an existing image
docker tag [imageName] [name:tag]
```

## Persist Data

The data should be stored outside the container in a Volume. A Volume is mapped to a logical folder.

```bash
# creates a new volume
docker create volume [volumeName]

# lists the volumes
docker volume ls

# display the volume info
docker  volume inspect [volumeName]

# deletes a volume
docker  volume rm [volumeName]

# deletes all volumes not mounted
docker volume prune

# run a container with a volume (logical folder already created)
docker run -d --name devtest -v myvol:/app nginx:latest

# inspect the container
docker inspect devtest
```
