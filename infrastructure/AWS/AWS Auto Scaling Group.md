### auto scaling groups
- for running multiple [[AWS EC2]] instances with autoscaling
- similar to [[AWS ECS Elastic Container Service]] with virtual machines instead of [[docker]] container

```
resource "aws_autoscaling_group" "example" {  
  launch_configuration = aws_launch_configuration.example.name  
  vpc_zone_identifier  = data.aws_subnets.default.ids  min_size = 2  
  max_size = 10  
  
  tag {  
    key                 = "Name"  
    value               = "terraform-asg-example"  
    propagate_at_launch = true  
  }  
}
```s