1. SSE-S3 
	1.  AWS handles keys
	2.  Object is encrypted at server side
	3.  AES-256
	4.  set header x-amz-server-side-encryption:AES256
2. SSE-KMS -
	1. AWS Key management Service - audit trial
	2. Object is encrypted at server side
	3. x-amz-server-side-encryption:aws:kms
3. SSE-C 
	1. Server side encryption
	2. user sends the key.
	3.  S3 doesn't store key
	4.  HTTPS must be used
	
4. Client side
	1. client libraries encrypt the data eg: Amazon S3 encrytion client


Transit
HTTP endpoint - non encrypted.


we can encrypt with different methods for each version of a file or we can provide a default encryption for the bucket.


	

