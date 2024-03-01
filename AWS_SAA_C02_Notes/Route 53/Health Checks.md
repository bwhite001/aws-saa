1. for public resources
2. Types - 
	1. Application, Server or other AWS resources
	2. other health checks (calculated health checks)
	3. monitors cloud watch
15 global health checkers will check
Healthy threshold is 3 - default
HTTP, HTTPS,TCP
if 18% of HC report healthy then healthy else not.
 Return codes must be 2xx or 3xx
 can be setup to pass or fail based on the first 5120 bytes of the response.
 
 For private VPC, healthcheks wont work, we can use cloud watch for that.