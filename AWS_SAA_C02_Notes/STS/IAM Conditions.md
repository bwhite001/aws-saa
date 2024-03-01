aws:SourceIp - Ip from which requests are coming
aws:requestedRegion - [[Region]] to which the API calls are made
ec2:ResourceTag, aws:PrincipalTag - tags
aws:MultiFactorAuthPresent - MFA

IAM Roles vs Resource Based Policies

When you assume a role, user app, service you give up your original permissions and take permissions assigned to the role

when using a resource based policy the principal doesn't have to give up permissions

Eg: User in account A needs to scan a DynamoDB table in Account A and Dump it in S3 bucket in account B

Supported by [[S3]], [[SNS]], [[SQS]]