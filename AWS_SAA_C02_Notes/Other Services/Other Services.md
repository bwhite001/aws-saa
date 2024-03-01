CI, CD

code - AWS CodeCommit 
build + test - AWS CodeBuild
deploy + provision - AWS Elastic BeanStalk / AWS CodeDeploy
Orchestrate via AWS CodePipeline


CloudFormation
infrastructure as code
stackset - CRUD stacks of infrastructure across accounts and regions
stepfunctions - orchestrate [[Lambda]] validity 1 year, serverless
SWF - coordinate work amongst apps. Code runs in [[EC2]], 1 year runtime, older not supported

EMR - Elastic Map reduce
OpsWorks - Managed Chef and puppet - automatic server configuration and repetitive actions

WorkSpaces - managed secure cloud desktop
AppSync - sync data across mobile and webapps in real time, uses graphQL

Cost Explorer

**CodeCommit:** service where you can store your code. Similar service is GitHub

**CodeBuild:** build and testing service in your CICD pipelines

**CodeDeploy:** deploy the packaged code onto EC2 and AWS Lambda

**CodePipeline:** orchestrate the actions of your CICD pipelines (build stages, manual approvals, many deploys, etc)

**CloudFormation:** Infrastructure as Code for AWS. Declarative way to manage, create and update resources.

**ECS (Elastic Container Service):** Docker container management system on AWS. Helps with creating micro-services.

**ECR (Elastic Container Registry):** Docker images repository on AWS. Docker Images can be pushed and pulled from there

**Step Functions:** Orchestrate / Coordinate Lambda functions and ECS containers into a workflow

**SWF (Simple Workflow Service):** Old way of orchestrating a big workflow.

**EMR (Elastic Map Reduce):** Big Data / Hadoop / Spark clusters on AWS, deployed on EC2 for you

**Glue:** ETL (Extract Transform Load) service on AWS

**OpsWorks:** managed Chef & Puppet on AWS

**ElasticTranscoder:** managed media (video, music) converter service into various optimized formats

**Organizations:** hierarchy and centralized management of multiple AWS accounts

**Workspaces:** Virtual Desktop on Demand in the Cloud. Replaces traditional on-premise VDI infrastructure

**AppSync:** GraphQL as a service on AWS

**SSO (Single Sign On):** One login managed by AWS to log in to various business SAML 2.0-compatible applications (office 365 etc)