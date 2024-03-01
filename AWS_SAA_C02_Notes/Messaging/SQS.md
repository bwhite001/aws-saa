Queue with Producers and consumers
[[Standard Queue]]

Autoscaling managed by AWS

SQS Access policies - cross account access to SQS queues, SNS, S3 to write to an SQS queue

Visibility Timeout - once a message is consumed, the time limit to which other consumers cannot see the message in the queue. Once it is passed, message will be visible to all consumers. Default 30s. max 12Hrs. ChangeMessageVisibilty Api call is used to update this value.

Dead Letter Queue - an SQS queue which can hold the messages sent from the main SQS queue after MaximumRecieves flag is exceeded. Used for debugging. 14 days retention period is good for a DLQ

Delay Queue - the delay to which a consumer can see a message after it was published to the queue. Max value is 15 minutes. Parameter is called delaySeconds

Request Response Systems - Implemented by SQS Temporay Queue Client

FIFO Queue - limited throughput 300msg/s, name should end with .fifo Group Id for grouping.


