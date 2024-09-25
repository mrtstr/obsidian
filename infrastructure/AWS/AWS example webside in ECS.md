## example webside in ECS
- components needed to host a website in [[AWS ECS]] and expose it to a local [[AWS VPC (virtual private cloud)]]

- [[AWS ECS cluster]]
	- [[AWS FARGATE]] or [[AWS ECS on EC2]] (then also [[AWS Auto Scaling Group]] and [[AWS launch template]] etc)
- [[AWS Application Load Balancer (ALB)]] to connect the [[AWS ECS task]] to the network
	- [[AWS Security Group]] to open the ports `443` and `80`
	- [[AWS target group]] to [[AWS ECS task|tasks]] of the [[AWS ECS service]]
	- [[AWS listner]] to foward [[hypertext transfer protocol (HTTP)]] requests
- [[AWS ECS service]]
	- [[AWS ECS task definition]]
	- [[AWS Security Group]] to open connection the [[AWS ECS task]] (their [[AWS target group]])
	- [[AWS autoscaling policy]]
	- [[AWS identity and access management IAM]] for [[AWS ECS task]] and execution



START
Basic
components needed to host a website in [[AWS ECS]] and expose it to a local [[AWS VPC (virtual private cloud)]] (1 + 4 + 5)
Back: 

- [[AWS ECS cluster]]
	- [[AWS FARGATE]] or [[AWS ECS on EC2]] (then also [[AWS Auto Scaling Group]] and [[AWS launch template]] etc)
- [[AWS Application Load Balancer (ALB)]] to connect the [[AWS ECS task]] to the network
	- [[AWS Security Group]] to open the ports `443` and `80`
	- [[AWS target group]] to [[AWS ECS task|tasks]] of the [[AWS ECS service]]
	- [[AWS listner]] to foward [[hypertext transfer protocol (HTTP)]] requests
- [[AWS ECS service]]
	- [[AWS ECS task definition]]
	- [[AWS Security Group]] to open connection the [[AWS ECS task]] (their [[AWS target group]])
	- [[AWS autoscaling policy]]
	- [[AWS identity and access management IAM]] for [[AWS ECS task]] and execution

______________________

###  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- for long-running application in an [[ESC cluster]] ([[AWS FARGATE]] or [[AWS EC2]])
- starts and controlled multiple [[AWS ECS task]]

#### properties
- has a [[AWS ECS task definition]]
- has a `launch_type`: [[AWS FARGATE]] or [[AWS EC2]] (type of capasity provider)

#### task connection
- needs a connection to the containers of its [[AWS ECS task|tasks]] on the container [[port]]
- thus the [[AWS ECS task|tasks]] needs a [[AWS target group]] (if a [[AWS Application Load Balancer (ALB)]] is set up its [[AWS target group]] can be reused)
- has a internal load balancer that is connected to the [[AWS target group]] of its [[AWS ECS task|tasks]] 
- a [[AWS Security Group]] that opend the `container port` is needed


### ESC cluster
- logical grouping of [[AWS ECS task]] /[[AWS ECS service]] and container instances ([[AWS EC2]])


### Application Load Balancer
- distributes traffic among multiple servers
- works in the [[application layer]] (e.g [[hypertext transfer protocol (HTTP)]] traffic)
- conducts healthchecks
- redirect diffent webservers depending on the request


#### listener
- a listner is needed to filter and forward incomming requests based on [[protocol]] and [[port]]
- a default response can be setup when no reachable

#### listener rule
- can have a listener rule based on the prefix of the path of the incomming [[uniform resource identifier (URI)]]

#### target group
- linkes the [[AWS Application Load Balancer (ALB)]] to a group of servers (in [[AWS Auto Scaling Group]] or [[AWS ECS service]] a ALB id can be referenced)
- can include a health checker

### task definition
- template for creating an [[AWS ECS task]] (concept on instance level)
- has a family: name for multiple versions of the task definition
- has a `launch_type` (type of ressource provider used) that can be [[AWS EC2]] or [[AWS FARGATE]]
- multiple [[d container]] (based on the [[d image]]) are running in it


#### properties
- resources required: CPU, memory units (on task level)
- has a execution [[AWS identity and access management IAM]]: running the [[AWS ECS]] actions like pulling the [[d image]]
- has a task [[AWS identity and access management IAM]]: running the application (e.g. needs [[AWS S3 bucket]] access)
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

Tags: infra
<!--ID: 1726754495845-->
END