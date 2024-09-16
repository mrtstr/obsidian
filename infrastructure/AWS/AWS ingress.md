- exposes HTTP and HTTPS routes from outside to a resource ([[AWS ECS service]] or [[AWS EC2]] instance)

```
# allow incomming TCP requests on port 8080 (all ips)
resource "aws_security_group" "instance" {
  name = "terraform-example-instance"
  ingress {
    from_port   = 8080
    to_port     = 8080
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```