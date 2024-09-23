### default route
- [[AWS subnet|subnets]] usually have a default [[AWS route]] in its [[AWS route table]] that is convering all [[internet protocol (IP)|ip adresses]] 
- its usually routed to a [[AWS internet gateway]] or a [[AWS Network Address translation (NAT) Gateway]]
- since this rule is the most general it have the least priority and is over ruled by all more specific [[AWS private ip]] ranges

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | `<igw-id>`    |


# ----------------

![[AWS route table#route table]]