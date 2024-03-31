## network
- group of devices that can comunicate directly with each other
- hirachical devided into subnetworks using[[networkmask|networkmasks]] that are connected over [[router|routers]] and [[gateway|gateways]] (subnetting)
- each [[network]] an adress space with adresses for its nodes and two special adresses

![[network adress#network adress]]

![[broadcast adress#broadcast adress]]

- when a data package with a destination in another [[network]] is sent the [[router]] will use the [[networkmask]] of the known networks in its [[router#routing table|routing table]] to determain to wich [[network]] to send the package
- within a [[network]] the [[host adress]] is used for multiplexing to the right recipient using [[switch|switches]]

![[host adress#host adress]]


### subnetting 
- process where big [[network|networks]] are divided into smaller [[network|subnetworks]] by deviding the adress space
- advantages:
	- more efficinent since less broadcast traffic
	- simpler and thus easier to debug

![[subnet 1.png]]
#### [[ip V4]] subnetting
- in [[ip V4]] the adress space is devided using a [[networkmask]]
![[networkmask#networkmask]]

```
11111111.11111111.11110000.00000000  # networkmask
xxxxxxxx.xxxxxxxx.xxxxxxxx.xxxxxxxx  # ip adress
------------------------------------
xxxxxxxx.xxxxxxxx.xxxx0000.00000000  # network adress
------------------------------------
00000000.00000000.0000xxxx.xxxxxxxx  # host adress
```

#### [[ip V6]] subnetting
- in [[ip V6]] the subnetting is not done by a [[networkmask]]
- its done by defining den length of the [[network adress]] directly
- notation: `<adress>/<length of network adress in bit>`
- e.g a network provider has usually `/32` and home networks can have `/64`

![[ipv6subnetting.png]]

# anki

START
Basic
how are [[network|networks]] devided in subnets?
- difference [[ip V4]] vs [[ip V6]]
Back: 

## subnetting 
- process where big [[network|networks]] are divided into smaller [[network|subnetworks]] by deviding the adress space
- advantages:
	- more efficinent since less broadcast traffic
	- simpler and thus easier to debug

![[subnet 2.png]]

### [[ip V4]] subnetting
- in [[ip V4]] the adress space is devided using a [[networkmask]]
#### networkmask
- Used for secifing blocks/groups of [[internet protocol (IP)]] adresses by deviding the adress space in 
- can devide a [[internet protocol (IP)]] adress into [[network adress]] and [[host adress]]
- property of a [[network|subnet]] that defines its adress space
- the [[network adress]] of a given [[internet protocol (IP)]] adress can calculcated by connection the [[internet protocol (IP)|ip adress]] and the [[networkmask]] with a bitwise and
- consits of $n$ times `1` followed by $32-n$ times `0`
$$
Networkadress = Adress \: \& \: Networkmask
$$
- two notations: `11...110...0` or `/n` 

### [[ip V6]] subnetting
- in [[ip V6]] the subnetting is not done by a [[networkmask]]
- its done by defining den length of the [[network adress]] directly
- notation: `<adress>/<length of network adress in bit>`
- e.g a network provider has usually `/32` and home networks can have `/64`

![[ipv6subnetting 1.png]]
______________________________________

### network adress
- unique identifierer of a [[network|subnet]] in the [[network]]
- allywas the first adress in the adress space of a [[network]]
- if a package is sent to a destination in another [[network|subnet]] the package is first sent to its [[network adress]] where it is multiplexed further
- can be calculated from a [[internet protocol (IP)]] adress and its [[networkmask]]

### host adress
- device’s individual identifier on a [[subnetwork]]
- used for multiplexing within a [[subnetwork]]
- least significant bits of the network nodes [[internet protocol (IP)]] adress

```
11111111.11111111.11110000.00000000  # networkmask
xxxxxxxx.xxxxxxxx.xxxxxxxx.xxxxxxxx  # ip adress
------------------------------------
xxxxxxxx.xxxxxxxx.xxxx0000.00000000  # network adress
------------------------------------
00000000.00000000.0000xxxx.xxxxxxxx  # host adress
```

Tags: code network
<!--ID: 1711734993920-->
END


START
Basic
What are
- [[broadcast adress]]
- [[networkmask]]
- [[network adress]]
- [[host adress]]

How are they related?

Back: 
### broadcast adress
- allways the last adress within a [[network|networks]] adress space
- packages sent to the [[broadcast adress]] will be sent to all nodes within the [[network]]

### networkmask
- Used for secifing blocks/groups of [[internet protocol (IP)]] adresses by deviding the adress space in 
- can devide a [[internet protocol (IP)]] adress into [[network adress]] and [[host adress]]
- property of a [[network|subnet]] that defines its adress space
- the [[network adress]] of a given [[internet protocol (IP)]] adress can calculcated by connection the [[internet protocol (IP)|ip adress]] and the [[networkmask]] with a bitwise and
- consits of $n$ times `1` followed by $32-n$ times `0`
$$
Networkadress = Adress \: \& \: Networkmask
$$
- two notations: `11...110...0` or `/n` 

### network adress
- unique identifierer of a [[network|subnet]] in the [[network]]
- allywas the first adress in the adress space of a [[network]]
- if a package is sent to a destination in another [[network|subnet]] the package is first sent to its [[network adress]] where it is multiplexed further
- can be calculated from a [[internet protocol (IP)]] adress and its [[networkmask]]

### host adress
- device’s individual identifier on a [[subnetwork]]
- used for multiplexing within a [[subnetwork]]
- least significant bits of the network nodes [[internet protocol (IP)]] adress

```
11111111.11111111.11110000.00000000  # networkmask
xxxxxxxx.xxxxxxxx.xxxxxxxx.xxxxxxxx  # ip adress
------------------------------------
xxxxxxxx.xxxxxxxx.xxxx0000.00000000  # network adress
------------------------------------
00000000.00000000.0000xxxx.xxxxxxxx  # host adress
```

Tags: code network
<!--ID: 1711734993925-->
END


START
Basic
What are
[[network]]
- defintion
- special adresses
- how is it devided

Back: 
## network
- group of devices that can comunicate directly with each other
- hirachical devided into subnetworks using[[networkmask|networkmasks]] that are connected over [[router|routers]] and [[gateway|gateways]] (subnetting)
- each [[network]] an adress space with adresses for its nodes and two special adresses

### network adress
- unique identifierer of a [[network|subnet]] in the [[network]]
- allywas the first adress in the adress space of a [[network]]
- if a package is sent to a destination in another [[network|subnet]] the package is first sent to its [[network adress]] where it is multiplexed further
- can be calculated from a [[internet protocol (IP)]] adress and its [[networkmask]]

### broadcast adress
- allways the last adress within a [[network|networks]] adress space
- packages sent to the [[broadcast adress]] will be sent to all nodes within the [[network]]

- when a data package with a destination in another [[network]] is sent the [[router]] will use the [[networkmask]] of the known networks in its [[router#routing table|routing table]] to determain to wich [[network]] to send the package
- within a [[network]] the [[host adress]] is used for multiplexing to the right recipient using [[switch|switches]]

### host adress
- device’s individual identifier on a [[subnetwork]]
- used for multiplexing within a [[subnetwork]]
- least significant bits of the network nodes [[internet protocol (IP)]] adress


## subnetting 
- process where big [[network|networks]] are divided into smaller [[network|subnetworks]] by deviding the adress space
- advantages:
	- more efficinent since less broadcast traffic
	- simpler and thus easier to debug

![[subnetting.png]]

### [[ip V4]] subnetting
- in [[ip V4]] the adress space is devided using a [[networkmask]]
#### networkmask
- used for dividing an [[internet protocol (IP)]] adress in [[network adress]] and [[host adress]]
- property of a [[network|subnet]]
- the [[network adress]] of a given [[internet protocol (IP)]] adress can calculcated by connection the [[internet protocol (IP)|ip adress]] and the [[networkmask]] with a bitwise and
- consits of $n$ times `1` followed by $32-n$ times `0`
$$
Networkadress = Adress \: \& \: Networkmask
$$

### [[ip V6]] subnetting
- in [[ip V6]] the subnetting is not done by a [[networkmask]]
- its done by defining den length of the [[network adress]] directly
- notation: `<adress>/<length of network adress in bit>`
- e.g a network provider has usually `/32` and home networks can have `/64`

![[ipv6subnetting 2.png]]
Tags: code network
<!--ID: 1711738120243-->
END