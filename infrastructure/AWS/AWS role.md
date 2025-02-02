### AWS role
- consists of a **trust policy** (who can take this role) and a **permission policy** (what is someone with this [[AWS role]] allowed to do)
- can be assumed with [[AWS STS (security token service)]] in a special kind of [[AWS session]]

#### trust policy
- defines the rule who can take on the role
- two basic ways for authentication: based on current identity or based on [[AWS JWT (json web token)]] for a trusted external identity provider
##### role that can be assumed based on permissions
- roles can be assumed based on the permissions of a [[AWS iam user]] or the currently assumes [[AWS role]] (and here an additional secret)

```
resource "aws_iam_role" "role_hardcoded_toke" {
  name               = "MyAssumeRole"
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      # works only for test aws account but not for dsf account
      {
        Effect = "Allow"
        Action = "sts:AssumeRole"
        Principal = { "AWS" : "<iam arn>" }
        Condition = {
          StringEquals = {
            "sts:ExternalId" = "hardcoded-token1"
          }
        }
      }
    ]
  })
}
```

##### role that can be assumed based on web token
- example role that can be assumed based on a [[AWS JWT (json web token)]]
- here in the case a OIDC from kubernetes
```
resource "aws_iam_role" "k8s_assume_role" {
  name               = "K8sAssumeRole"
  # assume_role_policy: who can assume the role: Example: access to role with OIDC from kubernetes
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect = "Allow"
        Principal = {
          Federated = "arn:aws:iam::<Kubernetes-Cluster-AWS-Account-ID>:oidc-provider/<OIDC-Provider>"
        }
        Action = "sts:AssumeRoleWithWebIdentity"
        Condition = {
          StringEquals = {
            "<OIDC-Provider>:sub" = "system:serviceaccount:<namespace>:<service-account-name>"
            
          }
        }
      }
    ]
  })
}
```

#### permission policy
- what is someone with the role allowed to do or access

##### grant role S3 access
- create the policy to access the [[AWS S3 bucket]]
```terraform
data "aws_iam_policy_document" "s3_access" {
  statement {
    effect = "Allow"
    # actions   = ["ec2:Describe*"]
    actions = [
      "s3:GetObject",
      "s3:ListBucket",
      "s3:PutObject"
    ]
    resources = [
      "arn:aws:s3:::${my_bucket.id}",
      "arn:aws:s3:::${my_bucket.id}/*"
    ]
  }
}

resource "aws_iam_policy" "s3_access" {
  name   = "${local.namespace_name}-s3-access-policy"
  policy = data.aws_iam_policy_document.s3_access.json
}
```
- attach the policy to a [[AWS role]]
```terraform
resource "aws_iam_role_policy_attachment" "s3_access" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.s3_access.arn
}

```

##### grant role access to secrets under path prefix
```terraform
## grant role access to secrets
data "aws_iam_policy_document" "sm_access" {
  statement {
    effect = "Allow"
    actions = [
      "secretsmanager:GetSecretValue",
      "secretsmanager:DescribeSecret"
    ]

    resources = [
"arn:aws:secretsmanager:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:secret:${var.project_name}/*",
"arn:aws:secretsmanager:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:secret:common/*",
    ]
  }
}


resource "aws_iam_policy" "sm_access" {
  name   = "${local.namespace_name}-sm-access-policy"
  policy = data.aws_iam_policy_document.sm_access.json
}

```

```
resource "aws_iam_role_policy_attachment" "sm_access" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.sm_access.arn
}
```

##### grant role access to the [[AWS ECR]]
- first allow the [[AWS role]] to authenticate with the [[AWS ECR]]
```
data "aws_iam_policy_document" "ecr_access_token" {
  statement {
    effect = "Allow"
    actions = [
      "ecr:GetAuthorizationToken", # Allow getting auth token for Docker login
    ]
    resources = ["*"]
  }
}

resource "aws_iam_policy" "ecr_access_token" {
  name   = "${local.namespace_name}-ecr-access-token-policy"
  policy = data.aws_iam_policy_document.ecr_access_token.json
}

resource "aws_iam_role_policy_attachment" "ecr_access_token" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.ecr_access_token.arn
}

```

