```
resource "aws_autoscaling_group" "example" {  
  launch_configuration = aws_launch_configuration.example.name  
  vpc_zone_identifier  = data.aws_subnets.default.ids  target_group_arns = [aws_lb_target_group.asg.arn]  
  health_check_type = "ELB"  min_size = 2  
  max_size = 10  
  
  tag {  
    key                 = "Name"  
    value               = "terraform-asg-example"  
    propagate_at_launch = true  
  }  
}

resource "aws_security_group" "alb" {  
  name = "terraform-example-alb"  # Allow inbound HTTP requests  
  ingress {  
    from_port   = 80  
    to_port     = 80  
    protocol    = "tcp"  
    cidr_blocks = ["0.0.0.0/0"]  
  }  
  
  # Allow all outbound requests  
  egress {  
    from_port   = 0  
    to_port     = 0  
    protocol    = "-1"  
    cidr_blocks = ["0.0.0.0/0"]  
  }  
}

resource "aws_lb" "example" {  
  name               = "terraform-asg-example"  
  load_balancer_type = "application"  
  subnets            = data.aws_subnets.default.ids  
  security_groups    = [aws_security_group.alb.id]  
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

![[AWS Elastic Load Balancer (ELB)#load balancer]]

![[AWS Security Group#security group]]

# anki

START
Basic
what is needed to make a [[AWS ECS Elastic Container Service]] cluster or a [[AWS Auto Scaling Group]] commnicate with the internet?
Back: 
- a [[AWS Elastic Load Balancer (ELB)]] to create a single service endpoint for the group/cluster and a [[AWS Security Group]] to allow outside communication


## load balancer
- assigned to a [[AWS Auto Scaling Group]] ([[AWS EC2]] instances) or a [[AWS ECS Elastic Container Service]] cluster to make them accessable from outside

#### Network Load Balancer
- load balancer that works in the [[transport layer]] 
- should be used for [[transmission control protocol (TCP)]] or [[user datagram protocol (UDP)]] traffic

#### Application Load Balancer
- load balancer that works in the [[application layer]]
- should be used for [[hypertext transfer protocol (HTTP)]] traffic

## security group
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

```
resource "aws_security_group" "web_server" {  
  name        = "web_server"  
  description = "Allow inbound traffic on tcp/80 & SSH 22"  
  vpc_id = aws_default_vpc.default.id  
  
  ingress {  
    description     = "Allow 80 from the ALB"  
    from_port       = 80  
    to_port         = 80  
    protocol        = "tcp"  
    security_groups = [aws_security_group.alb.id]  
  }  
  
  egress {  
    description = "Allow all outbound traffic"  
    from_port   = 0  
    to_port     = 0  
    protocol    = -1  
    cidr_blocks = ["0.0.0.0/0"]  
  }  
  
  
  tags = {  
    Name    = "web_server"  
    Purpose = "Manage inbound traafic"  
  }  
}
```

 
Tags: infra
<!--ID: 1726336374989-->
END