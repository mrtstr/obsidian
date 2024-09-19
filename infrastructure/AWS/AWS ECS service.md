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

# ----------------------

![[AWS ECS task#ECS task]]

![[AWS ECS task definition#task definition]]

![[AWS Security Group#security group]]

# anki

START
Basic
[[AWS ECS service]]
- concept and eqivalent in the [[kubernetes]] world
- how is it connected and what is neede? (5)
- Relationship to [[AWS ECS task]]
- where does it get the ressources from?

Back: 
###  ECS service
- comparable to a [[kubernetes]] [[deployment]]
- for long-running application in an [[ESC cluster]] ([[AWS FARGATE]] or [[AWS EC2]])
- starts and controlled multiple [[AWS ECS task]]

### setup
- has a [[AWS ECS task definition]]
- has a `launch_type`: [[AWS FARGATE]] or [[AWS EC2]] (type of capasity provider)

##### task connection
- needs a connection to the containers of its [[AWS ECS task|tasks]] on the container [[port]]
- thus the [[AWS ECS task|tasks]] needs a [[AWS target group]] (if a [[AWS Application Load Balancer (ALB)]] is set up its [[AWS target group]] can be reused)
- has a internal load balancer that is connected to the [[AWS target group]] of its [[AWS ECS task|tasks]] 
- a [[AWS Security Group]] that opend the `container port` is needed

_________________



### security group
- acts as a virtual firewall between [[AWS]] ressources ([[AWS EC2]] or [[AWS Elastic Load Balancer (ELB)]])
- since any network traffic is blocked by default a [[AWS Security Group]] is needed for external communication
- is assigned to a [[AWS VPC (virtual private cloud)]]

#### ingress
- controlls incomming traffic from the internet
- from a certain [[port]] to a certain [[port]]
- only allows incomming traffic from within the specified [[internet protocol (IP)]] range (`cidr_blocks`)

#### egress
- controlls outdoing traffic to the internet
- from a certain [[port]] to a certain [[port]]
- only allows traffic to the specified [[internet protocol (IP)]] range (`cidr_blocks`)

Tags: infra
<!--ID: 1726516929907-->
END