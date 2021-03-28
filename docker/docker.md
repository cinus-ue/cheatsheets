# GENERAL USAGE

## list all local images
```
$ docker images
```

## list containers
```
$ docker ps
$ docker ps -a
$ docker ps --filter label=<LABEL>
```

## run a container
```
$ docker run -d <IMAGE-ID>
$ docker run -d <IMAGE-NAME>:<TAG>
$ docker run -it <IMAGE-ID>
$ docker run -it <IMAGE-NAME>:<TAG> <CMD>
$ docker run --rm <IMAGE-ID> bash
```

## enter a running container
```
$ docker exec -it <CONTAINER-ID>
```

## inspect containers metadata
```
$ docker inspect <IMAGE-NAME>
$ docker inspect <IMAGE-ID>
```

## push the image to the registry
```
$ docker push <DOCKER-HUB>/<IMAGE-NAME>
```

## rename container
```
$ docker rename <CURRENT-NAME> <NEW_NAME>
```

## remove image
```
$ docker rmi <IMAGE-ID>
$ docker rmi $(docker images -q)
```

## remove container
```
$ docker rm <CONTAINER-ID>
$ docker rm -f <CONTAINER-ID> (stop and delete the container:)
$ docker rm $(docker ps --filter status=exited -q)
$ docker rm -v $(docker ps -a -q)
$ sudo ls /var/lib/docker/volumes/xxxxx
```

# VOLUMES

## list volumes
```
$ docker volume ls
```

## create a local volume
```
$ docker volume create --name <VOLUME-NAME>
```

## mounting a volume on container start
```
$ docker run -v <VOLUME-NAME>:/data <CONTAINER-NAME>
```

## destroy a volume
```
$ docker volume rm <VOLUME-NAME>
```

## remove all volumes
```
$ docker volume rm $(docker volume list -q)
```

## copying data from container to host
```
$ docker cp <CONTAINER-NAME>:/<DIR>/<FILE-NAME> .
```

## copying data from host to container
```
$ docker cp <FILE-NAME> <CONTAINER-NAME>:/<DIR>/<FILE-NAME>
```

# NETWORKING

## expose container ports to the host
```
$ docker run -p <HOST-PORT>:<CONTAINER-PORT> <IMAGE-ID>
$ docker run -dp <HOST-PORT>:<CONTAINER-PORT> <IMAGE>:<TAG>
```

## expose/publish all exposed ports to random ports on the host
```
$ docker run -d -P <>
```

## show exposed ports of a container
```
$ docker port <NAME>
```

## create a new docker network
```
$ docker network create <NET-NAME>
```

## delete network
```
$ docker network rm <NET-NAME>
```

## IPv6
```
$ vim /etc/sysconfig/docker
  OPTIONS='--selinux-enabled --ipv6'
$ docker -d --ipv6
```

## SECURITY

## be aware of CPU shares and memory
```
$ docker run -d -c 512 <IMAGE-NAME>
$ docker run -m 512m <IMAGE-NAME>
```

## set container filesystem to read-only
```
$ docker run --read-only <IMAGE-NAME>
```

## set volumes to read-only
```
$ docker run -v $(pwd)/secrets:/secrets:ro <IMAGE-NAME>
```

## turn off inter-container communication
```
$ docker -d --icc=false --iptables
```

## DOCKERFILE
```
FROM <IMG_NAME>:<TAG_NAME>  

ARG <PORT_ENV_VAR>
ENV NODE_ENV ${<NODE-ENV>}  

RUN <BASH_CMD> \
    && <BASH-CMD>

COPY <FILE_NAME> /destination/path/in/container
VOLUME /source/path/on/host:/destination/path/in/container  

EXPOSE ${<PORT_ENV_VAR>} 

USER <USER_NAME>   
WORKDIR <DIR_NAME>
CMD <BASH_CMD>    
```     