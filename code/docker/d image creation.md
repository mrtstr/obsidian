## [[d image creation]]
a [[d image]] can be created from a [[dockerfile]] using the command `docker build`

`docker build -t tires/myapp:v1.2.3 -f folder/mydockerfile --build-arg env_var=foo .`

```
docker build 
	-t <image repository>/<namespace>:<version> 
	-f <docker file path> 
	--build-arg <env variable during build process>
	<docker context where to build from normally .>
```

![[dockerfile#dockerfile]]

# anki

START
Basic
create a [[d image]] from a [[dockerfile]] (example)
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

START
Basic
[[d image creation]] froma [[dockerfile]]
- command 3 tags
- example
Back: 
a [[d image]] can be created from a [[dockerfile]] using the command `docker build`

`docker build -t tires/myapp:v1.2.3 -f folder/mydockerfile --build-arg env_var=foo .`

```
docker build 
	-t <image repository>/<namespace>:<version> 
	-f <docker file path> 
	--build-arg <env variable during build process>
	<docker context where to build from normally .>
```
Tags: code docker
<!--ID: 1700318860087-->
END

