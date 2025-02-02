### AWS STS (security token service)
- [[AWS]] service for providing credentials for a temporary credentials
- credentials are valid for a [[AWS session]]
- can be used for assuming a [[AWS role]] with the two base operations `sts:assume-role` and `sts:assume-role-with-web-identity`
#### check current identity
- check current identity including [[AWS iam user]], assumed [[AWS role]] and [[AWS session]]

```
aws sts get-caller-identity
```

```
import boto3
boto3.client('sts').get_caller_identity()
```

#### assume role
- roles can be assumed based on the permissions of a [[AWS iam user]] or the currently assumes [[AWS role]]

##### assume role with the aws cli
```bash
ASSUME_ROLE_OUTPUT=$(aws sts assume-role \
    --role-arn arn:aws:iam::481665083794:role/K8sAssumeRole \
    --role-session-name example-session \
    --external-id hardcoded-token1)

export AWS_ACCESS_KEY_ID=$(echo $ASSUME_ROLE_OUTPUT | jq -r '.Credentials.AccessKeyId')

export AWS_SECRET_ACCESS_KEY=$(echo $ASSUME_ROLE_OUTPUT | jq -r '.Credentials.SecretAccessKey')

export AWS_SESSION_TOKEN=$(echo $ASSUME_ROLE_OUTPUT | jq -r '.Credentials.SessionToken')

# reset
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_SESSION_TOKEN=""
```

##### assume role with the boto
```
import boto3
role_arn = "arn:aws:iam::481665083794:role/<role name>"
sts_client = boto3.client('sts')
response = sts_client.assume_role(
    RoleArn=role_arn,
    RoleSessionName='example-session',
    ExternalId='hardcoded-token1'
)
credentials = response['Credentials']
session = boto3.Session(
    aws_access_key_id=credentials['AccessKeyId'],
    aws_secret_access_key=credentials['SecretAccessKey'],
    aws_session_token=credentials['SessionToken']
)
```


