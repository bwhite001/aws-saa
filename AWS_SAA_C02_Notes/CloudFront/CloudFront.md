CDN
Read performance 
content is cached at edge locations
DDOS protection, integration with shield, firewall

*Origins*
1. S3 bucket - CloudFront Origin Access Identity, used as an ingress, caching
2. Custom origin (Http) - [[ALB]], [[EC2]], S2 Website, Any Http backend

Geo Restriction - whitelist, blacklist

CloudFront vs S3 Cross Region Replication
1. ClodFront - Global network, TTL 1 day, good for static content
2. S3 CRR - manually setup for each region, Files are updated near real time, read only, dynamic content.

Signed URL - single files
Signed Cookie - multiple files

*CloudFront signed URL*
1. Allow access to a path no matter the origin
2. Only root can manage the keypair
3. Can filer by IP, path, date, expiration
4. Caching features

*S3 Presigned URL*
1. Issue a request as the person wo presigned the URL
2. Uses the IAM key of the signing IAM principal
3. Limited lifetime

[[Pricing]]
[[Multiple Origins]]
[[Global Accelerator]]






