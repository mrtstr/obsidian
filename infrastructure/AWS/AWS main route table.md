### main route table
- [[AWS route table]] of a [[AWS VPC (virtual private cloud)]] that is assiciated with any [[AWS subnet]] that is not assiciated with any other [[AWS route table]]
# -----------

![[AWS route table#route table]]



START
Basic
[[AWS main route table]]
- concept
- relationship to [[AWS route table]] and [[AWS route]]
Back: 
### main route table
- [[AWS route table]] of a [[AWS VPC (virtual private cloud)]] that is assiciated with any [[AWS subnet]] that is not assiciated with any other [[AWS route table]]

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
<!--ID: 1727092048909-->
END