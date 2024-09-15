## variables
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
- secrets dont have a default value and always have to be defined in [[li environment variables]]
```bash
export TF_VAR_db_username="(YOUR_DB_USERNAME)"  
export TF_VAR_db_password="(YOUR_DB_PASSWORD)"
```

```terraform
variable "db_username" {  
  description = "The username for the database"  
  type        = string  
  sensitive   = true  
}  
  
variable "db_password" {  
  description = "The password for the database"  
  type        = string  
  sensitive   = true  
}
```


# anki

START
Basic
[[tf variables]] in [[terraform]]
- how are they used and how are secrets managed?

Back: 
## variables
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
- secrets dont have a default value and always have to be defined in [[li environment variables]]
```bash
export TF_VAR_db_username="(YOUR_DB_USERNAME)"  
export TF_VAR_db_password="(YOUR_DB_PASSWORD)"
```

```terraform
variable "db_username" {  
  description = "The username for the database"  
  type        = string  
  sensitive   = true  
}  
  
variable "db_password" {  
  description = "The password for the database"  
  type        = string  
  sensitive   = true  
}
```
Tags: infra
<!--ID: 1726414593780-->
END