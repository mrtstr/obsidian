## [[d image]] concept
- immutable, read-only templates containing instructions for creating a [[d container]]
- [[d image]] is composed of multiple stacked layers
- has a image id and a [[d image reference]]
- contains
	- operation system
	- code
	- binarys 
	- dependencies

![[d image reference#d image reference]]

![[d layer#d layer]]

## [[d image]] commands

#### show all [[d image]]:   
`docker image ls <-a for all>`
#### remove [[d image]]:   
`docker rmi <-f for force> <image id>`
#### print details about [[d image]]
`docker inspect <image id>`

![[d image creation#d image creation]]


# anki
START
Basic
[[d image]] concept (3)
[[d image]] structure (4)
[[d image]] commands
- show images
- remove images
- create images
- show details
Back: 
## [[d image]] concept
- immutable, read-only templates containing instructions for creating a [[d container]]
- [[d image]] is composed of multiple stacked layers
- contains
	- operation system
	- code
	- binarys 
	- dependencies

## [[d image reference]]
- full name of a [[d image]]
- contains [[d image repository]]
- a namespace (often app name)
- and a tag (version)

`<docker-registry-hostname>/<repository-name>:<tag>`

## [[d layer]]
- A [[docker]] build consists of a series of ordered build instructions
- Each instruction in a [[dockerfile]] roughly translates to an [[d image]] [[d layer]]
- If a [[d layer]] of an image is unchanged, then the builder picks it up from the build cache
- If a [[d layer]] has changed since the last build, that layer, and all layers that follow, must be rebuilt.

![[layers 3.png]]
→ things that take a long time to build and are rarely changing should be on top

## [[d image]] commands

#### show all [[d image]]:   
`docker image ls <-a for all>`
#### remove [[d image]]:   
`docker rmi <-f for force> <image id>`
#### print details about [[d image]]
`docker inspect <image id>`
#### [[d image creation]]
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
<!--ID: 1699721434955-->
END
