unlimited throughput
Default retention is 4 days Maximum is 14 days
256Kb per message size
can have duplicate message
can have out of ordering

SendMessage Api from SDK for publishing
Consumers can be [[EC2]], [[Lambda]]...
after polling, a consumer may receive upto 10 messages at a time
DeleteMessage APi is used to delete the message

in conjunction with a [[ASG]], we can utilize a cloud watch metric, ApproximateNumberOfMessages to scale up 

inflight - https
at-rest - KMS

[[IAM]]








