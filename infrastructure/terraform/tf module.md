### module
- set of Terraform configuration files in a single directory
- the `root module` is the folder where the [[terraform]] command is run
- the code has to be written like `name = "${var.var1}-alb"` in the code and will be replaced with the values when importing 

### importing of modules
- [[tf module|modules]] can be imported and parameterized using the following syntax
- everytime a module is created of the source path is changed `terraform init` has to be called

```
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

### module naming conventions
- **_variables.tf_:** Input variables
- **_outputs.tf:_** Output variables
- **_main.tf:_** Resources and data sources
- **_providers.tf:_** You may want to put your provider blocks into a _providers.tf_ file so you can see, at a glance, what providers the code talks to and what authentication you’ll have to provide.
- **_main-xxx.tf:_** If the _main.tf_ file is getting really long because it contains a large number of resources, you could break it down into smaller files that group the resources in some logical way: e.g., _main-iam.tf_ could contain all the IAM resources, _main-s3.tf_ could contain all the S3 resources, and so on.

# anki

START
Basic
- how is [[terraform]] code reused?
- [[tf module]] and how do import it (with example)
Back: 
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
<!--ID: 1726414593793-->
END