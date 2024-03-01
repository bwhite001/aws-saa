1. User based - [[IAM]] Explicit DENY in an IAM Policy will take precedence over an S3 bucket policy.
2. Resource based 
	1. Bucket Policies - bucket wide rules - evaluated before default encryption.
		1. Json Based
		2. used for grand public access to a bucket, Force objects to be encrypted at upload, Grant access to another account (cross account)
	2. Object Access control list - finer grain
	3. Bucket Access control list - less common


*Networking*
support VPC end points

*Logging and Audit* 
S3 access logs can be stored in other s3 buckets
API calls can be logged in AWS cloudtrail
									
*User security*
MFA delete on objects, pre signed URLS - premium video service for logged in users

*Pre signed urls*

1. Generated using SDK - uploads or CLI - downloads
2. default timeout 6 minutes
3. Users of the urls will get the privileges of the user who generated it.



									


