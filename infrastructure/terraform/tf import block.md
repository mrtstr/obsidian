```
import {
  to = aws_s3_bucket.my_bucket
  id = "ai-solutions-scm-shared-raw"

}

# run terraform plan -generate-config-out=import_bucket_config.tf to generate the to config automaticly

resource "aws_s3_bucket" "my_bucket" {

}
```
imports the properties in the state and declares