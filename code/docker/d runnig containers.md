## running [[d container]]
### start an existing [[d container]]
`docker start <container id>`

### create a [[d container]]
- `docker create <container id>`

### stop a [[d container]]
`docker stop <container id>`


### create and start and [[d container]] form a [[d image]]: 
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
example: 
- loading official light python 3.12 image and starting a interactivate terminal in it
`docker run --rm -it python:3.12-slim /bin/bash`

- start an existing image and starting a interactivate terminal in it
`docker run --rm -it b55fcc843b91 /bin/bash`

- running official light python 3.12 image in the background and set it sleep for 2 minuts
`docker run -d python:3.12-slim /bin/bash -c "sleep 180"`


# anki

START
Basic
create and start and [[d container]] form a [[d image]]
- command with 7 tags
- example: loading official light python 3.12 image and starting a interactivate terminal in it
- start an existing image and starting a interactivate terminal in it
- running official light python 3.12 image in the background and set it sleep for 2 minuts
Back: 
### create and start and [[d container]] form a [[d image]]: 
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
example: 
- loading official light python 3.12 image and starting a interactivate terminal in it
`docker run --rm -it python:3.12-slim /bin/bash`

- start an existing image and starting a interactivate terminal in it
`docker run --rm -it b55fcc843b91 /bin/bash`

- running official light python 3.12 image and set it sleep for 2 minuts
`docker run -d python:3.12-slim /bin/bash -c "sleep 180"`
Tags: code docker
<!--ID: 1699721434966-->
END


START
Basic
[[docker]] 4 commands for starting, stopping and creating [[d container]] (without tags)
Back: 
- start an existing [[d container]]: `docker start <container id>`
- create a [[d container]]:  `docker create <container id>`
- stop a [[d container]]:  `docker stop <container id>`
- create and start and [[d container]] form a [[d image]]: `docker run <image id>`
Tags: code docker
<!--ID: 1699721434960-->
END


