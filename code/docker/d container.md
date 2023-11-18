## [[d container]] concept
- instance of an [[d image]]
- will run as long their entry [[li process]] (`PID 1`) is running
- running on the [[d engine]]

## [[d container]] commands
###  show all [[d container]]
`docker ps -a` 

### remove [[d container]]
`docker rm -f <container id>`

### print details about [[d container]]
`docker inspect <container id>`

![[d runnig containers#running d container]]

![[d execute commands#d execute commands in a d container]]

# Anki

START
Basic
[[docker]] conmands for 
- show all [[d image]]
- show all [[d container]] 
- show all running [[d container]] 
Back: 
- show all [[d image]]:   `docker image ls`
- show all [[d container]] (running and sopped):   `docker ps -a` 
- show all [[d container]] (running):   `docker ps` 
Tags: code docker
<!--ID: 1699721434949-->
END


START
Basic
[[d container]]
- concept
[[docker]] conmands for 
- show all [[d container]]
- remove [[d container]]
- print details about [[d container]]
- running [[d container]] (4)
- [[d execute commands]] in a [[d container]]
Back: 
## [[d container]] concept
- instance of an [[d image]]
- will run as long their entry [[li process]] (`PID 1`) is running
- running on the [[d engine]]

## [[d container]] commands
###  show all [[d container]]
`docker ps -a` 

### remove [[d container]]
`docker rm -f <container id>`

### print details about [[d container]]
`docker inspect <container id>`

## running [[d container]]
#### start an existing [[d container]]
`docker start <container id>`

#### create a [[d container]]
- `docker create <container id>`

#### stop a [[d container]]
`docker stop <container id>`


#### create and start and [[d container]] form a [[d image]]: 
```
docker run 
	--rm         # Automatically remove the container when it exits
	--entrypoint # Overwrite the default ENTRYPOINT of the image
	-i           # Keep STDIN open even if not attached
	-t           # Allocate a pseudo-TTY
	-d           # run container in the background
	-e           # set environment variables e.g. x=yy
	<image id or tag>`
	<comand to overwrite cmd>
```

### [[d execute commands]] in a [[d container]]
- [[li process]] will only run while the primery [[li process]] (`PID 1`) is running
- COMMAND runs in the default directory of the container.
- A chained or a quoted command does not work. 

```
docker excec
	-i           # Keep STDIN open even if not attached
	-t           # Allocate a pseudo-TTY
	-d           # run container in the background
	<command>
```


Tags: code docker
<!--ID: 1700318860103-->
END