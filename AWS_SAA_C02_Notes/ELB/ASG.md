Auto Scaling Groups
Scaling in and out as per the load.
Scaling Policies can be on CPU, Network, custom metrics, schedules

1. Target tracking - I want the average ASG CPU to stay aroung 40%
2. Simple / Step Scaling - when [[Cloud Watch]] says CPU >70% add 2 units
3. Scheduled Actions - based on known usage patterns
4. Predictive Scaling - forecasting

Uses Launch Templates to create one
Health checks can be EC2 based on [[ELB]] based
For Updating, we have to provide another launch template
IAM roles attached to ASG will get assigned to the corresponding [[EC2]] instances.
ASG is free, underlying resources are chargeable.
It is possible to have an ASG without [[ELB]]

cool down period - time after scaling activity. During this time ASG will not change any instances


ASG Termination Policy
1. Find the AZ which has the most number of instances
2. Delete those instances with the oldest templates

Life Cycle Hooks - additional steps during states

1. Scale Out - Pending->Pending:Wait->Pending:Proceed->InService
2. Scale In - InService->Terminating->Terminating:Wait->Terminating:Proceed->Terminated

Launch Template vs Launch configuration
LT is new LC is old
LC must be recreated all time if there is an update
LT can have versions
LT can be parameterized for reusability



[[Cloud Watch]]


