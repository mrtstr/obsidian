
## aws network summary
### VPCs and subnet routing
- a [[AWS VPC (virtual private cloud)]] has a [[AWS private ip]] range block (e.g. `10.1.0.0/16`)
- the CIDR of a [[AWS VPC (virtual private cloud)|VPC]] is further devided in [[AWS subnet]] (e.g `10.1.1/24`)
- the [[AWS route|routes]] between [[AWS subnet|subnets]] and [[AWS gateway|gateways]] are defined in [[AWS route table|route tables]] of subnets
- within a [[AWS VPC (virtual private cloud)|VPC]] all [[AWS subnet|subnets]] are generally connected with the non changebal [[AWS local route]] but the connections between [[AWS subnet|subnets]] can be restricted with [[AWS network access control list (ACL)]]
- a [[AWS subnet]] can be connected to the internet by a [[AWS internet gateway]] (complete access with [[AWS public ip]]) or with a [[AWS Network Address translation (NAT) Gateway]] (outgoing traffic only) as a [[AWS default route|default route]]

### contolling network access
- the network access can be allowed and limited 
	- with [[AWS Security Group]] on ressource/instance level
	- with [[AWS network access control list (ACL)]] on [[AWS subnet]] level
- [[AWS Security Group]] default is to block everything → ingress and egress rules are needed to allow communication with a ressource
- [[AWS network access control list (ACL)]] default behavour is to allow everything but traffic flow can be resticted

### connecting networks
- two [[AWS VPC (virtual private cloud)]] in the same [[AWS region]] can be directly connected with a [[AWS VPC Peering]]
- on prem networks can be connected to [[AWS VPC (virtual private cloud)]] over the internet with a [[AWS site to site VPN]] or physicly with a [[AWS direct connect gateway]]
- to connect a incomming conntion to a [[AWS VPC (virtual private cloud)]] a [[AWS virtual private gateway (VPG)]] or a [[AWS transit gateway]] is needed
	- [[AWS transit gateway]] is a hub like structure for connection multiple incomming connections and VPCs



# anki

START
Basic
summary [[AWS network]]
- VPCs and subnet routing (5)
- contolling network access (2)
- connecting networks (5)

Back: 
## aws network summary
### VPCs and subnet routing
- a [[AWS VPC (virtual private cloud)]] has a [[AWS private ip]] range block (e.g. `10.1.0.0/16`)
- the CIDR of a [[AWS VPC (virtual private cloud)|VPC]] is further devided in [[AWS subnet]] (e.g `10.1.1/24`)
- the [[AWS route|routes]] between [[AWS subnet|subnets]] and [[AWS gateway|gateways]] are defined in [[AWS route table|route tables]] of subnets
- within a [[AWS VPC (virtual private cloud)|VPC]] all [[AWS subnet|subnets]] are generally connected with the non changebal [[AWS local route]] but the connections between [[AWS subnet|subnets]] can be restricted with [[AWS network access control list (ACL)]]
- a [[AWS subnet]] can be connected to the internet by a [[AWS internet gateway]] (complete access with [[AWS public ip]]) or with a [[AWS Network Address translation (NAT) Gateway]] (outgoing traffic only) as a [[AWS default route|default route]]

### contolling network access
- the network access can be allowed and limited 
	- with [[AWS Security Group]] on ressource/instance level
	- with [[AWS network access control list (ACL)]] on [[AWS subnet]] level
- [[AWS Security Group]] default is to block everything → ingress and egress rules are needed to allow communication with a ressource
- [[AWS network access control list (ACL)]] default behavour is to allow everything but traffic flow can be resticted

### connecting networks
- two [[AWS VPC (virtual private cloud)]] in the same [[AWS region]] can be directly connected with a [[AWS VPC Peering]]
- on prem networks can be connected to [[AWS VPC (virtual private cloud)]] over the internet with a [[AWS site to site VPN]] or physicly with a [[AWS direct connect gateway]]
- to connect a incomming conntion to a [[AWS VPC (virtual private cloud)]] a [[AWS virtual private gateway (VPG)]] or a [[AWS transit gateway]] is needed
	- [[AWS transit gateway]] is a hub like structure for connection multiple incomming connections and VPCs
Tags: infra
<!--ID: 1727164002836-->
END