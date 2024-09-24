
## aws network summary
- a [[AWS VPC (virtual private cloud)]] has a [[AWS private ip]] range block (e.g. `10.1.0.0/16`)
- the CIDR of a [[AWS VPC (virtual private cloud)|VPC]] is further devided in [[AWS subnet]] (e.g `10.1.1/24`)
- the [[AWS route|routes]] between [[AWS subnet|subnets]] and [[AWS gateway|gateways]] are defined in [[AWS route table|route tables]] of subnets
- within a [[AWS VPC (virtual private cloud)|VPC]] all [[AWS subnet|subnets]] are generally connected with the non changebal [[AWS local route]] but the connections between [[AWS subnet|subnets]] can be restricted with [[AWS network access control list (ACL)]]
- a [[AWS subnet]] can be connected to the internet by a [[AWS internet gateway]] (complete access with [[AWS public ip]]) or with a [[AWS Network Address translation (NAT) Gateway]] (outgoing traffic only) as a [[AWS default route|default route]]

# ------------------

![[AWS VPC (virtual private cloud)#virtual private cloud]]

![[AWS subnet#subnet]]

![[AWS Network Address translation (NAT) Gateway]]