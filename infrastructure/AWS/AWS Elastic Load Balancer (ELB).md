### load balancer
- assigned to a [[AWS Auto Scaling Group]] ([[AWS EC2]] instances) or a [[AWS ECS Elastic Container Service]] cluster to make them accessable from outside
- consists of multiple servers that can run in seperate [[AWS subnet]]
- [[AWS]] automatically scales the number of load balancer servers up and down based on traffic
- by default don't allow any traffic to a [[AWS Security Group]] is needed

![[AWS Network Load Balancer (NLB)#Network Load Balancer]]

![[AWS Application Load Balancer (ALB)#Application Load Balancer]]
 


# anki

START
Basic
general concept
releationship to [[AWS subnet]]
relationship to [[AWS Security Group]]
different kinds of [[AWS Elastic Load Balancer (ELB)]] (2)
what are they used for?
Back: 

### load balancer
- assigned to a [[AWS Auto Scaling Group]] ([[AWS EC2]] instances) or a [[AWS ECS Elastic Container Service]] cluster to make them accessable from outside
- consists of multiple servers that can run in seperate [[AWS subnet]]
- [[AWS]] automatically scales the number of load balancer servers up and down based on traffic
- by default don't allow any traffic to a [[AWS Security Group]] is needed

### Network Load Balancer
- load balancer that works in the [[transport layer]] 
- should be used for [[transmission control protocol (TCP)]] or [[user datagram protocol (UDP)]] traffic

### Application Load Balancer
- load balancer that works in the [[application layer]]
- should be used for [[hypertext transfer protocol (HTTP)]] traffic

 
Tags: infra

END