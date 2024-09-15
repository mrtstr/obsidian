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

### example setup of a [[AWS S3 bucket]] containing the [[tf state]]
```terraform
resource "aws_s3_bucket" "terraform_state" {  
  bucket = "terraform-up-and-running-state"  
   
  # Prevent accidental deletion of this S3 bucket  
  lifecycle {  
    prevent_destroy = true  
  }  
}

# enable versioning so that a new version is created with each change
resource "aws_s3_bucket_versioning" "enabled" {  
  bucket = aws_s3_bucket.terraform_state.id  
  versioning_configuration {  
    status = "Enabled"  
  }  
}

resource "aws_s3_bucket_server_side_encryption_configuration" "default" {  
  bucket = aws_s3_bucket.terraform_state.id  
  
  rule {  
    apply_server_side_encryption_by_default {  
      sse_algorithm = "AES256"  
    }  
  }  
}

# make it private explicitely
resource "aws_s3_bucket_public_access_block" "public_access" {  
  bucket                  = aws_s3_bucket.terraform_state.id  
  block_public_acls       = true  
  block_public_policy     = true  
  ignore_public_acls      = true  
  restrict_public_buckets = true  
}

# lock machanism
resource "aws_dynamodb_table" "terraform_locks" {  
  name         = "terraform-up-and-running-locks"  
  billing_mode = "PAY_PER_REQUEST"  
  hash_key     = "LockID"  
  
  attribute {  
    name = "LockID"  
    type = "S"  
  }  
}
```