### S3 bucket
- [[AWS]] object storage that lives outside the [[AWS VPC (virtual private cloud)]]
- is connected to a [[AWS VPC (virtual private cloud)]] with a [[AWS VPC endpoint]]
- access is managed by [[AWS identity and access management IAM]]

# -------------

![[AWS VPC endpoint#VPC endpoint]]


# anki

START
Basic
[[AWS S3 bucket]]
- concept
- how to connet it to a [[AWS VPC (virtual private cloud)]] (plus concept)

Back: 
### S3 bucket
- [[AWS]] object storage that lives outside the [[AWS VPC (virtual private cloud)]]
- is connected to a [[AWS VPC (virtual private cloud)]] with a [[AWS VPC endpoint]]
- access is managed by [[AWS identity and access management IAM]]


### VPC endpoint
- ensures private connection to [[AWS]] managed services outside the [[AWS VPC (virtual private cloud)]] like [[AWS S3 bucket]]
- does not require a [[AWS public ip]] to access the services that are usually only accasable over the internet

#### gateway endpoints
- only for [[AWS S3 bucket]] and DynamoDB

#### interace enpoints
- create a service inside a [[AWS VPC (virtual private cloud)]] and make it acceccable to other [[AWS VPC (virtual private cloud)]] by direct [[AWS route]]
Tags: infra
<!--ID: 1727197209050-->
END