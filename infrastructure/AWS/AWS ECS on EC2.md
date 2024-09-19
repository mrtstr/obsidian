### ECS on EC2
- running [[AWS ECS]] while manage the [[AWS EC2]] host instances where the [[d container]] are running  
- instances from an [[AWS Auto Scaling Group]] that is creating [[AWS EC2]] instances based on a [[AWS launch template]] are used as host for the [[AWS ECS task]]/containers
- autoscaling has to be defined manuelly to make sure there are enough instances avaliable without too much ideling ressources
- billed by specifications of the running [[AWS EC2]]

![[AWS FARGATE#FARGATE]]

![[AWS ECS#AWS ECS]]
# anki

START
Basic
[[AWS ECS on EC2]] vs [[AWS FARGATE]]
- concept
- how is it billed
Back: 
### FARGATE
- [[AWS]] service that provides compute ressources for [[d container]] appliations
- management of the underlaying [[AWS EC2]] instances is done by [[AWS]]
- billed by used [[li memory]] and [[li cpu]] cores instead of on instance level

### ECS on EC2
- running [[AWS ECS]] while manage the [[AWS EC2]] host instances where the [[d container]] are running  
- instances from an [[AWS Auto Scaling Group]] that is creating [[AWS EC2]] instances based on a [[AWS launch template]] are used as host for the [[AWS ECS task]]/containers
- autoscaling has to be defined manuelly to make sure there are enough instances avaliable without too much ideling ressources
- billed by specifications of the running [[AWS EC2]]
_____________________



## EC2
- virtual machine

### properties
- create from [[AWS Amazon Machine Image (AMI)]]
- user data: script that executed when the instance is started
- `instance_type`: machine type
- [[AWS Security Group]] for network access
- [[AWS subnet]] to launch in
- `key name` for a [[AWS EC2 key pairs]] for setting up [[secure shell protocol (SSH)]] access


### file system
- no data persitence without persistent data storage
	- [[AWS elastic file system EFS]]: multiple instances can use it
	- [[AWS Elastic Block Store (EBS)]]: only one instance can use it


Tags: infra
<!--ID: 1726750986420-->
END