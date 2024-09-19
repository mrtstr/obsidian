
## EC2
- virtual machine

### properties
- create from [[AWS Amazon Machine Image (AMI)]]
- user data: script that executed when the instance is started
- `instance_type`: machine type
- [[AWS Security Group]] for network access
- [[AWS subnet]] to launch in
- `key name` for a [[AWS EC2 key pairs]] for setting up [[secure shell protocol (SSH)]] access


### file system
- no data persitence without persistent data storage
	- [[AWS elastic file system EFS]]: multiple instances can use it
	- [[AWS Elastic Block Store (EBS)]]: only one instance can use it


# anki

START
Basic
[[AWS EC2]]
- concept
- properties (6)
- persistent storage option (2)
Back: 
## EC2
- virtual machine

### properties
- create from [[AWS Amazon Machine Image (AMI)]]
- user data: script that executed when the instance is started
- `instance_type`: machine type
- [[AWS Security Group]] for network access
- [[AWS subnet]] to launch in
- `key name` for a [[AWS EC2 key pairs]] for setting up [[secure shell protocol (SSH)]] access


### file system
- no data persitence without persistent data storage
	- [[AWS elastic file system EFS]]: multiple instances can use it
	- [[AWS Elastic Block Store (EBS)]]: only one instance can use it


Tags: infra
<!--ID: 1726750986434-->
END