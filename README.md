# Installation

## Ubuntu 16.04
```console
$ sudo apt-get purge docker lxc-docker docker-engine docker.io
$ sudo apt-get install  curl  apt-transport-https ca-certificates software-properties-common
$ sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce
```

## Check Docker version
```console
$ sudo docker --version
```

## Test your installation
```console
$ sudo socker run hello-world
```

## Install Nvidia-docker2
https://github.com/NVIDIA/nvidia-docker/wiki/Installation-(version-2.0)

# Usage

## Info
```console
$ sudo docker info
$ sudo docker ps 
$ sudo docker ps -a 
$ sudo docker image ls 
$ sudo docker images -a
```

## Building image
```console
$ sudo docker build -t docker-obj-det-copel -f Dockerfile .
```

## Run a container
```console
$ sudo docker run -it --runtime=nvidia docker-obj-det-copel bash
```

## Getting shell from running container
```console
$ docker exec -i -t <CONTAINER_ID>  /bin/bash
```

## Run a exited container
```console
$ docker start -a -i <CONTAINER_ID>
```

## Commiting changes
```console
$ sudo docker commit <CONTAINER_ID> <TAG_IMAGE>
```

## Removing images
```console
$ sudo docker rmi <IMAGE_ID> -f
