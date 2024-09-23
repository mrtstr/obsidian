### route
- entry in a [[AWS route table]] that connects [[AWS subnet|subnets]] and [[AWS gateway|gateways]] within a [[AWS VPC (virtual private cloud)]]
- is associated with a [[AWS route table]], has a [[AWS private ip]] range (e.g. `10.0.1.0/22`) and has a target type (e.g. [[AWS gateway]] type)

example
```terraform
resource "aws_route" "r" {
  route_table_id            = aws_route_table.testing.id
  destination_cidr_block    = "10.0.1.0/22"
  vpc_peering_connection_id = "pcx-45ff3dc1"
}
```