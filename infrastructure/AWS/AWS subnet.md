### subnet
- subnet within a [[AWS VPC (virtual private cloud)]]
- has range of [[internet protocol (IP)]] adresses of the [[AWS private ip]] adress range of its [[AWS VPC (virtual private cloud)]]
- lives in an single [[AWS AZ (isolated datacenter)]]
- ressources (like [[AWS EC2]] instances) are launched into a [[AWS subnet]]
- has a [[AWS route table]]


#### public subnet
- direct access to a [[AWS internet gateway]]
- ressource get a [[AWS private ip]] and a [[AWS public ip]] assigned

#### private subnet
- no connection to a [[AWS internet gateway]]
- (private subnet may be in a [[AWS VPC (virtual private cloud)]] with an attached[[AWS internet gateway]] butis not routed to it)
- ressources inside it only have a [[AWS private ip]] and can only be accessed from inside its [[AWS VPC (virtual private cloud)]]
- can be connected to the internet with a [[AWS Network Address translation (NAT) Gateway]]

#### VPN-only subnet


#### isolated subnet 

-  public subnet – direct access to the internet
-  private subnet – no direct access to the internet without [[AWS Network Address translation (NAT) Gateway]]
-   VPN-only subnet – The subnet has a route to a [Site-to-Site VPN connection](https://docs.aws.amazon.com/vpn/latest/s2svpn/) through a virtual private gateway. The subnet does not have a route to an internet gateway.
-   Isolated subnet – The subnet has no routes to destinations outside its VPC. Resources in an isolated subnet can only access or be accessed by other resources in the same VPC.

# ---------------


![[AWS VPC (virtual private cloud)]]


# anki

START
Basic
two network concepts within [[AWS]] with properties (1 + 6)
Back: 

### subnet
- subnet within a [[AWS VPC (virtual private cloud)]]
- range of [[internet protocol (IP)]] adresses
- can be in [[ip V4]], [[ip V6]] or both
- lives in an [[AWS AZ (isolated datacenter)]]

#### subnet types 
-  public subnet – direct access to the internet
-  private subnet – no direct access to the internet without [[AWS Network Address translation (NAT) Gateway]]
-   VPN-only subnet – The subnet has a route to a [Site-to-Site VPN connection](https://docs.aws.amazon.com/vpn/latest/s2svpn/) through a virtual private gateway. The subnet does not have a route to an internet gateway.
-   Isolated subnet – The subnet has no routes to destinations outside its VPC. Resources in an isolated subnet can only access or be accessed by other resources in the same VPC.

## virtual private cloud
- virtual isolated network within a [[AWS]]


 
Tags: infra
<!--ID: 1726336375013-->
END