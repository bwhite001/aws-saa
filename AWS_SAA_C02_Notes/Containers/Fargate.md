*Fargate*
no [[EC2]] instance to manage
Server less
each container is called a task
each task will have [[Elastic Network Interfaces]]
*EKS*

integrates with [[EFS]]

integrates with [[ALB]] uses dynamic port mapping. So [[Elastic Network Interfaces]] [[Security Group]] must allow any port from [[ALB]]

*Scaling*
using cloud watch metric using cpu usage