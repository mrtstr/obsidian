### subnet
- subnet within a [[AWS VPC (virtual private cloud)]]
- range of [[internet protocol (IP)]] adresses
- can be in [[ip V4]], [[ip V6]] or both
- lives in an [[AWS AZ (isolated datacenter)]]

#### subnet types 
-  public subnet – direct access to the internet
-  private subnet – no direct access to the internet without [[AWS NATGateway (network address translation)]]
-   VPN-only subnet – The subnet has a route to a [Site-to-Site VPN connection](https://docs.aws.amazon.com/vpn/latest/s2svpn/) through a virtual private gateway. The subnet does not have a route to an internet gateway.
-   Isolated subnet – The subnet has no routes to destinations outside its VPC. Resources in an isolated subnet can only access or be accessed by other resources in the same VPC.

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
-  private subnet – no direct access to the internet without [[AWS NATGateway (network address translation)]]
-   VPN-only subnet – The subnet has a route to a [Site-to-Site VPN connection](https://docs.aws.amazon.com/vpn/latest/s2svpn/) through a virtual private gateway. The subnet does not have a route to an internet gateway.
-   Isolated subnet – The subnet has no routes to destinations outside its VPC. Resources in an isolated subnet can only access or be accessed by other resources in the same VPC.

## virtual private cloud
- virtual isolated network within a [[AWS]]


 
Tags: infra
<!--ID: 1726336375013-->
END