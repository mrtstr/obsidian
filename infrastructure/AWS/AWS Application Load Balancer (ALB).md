### Application Load Balancer
- [[AWS Elastic Load Balancer (ELB)]] that works in the [[application layer]]
- should be used for [[hypertext transfer protocol (HTTP)]] traffic
- needs a listener 
- needs a target group




# anki

START
Basic
[[AWS Application Load Balancer (ALB)]] example 
Back: 
### Application Load Balancer
- [[AWS Elastic Load Balancer (ELB)]] that works in the [[application layer]]
- should be used for [[hypertext transfer protocol (HTTP)]] traffic
- need a listener

```
resource "aws_lb" "example" {  
  name               = "terraform-asg-example"  
  load_balancer_type = "application"  
  subnets            = data.aws_subnets.default.ids  
}

resource "aws_lb_listener" "http" {  
  load_balancer_arn = aws_lb.example.arn  
  port              = 80  
  protocol          = "HTTP"  
  
  # By default, return a simple 404 page  
  default_action {  
    type = "fixed-response"  
  
    fixed_response {  
      content_type = "text/plain"  
      message_body = "404: page not found"  
      status_code  = 404  
    }  
  }  
}
```


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