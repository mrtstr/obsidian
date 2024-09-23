### internet gateway
- virtual [[router]] that connects a [[AWS VPC (virtual private cloud)]] (and [[AWS subnet|subnets]] withing) to the internet
- the following [[AWS route]] in the [[AWS route table]] would connect it to an [[AWS internet gateway]] 

| Destination    | Target |
| -------- | ------- |
| `0.0.0.0/0`  | `igw-id`    |
