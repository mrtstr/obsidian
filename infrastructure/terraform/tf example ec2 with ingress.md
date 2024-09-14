- create a simple [[AWS EC2]] instance from a[[AWS Amazon Machine Image (AMI)]]
- start a simple web server in it using busybox (`user_data` script is executed when the instance is created)
- creates a [[AWS Security Group]] with a [[AWS ingress]] that opens all up port `8080` for all external ip addresses

```
resource "aws_instance" "example" {
  ami                    = "ami-0fb653ca2d3203ac1"
  instance_type          = "t2.micro"
  user_data = <<-EOF
              #!/bin/bash
              echo "Hello, World" > index.html
              nohup busybox httpd -f -p 8080 &
              EOF
  
  user_data_replace_on_change = true
  vpc_security_group_ids = [aws_security_group.instance.id]

  tags = {
    Name = "terraform-example"
  }
}
 

# allow incomming TCP requests on port 8080
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
