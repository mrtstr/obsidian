
## route table
- every [[AWS VPC (virtual private cloud)]] has a implicit [[router]] that is completly managed by [[AWS]] and cant be accesed
- a [[AWS subnet]] is assiciated with a [[AWS route table]] (either expicite with a custom [[AWS route table]] or implicite with the main route table)
- contains a set of rules (routes) that determine where network traffic from your subnet or gateway is directed


- subnets within the same VPC can communicate with each other by default
- This is because the main route table of a VPC typically has an entry that allows all subnets in the VPC to communicate
- Specifically, you might see a route with a destination of `10.130.0.0/16` (your VPC's CIDR block) and a target of "local", which means all traffic within the VPC is locally routable.

However, if you want to prevent two subnets from communicating with each other, you can do so using [[AWS network access control list (ACL)]] or Security Groups (SGs). Here's how you can do it:




- Every VPC is attached to an implicit [[router]]
- This router is not visible to the user and is fully managed and scaled by AWS
- What is visible is the route table associated with each subnet, which is used by the VPC router to determine the allowed routes for outbound network traffic leaving a subnet
- Note from the screenshot below that every route table contains a default local route to facilitate communication between instances in the same VPC, even across subnets.
- This intra-VPC local route is implied and cannot be changed. In the case of the main route table that is associated with a default subnet, there will also be a route out to the Internet via the default gateway for the VPC.
- 

![[local_rule.jpeg]]!


![[vpc-resource-map-update.png]]