[How to Deploy an AWS ECS Cluster with Terraform [Tutorial] (spacelift.io)](https://spacelift.io/blog/terraform-ecs)
[How to run ECS Fargate Terraform — AWS Cloud by nexgeneerz](https://nexgeneerz.io/how-to-setup-amazon-ecs-fargate-terraform/)
https://engineering.finleap.com/posts/2020-02-20-ecs-fargate-terraform/

## AWS ECS
- running [[d image]] in containers 
- capacity provider can be managed: FARGATE or manuelly managed with [[AWS Auto Scaling Group]] of [[AWS EC2]] 

#### components
- [[AWS ECS cluster]]: grouping of [[AWS ECS task]], [[AWS ECS service]] and [[AWS EC2]] container instances
- [[AWS Application Load Balancer (ALB)]] + [[AWS Security Group]] to expose the [[AWS EC2]] instances where the [[d image]] are running to the internet
	- [[AWS ingress]] exposing [[port]] `80` and `443` of [[transmission control protocol (TCP)|TCP]] for [[hypertext transfer protocol (HTTP)|HTTP]] communication
- [[AWS ECS service]] for each deployment
	- manages the [[AWS ECS task]]
	- has a [[AWS ECS task definition]] containing a blueprint
	- [[AWS Security Group]] for traffic between [[AWS ECS task]] and [[AWS ECS service]]
- capacity provider that is providing the [[AWS EC2]] instances
	- FARGATE (managed): needs autoscaling policy for instances, cpu and memory can be provided
	- manuelly managed with [[AWS Auto Scaling Group]] and launch template

![[ecs-task-definition-terraform.jpg]]



![[AWS ECS cluster#ESC cluster]]

![[AWS ECS task#ECS task]]

![[AWS ECS task definition#task definition]]

![[AWS ECS service#ECS service]]



### Container Instance
-  synonym for an EC2 Instance

### ECS Container Agent
- allows Container Instances to connect to the ECS Cluster

### Fargate vs ES2
the following the following resources have to be managed by us vs AWS
- EC2 Launch Templates 
- Autoscaling Groups,
- Capacity Providers

### aws_launch_template
- similar concept to aws_launch_configuration


# anki


START
Basic
what network settings are needed that a [[AWS ECS service]] can manage its [[AWS ECS task|tasks]] in an [[AWS ECS cluster]]?

Back: 
there need to be a connection on the `container port` that can be chosen between the containers inside the [[AWS ECS task]] and the [[AWS ECS service]]

1) there need to be a `port mapping` between the container and its host [[AWS EC2]] instance (in order that the container can connect to the outside)
2) there need to be a [[AWS Security Group]] for the traffic between [[AWS ECS task]] and [[AWS ECS service]]
3) the `container port` needs to be setup in the [[AWS Elastic Load Balancer (ELB)]] of the [[AWS ECS service]]
_________________
## AWS ECS
- running [[d image]] in containers 
- capacity provider can be managed: FARGATE or manuelly managed with [[AWS Auto Scaling Group]] of [[AWS EC2]] 

#### components
- [[AWS ECS cluster]]: grouping of [[AWS ECS task]], [[AWS ECS service]] and [[AWS EC2]] container instances
- [[AWS Application Load Balancer (ALB)]] + [[AWS Security Group]] to expose the [[AWS EC2]] instances where the [[d image]] are running to the internet
	- [[AWS ingress]] exposing [[port]] `80` and `443` of [[transmission control protocol (TCP)|TCP]] for [[hypertext transfer protocol (HTTP)|HTTP]] communication
- [[AWS ECS service]] for each deployment
	- manages the [[AWS ECS task]]
	- has a [[AWS ECS task definition]] containing a blueprint
	- [[AWS Security Group]] for traffic between [[AWS ECS task]] and [[AWS ECS service]]
- capacity provider that is providing the [[AWS EC2]] instances
	- FARGATE (managed): needs autoscaling policy for instances, cpu and memory can be provided
	- manuelly managed with [[AWS Auto Scaling Group]] and launch template

![[ecs-task-definition-terraform 1.jpg]]

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

### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]


###  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- is running in a [[ESC cluster]]
- has a [[AWS ECS task definition]] and manages multiple [[AWS ECS task]]
- has a `launch_type`: [[AWS FARGATE]] or manuelly (type of capasity provider)
- is connected to its [[AWS ECS task|tasks]] (traffic over a [[AWS Security Group]] on [[port]] `container port`) and has a internal [[AWS Elastic Load Balancer (ELB)]] (port mapping needed in the `container definition`  of the [[AWS ECS task definition]])


Tags: infra
<!--ID: 1726516929911-->
END


START
Basic
[[AWS ECS]]
- how is it organized?
- 2 nesseary networks connections between components to expose a web page?

Back: 
## AWS ECS
- running [[d image]] in containers 
- how are the components working togather?
- capacity provider can be managed: FARGATE or manuelly managed with [[AWS Auto Scaling Group]] of [[AWS EC2]] 
- how are the [[AWS EC2]] instances managed?

#### components
- [[AWS ECS cluster]]: grouping of [[AWS ECS task]], [[AWS ECS service]] and [[AWS EC2]] container instances
- [[AWS Application Load Balancer (ALB)]] + [[AWS Security Group]] to expose the [[AWS EC2]] instances where the [[d image]] are running to the internet
	- [[AWS ingress]] exposing [[port]] `80` and `443` of [[transmission control protocol (TCP)|TCP]] for [[hypertext transfer protocol (HTTP)|HTTP]] communication
- [[AWS ECS service]] for each deployment
	- manages the [[AWS ECS task]]
	- has a [[AWS ECS task definition]] containing a blueprint
	- [[AWS Security Group]] for traffic between [[AWS ECS task]] and [[AWS ECS service]]
- capacity provider that is providing the [[AWS EC2]] instances
	- FARGATE (managed): needs autoscaling policy for instances, cpu and memory can be provided
	- manuelly managed with [[AWS Auto Scaling Group]] and launch template

![[ecs-task-definition-terraform 2.jpg]]

_________________

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

### ECS task
- comparable to a [[kubernetes]] [[pod]]
- can be managed by a [[AWS ECS service]] based on a [[AWS ECS task definition]] or be independent
- can have multiple containers that are based on a [[d image]]


###  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- is running in a [[ESC cluster]]
- has a [[AWS ECS task definition]] and manages multiple [[AWS ECS task]]
- has a `launch_type`: [[AWS FARGATE]] or manuelly (type of capasity provider)
- is connected to its [[AWS ECS task|tasks]] (traffic over a [[AWS Security Group]] on [[port]] `container port`) and has a internal [[AWS Elastic Load Balancer (ELB)]] (port mapping needed in the `container definition`  of the [[AWS ECS task definition]])


Tags: infra
<!--ID: 1726516929914-->
END