[How to Deploy an AWS ECS Cluster with Terraform [Tutorial] (spacelift.io)](https://spacelift.io/blog/terraform-ecs)
[How to run ECS Fargate Terraform — AWS Cloud by nexgeneerz](https://nexgeneerz.io/how-to-setup-amazon-ecs-fargate-terraform/)
https://engineering.finleap.com/posts/2020-02-20-ecs-fargate-terraform/

## AWS ECS
- [[AWS]] service fpr running [[d image]] 
- ressource provider can be [[AWS FARGATE]] or manuelly managed [[AWS EC2]]  instances from an [[AWS Auto Scaling Group]] ([[AWS ECS on EC2]])
- [[AWS ECS cluster]]: grouping of [[AWS ECS task]], [[AWS ECS service]] and [[AWS EC2]] container instances
- [[AWS ECS task]] and [[AWS ECS service]] (which care managing tasks) are running in an [[ESC cluster]]


![[ecs-task-definition-terraform.jpg]]

# ---------------------



![[AWS ECS cluster#ESC cluster]]

![[AWS ECS task#ECS task]]

![[AWS ECS task definition#task definition]]

![[AWS ECS service#ECS service]]




# anki

START
Basic
how are the following concepts connected
- [[AWS ECS cluster]]
- [[AWS ECS service]]
- [[AWS ECS task]]
- container

Back: 
[[AWS ECS cluster]]
- logical group of [[AWS ECS task]] and [[AWS ECS service]] and ressoucres ([[AWS EC2]] instances)

[[AWS ECS service]]
- manages multiple [[AWS ECS task]] and is running in an [[AWS ECS cluster]]

[[AWS ECS task]]
- running in a host [[AWS EC2]] instance and has multiple [[d container]] running in it
- can be created directly or be managed by a [[AWS ECS service]]

[[d container]]
- is attatched to a [[AWS ECS task]]
- created based on a [[d image]]

_________________
## AWS ECS
- [[AWS]] service fpr running [[d image]] 
- ressource provider can be [[AWS FARGATE]] or manuelly managed [[AWS EC2]]  instances from an [[AWS Auto Scaling Group]] ([[AWS ECS on EC2]])
- [[AWS ECS cluster]]: grouping of [[AWS ECS task]], [[AWS ECS service]] and [[AWS EC2]] container instances
- [[AWS ECS task]] and [[AWS ECS service]] (which care managing tasks) are running in an [[ESC cluster]]


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


### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]


##  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- for long-running application in an [[ESC cluster]] ([[AWS FARGATE]] or [[AWS EC2]])
- starts and controlled multiple [[AWS ECS task]]

### properties
- has a [[AWS ECS task definition]]
- has a `launch_type`: [[AWS FARGATE]] or [[AWS EC2]] (type of capasity provider)

### task connection
- needs a connection to the containers of its [[AWS ECS task|tasks]] on the container [[port]]
- thus the [[AWS ECS task|tasks]] needs a [[AWS target group]] (if a [[AWS Application Load Balancer (ALB)]] is set up its [[AWS target group]] can be reused)
- has a internal load balancer that is connected to the [[AWS target group]] of its [[AWS ECS task|tasks]] 
- a [[AWS Security Group]] that opend the `container port` is needed


Tags: infra
<!--ID: 1726750986428-->
END


START
Basic
what network settings are needed that a [[AWS ECS service]] can manage its [[AWS ECS task|tasks]] in an [[AWS ECS cluster]]? (3)

Back: 
there need to be a connection between the containers inside the [[AWS ECS task]] and the [[AWS ECS service]]

1) there need to be a `port mapping` between the container and its host [[AWS EC2]] instance (in order that the container can connect to the outside)
2) there need to be a [[AWS Security Group]] for the traffic between [[AWS ECS task]] and [[AWS ECS service]]
3) the `container port` needs to be setup in the [[AWS Elastic Load Balancer (ELB)]] of the [[AWS ECS service]]
_________________
## AWS ECS
- [[AWS]] service fpr running [[d image]] 
- ressource provider can be [[AWS FARGATE]] or manuelly managed [[AWS EC2]]  instances from an [[AWS Auto Scaling Group]] ([[AWS ECS on EC2]])
- [[AWS ECS cluster]]: grouping of [[AWS ECS task]], [[AWS ECS service]] and [[AWS EC2]] container instances
- [[AWS ECS task]] and [[AWS ECS service]] (which care managing tasks) are running in an [[ESC cluster]]


![[ecs-task-definition-terraform 1.jpg]]

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


### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]


##  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- for long-running application in an [[ESC cluster]] ([[AWS FARGATE]] or [[AWS EC2]])
- starts and controlled multiple [[AWS ECS task]]

### properties
- has a [[AWS ECS task definition]]
- has a `launch_type`: [[AWS FARGATE]] or [[AWS EC2]] (type of capasity provider)

### task connection
- needs a connection to the containers of its [[AWS ECS task|tasks]] on the container [[port]]
- thus the [[AWS ECS task|tasks]] needs a [[AWS target group]] (if a [[AWS Application Load Balancer (ALB)]] is set up its [[AWS target group]] can be reused)
- has a internal load balancer that is connected to the [[AWS target group]] of its [[AWS ECS task|tasks]] 
- a [[AWS Security Group]] that opend the `container port` is needed


Tags: infra
<!--ID: 1726516929911-->
END


START
Basic
[[AWS ECS]]
- concept
- how are ressources provided (2 options)
- how are workloads managed (3 concepts)

Back: 
## AWS ECS
- [[AWS]] service fpr running [[d image]] 
- ressource provider can be [[AWS FARGATE]] or manuelly managed [[AWS EC2]]  instances from an [[AWS Auto Scaling Group]] ([[AWS ECS on EC2]])
- [[AWS ECS cluster]]: grouping of [[AWS ECS task]], [[AWS ECS service]] and [[AWS EC2]] container instances
- [[AWS ECS task]] and [[AWS ECS service]] (which care managing tasks) are running in an [[ESC cluster]]

![[ecs-task-definition-terraform 2.jpg]]

_________________

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


### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]


##  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- for long-running application in an [[ESC cluster]] ([[AWS FARGATE]] or [[AWS EC2]])
- starts and controlled multiple [[AWS ECS task]]

### properties
- has a [[AWS ECS task definition]]
- has a `launch_type`: [[AWS FARGATE]] or [[AWS EC2]] (type of capasity provider)

### task connection
- needs a connection to the containers of its [[AWS ECS task|tasks]] on the container [[port]]
- thus the [[AWS ECS task|tasks]] needs a [[AWS target group]] (if a [[AWS Application Load Balancer (ALB)]] is set up its [[AWS target group]] can be reused)
- has a internal load balancer that is connected to the [[AWS target group]] of its [[AWS ECS task|tasks]] 
- a [[AWS Security Group]] that opend the `container port` is needed


Tags: infra
<!--ID: 1726516929914-->
END