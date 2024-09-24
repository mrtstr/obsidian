### VPC Peering
- direct connection between [[AWS VPC (virtual private cloud)]] in the same [[AWS region]] that enables private [[AWS route|routes]] between them

### example
- connecting two [[AWS subnet]] with different [[AWS VPC (virtual private cloud)]] with [[AWS VPC Peering]]

![[two-vpcs-to-two-subnets-one-vpc.png]]

#### VPC A
subnet 1

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC A CIDR` | `Local`  |
| `VPC B CIDR` |   `pcx-aaaabbbb`    |

subnet2

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC A CIDR` | `Local`  |
| `VPC C CIDR` |   `pcx-aaaacccc`    |

#### VPC B

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC B CIDR` | `Local`  |
| `Subnet 1 CIDR`|   `pcx-aaaabbbb`    |

#### VPC C

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC C CIDR` | `Local`  |
| `Subnet 2 CIDR`|   `pcx-aaaacccc`    |



START
Basic
 how to connct two [[AWS subnet]] within one [[AWS VPC (virtual private cloud)]] with different VPCs?
- with [[AWS route table]]

Back: 

### example
- connecting two [[AWS subnet]] with different [[AWS VPC (virtual private cloud)]] with [[AWS VPC Peering]]

![[two-vpcs-to-two-subnets-one-vpc 1.png]]

#### VPC A
subnet 1

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC A CIDR` | `Local`  |
| `VPC B CIDR` |   `pcx-aaaabbbb`    |

subnet2

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC A CIDR` | `Local`  |
| `VPC C CIDR` |   `pcx-aaaacccc`    |

#### VPC B

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC B CIDR` | `Local`  |
| `Subnet 1 CIDR`|   `pcx-aaaabbbb`    |

#### VPC C

| Destination   |      Target      |
| -------- |:-------------:|
| `VPC C CIDR` | `Local`  |
| `Subnet 2 CIDR`|   `pcx-aaaacccc`    |

____________


### VPC Peering
- direct connection between [[AWS VPC (virtual private cloud)]] in the same [[AWS region]] that enables private [[AWS route|routes]] between them

Tags: infra
<!--ID: 1727197209046-->
END