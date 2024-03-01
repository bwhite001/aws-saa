Helps with auditing and recording compliance of aws resource.
records configurations over time
eg: is there are unrestricted ssh access to the security groups,
do buckets have public access
can receive [[SNS]] alerts for the changes
per [[Region]] service
can be aggregated across [[Region]] and accounts
can be saved to [[S3]] and queried by [[Athena]]

No free tier

Remediation - automate remediation of non-compliant resources using SSM Automation Documents. eg IAM Access key expired.

Notification sent through [[Event Bridge]] or [[SNS]]