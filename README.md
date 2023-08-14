# Docker Tutorial


### To check the docker version
>docker -v 

### pull image
>docker pull [imageName] <br>
>docker pull openjdk <br>

### pull specific images version from hub
>docker pull [imageName]:[tags] <br>
>docker pull openjdk:18 <br>

### get a list of docker images
>docker images <br>

### search specific docker images
>docker search [imageName] <br>
>docker search MySQL <br>

### running docker images
>docker run [imageName] or docker run [imageId] <br>
>docker run MySQL <br>

### check docker container
>docker ps <br>
>docker ps -a <br>

### passing enviorment variables
>docker run --env <br>

### passing name
>docker run --name [name] [imageName] <br>
>docker run --name mysqlContainer MySQL <br>

### run container in detach mode 
```(Detached mode, started by the option --detach or –d flag in docker run command, means that a Docker container runs in the background of your terminal. It does not receive input or display output. Using detached mode also allows you to close the opened terminal session without stopping the container.) or (It will keep running in background [background me chalta rahega])```

>docker run -d [imageName] <br>
>docker run -d MySQL <br>

### run docker in interactive mode
>docker run -it [imageName]
>docker run -it -d openjdk <br>
>docker run --name opjkdk -it -d openjdk <br>

### run docker in exec mode 
>docker exec -it(for running in interactive mode) [imageName/imageId] command(present in docker ps) <br>
>docker exec -it cb62d6647c50 jshell <br>

### inspect docker image
>docker inspect [imageName/imageId] <br>
>docker inspect openjdk <br>

### to stop a docker container
>docker stop [containerName/containerId] <br>
>docker stop 69fa946a4964 <br>
>docker stop 6ad88f35af1e 69fa946a4964 (for multiple files) <br>

### running a sevice on a port in docker
>docker run --name [name] -d -p [portOnHost]:[portInConatiner] [serviceName] <br>
>docker run --name apacheServer -d -p 8080:80 httpd <br>

### remove docker container
>docker rm [containerId] <br>
>docker rm 6ad88f35af1e <br>
>docker stop 6ad88f35af1e 69fa946a4964 (for multiple files) <br>

### remove docker images
>docker rmi [imageName] <br>
>docker rmi 9c7a54a9a43c <br>
>docker rmi 9c7a54a9a43c 71260f256d19 (for multiple files) <br>

### remove unused image 
>docker remove prune <br>

### restart container
>docker restart [containerName/containerId] <br>
>docker restart opjk <br>

### docker logs
>docker logs [containerName/containerId] <br>

### creating docker image
>create a fileName "DockerFile" without quote <br>

>FROM ubuntu [replace this with baseImage Name] <br>
>WOKRDIR /usr/src [replace this with working directory] <br>
>LABEL user="Sushant" [replace this with userName]   <br>
>RUN apt update <br>
>CMD ["echo", "HI VIKING"] <br>


### command to build docker image 
>docker build -t [imageName] .(here '.' means same whole directory) <br>
>docker build -t myubuntu . <br>


### pushing dockerImage on docker hub 
```
1. Create a repository 'springboot_test'
2. docker build -t sushant0999/springboot_test:sbp -f C:\Users\sushant.raj\dockerProject\docker-compose\javaTestCompose\Dockerfile .
3. docker push sushant0999/springboot_test:sbp
```

## ERROR & SOLUTION
### 1. Error : <br>
`failed to solve: failed to read dockerfile: open /var/lib/docker/tmp/buildkit-mount2573332828/Dockerfile: no such file or directory)`

### Solution:
Provide full path
docker build -t image-name -f [C:\Users\sushant.raj\dockerProject\java\DockerFile] .
