# Docker Tutorial


### To check the docker version
>docker -v 

### pull image
>docker pull [imageName]
>docker pull openjdk

### pull specific images from hub
>docker pull [imageName]:[tags]
>docker pull openjdk:18

### get a list of docker images
>docker images

### search specific docker images
>docker search [imageName]
>docker search MySQL

### running docker images
>docker run [imageName] or docker run [imageId]
>docker run MySQL 

### check docker container
>docker ps
>docker ps -a

### #passing enviorment variables
>docker run --env

### passing name
>docker run --name [name] [imageName]
>docker run --name mysqlContainer MySQL 

### run container in detach mode 
```(Detached mode, started by the option --detach or –d flag in docker run command, means that a Docker container runs in the background of your terminal. It does not receive input or display output. Using detached mode also allows you to close the opened terminal session without stopping the container.) or (It will keep running in background [background me chalta rahega])```

>docker run -d [imageName]
>docker run -d MySQL

### run docker in interactive mode
>docker run -it [imageName]
>docker run -it -d openjdk
>docker run --name opjkdk -it -d openjdk

### run docker in exec mode 
>docker exec -it(for running in interactive mode) [imageName/imageId] command(present in docker ps)
>docker exec -it cb62d6647c50 jshell

### inspect docker image
>docker inspect [imageName/imageId]
>docker inspect openjdk

### to stop a docker container
>docker stop [containerName/containerId]
>docker stop 69fa946a4964 
>docker stop 6ad88f35af1e 69fa946a4964 (for multiple files)

### running a sevice on a port in docker
>docker run --name [name] -d -p [portOnHost]:[portInConatiner] [serviceName]
>docker run --name apacheServer -d -p 8080:80 httpd

### remove docker container
>docker rm [containerId]
>docker rm 6ad88f35af1e 
>docker stop 6ad88f35af1e 69fa946a4964 (for multiple files)

### remove docker images
>docker rmi [imageName]
>docker rmi 9c7a54a9a43c
>docker rmi 9c7a54a9a43c 71260f256d19 (for multiple files)

### remove unused image 
>docker remove prune

### restart container
>docker restart [containerName/containerId]
>docker restart opjk

### docker logs
>docker logs [containerName/containerId]

### creating docker image
>create a fileName "DockerFile" without quote

>FROM ubuntu [replace this with baseImage Name] <br>
>WOKRDIR /usr/src [replace this with working directory] <br>
>LABEL user="Sushant" [replace this with userName]   <br>
>RUN apt update <br>
>CMD ["echo", "HI VIKING"] <br>


### command to build docker image 
>docker build -t [imageName] .(here '.' means same whole directory)
>docker build -t myubuntu .

<h2>ERROR & SOLUTION</h2>
### ERROR :
```
failed to solve: failed to read dockerfile: open /var/lib/docker/tmp/buildkit-mount2573332828/Dockerfile: no such file or directory)
```

### Solution:
Provide full path
docker build -t image-name -f [C:\Users\sushant.raj\dockerProject\java\DockerFile] .
