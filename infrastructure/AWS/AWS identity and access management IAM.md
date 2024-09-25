


## IAM roles
- roles are a set of permissions (**permission policy**) an entity (e.g. [[AWS user]]) can take on terporary to perform certain actions
- don't have a password and provide temporary security credentials to whomever has the ability to assume that role (**turst policy**)

### trust policy
- entitys that can assume the IAM role
- add the [[AWS amazon ressource name (ARN)]] of the [[AWS user]] that should be able to assube the role

```bash
{
"Version": "2012-10-17",
"Statement": [
 {
  "Sid": "Statement1",
  "Effect": "Allow",
  "Principal": {
      "AWS": "arn:aws:iam::xxxxxxxxxxx:user/omkar"
  },
  "Action": "sts:AssumeRole"
 }
]
}
```

### permission policy
- What does the role allow once you assume it


### swiching profiles
- the currently selected role is saved under `~/.aws/config`
- `source_profile` are the credentials to assume the role

```bash
[profile rdsadmin]
   role_arn = arn:aws:iam::123456789012:role/AWSIAMRoleForRDS
   source_profile = default
```
# ----------------------


![[AWS amazon ressource name (ARN)#amazon ressource name]]

![[AWS user]]

# anki


START
Basic
[[AWS identity and access management IAM]] roles
- concept and 2 importent attributes
- where is the selected role saved?

Back: 
## IAM roles
- roles are a set of permissions (**permission policy**) an entity (e.g. [[AWS user]]) can take on terporary to perform certain actions
- don't have a password and provide temporary security credentials to whomever has the ability to assume that role (**turst policy**)

### trust policy
- entitys that can assume the IAM role
- add the [[AWS amazon ressource name (ARN)]] of the [[AWS user]] that should be able to assube the role

```bash
{
"Version": "2012-10-17",
"Statement": [
 {
  "Sid": "Statement1",
  "Effect": "Allow",
  "Principal": {
      "AWS": "arn:aws:iam::xxxxxxxxxxx:user/omkar"
  },
  "Action": "sts:AssumeRole"
 }
]
}
```

### permission policy
- What does the role allow once you assume it


### swiching profiles
- the currently selected role is saved under `~/.aws/config`
- `source_profile` are the credentials to assume the role

```bash
[profile rdsadmin]
   role_arn = arn:aws:iam::123456789012:role/AWSIAMRoleForRDS
   source_profile = default
```

__________

### amazon ressource name
- uniquely identifies [[AWS]] resources
- ressources can be [[AWS S3 bucket]], [[AWS EC2]], [[AWS ECS service]], [[AWS user]] ...

```
arn:partition:service:region:account-id:resource-type:resource-id
```

- wildcards are possible
```
arn:partition:service:region:account-id:resource-type:*
```

Tags: infra
<!--ID: 1727268499955-->
END