Elastic load balancing
Managed load balance by aws
less configurable
Health checks is done on a port and route on an [[EC2]] Instance. If response is not 200, the instance is unhealthy
4 types of managed load balancers
1. [[CLB]] 
2. [[ALB]]
3. [[NLB]]
4. [[GLB]]

Can be applied on internal or external networks
when [[Security Group]] is configured behind an ELB, provide the security group of the ELB

Server Name Indication (SNI) allows you to expose multiple HTTPS applications each with its own SSL certificate on the same listener.

[[Sticky Sessions]]

[[Cross Zone load balancing]]

[[SSL]]

[[Connection Draining]]

[[ASG]]

Scalability - How much we can make the system Available
Availability - Is the system available for operations
Vertical Scalability - Increase the scalability by adding more  resource to the current operational unit. Used in databases like [[RDS]] or linke in [[Elastic Cache]]
Horizontal Scalability - Increase the scalability by adding more operational units and using them parallel - For High availability horizontal scaling is used because we have hardware limit for vertical scalability. Goal is to cater data centre loss.



