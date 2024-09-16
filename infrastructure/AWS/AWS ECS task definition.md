### task definition
- template for creating an [[AWS ECS task]]
- resources required: CPU, memory units (on task level)
- has a execution [[AWS iam role]]: running the [[AWS ECS]] actions like pulling the [[d image]]
- has a task [[AWS iam role]]: running the application (e.g. needs [[AWS S3 bucket]] access)
- has a family: name for multiple versions of the task definition
- has a `launch_type`: `EC2` | `FARGATE`
- can have multiple container definitions

#### container definition
- [[d image]] to use
- resources required: CPU, memory units (on container level)
- **port mapping**: allow containers to access [[port]] on the host instance to send or receive traffic (port and protocol needs to be specitied)


# ---------------------

![[AWS ECS task#ECS task]]

# anki

START
Basic
[[AWS ECS task definition]]
- concept and eqivalent in the [[kubernetes]] world
- properties (4)
- how is it connected and what is neede?
- where does it get the ressources from?
- relationship to [[AWS ECS service]] and container

Back: 
### task definition
- template for creating an [[AWS ECS task]]
- resources required: CPU, memory units (on task level)
- has a execution [[AWS iam role]]: running the [[AWS ECS]] actions like pulling the [[d image]]
- has a task [[AWS iam role]]: running the application (e.g. needs [[AWS S3 bucket]] access)
- has a family: name for multiple versions of the task definition
- has a `launch_type`: `EC2` | `FARGATE`
- can have multiple container definitions

#### container definition
- [[d image]] to use
- resources required: CPU, memory units (on container level)
- **port mapping**: allow containers to access [[port]] on the host instance to send or receive traffic (port and protocol needs to be specitied)


_________________

### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]


###  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- is running in a [[ESC cluster]]
- has a [[AWS ECS task definition]] and manages multiple [[AWS ECS task]]
- has a `launch_type`: [[AWS FARGATE]] or manuelly (type of capasity provider)
- is connected to its [[AWS ECS task|tasks]] (traffic over a [[AWS Security Group]] on [[port]] `0`) and has a internal [[AWS Elastic Load Balancer (ELB)]] (port mapping needed in the `container definition`  of the [[AWS ECS task definition]])


Tags: infra
<!--ID: 1726516929903-->
END