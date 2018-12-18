# Part 1

## Task 1

```
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
7cf864548772        nginx               "nginx -g 'daemon of…"   23 seconds ago      Up 22 seconds               80/tcp              thirsty_babbage
2b209afff313        nginx               "nginx -g 'daemon of…"   24 seconds ago      Exited (0) 14 seconds ago                       sad_ganguly
9b392cd4d679        nginx               "nginx -g 'daemon of…"   26 seconds ago      Exited (0) 17 seconds ago                       thirsty_hypatia
$
```

## Task  2

```
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
$ 
```

## Task 3

1. Start the container with following command and afterwards escape container by pressing CTRL+P and CTRL+Q.
```
$ docker run -it --name curler ubuntu:latest sh -c 'read website; sleep 3; curl http://$website;'
```


2. Update package cache and install dependency package 'curl':
```
$ docker exec curler sh -c 'apt update && apt install -y curl'
```

3. Attach yourself to container with following command ,then type helsinki.fi and press enter. Response from helsinki.fi should be shown.
```
$ docker attach curler
```

If you want to run container again, do it by executing following commands then type address and press enter.
```
$ docker start curler
$ docker attach curler
```
## Task 4

### Files
[Dockerfile](task_4/Dockerfile)
[Script](task_4/curl.sh)

### Commands
```
$ docker build -t curler .
$ docker run -it curler
```

## Task 5

### File
[Dockerfile](task_5/Dockerfile)

### Commands
```
$ docker build -t task1_5 .
$ docker run -d -p 5000:5000 task1_5
```

## Task 6

### File
[Dockerfile](task_6/Dockerfile)

### Commands
```
$ docker build -t task1_6 .
$ touch logs.txt
$ docker run -d -p 8000:8000 -v $(pwd)/logs.txt:/app/logs.txt task1_6
```

## Task 7

### Files
[Frontend Dockerfile](task_7/Dockerfile_front)
[Backend Dockerfile](task_7/Dockerfile_back)

### Commands
```
$ docker build -t task1_7_front -f Dockerfile_frontend .
$ docker build -t task1_7_back -f Dockerfile_backend .
$ docker run -d -p 5000:5000 task1_7_front
$ touch logs.txt
$ docker run -d -p 8000:8000 -v $(pwd)/logs.txt:/app/logs.txt task1_7_back
```

## Task 8

### File
[Dockerfile](task_8/Dockerfile)

### Commands
To run Docker image you can do either of following:

1. Build and run from Dockerfile:
```
$ docker build -t ohtutips .
$ docker run -d -p 8080:8080 ohtutips
```

2. Pull and run from [Docker Hub](https://cloud.docker.com/repository/docker/akiutoslahti/ohtutips):
```
$ docker run -it -p 8080:8080 akiutoslahti/ohtutips
```

Afterwards navigate browser to [http://localhost:8080](http://localhost:8080)

## Task 9

### Readme
This docker image is based on Ubuntu 18.04 docker image and contains my preferred tools for Node.js development.

Tools included:
- Git 2.17.1
- Vim 8.0.1453
- Node.js 8.14.0
- Yarn 1.12.3

### File
[Dockerfile](task_9/Dockerfile)

### Commands
To run Docker image you can do either of the following

1. Build and run from Dockerfile:
```
$ docker build -t devenv .
$ docker run -it devenv
```

2. Pull and run from [Docker Hub](https://cloud.docker.com/repository/docker/akiutoslahti/devenv)
```
$ docker run -it akiutoslahti/devenv
```
You can deattach from container with CTRL+P and CTRL+Q or shut it down with `exit` command.