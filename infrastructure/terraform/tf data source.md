### data source
- data source represents a piece of read-only information that is fetched from the provider (e.g. [[AWS]])
- used for looking up [[AWS VPC (virtual private cloud)]], [[AWS subnet]], [[AWS Amazon Machine Image (AMI)]] ids or [[internet protocol (IP)]] adress ranges
- makes pre-existing infrastructure ressources usable in [[terraform]] code without importing them

```
data "<PROVIDER>_<TYPE>" "<NAME>" {  
  [CONFIG ...]  
}
```

e.g. [[AWS VPC (virtual private cloud)]]

```
data "aws_vpc" "default" {  
  default = true  
}

# accesed with 
data.aws_vpc.default.id
```

e.g. [[AWS subnet]]
```
data "aws_subnets" "default" {  
  filter {  
    name   = "vpc-id"  
    values = [data.aws_vpc.default.id]  
  }  
}
```


# anki

START
Basic
- how to use [[AWS VPC (virtual private cloud)]] [[AWS subnet]] in [[terraform]] code

Back: 
they could be imported but its better maintainable to use [[tf data source]]

### data source
- data source represents a piece of read-only information that is fetched from the provider (e.g. [[AWS]])
- used for looking up [[AWS VPC (virtual private cloud)]], [[AWS subnet]], [[AWS Amazon Machine Image (AMI)]] ids or [[internet protocol (IP)]] adress ranges
- makes pre-existing infrastructure ressources usable in [[terraform]] code without importing them

```
data "<PROVIDER>_<TYPE>" "<NAME>" {  
  [CONFIG ...]  
}
```

e.g. [[AWS VPC (virtual private cloud)]]

```
data "aws_vpc" "default" {  
  default = true  
}

# accesed with 
data.aws_vpc.default.id
```

e.g. [[AWS subnet]]
```
data "aws_subnets" "default" {  
  filter {  
    name   = "vpc-id"  
    values = [data.aws_vpc.default.id]  
  }  
}
```

Tags: infra
<!--ID: 1726336374995-->
END