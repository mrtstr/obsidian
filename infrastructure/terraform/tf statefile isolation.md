## statefile isolation
- each [[tf stages]] (`dev`,  `prod`, `qa`, `global`) [[tf state|statefile]] 
- this can be achived by using [[tf workspace|workspaces]] which is error-prone and not recommended or by file layout

### statefile isolation by layout
- each stage folder has its own configuration file where the folder for the state file is specified
- for example a different location for the same state file in the same [[AWS S3 bucket]] is used or even a completly diffent [[AWS]] account is used

```terraform
terraform {  
  backend "s3" {  
    bucket         = "terraform-up-and-running-state"  
    key            = "<stage>/terraform.tfstate"  
    region         = "us-east-2"    
    dynamodb_table = "terraform-up-and-running-locks"  
    encrypt        = true  
  }  
}
```

# -----------------
![[tf stages#stages]]

![[tf state#state]]


# anki

START
Basic
- how should the statefiles be organized in a [[tf stages|multistage]] infrastructure?
Back: 
## statefile isolation
- each [[tf stages]] (`dev`,  `prod`, `qa`, `global`) [[tf state|statefile]] 
- this can be achived by using [[tf workspace|workspaces]] which is error-prone and not recommended or by file layout

### statefile isolation by layout
- each stage folder has its own configuration file where the folder for the state file is specified
- for example a different location for the same state file in the same [[AWS S3 bucket]] is used or even a completly diffent [[AWS]] account is used

```terraform
terraform {  
  backend "s3" {  
    bucket         = "terraform-up-and-running-state"  
    key            = "<stage>/terraform.tfstate"  
    region         = "us-east-2"    
    dynamodb_table = "terraform-up-and-running-locks"  
    encrypt        = true  
  }  
}
```


----------------------
## state
- record of infrastructure managed by [[terraform]] and its properties
- contains secrets thus should not be in git but in a [[AWS S3 bucket]] that is
	- encrypted
	- has a lock mechanism
	- is versioned to restore it when it breaks

- can be configured with the following ([[tf init]] required)
- the `key` contains the path where the state should be stored 
```terraform
terraform {  
  backend "s3" {  
    # Replace this with your bucket name!  
    bucket         = "terraform-up-and-running-state"  
    key            = "global/s3/terraform.tfstate"  
    region         = "us-east-2"    
    dynamodb_table = "terraform-up-and-running-locks"  
    encrypt        = true  
  }  
}
```

Tags: infra
<!--ID: 1726414593784-->
END