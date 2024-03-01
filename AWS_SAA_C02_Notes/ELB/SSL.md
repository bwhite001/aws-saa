SSL - Inflight encryption
TLS is the new version
issued by Certificate Authorities
have an expiry date
certificate file is called X.509 certificate
Can use Amazon Certificate Manager to manage the certificates. Custom certificates can be uploaded.

Server Name Identification - loading multiple certificates behind [[ELB]]
only works for [[ALB]] and [[NLB]]

for [[CLB]] supports only one SSL. Must use multiple [[CLB]] for multiple host names