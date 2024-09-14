- visualizes the dependencies between resources
- e.g of the [[AWS EC2]] instance is assigned to a [[AWS Security Group]] then there existes a dependency from the [[AWS EC2]] to the [[AWS Security Group]] thus the [[AWS Security Group]] has to be created first

can be visualized with the following command and plotted on https://dreampuf.github.io/GraphvizOnline

```
terraform graph
```