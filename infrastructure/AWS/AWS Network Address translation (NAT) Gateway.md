### NAT Gateway 
- mapps [[AWS private ip]] to [[AWS public ip]] (n to 1)
- can connect a private [[AWS subnet]] to the internet, but only allows outbound traffic because multiple ressources can share the same [[AWS public ip]]
- the following [[AWS route]] in a [[AWS route table]] of a [[AWS subnet]] can connect the ressources over a [[AWS Network Address translation (NAT) Gateway]] to the internet

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | ``nat-gateway-id``    |

- for a bidirectionnal internet connection a [[AWS internet gateway]] is needed
# -----------------

![[AWS route table#route table]]

START
Basic
given a private [[AWS subnet]]
- how to connect it to the internet (incomming traffic only)
- complete internet connection
Back: 
### NAT Gateway 
- mapps [[AWS private ip]] to [[AWS public ip]] (n to 1)
- can connect a private [[AWS subnet]] to the internet, but only allows outbound traffic because multiple ressources can share the same [[AWS public ip]]
- the following [[AWS route]] in a [[AWS route table]] of a [[AWS subnet]] can connect the ressources over a [[AWS Network Address translation (NAT) Gateway]] to the internet
- for a bidirectionnal internet connection a [[AWS internet gateway]] is needed

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | ``nat-gateway-id``    |


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