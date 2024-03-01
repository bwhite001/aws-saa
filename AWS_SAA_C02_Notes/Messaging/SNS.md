Pub Sub model
10million subscribers
event type is called topic
100000 topic limit
Subscribers can be - SQS, HTTP, Lambda, email, SMS, Push notification NOT [[Kinesis]]
Publishers can be - Cloud watch, [[ASG]] notifications, [[S3]] events

Publish - using [[AWS SDK]]
HTTPS + KMS 

[[IAM]] access control
SNS Access Policies

SNS + SQS : Fan out - Publish once in SNS, receive in all SQS queues that are subscribers

FIFO SNS - name should end with .fifo
Message Filtering - filter for subscription events