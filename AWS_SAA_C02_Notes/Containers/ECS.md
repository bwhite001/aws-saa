*ECS*

Elastic container service
Launch docker containers on aws
user must maintain EC2 instances
aws takes care of starting and stopping of containers
integrates with [[ALB]] uses dynamic port mapping. So EC2 [[Security Group]] must allow any port from [[ALB]]

ECS Agent will be present in all EC2 machines

IAM Roles
1. EC2 Instance profile - used by ECS agent. Makes API call to ECS service, send container logs to cloudwatch, pull docker images from [[ECR]], 
2. ECS Task Role - Allow each task to have a specific role
	1. Allow each tasks to have a specific role
	2. Use different roles for each services to run
	3. Task role is defined in task definition

integrates with [[EFS]]
Use case: Persistent multi [[Availabilty Zone]] shared storage for the containers.

Event bridge integrates [[S3]] to ECS with events

*Scaling*
using cloud watch metric using cpu usage
[[SQS]] queue length