- grant the [[AWS role]] access to the [[AWS ECR]] by creating the role and attaching the policy to the [[AWS role]]
```
data "aws_iam_policy_document" "ecr_access" {
  statement {
    effect = "Allow"
    actions = [
      "ecr:BatchCheckLayerAvailability",
      "ecr:BatchGetImage",
      "ecr:PutImage",            # Allow pushing an image to the repository
      "ecr:InitiateLayerUpload", # Allow initiating layer uploads
      "ecr:UploadLayerPart",     # Allow uploading layer parts
      "ecr:CompleteLayerUpload", # Allow completing the layer upload
    ]

    resources = [
      "arn:aws:ecr:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:repository/${var.project_name}/*",
      "arn:aws:ecr:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:repository/common/*",
    ]
  }
}



resource "aws_iam_policy" "ecr_access" {
  name   = "${local.namespace_name}-ecr-access-policy"
  policy = data.aws_iam_policy_document.ecr_access.json
}

resource "aws_iam_role_policy_attachment" "ecr_access" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.ecr_access.arn

}
```
# ------------------
![[AWS JWT (json web token)#AWS JWT (json web token)]]

![[AWS STS (security token service)#AWS STS (security token service)]]


# anki

START
Basic
[[AWS role]]
- concept
- trust policy: what is it and two different kinds
- relationship to [[AWS session]] and [[AWS STS (security token service)]] and [[AWS JWT (json web token)]]


Back: 
### AWS role
- consists of a **trust policy** (who can take this role) and a **permission policy** (what is someone with this [[AWS role]] allowed to do)
- can be assumed with [[AWS STS (security token service)]] in a special kind of [[AWS session]]

#### trust policy
- defines the rule who can take on the role
- two basic ways for authentication: based on current identity or based on [[AWS JWT (json web token)]] for a trusted external identity provider
##### role that can be assumed based on permissions
- roles can be assumed based on the permissions of a [[AWS iam user]] or the currently assumes [[AWS role]] (and here an additional secret)

```
resource "aws_iam_role" "role_hardcoded_toke" {
  name               = "MyAssumeRole"
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      # works only for test aws account but not for dsf account
      {
        Effect = "Allow"
        Action = "sts:AssumeRole"
        Principal = { "AWS" : "<iam arn>" }
        Condition = {
          StringEquals = {
            "sts:ExternalId" = "hardcoded-token1"
          }
        }
      }
    ]
  })
}
```

##### role that can be assumed based on web token
- example role that can be assumed based on a [[AWS JWT (json web token)]]
- here in the case a OIDC from kubernetes
```
resource "aws_iam_role" "k8s_assume_role" {
  name               = "K8sAssumeRole"
  # assume_role_policy: who can assume the role: Example: access to role with OIDC from kubernetes
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect = "Allow"
        Principal = {
          Federated = "arn:aws:iam::<Kubernetes-Cluster-AWS-Account-ID>:oidc-provider/<OIDC-Provider>"
        }
        Action = "sts:AssumeRoleWithWebIdentity"
        Condition = {
          StringEquals = {
            "<OIDC-Provider>:sub" = "system:serviceaccount:<namespace>:<service-account-name>"
            
          }
        }
      }
    ]
  })
}
```

#### permission policy
- what is someone with the role allowed to do or access

##### grant role S3 access
- create the policy to access the [[AWS S3 bucket]]
```terraform
data "aws_iam_policy_document" "s3_access" {
  statement {
    effect = "Allow"
    # actions   = ["ec2:Describe*"]
    actions = [
      "s3:GetObject",
      "s3:ListBucket",
      "s3:PutObject"
    ]
    resources = [
      "arn:aws:s3:::${my_bucket.id}",
      "arn:aws:s3:::${my_bucket.id}/*"
    ]
  }
}

resource "aws_iam_policy" "s3_access" {
  name   = "${local.namespace_name}-s3-access-policy"
  policy = data.aws_iam_policy_document.s3_access.json
}
```
- attach the policy to a [[AWS role]]
```terraform
resource "aws_iam_role_policy_attachment" "s3_access" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.s3_access.arn
}

```

##### grant role access to secrets under path prefix
```terraform
## grant role access to secrets
data "aws_iam_policy_document" "sm_access" {
  statement {
    effect = "Allow"
    actions = [
      "secretsmanager:GetSecretValue",
      "secretsmanager:DescribeSecret"
    ]

    resources = [
"arn:aws:secretsmanager:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:secret:${var.project_name}/*",
"arn:aws:secretsmanager:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:secret:common/*",
    ]
  }
}


resource "aws_iam_policy" "sm_access" {
  name   = "${local.namespace_name}-sm-access-policy"
  policy = data.aws_iam_policy_document.sm_access.json
}

```

```
resource "aws_iam_role_policy_attachment" "sm_access" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.sm_access.arn
}
```

##### grant role access to the [[AWS ECR]]
- first allow the [[AWS role]] to authenticate with the [[AWS ECR]]
```
data "aws_iam_policy_document" "ecr_access_token" {
  statement {
    effect = "Allow"
    actions = [
      "ecr:GetAuthorizationToken", # Allow getting auth token for Docker login
    ]
    resources = ["*"]
  }
}

resource "aws_iam_policy" "ecr_access_token" {
  name   = "${local.namespace_name}-ecr-access-token-policy"
  policy = data.aws_iam_policy_document.ecr_access_token.json
}

resource "aws_iam_role_policy_attachment" "ecr_access_token" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.ecr_access_token.arn
}

```

- grant the [[AWS role]] access to the [[AWS ECR]] by creating the role and attaching the policy to the [[AWS role]]
```
data "aws_iam_policy_document" "ecr_access" {
  statement {
    effect = "Allow"
    actions = [
      "ecr:BatchCheckLayerAvailability",
      "ecr:BatchGetImage",
      "ecr:PutImage",            # Allow pushing an image to the repository
      "ecr:InitiateLayerUpload", # Allow initiating layer uploads
      "ecr:UploadLayerPart",     # Allow uploading layer parts
      "ecr:CompleteLayerUpload", # Allow completing the layer upload
    ]

    resources = [
      "arn:aws:ecr:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:repository/${var.project_name}/*",
      "arn:aws:ecr:${[data.aws_region.current.name](http://data.aws_region.current.name)}:*:repository/common/*",
    ]
  }
}



resource "aws_iam_policy" "ecr_access" {
  name   = "${local.namespace_name}-ecr-access-policy"
  policy = data.aws_iam_policy_document.ecr_access.json
}

resource "aws_iam_role_policy_attachment" "ecr_access" {
  role       = [aws_iam_role.k8s_assume_role.name](http://aws_iam_role.k8s_assume_role.name)
  policy_arn = aws_iam_policy.ecr_access.arn

}
```
Tags: infra AWS

END
