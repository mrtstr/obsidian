### terraform remote state
- [[tf output]] values are saved in the [[tf state|statefile]] and can be read using the following syntax

```terraform
data.terraform_remote_state.<NAME>.outputs.<ATTRIBUTE>
```


### example
```terraform
output "address" {  
  value       = aws_db_instance.example.address  
  description = "Connect to the database at this endpoint"  
}  
  
output "port" {  
  value       = aws_db_instance.example.port  
  description = "The port the database is listening on"  
}
```


```
user_data = <<EOF  
#!/bin/bash  
echo "Hello, World" >> index.html  
echo "${data.terraform_remote_state.db.outputs.address}">>index.html  
echo "${data.terraform_remote_state.db.outputs.port}">>index.html  
nohup busybox httpd -f -p ${var.server_port} &  
EOF
```


# anki

START
Basic
how to save and retriev variables from the remote [[tf state]] in [[terraform]]?
Back: 
### terraform remote state
- [[tf output]] values are saved in the [[tf state|statefile]] and can be read using the following syntax

```terraform
data.terraform_remote_state.<NAME>.outputs.<ATTRIBUTE>
```


### example
```terraform
output "address" {  
  value       = aws_db_instance.example.address  
  description = "Connect to the database at this endpoint"  
}  
  
output "port" {  
  value       = aws_db_instance.example.port  
  description = "The port the database is listening on"  
}
```


```
user_data = <<EOF  
#!/bin/bash  
echo "Hello, World" >> index.html  
echo "${data.terraform_remote_state.db.outputs.address}">>index.html  
echo "${data.terraform_remote_state.db.outputs.port}">>index.html  
nohup busybox httpd -f -p ${var.server_port} &  
EOF
```
Tags: infra
<!--ID: 1726414593775-->
END