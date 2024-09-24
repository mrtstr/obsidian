### NAT Gateway 
- mapps [[internet protocol (IP)|IP adresses]] n to 1
- can be used to connect a private subnet to the internet ([[AWS private ip]] to [[AWS public ip]])
- can be used to connect one private [[AWS VPC (virtual private cloud)|VPC]] to another ([[AWS private ip]] to [[AWS private ip]])

#### for outboung internet accsess for a private subnet
- can connect a private [[AWS subnet]] to the internet, but only allows outbound traffic because multiple ressources can share the same [[AWS public ip]]
- the [[AWS Network Address translation (NAT) Gateway]] will be placed in a public subnet and a [[AWS default route]] to that [[AWS Network Address translation (NAT) Gateway|NAT gateway]] is created in the private subnet
- the following [[AWS route]] in a [[AWS route table]] of a [[AWS subnet]] can connect the ressources over a [[AWS Network Address translation (NAT) Gateway]] to the internet

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | ``nat-gateway-id``    |

![[public-nat-gateway-diagram.png]]

# -----------------

![[AWS route table#route table]]

START
Basic
[[AWS Network Address translation (NAT) Gateway]]
- concepts
- two usecases
Back: 
### NAT Gateway 
- mapps [[internet protocol (IP)|IP adresses]] n to 1
- can be used to connect a private subnet to the internet ([[AWS private ip]] to [[AWS public ip]])
- can be used to connect one private [[AWS VPC (virtual private cloud)|VPC]] to another ([[AWS private ip]] to [[AWS private ip]])

#### for outboung internet accsess for a private subnet
- can connect a private [[AWS subnet]] to the internet, but only allows outbound traffic because multiple ressources can share the same [[AWS public ip]]
- the [[AWS Network Address translation (NAT) Gateway]] will be placed in a public subnet and a [[AWS default route]] to that [[AWS Network Address translation (NAT) Gateway|NAT gateway]] is created in the private subnet
- the following [[AWS route]] in a [[AWS route table]] of a [[AWS subnet]] can connect the ressources over a [[AWS Network Address translation (NAT) Gateway]] to the internet

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | ``nat-gateway-id``    |

![[public-nat-gateway-diagram 2.png]]


_______________________


### route table
- contains [[AWS route|routes]] that direct network traffic between [[AWS subnet|subnets]] and [[AWS gateway|gateways]]

### route
- entry in a [[AWS route table]] that connects [[AWS subnet|subnets]] and [[AWS gateway|gateways]] within a [[AWS VPC (virtual private cloud)]]
- is associated with a [[AWS route table]], has a [[internet protocol (IP)|IP range]] and has a target type (e.g. [[AWS gateway]] type)

example
```terraform
resource "aws_route" "r" {
  route_table_id            = aws_route_table.testing.id
  destination_cidr_block    = "10.0.1.0/22"
  vpc_peering_connection_id = "pcx-45ff3dc1"
}
```

Tags: infra
<!--ID: 1727162581630-->
END

START
Basic
given a private [[AWS subnet]]
- how to connect it to the internet (outboung access only)
- complete internet connection
Back: 
### NAT Gateway 
- mapps [[internet protocol (IP)|IP adresses]] n to 1
- can be used to connect a private subnet to the internet ([[AWS private ip]] to [[AWS public ip]])
- can be used to connect one private [[AWS VPC (virtual private cloud)|VPC]] to another ([[AWS private ip]] to [[AWS private ip]])

#### for outbound internet accsess for a private subnet
- can connect a private [[AWS subnet]] to the internet, but only allows outbound traffic because multiple ressources can share the same [[AWS public ip]]
- the [[AWS Network Address translation (NAT) Gateway]] will be placed in a public subnet and a [[AWS default route]] to that [[AWS Network Address translation (NAT) Gateway|NAT gateway]] is created in the private subnet
- the following [[AWS route]] in a [[AWS route table]] of a [[AWS subnet]] can connect the ressources over a [[AWS Network Address translation (NAT) Gateway]] to the internet

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | ``nat-gateway-id``    |
![[public-nat-gateway-diagram 1.png]]

### internet gateway
- virtual [[router]] that connects a [[AWS VPC (virtual private cloud)]] (and [[AWS subnet|subnets]] withing) to the internet
- the following [[AWS route]] in the [[AWS route table]] would connect it to an [[AWS internet gateway]] 

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | `igw-id`    |

_______________________


### route table
- contains [[AWS route|routes]] that direct network traffic between [[AWS subnet|subnets]] and [[AWS gateway|gateways]]

### route
- entry in a [[AWS route table]] that connects [[AWS subnet|subnets]] and [[AWS gateway|gateways]] within a [[AWS VPC (virtual private cloud)]]
- is associated with a [[AWS route table]], has a [[internet protocol (IP)|IP range]] and has a target type (e.g. [[AWS gateway]] type)

example
```terraform
resource "aws_route" "r" {
  route_table_id            = aws_route_table.testing.id
  destination_cidr_block    = "10.0.1.0/22"
  vpc_peering_connection_id = "pcx-45ff3dc1"
}
```

Tags: infra
<!--ID: 1727092048930-->
END