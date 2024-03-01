Governance, compliance and audit for aws account
enabled by default
Get history of events, API calls within AWS account by
1. console
2. SDK
3. CLI
4. AWS Services

can put the logs into [[Cloud Watch]] or [[S3]]
A trail can be applied to All [[Region]] or a single [[Region]]

1. Management Events - operations that performed on resources.eg AttachRolePolicy, CreateSubnet. By default it will be logged. can separate Read Events from Write Events
2. Data Events - not logged due to high volume. GetObject, DeleteObject, PutObject. Can separate Read and Write events.
3. CloudTrail Insights Events - detect unusual activity. inaccurate resource provisioning, hitting service limits, Bursts of AWS IAM actions, Gaps in periodic maintenance activity. 90 days TTL. after that send them to [[S3]] or [[Athena]]