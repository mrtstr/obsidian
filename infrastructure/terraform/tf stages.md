## stages
- first build [[tf module|modules]] for projects (the project `main.tf` file can contain submodules)
- create a folder for every stage (e.g. dev, qa, prod) and maybe one global folder
- then import a parameterized version in each stage it should be deployed to

![[stages.jpg]]

# ----------------
![[tf module#module]]

![[tf module#importing of modules]]


# anki

START
Basic
- how to organize a multi stage infrastructure in [[terraform]]?
Back: 
## stages
- first build [[tf module|modules]] for projects (the project `main.tf` file can contain submodules)
- create a folder for every stage (e.g. dev, qa, prod) and maybe one global folder
- then import a parameterized version in each stage it should be deployed to

![[stages 1.jpg]]


### module
- set of Terraform configuration files in a single directory
- the `root module` is the folder where the [[terraform]] command is run
- the code has to be written like `name = "${var.var1}-alb"` in the code and will be replaced with the values when importing 

### importing of modules
- [[tf module|modules]] can be imported and parameterized using the following syntax
- everytime a module is created of the source path is changed `terraform init` has to be called

```terraform
module "<NAME>" {  
  source = "<SOURCE>"  
  
  [CONFIG ...]  
}
```

```terraform
provider "aws" {  
  region = "us-east-2"  
}  
  
module "webserver_cluster" {  
  source = "../../../modules/services/webserver-cluster"
  var1 = "val1"
  var2 = "val2"
}
```

Tags: infra
<!--ID: 1726414593790-->
END