![[AWS role#role that can be assumed based on permissions]]

#### assume role with identity provider
- external identity providers have to be registered 
- then [[AWS JWT (json web token)]] generated from them are accepted for authentication (for example for assuming a [[AWS role]])

##### register a k8 oidc identity provider
```terraform
resource "aws_iam_openid_connect_provider" "eks_oidc_provider" {
  url = [https://oidc.eks.eu-central-1.amazonaws.com/id/14187A24BB02EE90F1221E2B321D1728]
  # Thumbprint for the OIDC URL (use the actual thumbprint)
  thumbprint_list = ["E0E26D9ED4D7.."] 

  client_id_list = ["[sts.amazonaws.com](http://sts.amazonaws.com)"]
}
```

##### assume role with the boto
```
import boto3
web_identity_token = "eyJhbGc..."
role_arn = "arn:aws:iam::481665083794:role/K8sAssumeRole"
sts_client = boto3.client('sts')
response = sts_client.assume_role_with_web_identity(
    RoleArn=role_arn,
    RoleSessionName="TestSession",
    WebIdentityToken=web_identity_token
)
credentials = response['Credentials']
session = boto3.Session(
    aws_access_key_id=credentials['AccessKeyId'],
    aws_secret_access_key=credentials['SecretAccessKey'],
    aws_session_token=credentials['SessionToken']
)
```

##### assume role with env vars
- assume a role with env variables based file containing a [[AWS JWT (json web token)]]
- set the following env variables
```bash
AWS_ROLE_ARN=arn:aws:iam::682562199936:role/dynamic-target-stock-dev
AWS_WEB_IDENTITY_TOKEN_FILE=<path to file with token>
AWS_STS_REGIONAL_ENDPOINTS=regional
AWS_DEFAULT_REGION=eu-central-1
AWS_REGION=eu-central-1
```


![[AWS role#role that can be assumed based on web token]]




# -----------------
![[AWS JWT (json web token)#AWS JWT (json web token)]]

![[AWS session#AWS session]]


# anki

START
Basic
[[AWS STS (security token service)]]
- concept
- two ways for authentication plus 3 different ways to use it each

Back: 
### AWS STS (security token service)
- [[AWS]] service for providing credentials for a temporary credentials
- credentials are valid for a [[AWS session]]
- can be used for assuming a [[AWS role]] with the two base operations `sts:assume-role` and `sts:assume-role-with-web-identity`
#### check current identity
- check current identity including [[AWS iam user]], assumed [[AWS role]] and [[AWS session]]

```
aws sts get-caller-identity
```

```
import boto3
boto3.client('sts').get_caller_identity()
```

#### assume role
- roles can be assumed based on the permissions of a [[AWS iam user]] or the currently assumes [[AWS role]]

##### assume role with the aws cli
```bash
ASSUME_ROLE_OUTPUT=$(aws sts assume-role \
    --role-arn arn:aws:iam::481665083794:role/K8sAssumeRole \
    --role-session-name example-session \
    --external-id hardcoded-token1)

export AWS_ACCESS_KEY_ID=$(echo $ASSUME_ROLE_OUTPUT | jq -r '.Credentials.AccessKeyId')

export AWS_SECRET_ACCESS_KEY=$(echo $ASSUME_ROLE_OUTPUT | jq -r '.Credentials.SecretAccessKey')

export AWS_SESSION_TOKEN=$(echo $ASSUME_ROLE_OUTPUT | jq -r '.Credentials.SessionToken')

# reset
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_SESSION_TOKEN=""
```

##### assume role with the boto
```
import boto3
role_arn = "arn:aws:iam::481665083794:role/<role name>"
sts_client = boto3.client('sts')
response = sts_client.assume_role(
    RoleArn=role_arn,
    RoleSessionName='example-session',
    ExternalId='hardcoded-token1'
)
credentials = response['Credentials']
session = boto3.Session(
    aws_access_key_id=credentials['AccessKeyId'],
    aws_secret_access_key=credentials['SecretAccessKey'],
    aws_session_token=credentials['SessionToken']
)
```


#### assume role with identity provider
- external identity providers have to be registered 
- then [[AWS JWT (json web token)]] generated from them are accepted for authentication (for example for assuming a [[AWS role]])

##### register a k8 oidc identity provider
```terraform
resource "aws_iam_openid_connect_provider" "eks_oidc_provider" {
  url = [https://oidc.eks.eu-central-1.amazonaws.com/id/14187A24BB02EE90F1221E2B321D1728]
  # Thumbprint for the OIDC URL (use the actual thumbprint)
  thumbprint_list = ["E0E26D9ED4D7.."] 

  client_id_list = ["[sts.amazonaws.com](http://sts.amazonaws.com)"]
}
```

##### assume role with the boto
```python
import boto3
web_identity_token = "eyJhbGc..."
role_arn = "arn:aws:iam::481665083794:role/K8sAssumeRole"
sts_client = boto3.client('sts')
response = sts_client.assume_role_with_web_identity(
    RoleArn=role_arn,
    RoleSessionName="TestSession",
    WebIdentityToken=web_identity_token
)
credentials = response['Credentials']
session = boto3.Session(
    aws_access_key_id=credentials['AccessKeyId'],
    aws_secret_access_key=credentials['SecretAccessKey'],
    aws_session_token=credentials['SessionToken']
)
```

##### assume role with env vars
- assume a role with env variables based file containing a [[AWS JWT (json web token)]]
- set the following env variables
```bash
export AWS_ROLE_ARN=arn:aws:iam::682562199936:role/dynamic-target-stock-dev
export AWS_WEB_IDENTITY_TOKEN_FILE=<path to file with token>
export AWS_STS_REGIONAL_ENDPOINTS=regional
export AWS_DEFAULT_REGION=eu-central-1
export AWS_REGION=eu-central-1
```



________________________________
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

### AWS JWT (json web token)
- used for authenticating based on a trusted external identity provider 
- used for [[AWS STS (security token service)]] when assuming a role with web token
- encoded json containing information about the issuer the audience and other information

```
import jwt

web_identity_token = "eyJhbGciO..."

jwt.decode(web_identity_token, options={"verify_signature": False})

{'aud': ['[sts.amazonaws.com](http://sts.amazonaws.com)'],
'exp': 1738229015,
'iat': 1738142615,
'iss': '[[https://oidc.eks.eu-central-1.amazonaws.com/id/14187A24BB02EE90F1221E2B321D1728]...
}
```

Tags: infra AWS

END
