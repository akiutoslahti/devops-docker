# Part 3

## Task 1

### Files
[Dockerfile Backend](task_1/Dockerfile_back)  
[Dockerfile Frontend](task_1/Dockerfile_front)

### Sizes
```
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
frontend_after      latest              1ab0b517c3e8        19 seconds ago      339MB
frontend_before     latest              8e7bc4cae2fd        5 minutes ago       458MB
backend_after       latest              8f2917c0f358        8 minutes ago       264MB
backend_before      latest              adc0811d3e20        30 minutes ago      384MB
```

## Task 2

### File
[Dockerfile](task_2/Dockerfile)

### Commands
```
$ docker build -t yle-dl .
$ docker run -v $(pwd):/videos yle-dl https://areena.yle.fi/1-2101788
```

## Task 3

### Files
[Dockerfile Backend](task_3/Dockerfile_back)  
[Dockerfile Frontend](task_3/Dockerfile_front)

### Commands
```
$ docker build -t task_3_3_back -f Dockerfile_back .
$ docker build -t task_3_3_front -f Dockerfile_front .
$ docker run -it -e FRONT_URL=http://localhost:5000 -p 8000:8000 task_3_3_back
$ docker run -it -e API_URL=http://localhost:8000 -p 5000:5000 task_3_3_front
```

## Task 4

### Files
[Dockerfile Backend](task_4/Dockerfile_back_alpine)  
[Dockerfile Frontend](task_4/Dockerfile_front_alpine)

### Commands
```
$ docker build -t task_3_4_back -f Dockerfile_back_alpine .
$ docker build -t task_3_4_front -f Dockerfile_front_alpine .
$ docker run -it -e FRONT_URL=http://localhost:5000 -p 8000:8000 task_3_4_back
$ docker run -it -e API_URL=http://localhost:8000 -p 5000:5000 task_3_4_front
```

### Sizes
```
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED              SIZE
task_3_4_front      latest              81befcf0c3db        About a minute ago   199MB
task_3_4_back       latest              beab9db0955e        3 minutes ago        124MB
task_3_3_front      latest              4e3105d66b1a        36 minutes ago       339MB
task_3_3_back       latest              0210f973f52f        36 minutes ago       265MB

```

## Task 5

### File
[Dockerfile](task_5/Dockerfile)

### Commands
```
$ docker build -t yle-dl_alpine .
$ docker run -v $(pwd):/videos yle-dl_alpine https://areena.yle.fi/1-2101788
```

### Sizes
```
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
yle-dl_alpine       latest              23665ae16e55        56 seconds ago      162MB
yle-dl              latest              5844f6ce5c2d        11 minutes ago      720MB

```

## Task 6

[Report 3.6b](task_6/task_6.md)
