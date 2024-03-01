Private endpoint to AWS service without getting into public internet
scale horizontally

1. Interface Endpoints - provisions a [[Elastic Network Interfaces]] as an entrypoint. must attach [[Security Group]]
2. Gateway Endpoints - Provisions a gateway and must be used as target in a route table. Supports only [[S3]] and [[Dynamo DB]]