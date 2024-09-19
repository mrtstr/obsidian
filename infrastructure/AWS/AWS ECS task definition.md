## task definition
- template for creating an [[AWS ECS task]] (concept on instance level)
- has a family: name for multiple versions of the task definition
- has a `launch_type` (type of ressource provider used) that can be [[AWS EC2]] or [[AWS FARGATE]]
- multiple [[d container]] (based on the [[d image]]) are running in it


### properties
- resources required: CPU, memory units (on task level)
- has a execution [[AWS iam role]]: running the [[AWS ECS]] actions like pulling the [[d image]]
- has a task [[AWS iam role]]: running the application (e.g. needs [[AWS S3 bucket]] access)
- has a container definition
- has a networking mode that defines the networking properties of the tasks and containers 

#### container definition
- blueprint of the (potentially multiple) [[d container]] inside the [[AWS ECS task]]
- [[d image]] to use
- resources required: CPU, memory units (on container level)
- [[li environment variables]]
- start command and entrypoint
- **port mapping**: allow containers to access [[port]] on the host instance to send or receive traffic (port and protocol needs to be specitied)

#### network
- generally the container and its host [[AWS EC2]] instance are different network entities
- depending on the network mode the  `containerPort` and `hostPort` might need to be mapped to allow outside communication of the container
- [[AWS ECS task]] can operate in one of 4 network modes
1) `awsvpc`: the has its own [[AWS elastic network interface (ENI)]] and thus the same networking properites as a [[AWS EC2]] instance
2) `bridge`: the [[AWS ECS task]] uses [[docker]] built-in virtual network on [[linux]]
3) `host`: the [[AWS ECS task]] uses the [[AWS EC2]] instances [[AWS elastic network interface (ENI)]] by mapping all [[port]] (only one container and task per [[AWS EC2]])
4) `none`: no network connectivity


# ---------------------

![[AWS ECS task#ECS task]]

# anki

START
Basic
container definition inside a [[AWS ECS task definition]]
- what is a port mapping, and why is it needed?
- how are containers and tasks connected to the [[network]]?


Back: 
## task definition
- template for creating an [[AWS ECS task]] (concept on instance level)
- has a family: name for multiple versions of the task definition
- has a `launch_type` (type of ressource provider used) that can be [[AWS EC2]] or [[AWS FARGATE]]
- multiple [[d container]] (based on the [[d image]]) are running in it


### properties
- resources required: CPU, memory units (on task level)
- has a execution [[AWS iam role]]: running the [[AWS ECS]] actions like pulling the [[d image]]
- has a task [[AWS iam role]]: running the application (e.g. needs [[AWS S3 bucket]] access)
- has a container definition
- has a networking mode that defines the networking properties of the tasks and containers 

#### container definition
- blueprint of the (potentially multiple) [[d container]] inside the [[AWS ECS task]]
- [[d image]] to use
- resources required: CPU, memory units (on container level)
- [[li environment variables]]
- start command and entrypoint
- **port mapping**: allow containers to access [[port]] on the host instance to send or receive traffic (port and protocol needs to be specitied)

#### network
- generally the container and its host [[AWS EC2]] instance are different network entities
- depending on the network mode the  `containerPort` and `hostPort` might need to be mapped to allow outside communication of the container
- [[AWS ECS task]] can operate in one of 4 network modes
1) `awsvpc`: the has its own [[AWS elastic network interface (ENI)]] and thus the same networking properites as a [[AWS EC2]] instance
2) `bridge`: the [[AWS ECS task]] uses [[docker]] built-in virtual network on [[linux]]
3) `host`: the [[AWS ECS task]] uses the [[AWS EC2]] instances [[AWS elastic network interface (ENI)]] by mapping all [[port]] (only one container and task per [[AWS EC2]])
4) `none`: no network connectivity


_________________

### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]



Tags: infra
<!--ID: 1726750986430-->
END


START
Basic
[[AWS ECS task definition]] and container definition
- concept and eqivalent in the [[kubernetes]] world
- difference task vs container
- where does it get the ressources from?
- relationship to [[AWS ECS service]]
- properties task (3)
- properties container (5)

Back: 
## task definition
- template for creating an [[AWS ECS task]] (concept on instance level)
- has a family: name for multiple versions of the task definition
- has a `launch_type` (type of ressource provider used) that can be [[AWS EC2]] or [[AWS FARGATE]]
- multiple [[d container]] (based on the [[d image]]) are running in it


### properties
- resources required: CPU, memory units (on task level)
- has a execution [[AWS iam role]]: running the [[AWS ECS]] actions like pulling the [[d image]]
- has a task [[AWS iam role]]: running the application (e.g. needs [[AWS S3 bucket]] access)
- has a container definition
- has a networking mode that defines the networking properties of the tasks and containers 

#### container definition
- blueprint of the (potentially multiple) [[d container]] inside the [[AWS ECS task]]
- [[d image]] to use
- resources required: CPU, memory units (on container level)
- [[li environment variables]]
- start command and entrypoint
- **port mapping**: allow containers to access [[port]] on the host instance to send or receive traffic (port and protocol needs to be specitied)

#### network
- generally the container and its host [[AWS EC2]] instance are different network entities
- depending on the network mode the  `containerPort` and `hostPort` might need to be mapped to allow outside communication of the container
- [[AWS ECS task]] can operate in one of 4 network modes
1) `awsvpc`: the has its own [[AWS elastic network interface (ENI)]] and thus the same networking properites as a [[AWS EC2]] instance
2) `bridge`: the [[AWS ECS task]] uses [[docker]] built-in virtual network on [[linux]]
3) `host`: the [[AWS ECS task]] uses the [[AWS EC2]] instances [[AWS elastic network interface (ENI)]] by mapping all [[port]] (only one container and task per [[AWS EC2]])
4) `none`: no network connectivity


_________________

### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]



Tags: infra
<!--ID: 1726516929903-->
END