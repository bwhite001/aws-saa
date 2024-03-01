CNAME - host name to another host name
	1. Can't create CNAME for the top node of a DNS namespace (Zone Apex) eg. can't create a CNAME for example.com but for www.example.com ??
CNAME for root domain no possible 
	
	vs 
	*Alias*
	1. Maps Hostname to AWS resources. Extension not addition
	2. Automatically recoginizes changes in the resource's ip address
	3. can create for example.com
	4. Alias will always be of A or AAAA for AWS resources.
	5. There is no TTL
	6. Can't set an ALIAS to EC2 DNS name.
	
	
	
	
	
	
	
	
	
	
