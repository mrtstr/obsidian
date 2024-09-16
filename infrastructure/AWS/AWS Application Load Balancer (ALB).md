### Application Load Balancer
- [[AWS Elastic Load Balancer (ELB)]] that works in the [[application layer]]
- should be used for [[hypertext transfer protocol (HTTP)]] traffic

```
resource "aws_lb" "example" {  
  name               = "terraform-asg-example"  
  load_balancer_type = "application"  
  subnets            = data.aws_subnets.default.ids  
  security_groups    = [aws_security_group.alb.id]
}
```

![[ALB 1.jpg]]

#### listener
- a listner is needed to filter and forward incomming requests based on [[protocol]] and [[port]]
- a default response can be setup when no reachable

```terraform
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

#### listener rule
- can have a listener rule based on the prefix of the path of the incomming [[uniform resource identifier (URI)]]

```terraform
resource "aws_lb_listener_rule" "asg" {  
  listener_arn = aws_lb_listener.http.arn  
  priority     = 100  
  
  condition {  
    path_pattern {  
      values = ["*"]  
    }  
  }  
  
  action {  
    type             = "forward"  
    target_group_arn = aws_lb_target_group.asg.arn  
  }  
}
```

#### target group
- group of instances the request is forwarded to
- a list of e.g. [[AWS EC2]] instances can be procided but most of the time the target group should be assigned to a [[AWS Auto Scaling Group]] or a [[AWS ECS]] luster
- can include a health checker

```terraform
resource "aws_lb_target_group" "asg" {  
  name     = "terraform-asg-example"  
  port     = var.server_port  
  protocol = "HTTP"  
  vpc_id   = data.aws_vpc.default.id  
  
  health_check {  
    path                = "/"  
    protocol            = "HTTP"  
    matcher             = "200"  
    interval            = 15  
    timeout             = 3  
    healthy_threshold   = 2  
    unhealthy_threshold = 2  
  }  
}
```





# anki

START
Basic
[[AWS Application Load Balancer (ALB)]] 
- what is it doing
- components (3) with example
Back: 
### Application Load Balancer
- [[AWS Elastic Load Balancer (ELB)]] that works in the [[application layer]]
- should be used for [[hypertext transfer protocol (HTTP)]] traffic


![[ALB.jpg]]


#### listener
- a listner is needed to filter and forward incomming requests based on [[protocol]] and [[port]]
- a default response can be setup when no reachable

```terraform
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

#### listener rule
- can have a listener rule based on the prefix of the path of the incomming [[uniform resource identifier (URI)]]

```terraform
resource "aws_lb_listener_rule" "asg" {  
  listener_arn = aws_lb_listener.http.arn  
  priority     = 100  
  
  condition {  
    path_pattern {  
      values = ["*"]  
    }  
  }  
  
  action {  
    type             = "forward"  
    target_group_arn = aws_lb_target_group.asg.arn  
  }  
}
```

#### target group
- group of instances the request is forwarded to
- a list of e.g. [[AWS EC2]] instances can be procided but most of the time the target group should be assigned to a [[AWS Auto Scaling Group]] or a [[AWS ECS]] luster
- can include a health checker

```terraform
resource "aws_lb_target_group" "asg" {  
  name     = "terraform-asg-example"  
  port     = var.server_port  
  protocol = "HTTP"  
  vpc_id   = data.aws_vpc.default.id  
  
  health_check {  
    path                = "/"  
    protocol            = "HTTP"  
    matcher             = "200"  
    interval            = 15  
    timeout             = 3  
    healthy_threshold   = 2  
    unhealthy_threshold = 2  
  }  
}
```

_______________________


### load balancer
- assigned to a [[AWS Auto Scaling Group]] ([[AWS EC2]] instances) or a [[AWS ECS]] cluster to make them accessable from outside
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
<!--ID: 1726336375007-->
END