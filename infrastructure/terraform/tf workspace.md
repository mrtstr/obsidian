## workspace
- after running `terraform init` a backend config (e.g. [[tf state|statefile]] storage) is created
- multiple workspaces can be used to swich between [[tf stages]] that have their own stagefile
- create a new [[tf workspace]]: `terraform workspace new workspacename`
- `terraform workspace list`
- `terraform workspace select example1`
- information about the workspaces is stored in the `.env` folder in the backend storage

#### using 
- can be accesed as a variable with `terraform.workspace`
- example: selected a different machine type for different workspaces:
```terraform
resource "aws_instance" "example" {  
  ami           = "ami-0fb653ca2d3203ac1"  
  instance_type = (  
    terraform.workspace == "default" ? "t2.medium" : "t2.micro"  
  )  
}
```