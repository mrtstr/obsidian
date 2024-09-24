
## route table
- contains [[AWS route|routes]] that direct network traffic between [[AWS subnet|subnets]] and [[AWS gateway|gateways]]
- can be assiciated to multiple [[AWS subnet|subnets]] and [[AWS gateway|gateways]]


![[AWS route#route]]


## route priority
- generally the most specific route that matches the traffic is used
	→ the route with the nongest matching prefix is used
	→ example `10.10.2.15/32` has priority over `10.10.2.0/24`

## route propagation
- [[AWS route|routes]] from a connected [[AWS virtual private gateway (VPG)]] are added to a [[AWS route table]] by reference

## example
- the local rule ensures connectivity to the CIDR of the [[AWS VPC (virtual private cloud)]] and cant be changes
- the default rule is to the [[AWS internet gateway]] because all relevant private ranges are covered with a more specific rule

| Destination    | Target |
| -------- | ------- |
| `10.0.0.0/16`  | `local`    |
| `172.31.0.0/16`  | `pcx-11223344556677889`    |
| `0.0.0.0/0`  | `igw-12345678901234567`    |

- `10.0.0.0/16` (`10.0.0.0` to `10.0.255.255`) is covered by the local [[AWS route]]
- `172.31.0.0/16` (`172.31.0.0` to `172.31.255.255`) is sent to a [[AWS VPC Peering]]
- every adress (`0.0.0.0/0`) is routed to an [[AWS internet gateway]]
→ erything that is not in the local range or the [[AWS VPC Peering]] is sent to the [[AWS internet gateway]]

# ----------------

![[ip V4#private an public ip ranges]]

![[vpc-resource-map-update.png]]


# anki

START
Basic
[[AWS route table]] in [[AWS]]
- how to the enys look like?
- how are rules prioritized?
- what is route propagation?
- example [[AWS route table]] for a public subnet that is connected wi another [[AWS VPC (virtual private cloud)]] via [[AWS VPC Peering]]

Back: 
## route table
- contains [[AWS route|routes]] that direct network traffic between [[AWS subnet|subnets]] and [[AWS gateway|gateways]]
- can be assiciated to multiple [[AWS subnet|subnets]] and [[AWS gateway|gateways]]


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


## route priority
- generally the most specific route that matches the traffic is used
	→ the route with the nongest matching prefix is used
	→ example `10.10.2.15/32` has priority over `10.10.2.0/24`

## route propagation
- [[AWS route|routes]] from a connected [[AWS virtual private gateway (VPG)]] are added to a [[AWS route table]] by reference

## example
- the local rule ensures connectivity to the CIDR of the [[AWS VPC (virtual private cloud)]] and cant be changes
- the default rule is to the [[AWS internet gateway]] because all relevant private ranges are covered with a more specific rule

| Destination    | Target |
| -------- | ------- |
| `10.0.0.0/16`  | `local`    |
| `172.31.0.0/16`  | `pcx-11223344556677889`    |
| `0.0.0.0/0`  | `igw-12345678901234567`    |

- `10.0.0.0/16` (`10.0.0.0` to `10.0.255.255`) is covered by the local [[AWS route]]
- `172.31.0.0/16` (`172.31.0.0` to `172.31.255.255`) is sent to a [[AWS VPC Peering]]
- every adress (`0.0.0.0/0`) is routed to an [[AWS internet gateway]]
→ verything that is not in the local range or the [[AWS VPC Peering]] is sent to the [[AWS internet gateway]]

______________

## private an public ip ranges
- `10.0.0.0/8` (`10.0.0.0`  to `10.255.255.255`)
- `172.16.0.0/20` (`172.16.0.0` to `172.31.255.255`)
- `192.168.0.0/16` (`192.168.0.0` to `192.168.255.255`)

- everything else is public



Tags: infra
<!--ID: 1727092048917-->
END

START
Basic
3 main concepts for controlling (allow and deny) traffic in [[AWS]] and their differences

Back: 
### route table
- contains routes that direct network traffic between [[AWS subnet|subnets]] and [[AWS gateway|gateways]]

#### route
- entry in a [[AWS route table]] that connects [[AWS subnet|subnets]] and [[AWS gateway|gateways]] within a [[AWS VPC (virtual private cloud)]]
- is associated with a [[AWS route table]], has a [[internet protocol (IP)|IP range]] and has a target type (e.g. [[AWS gateway]] type)

### network access control list
- allows or denies specific inbound or outbound traffic at the [[AWS subnet]] level.
- per default a [[AWS subnet]] is automatically associated with the default [[AWS network access control list (ACL)]]: allow all traffic to flow in and out of the subnets

### security group
- virtual firewall between [[AWS]] ressources (e.g. [[AWS EC2]] or [[AWS Elastic Load Balancer (ELB)]])
- any network traffic is blocked by default thus a [[AWS Security Group]] is needed for external communication
- incomming traffic is controlled with an ingress rule and outgoing traffic is controlled with a egress rule
- rules are defined by [[protocol]], [[internet protocol (IP)|ip range]] and [[port]]

Tags: infra
<!--ID: 1727092048921-->
END

START
Basic
- `10.0.0.0` to `10.0.255.255` is the CIDR of the [[AWS VPC (virtual private cloud)]]
- `172.31.0.0` to `172.31.255.255` should be sent to a [[AWS VPC Peering]]
- the [[AWS subnet]] is connected to the internet

how does the [[AWS route table]] look like

Back: 

- the local rule ensures connectivity to the CIDR of the [[AWS VPC (virtual private cloud)]] and cant be changes
- the default rule is to the [[AWS internet gateway]] because all relevant private ranges are covered with a more specific rule

| Destination    | Target |
| -------- | ------- |
| `10.0.0.0/16`  | `local`    |
| `172.31.0.0/16`  | `pcx-11223344556677889`    |
| `0.0.0.0/0`  | `igw-12345678901234567`    |

- `10.0.0.0/16` (`10.0.0.0` to `10.0.255.255`) is covered by the local[[AWS route]]
- `172.31.0.0/16` (`172.31.0.0` to `172.31.255.255`) is sent to a [[AWS VPC Peering]]
- every adress (`0.0.0.0/0`) is routed to an [[AWS internet gateway]]
→ everyting that is not in the local range or the [[AWS VPC Peering]] is sent to the [[AWS internet gateway]] because of the route priority

### route table
- contains [[AWS route|routes]] that direct network traffic between [[AWS subnet|subnets]] and [[AWS gateway|gateways]]
- can be assiciated to multiple [[AWS subnet|subnets]] and [[AWS gateway|gateways]]
- types
	- `subnet route table`: associated with a [[AWS subnet]]
	- `gateway route table`: assiciated with [[AWS virtual private gateway (VPG)]] and [[AWS internet gateway]]
	- `trasit gateway route table`: assiciated with [[AWS transit gateway]]


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


### route priority
- generally the most specific route that matches the traffic is used
	→ the route with the nongest matching prefix is used
	→ example `10.10.2.15/32` has priority over `10.10.2.0/24`


Tags: infra
<!--ID: 1727092048924-->
END

