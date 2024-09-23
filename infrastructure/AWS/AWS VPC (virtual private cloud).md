## virtual private cloud
- virtual isolated network within a [[AWS]]
- is located insice a [[AWS region]] but spread over multiple [[AWS AZ (isolated datacenter)]]
- has a range of private ips but they can't be used directly without [[AWS subnet|subnets]]
- all [[AWS subnet|subnets]] within a [[AWS VPC (virtual private cloud)]] are connected by default with the `local route` which can't be changed
- has a [[AWS main route table]] that is used for every [[AWS subnet]] without a custom [[AWS route table]]
- can be connected via [[AWS gateway|gateways]] to the 
	- internet ([[AWS internet gateway]] and [[AWS Network Address translation (NAT) Gateway]]) 
	- other [[AWS VPC (virtual private cloud)|VPCs]] and on prem networks ([[AWS virtual private gateway (VPG)]], [[AWS direct connect gateway]], [[AWS transit gateway]])

### IP ranges
- has a range for [[AWS private ip|private ip]] adresses if the general range for private [[internet protocol (IP)|IP]] adresses 
- allowed sizes are between `/16` (65,536 IP addresses) and  `/28` (16 IP addresses)
- within this range [[AWS subnet|subnets]] can be created



![[how-it-works.png]]

# -------------------------


![[ip V4#private an public ip ranges]]

![[AWS main route table#main route table]]