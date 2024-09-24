
## gateways

### internet connection
![[AWS internet gateway#internet gateway]]


![[AWS Network Address translation (NAT) Gateway#NAT Gateway]]

### network connectors
- one of the following gateways is needed to connect an incomming [[AWS direct connect gateway]] or [[AWS site to site VPN]] to a [[AWS VPC (virtual private cloud)]]

![[AWS virtual private gateway (VPG)#Virtual Private Gateway]]

![[AWS transit gateway#transit gateway]]

### network connections
- on prem networks can either be physicly connected or with a [[VPN]] over the internet

![[AWS direct connect gateway#direct connect gateway]]

![[AWS site to site VPN#site to site VPN]]

### direction connection between VPCs

![[AWS VPC Peering#VPC Peering]]

## example connection of multiple networks
![[connectivity-overview.png]]

# anki

START
Basic
[[AWS gateway]] connections between [[AWS VPC (virtual private cloud)]] and on prem networks
- 5 comcepts with difference
- overview diagram
Back: 
### network connectors
- one of the following gateways is needed to connect an incomming [[AWS direct connect gateway]] or [[AWS site to site VPN]] to a [[AWS VPC (virtual private cloud)]]

#### virtual private gateway
- connector for connecting a [[AWS VPC (virtual private cloud)]] to incomming [[AWS site to site VPN]] or [[AWS direct connect gateway]] connections

#### transit gateway
- central hub for connecting multiple [[AWS VPC (virtual private cloud)]] and to incomming [[AWS site to site VPN]] and [[AWS direct connect gateway]] connections

### network connections

#### direct connect gateway
- physicly connects an on premise network with [[AWS VPC (virtual private cloud)]]
- a [[AWS virtual private gateway (VPG)]] or a [[AWS transit gateway]] is needed to connect it to the [[AWS VPC (virtual private cloud)|VPC]] 

#### site to site VPN
- connects an on premise network with [[AWS VPC (virtual private cloud)]] over the internet with a [[VPN]]
- a [[AWS virtual private gateway (VPG)]] or a [[AWS transit gateway]] is needed to connect it to the [[AWS VPC (virtual private cloud)|VPC]] 

### direction connection between VPCs

#### VPC Peering
- direct connection between [[AWS VPC (virtual private cloud)]] in the same [[AWS region]] that enables private [[AWS route|routes]] between them

![[connectivity-overview 1.png]]


Tags: infra
<!--ID: 1727162581620-->
END


START
Basic
simple way for vonnection two [[AWS VPC (virtual private cloud)]] within the same [[AWS region]]
Back: 
#### VPC Peering
- direct connection between [[AWS VPC (virtual private cloud)]] in the same [[AWS region]] that enables private [[AWS route|routes]] between them

Tags: infra
<!--ID: 1727162581624-->
END


START
Basic
how to connect a on prem network with a [[AWS VPC (virtual private cloud)]]
- when its just one incomming conning
- when there are multiple incomming connections
Back: 
### network connectors
- one of the following gateways is needed to connect an incomming [[AWS direct connect gateway]] or [[AWS site to site VPN]] to a [[AWS VPC (virtual private cloud)]]

#### virtual private gateway
- connector for connecting a [[AWS VPC (virtual private cloud)]] to incomming [[AWS site to site VPN]] or [[AWS direct connect gateway]] connections

#### transit gateway
- central hub for connecting multiple [[AWS VPC (virtual private cloud)]] and to incomming [[AWS site to site VPN]] and [[AWS direct connect gateway]] connections

### network connections

#### direct connect gateway
- physicly connects an on premise network with [[AWS VPC (virtual private cloud)]]
- a [[AWS virtual private gateway (VPG)]] or a [[AWS transit gateway]] is needed to connect it to the [[AWS VPC (virtual private cloud)|VPC]] 

#### site to site VPN
- connects an on premise network with [[AWS VPC (virtual private cloud)]] over the internet with a [[VPN]]
- a [[AWS virtual private gateway (VPG)]] or a [[AWS transit gateway]] is needed to connect it to the [[AWS VPC (virtual private cloud)|VPC]] 

Tags: infra
<!--ID: 1727162581627-->
END