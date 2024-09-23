### subnet
- range of [[internet protocol (IP)|IP adresses]] in a [[AWS VPC (virtual private cloud)]]
- has a [[AWS route table]] that determines which networks adresses are reachable
- lives in a single [[AWS AZ (isolated datacenter)]]
- ressources (like [[AWS EC2]] instances) are launched into a [[AWS subnet]]
- allways internal [[AWS DNS hostname]] pointing to its [[AWS private ip]]

### subnet route table
- can have a **custom route table** or the (default) [[AWS main route table]] of its [[AWS VPC (virtual private cloud)]]
- every [[AWS route table]] of a [[AWS subnet]] has by default the local rule to all [[AWS subnet|subnets]] within its [[AWS VPC (virtual private cloud)|VPC]] that can't be changes
- based on the entrys in its [[AWS route table]] the a [[AWS subnet]] can be described as 
	- a public subnet
	- a private subnet
	- a isolated subnet
	- a [[VPN]] only subnet

##### public subnet
- direct access to a [[AWS internet gateway]]
- ressource get a [[AWS private ip]] and a [[AWS public ip]] assigned by default
- usually the [[AWS route]] associated with the [[AWS internet gateway]] is the default and all relevate private ranges are covered by more specific [[AWS route|routes]]

![[AWS internet gateway#internet gateway]]


##### private subnet
- no connection to a [[AWS internet gateway]]
- ressources inside it only have a [[AWS private ip]] and can only be accessed from inside its [[AWS VPC (virtual private cloud)]]
- can be connected to the internet with a [[AWS Network Address translation (NAT) Gateway]]
- if a private subnet is connected to a [[AWS Network Address translation (NAT) Gateway]] its the default [[AWS route]]

![[AWS Network Address translation (NAT) Gateway#NAT Gateway]]


##### isolated subnet 
- has no connection to other [[AWS subnet|subnets]] within its [[AWS VPC (virtual private cloud)|VPC]]
- since all [[AWS subnet]] are conned by the `local rule` which cant be changed this can be done by sing a [[AWS network access control list (ACL)]]
- example: two subnets `10.130.1.0/24` and `10.130.2.0/24`

-   Create a [[AWS network access control list (ACL)]] for each [[AWS subnet]].
-   For subnet `10.130.1.0/24`:
	1.  Allow all inbound and outbound traffic.
	2.  Add a rule to deny all outbound traffic to `10.130.2.0/24`.
	3.  Similarly, add a rule to deny all inbound traffic from `10.130.2.0/24`.
-   For subnet `10.130.2.0/24`, do the opposite:
	1.  Allow all inbound and outbound traffic.
	2.  Add a rule to deny all outbound traffic to `10.130.1.0/24`.
	3.  Add a rule to deny all inbound traffic from `10.130.1.0/24`.
-   Associate each NACL with its respective subnet.

![[AWS network access control list (ACL)#network access control list]]
# ---------------------

![[ip V4#private an public ip ranges]]

![[AWS route table#route table]]



![[AWS VPC (virtual private cloud)#virtual private cloud]]


# anki

START
Basic
difference and similaritys between private and public [[AWS subnet]]:
- ip adresses
- connectivity
- internet access

Back: 
both are
- connected to all subnets within the [[AWS VPC (virtual private cloud)]] local route

ressources in a public subnet 
- are connected to a [[AWS internet gateway]] (and the default [[AWS route]] is pointing to it)
- have a [[AWS private ip]] and a [[AWS public ip]] (and a [[AWS DNS hostname]] poining to it)
- can load from the internet and expose content to it

ressources in a private subnet
- are not connected to a [[AWS internet gateway]] and thus dont have a [[AWS public ip]]
- can load from the internet if they are connected to a [[AWS Network Address translation (NAT) Gateway]] (default [[AWS route]] to [[AWS Network Address translation (NAT) Gateway|NAT]])
	→ private ip is mapped to a public ip, but it's not 1 to 1 so It's not its own [[AWS public ip]]

### subnet
- range of [[internet protocol (IP)|IP adresses]] in a [[AWS VPC (virtual private cloud)]]
- has a [[AWS route table]] that determines which networks adresses are reachable
- lives in a single [[AWS AZ (isolated datacenter)]]
- ressources (like [[AWS EC2]] instances) are launched into a [[AWS subnet]]
- allways internal [[AWS DNS hostname]] pointing to its [[AWS private ip]]

### subnet route table
- can have a **custom route table** or the (default) [[AWS main route table]] of its [[AWS VPC (virtual private cloud)]]
- every [[AWS route table]] of a [[AWS subnet]] has by default the local rule to all [[AWS subnet|subnets]] within its [[AWS VPC (virtual private cloud)|VPC]] that can't be changes
- based on the entrys in its [[AWS route table]] the a [[AWS subnet]] can be described as 
	- a public subnet
	- a private subnet
	- a isolated subnet
	- a [[VPN]] only subnet

#### public subnet
- direct access to a [[AWS internet gateway]]
- ressource get a [[AWS private ip]] and a [[AWS public ip]] assigned by default
- usually the [[AWS route]] associated with the [[AWS internet gateway]] is the default and all relevate private ranges are covered by more specific [[AWS route|routes]]

##### internet gateway
- virtual [[router]] that connects a [[AWS VPC (virtual private cloud)]] (and [[AWS subnet|subnets]] withing) to the internet
- the following [[AWS route]] in the [[AWS route table]] would connect it to an [[AWS internet gateway]] 

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | `igw-id`    |


#### private subnet
- no connection to a [[AWS internet gateway]]
- ressources inside it only have a [[AWS private ip]] and can only be accessed from inside its [[AWS VPC (virtual private cloud)]]
- can be connected to the internet with a [[AWS Network Address translation (NAT) Gateway]]
- if a private subnet is connected to a [[AWS Network Address translation (NAT) Gateway]] its the default [[AWS route]]

##### NAT Gateway 
- mapps [[AWS private ip]] to [[AWS public ip]] (n to 1)
- can connect a private [[AWS subnet]] to the internet, but only allows outbound traffic because multiple ressources can share the same [[AWS public ip]]
- the following [[AWS route]] in a [[AWS route table]] of a [[AWS subnet]] can connect the ressources over a [[AWS Network Address translation (NAT) Gateway]] to the internet

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | ``nat-gateway-id``    |

- for a bidirectionnal internet connection a [[AWS internet gateway]] is needed


# ---------------------

### private an public ip ranges
- `10.0.0.0/16` (`10.0.0.0`  to `10.255.255.255`)
- `172.16.0.0/16`  (`172.16.0.0` to `172.31.255.255`)
- `192.168.0.0/16` (`192.168.0.0` to `192.168.255.255`)

- everything else is public

### route table
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


### virtual private cloud
- virtual isolated network within a [[AWS]]
- is located insice a [[AWS region]] but spread over multiple [[AWS AZ (isolated datacenter)]]
- has a range of private ips but they can't be used directly without [[AWS subnet|subnets]]
- all [[AWS subnet|subnets]] within a [[AWS VPC (virtual private cloud)]] are connected by default with the `local route` which can't be changed
- has a [[AWS main route table]] that is used for every [[AWS subnet]] without a custom [[AWS route table]]
- can be connected via [[AWS gateway|gateways]] to the 
	- internet ([[AWS internet gateway]] and [[AWS Network Address translation (NAT) Gateway]]) 
	- other [[AWS VPC (virtual private cloud)|VPCs]] and on prem networks ([[AWS virtual private gateway (VPG)]], [[AWS direct connect gateway]], [[AWS transit gateway]])

### IP ranges
- has a range for [[AWS private ip|private ip]] adresses if the general range for private [[internet protocol (IP)|IP]] adresses 
- allowed sizes are between `/16` (65,536 IP addresses) and  `/28` (16 IP addresses)
- within this range [[AWS subnet|subnets]] can be created


Tags: infra
<!--ID: 1727092048914-->
END

START
Basic
[[AWS subnet]]
- concept
- [[AWS public ip]] and [[AWS private ip]] ranges
- relationship to [[AWS VPC (virtual private cloud)]]
- relationship to [[AWS route table]]
- 3 types and how are they implemented

Back: 
### subnet
- range of [[internet protocol (IP)|IP adresses]] in a [[AWS VPC (virtual private cloud)]]
- has a [[AWS route table]] that determines which networks adresses are reachable
- lives in a single [[AWS AZ (isolated datacenter)]]
- ressources (like [[AWS EC2]] instances) are launched into a [[AWS subnet]]
- allways internal [[AWS DNS hostname]] pointing to its [[AWS private ip]]

### subnet route table
- can have a **custom route table** or the (default) [[AWS main route table]] of its [[AWS VPC (virtual private cloud)]]
- every [[AWS route table]] of a [[AWS subnet]] has by default the local rule to all [[AWS subnet|subnets]] within its [[AWS VPC (virtual private cloud)|VPC]] that can't be changes
- based on the entrys in its [[AWS route table]] the a [[AWS subnet]] can be described as 
	- a public subnet
	- a private subnet
	- a isolated subnet
	- a [[VPN]] only subnet

#### public subnet
- direct access to a [[AWS internet gateway]]
- ressource get a [[AWS private ip]] and a [[AWS public ip]] assigned by default
- usually the [[AWS route]] associated with the [[AWS internet gateway]] is the default and all relevate private ranges are covered by more specific [[AWS route|routes]]

##### internet gateway
- virtual [[router]] that connects a [[AWS VPC (virtual private cloud)]] (and [[AWS subnet|subnets]] withing) to the internet
- the following [[AWS route]] in the [[AWS route table]] would connect it to an [[AWS internet gateway]] 

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | `igw-id`    |



#### private subnet
- no connection to a [[AWS internet gateway]]
- ressources inside it only have a [[AWS private ip]] and can only be accessed from inside its [[AWS VPC (virtual private cloud)]]
- can be connected to the internet with a [[AWS Network Address translation (NAT) Gateway]]
- if a private subnet is connected to a [[AWS Network Address translation (NAT) Gateway]] its the default [[AWS route]]

##### NAT Gateway 
- mapps [[AWS private ip]] to [[AWS public ip]] (n to 1)
- can connect a private [[AWS subnet]] to the internet, but only allows outbound traffic because multiple ressources can share the same [[AWS public ip]]
- the following [[AWS route]] in a [[AWS route table]] of a [[AWS subnet]] can connect the ressources over a [[AWS Network Address translation (NAT) Gateway]] to the internet

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | ``nat-gateway-id``    |

- for a bidirectionnal internet connection a [[AWS internet gateway]] is needed


#### isolated subnet 
- has no connection to other [[AWS subnet|subnets]] within its [[AWS VPC (virtual private cloud)|VPC]]
- since all [[AWS subnet]] are conned by the `local rule` which cant be changed this can be done by sing a [[AWS network access control list (ACL)]]
- example: two subnets `10.130.1.0/24` and `10.130.2.0/24`

-   Create a [[AWS network access control list (ACL)]] for each [[AWS subnet]].
-   For subnet `10.130.1.0/24`:
	1.  Allow all inbound and outbound traffic.
	2.  Add a rule to deny all outbound traffic to `10.130.2.0/24`.
	3.  Similarly, add a rule to deny all inbound traffic from `10.130.2.0/24`.
-   For subnet `10.130.2.0/24`, do the opposite:
	1.  Allow all inbound and outbound traffic.
	2.  Add a rule to deny all outbound traffic to `10.130.1.0/24`.
	3.  Add a rule to deny all inbound traffic from `10.130.1.0/24`.
-   Associate each NACL with its respective subnet.

##### network access control list
- allows or denies specific inbound or outbound traffic at the [[AWS subnet]] level.
- per default a [[AWS subnet]] is automatically associated with the default [[AWS network access control list (ACL)]]: allow all traffic to flow in and out of the subnets
# ---------------------

### private an public ip ranges
- `10.0.0.0/16` (`10.0.0.0`  to `10.255.255.255`)
- `172.16.0.0/16`  (`172.16.0.0` to `172.31.255.255`)
- `192.168.0.0/16` (`192.168.0.0` to `192.168.255.255`)

- everything else is public

### route table
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




### virtual private cloud
- virtual isolated network within a [[AWS]]
- is located insice a [[AWS region]] but spread over multiple [[AWS AZ (isolated datacenter)]]
- has a range of private ips but they can't be used directly without [[AWS subnet|subnets]]
- all [[AWS subnet|subnets]] within a [[AWS VPC (virtual private cloud)]] are connected by default with the `local route` which can't be changed
- has a [[AWS main route table]] that is used for every [[AWS subnet]] without a custom [[AWS route table]]
- can be connected via [[AWS gateway|gateways]] to the 
	- internet ([[AWS internet gateway]] and [[AWS Network Address translation (NAT) Gateway]]) 
	- other [[AWS VPC (virtual private cloud)|VPCs]] and on prem networks ([[AWS virtual private gateway (VPG)]], [[AWS direct connect gateway]], [[AWS transit gateway]])

### IP ranges
- has a range for [[AWS private ip|private ip]] adresses if the general range for private [[internet protocol (IP)|IP]] adresses 
- allowed sizes are between `/16` (65,536 IP addresses) and  `/28` (16 IP addresses)
- within this range [[AWS subnet|subnets]] can be created


 
Tags: infra
<!--ID: 1726336375013-->
END