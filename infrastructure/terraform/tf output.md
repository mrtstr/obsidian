### output
- make information about your infrastructure (that might not be defined before applying like ip) available on the command line
- expost information to the [[tf state|statefile]]
- optional properties: `description`, `sensitive`, and `depends_on`

```terraform
output "instance_ip_addr" {
  value = aws_instance.server.private_ip
}
```


# anki

START
Basic
[[tf output]] in [[terraform]]
- concept and difference to [[tf variables]]
Back: 
### output
- make information about your infrastructure (that might not be defined before applying like ip) available on the command line
- expost information to the [[tf state|statefile]]
- optional properties: `description`, `sensitive`, and `depends_on`

```terraform
output "instance_ip_addr" {
  value = aws_instance.server.private_ip
}
```

### variables
- make [[terraform]] [[tf module]] customizable and reusable
```terraform
variable "image_id" {
  type = string
}

variable "availability_zone_names" {
  type    = list(string)
  default = ["us-west-1a"]
}

variable "port" {  
  description = "..."  
  type        = int   
  default     = 8080
}
```

- the default value can be overwritten by [[li environment variables]]: e.g. `TF_VAR_port=8081 `

Tags: infra
<!--ID: 1726414593770-->
END