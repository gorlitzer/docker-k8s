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
