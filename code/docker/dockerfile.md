## [[dockerfile]]
File containing the commands for [[d image creation|creating]] an [[d image]]  

```dockerfile
FROM python:3.12-slim  # base image

RUN apt-get update && apt-get -y install package-bar 
								# running shell commands

COPY myscript.py myscript.py  # basic copying

ARG my_build_var = XYZ  # <name>[=<default value>]
						# can be overwritten using --build-arg
						# will only available during the build

ENV my_container_var ABC  # will be available in the container

USER Bob  # <user>[:<group>]

WORKDIR ~/my_folder

ENTRYPOINT ["python"] # first part of the start command
					  # often used base process
CMD ["myscript.py"]   # second part of the start command
					  # often used for parameter
					  # often overwritten
```

# anki
START
Basic
[[dockerfile]]
- concept
- commands (9)
Back: 

File containing the commands for [[d image creation|creating]] an [[d image]]  

```dockerfile
FROM python:3.12-slim  # base image

RUN apt-get update && apt-get -y install package-bar 
								# running shell commands

COPY myscript.py myscript.py  # basic copying

ARG my_build_var = XYZ  # <name>[=<default value>]
						# can be overwritten using --build-arg
						# will only available during the build

ENV my_container_var ABC  # will be available in the container

USER Bob  # <user>[:<group>]

WORKDIR ~/my_folder

ENTRYPOINT ["python"] # first part of the start command
					  # often used base process
CMD ["myscript.py"]   # second part of the start command
					  # often used for parameter
					  # often overwritten
```
Tags: code docker
<!--ID: 1700318860093-->
END


START
Basic
[[dockerfile]]
- difference `ARG` and `ENV`
- difference `CMD` and `ENTRYPOINT`
- how to run a command during the build process
- how to set the user name
Back: 

File containing the commands for [[d image creation|creating]] an [[d image]]  

```dockerfile
FROM python:3.12-slim  # base image

RUN apt-get update && apt-get -y install package-bar 
								# running shell commands

COPY myscript.py myscript.py  # basic copying

ARG my_build_var = XYZ  # <name>[=<default value>]
						# can be overwritten using --build-arg
						# will only available during the build

ENV my_container_var ABC  # will be available in the container

USER Bob  # <user>[:<group>]

WORKDIR ~/my_folder

ENTRYPOINT ["python"] # first part of the start command
					  # often used base process
CMD ["myscript.py"]   # second part of the start command
					  # often used for parameter
					  # often overwritten
```
Tags: code docker
<!--ID: 1700318860096-->
END
