### Application Load Balancer
- distributes traffic among multiple servers
- works in the [[application layer]] (e.g [[hypertext transfer protocol (HTTP)]] traffic)
- conducts healthchecks
- redirect diffent webservers depending on the request

![[ALB 1.jpg]]

#### listener
- a listner is needed to filter and forward incomming requests based on [[protocol]] and [[port]]
- a default response can be setup when no reachable

#### listener rule
- can have a listener rule based on the prefix of the path of the incomming [[uniform resource identifier (URI)]]

![[AWS target group#target group]]

## [[terraform]] example

```
resource "aws_lb" "example" {  
  name               = "terraform-asg-example"  
  load_balancer_type = "application"  
  subnets            = data.aws_subnets.default.ids  
  security_groups    = [aws_security_group.alb.id]
}
```

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


# anki

START
Basic
[[AWS Application Load Balancer (ALB)]] 
- what is it doing
- components (2 + 2 + 2)
- how is it connected to servers?
- [[terraform]] example
Back: 
### Application Load Balancer
- distributes traffic among multiple servers
- works in the [[application layer]] (e.g [[hypertext transfer protocol (HTTP)]] traffic)
- conducts healthchecks
- redirect diffent webservers depending on the request


![[ALB.jpg]]


#### listener
- a listner is needed to filter and forward incomming requests based on [[protocol]] and [[port]]
- a default response can be setup when no reachable

#### listener rule
- can have a listener rule based on the prefix of the path of the incomming [[uniform resource identifier (URI)]]

#### target group
- linkes the [[AWS Application Load Balancer (ALB)]] to a group of servers (in [[AWS Auto Scaling Group]] or [[AWS ECS service]] a ALB id can be referenced)
- can include a health checker

## [[terraform]] example

```
resource "aws_lb" "example" {  
  name               = "terraform-asg-example"  
  load_balancer_type = "application"  
  subnets            = data.aws_subnets.default.ids  
  security_groups    = [aws_security_group.alb.id]
}
```

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