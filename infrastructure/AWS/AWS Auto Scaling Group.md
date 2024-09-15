### auto scaling groups
- for running multiple [[AWS EC2]] instances with autoscaling
- similar to [[AWS ECS Elastic Container Service]] with virtual machines instead of [[docker]] container

```
resource "aws_autoscaling_group" "example" {  
  launch_configuration = aws_launch_configuration.example.name  
  vpc_zone_identifier  = data.aws_subnets.default.ids  
  min_size = 2  
  max_size = 10  
  tag {  
    key                 = "Name"  
    value               = "terraform-asg-example"  
    propagate_at_launch = true  
  }  
}
```

### launch configuration
- need a `aws_launch_configuration` that defines the propertie of the [[AWS EC2]] instances
 [[AWS lifecycle settings]] with `create_before_destroy = true` are recommended because otherwise the launch config cant be changed because of the reference to the outtoscaling group
- need a [[AWS VPC (virtual private cloud)]] where the machines will be deployed to

```terraform
resource "aws_launch_configuration" "example" {  
  image_id        = "ami-0fb653ca2d3203ac1"  
  instance_type   = "t2.micro"  
  security_groups = [aws_security_group.instance.id]  
  
  user_data = <<-EOF  
              #!/bin/bash  
              echo "Hello, World" > index.html  
              nohup busybox httpd -f -p ${var.server_port} &  
              EOF  # Required when using a launch configuration with an ASG.  
  lifecycle {  
    create_before_destroy = true  
  }  
}
```

# anki


START
Basic
how to change immutable propertie of a [[AWS]] ressource when there is a reference from another ressource to it

Back: 
- normaly [[terraform]] would destroy and recreate the ressource but this will not work because of the reference
- [[AWS lifecycle settings]] with `create_before_destroy = true` are recommended because otherwise the launch config cant be changed because of the reference to the outtoscaling group

```
resource "aws_autoscaling_group" "example" {  
  launch_configuration = aws_launch_configuration.example.name  
  vpc_zone_identifier  = data.aws_subnets.default.ids  
  min_size = 2  
  max_size = 10  
  
  tag {  
    key                 = "Name"  
    value               = "terraform-asg-example"  
    propagate_at_launch = true  
  }  
}

resource "aws_launch_configuration" "example" {  
  image_id        = "ami-0fb653ca2d3203ac1"  
  instance_type   = "t2.micro"  
  security_groups = [aws_security_group.instance.id]  
  
  user_data = <<-EOF  
              #!/bin/bash  
              echo "Hello, World" > index.html  
              nohup busybox httpd -f -p ${var.server_port} &  
              EOF  # Required when using a launch configuration with an ASG.  
  lifecycle {  
    create_before_destroy = true  
  }  
}
```

Tags: infra
<!--ID: 1726379196596-->
END

START
Basic
[[AWS Auto Scaling Group]]
- plus one nesseay component with example each
- concent end differenct to [[AWS ECS Service]]

Back: 
### auto scaling groups
- for running multiple [[AWS EC2]] instances with autoscaling
- similar to [[AWS ECS Elastic Container Service]] with virtual machines instead of [[docker]] container

```
resource "aws_autoscaling_group" "example" {  
  launch_configuration = aws_launch_configuration.example.name  
  vpc_zone_identifier  = data.aws_subnets.default.ids  
  min_size = 2  
  max_size = 10  
  tag {  
    key                 = "Name"  
    value               = "terraform-asg-example"  
    propagate_at_launch = true  
  }  
}
```

### launch configuration
- need a `aws_launch_configuration` that defines the propertie of the [[AWS EC2]] instances
 [[AWS lifecycle settings]] with `create_before_destroy = true` are recommended because otherwise the launch config cant be changed because of the reference to the outtoscaling group
- need a [[AWS VPC (virtual private cloud)]] where the machines will be deployed to

```terraform
resource "aws_launch_configuration" "example" {  
  image_id        = "ami-0fb653ca2d3203ac1"  
  instance_type   = "t2.micro"  
  security_groups = [aws_security_group.instance.id]  
  
  user_data = <<-EOF  
              #!/bin/bash  
              echo "Hello, World" > index.html  
              nohup busybox httpd -f -p ${var.server_port} &  
              EOF  # Required when using a launch configuration with an ASG.  
  lifecycle {  
    create_before_destroy = true  
  }  
}
```


Tags: infra
<!--ID: 1726379196600-->
END