[[docker commands]] to create a [[docker image]]

example:
```
docker build 

-f <path to Dockerfile to use> \   

-t <TAG often DOCKER_IMAGE_REPO:IMAGE_VERSION> \

--build-arg <extra arguments> 

<PATH where to run from>
```


START
Basic
create a [[docker image]] from a [[dockerfile]] (example)
Back: 
```
docker build 

-f <path to Dockerfile to use> \   

-t <TAG often DOCKER_IMAGE_REPO:$IMAGE_VERSION> \

--build-arg <extra arguments> 

<PATH where to run from>
```
Tags: code docker
<!--ID: 1666875324163-->
END