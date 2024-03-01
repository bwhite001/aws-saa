Cloudwatch - every service in aws
Metric is a variable to monitor - CPUUtilization, networking
belong to namespaces 
Dimension is an attribute of the metric
upto 10 dimensions per metric
Metrics have timestamps
Can create Cloudwatch dashboard

*Custom Metrics*

Memory, RAM, diskspace, number of logged in users
API PutMetricData
dimentions include Instance.Id, Environment.name

Accepts metric data points 2 weeks in the past and 2 hours in the future. So make sure EC2 instance time is correct


*Dashboards*
Global
can include graphs from different accounts and regions
can change the time zone
can set up auto refresh
Can be accessed by people who doesn't have AWS account. public, email address, 3rd party SSO provider through Amazon Cognito
3 dashboards for free
3$/ dashboard/month afterwards

*Logs*

Log groups - name representing an app
Log stream - instances within an app / log files / containers
can define log expiration policies
can send log to - [[S3]], [[Kinesis]] data streams, [[Lambda]]
logs sources - sdk, cloudwatch log agent, cloudwatch unified agent, elastic bean stalk, [[ECS]], VPC flow logs, [[API Gateway]], ClodTrail, [[Route 53]]

Filter expressions - eg: find an ip inside a log, number of occurance of string 'ERROR'
Metric Filters can be used to trigger CloudWatch Alarms
Log insights can be used to query logs and add queries to cloudwatch dashboards.

s3 export - upto 12 hours for ready to export
API - CreateExportTask
Not real time. For real time use log subscriptions
Subscription filter can send events to [[Lambda]] or [[Kinesis]]fire hose
Cross account and cross [[Region]] log aggregation possible

[[Cloud Watch for EC2]]

*Alarms*
Notification for any metric
states - OK , INSUFFICIENT_DATA
Period - time

target - 
1. stop, terminate, reboot or recover an ec2 instance
2. Trigger an auto scaling action
3. send notification to SNS

use setAlarmstate to test alram



