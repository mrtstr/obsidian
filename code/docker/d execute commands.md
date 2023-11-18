## [[d execute commands]] in a [[d container]]
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

### examples
#### open a terminal in a [[d container]]:   
`docker exec -it <container id> \bin\bash` 
#### exec a command in a running [[d container]]: 
`docker exec <container id> <command>` 


# Anki

START
Basic
[[d execute commands]] in a [[d container]]
- command (3 tags)
- 2 limitations
examples for
- open a terminal in a [[d container]]
- exec a command in a running [[d container]]
Back: 
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

### examples
#### open a terminal in a [[d container]]:   
`docker exec -it <container id> \bin\bash` 
#### exec a command in a running [[d container]]: 
`docker exec <container id> <command>` 

Tags: code docker
<!--ID: 1699721434964-->
END