
#### target group
- linkes the [[AWS Application Load Balancer (ALB)]] to a group of servers (in [[AWS Auto Scaling Group]] or [[AWS ECS service]] a ALB id can be referenced)
- can include a health checker### listener
- a listner is needed to filter and forward incomming requests based on [[protocol]] and [[port]]
- a default response can be setup when no reachable

### listener rule
- can have a listener rule based on the prefix of the path of the incomming [[uniform resource identifier (URI)]]