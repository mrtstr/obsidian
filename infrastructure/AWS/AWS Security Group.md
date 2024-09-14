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

![[AWS VPC (virtual private cloud)]]

# anki

START
Basic
- how to allow and controll traffic between [[AWS]] ressource and internet (incomming and outgoing)
- with [[terraform]] example
Back: 
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

Tags: infra
<!--ID: 1726336375004-->
END


```

## virtual private cloud
- virtual isolated network within a [[AWS]]

Tags: infra

END