Encryption strategies

SSL - inflight
KMS - at rest
Client side

[[KMS]]

*AWS Secrets Manager* - newer service, force rotation of secrets every X days, Automate secret generation rotation with [[Lambda]], integrates with [[RDS]], [[KMS]] integration. better than [[SSM Parameters]]

[[Cloud HSM]]

*Shield*

1. Standard - free, protects from  DDOS attacks such as SYN/UDP floods, Reflection attacks, other layer3 -4 attacks 
2. Advanced  - DDoS mitigation service, DDoS response team (24/7) , higher fees are waived during the attack. 


[[WAF]]

GuardDuty - AI thereat discovery
uses [[Cloud Trail]] logs , [[VPC]] Flow logs, DNS logs
can setup [[Cloudwatch Events]] rule to be notified in case of findings 
can identify crypto currency attacks

Inspector - automated security assessments for [[EC2]]
checks against an OS and network
Inspector agent must be installed
report is generated with a list of vulnerabilities
[[SNS]] integration

Macie - machine learning to protect sensitive data
Finds personally identifiable information (PII)
integrates with [[S3]]
uses [[Event Bridge]] for notification

[[Shared Responsibility Model]]