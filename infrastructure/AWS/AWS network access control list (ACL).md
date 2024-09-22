- allows or denies specific inbound or outbound traffic at the [[AWS subnet]] level.
- If you don't specifically associate an ACL with a subnet, the subnet is automatically associated with the default ACL. This is the case with your default VPCs which have all subnets associated with the default ACL.


example: isolate two subnets from each other using [[AWS network access control list (ACL)]]

-   Network ACLs are stateless, meaning you need to define rules for both inbound and outbound traffic.
-   Create a NACL for each subnet.
-   For subnet `10.130.1.0/24`:
	1.  Allow all inbound and outbound traffic.
	2.  Add a rule to deny all outbound traffic to `10.130.2.0/24`.
	3.  Similarly, add a rule to deny all inbound traffic from `10.130.2.0/24`.
-   For subnet `10.130.2.0/24`, do the opposite:
	1.  Allow all inbound and outbound traffic.
	2.  Add a rule to deny all outbound traffic to `10.130.1.0/24`.
	3.  Add a rule to deny all inbound traffic from `10.130.1.0/24`.
-   Associate each NACL with its respective subnet.


![[network-acl.png]]