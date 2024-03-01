# Practice Test AWS Solutions Architect Associate SAA C03: 


## Question 1:

 Your applications are currently hosted on-premises and you are exploring the use of Cloud Storage to store your database backup files for disaster recovery.  Which region will you use for storing the database backup files?

- 1. Nearest Region for lowest latency
- 2. Region farthest from your datacenter to protect against natural disasters
- 3. Region offering lowest cost
- 4. Region that meets your organization's regulatory requirement for disaster recovery(Correct)

*Correct Answer(s):*
 4. Region that meets your organization's regulatory requirement for disaster recovery

**Explanation:**
With AWS offering services globally, you would need to pick a region that meets specific organization's regulatory requirement for disaster recovery

## Question 2:

 Which one of these assumptions are not valid?

- 1. Cloud makes it easy to identify the usage and cost of the systems
- 2. Your AWS month-month bill will vary based on resources consumed
- 3. Data Transfer is free with on-premises whereas you must pay for it in the cloud(Correct)
- 4. Managed Services reduce the cost of ownership

*Correct Answer(s):*
 3. Data Transfer is free with on-premises whereas you must pay for it in the cloud

**Explanation:**
Networking infrastructure and bandwidth are costly components of the data center operation. However, it is challenging to estimate the cost of data transfer for an application in an on-premises setup. Whereas in the cloud, you get precise information as data transfer is one of the components of the consumption-based pricing model. Managed services reduce operational burden. Since managed services operate at cloud scale, they can offer a lower costTCO Calculator: https://aws.amazon.com/tco-calculator/Cost Optimization Pillar: https://d1.awsstatic.com/whitepapers/architecture/AWS-Cost-Optimization-Pillar.pdf

## Question 3:

 CloudFormation does not support this:

- 1. Provision Cloud Infrastructure Resources
- 2. Treat your infrastructure as Code
- 3. Ability to update and change resources
- 4. Automatic check of Account Limits(Correct)

*Correct Answer(s):*
 4. Automatic check of Account Limits

**Explanation:**
CloudFormation does not check for account limits. Your stack creation may fail if the number of resources or configuration exceeds your account limit

## Question 4:

 As part of application configuration step in an EC2 instance, the configuration script needs user data specified when launching the EC2 instance.  What mechanism can the script use to get this data?

- 1. Use Metadata query service http://169.254.169.254/latest/user-data  (Correct)
- 2. User Data is not accessible from within the instance
- 3. Use EC2 instance USER_DATA environment variable
- 4. Use tools provided by respective OS distributions

*Correct Answer(s):*
 1. Use Metadata query service http://169.254.169.254/latest/user-data  

**Explanation:**
Metadata query service available at http://169.254.169.254/latest/meta-data/ can be used to query instance related metadata. OS tools would not provide reliable information due to virtualized infrastructure

## Question 5:

 Your application services are used by several third parties.  To ensure quality of service for all customers and to prevent a single customer from consuming all the resources, you want to enforce limits on maximum requests per second that can be made by a single customer.  Which AWS service can you use for this need?

- 1. Cognito
- 2. Elastic Load Balancer
- 3. Lambda
- 4. API Gateway(Correct)

*Correct Answer(s):*
 4. API Gateway

**Explanation:**
API Gateway can act as a single point for your third parties to integrate with your services.  API Gateway allows to throttle requests at specific method level and manage individual API Keys. It also allows you to cache the responses so that API Gateway can directly answer certain method calls without invoking your backend services for every request.  You can configure your API methods to require authorization can support IAM based control, third party identity providers, custom authorizers and so forth.

## Question 6:

 Starnet corporation needs a high-performance cluster with 750 servers in a cluster placement group. The cluster workload is expected to run for a few days, after which the cluster can be terminated. However, attempts to launch the cluster were unsuccessful. The solutions architect verified and confirmed that quota limits are not an issue. The architect now suspects possible AWS capacity issues.What is the solution for this?

- 1. Purchase Reservation to guarantee server capacity
- 2. Purchase Savings Plan to guarantee server capacity
- 3. Spread the instances in cluster placement group across multiple availability zones
- 4. Purchase On-Demand Capacity Reservation to guarantee server capacity(Correct)
- 5. Spread the instances in cluster placement group across multiple regions

*Correct Answer(s):*
 4. Purchase On-Demand Capacity Reservation to guarantee server capacity

**Explanation:**
We can purchase On-Demand Capacity Reservation when you require guaranteed availability of servers. On-demand reservation does not require any long-term commitment, and you need to specify the number of instances you require, the availability zone, and the instance attributes. The billing starts as soon as the capacity reservation enters the Active State, and you are guaranteed access to the requested EC2 capacity. When the reservation is active, you are charged the equivalent on-demand rates whether you run instances or not. So, launch instances that match reservation attributes. If you do not run any instances, this shows up as an unused reservation on your EC2 bill. When you no longer need it, you can cancel the reservation.Since the requirement calls for high-performance computing using a cluster placement group, all the instances are located in the same availability zone. So, the choices of multiple availability zones and regions are incorrect.Savings plan and Reservations are not needed as the cluster instances are needed only for a few days

## Question 7:

 The Fruit company needs to analyze data generated by sensors of their autonomous car. The dataset size in 100s of TBs and stored in S3 standard storage. To analyze all this data, data science team needs a high-performance cluster with over 1000 servers with very low latency and very high throughput network connectivity. The servers also need low latency data access. How should they design the system? (Choose Two)

- 1. Create cluster using Spread Placement Group
- 2. Use FSx for Lustre linked to an S3 bucket(Correct)
- 3. Use Auto Scaling to launch the servers across at least two availability zones to protect from availability zone failure
- 4. Use Storage gateway configured as File gateway
- 5. Create cluster using Cluster Placement Group(Correct)

*Correct Answer(s):*
 2. Use FSx for Lustre linked to an S3 bucket5. Create cluster using Cluster Placement Group

**Explanation:**
Use FSx for Lustre and launch the EC2 in a Cluster Placement Group.FSx for Lustre is a high-performance file share that offers low latency data access. This is optimized for high performance computing and fast processing. FSx for Lustre can operate as a standalone file share or you can link it to S3 bucket and present the content of S3 bucket as a file share. Any changes you make to the file system is automatically updated to S3. Similarly, the linked file system is automatically updated as objects are changed in S3.For High performance computing use cases, we can use the EC2 Placement Groups.With EC2’s Cluster Placement Group, the instances are packed closely together in a single availability zone. These instances may share the same rack and networking infrastructure to achieve low latency.A spread placement group places each instance in a separate rack, with each rack having its own network and power source. This option is recommended for applications that have a small number of critical instances that should be kept separate from each other. A spread placement group can also span multiple availability zones in a region.Another option is the Partition Placement Group. This option minimizes the impact to your application due correlated hardware failure. EC2 distributes the instances across the number of partitions that you specify. And each partition is placed in a separate rack and each rack has its own power source and network.Storage Gateway is not meant for High Performance Computing use casesSpreading across multiple availability zones using Auto scaling is a cloud best practice. However, high performance computing is one exception where you want all instances placed closely to each other.

## Question 8:

 You are using autoscaling to dynamically adjust capacity to add and remove instances.  Before instances are terminated, important log files need to be collected and stored in S3.  What is the cost effective mechanism for collecting these files?

- 1. Store log files in Elastic File System (EFS) in a central location
- 2. Modify your application to directly write log data to S3
- 3. Use Life Cycle hooks provided by Autoscaling to execute custom logic for moving the log data to a S3 bucket(Correct)
- 4. Use Storage Gateway configured as a File Gateway and use this for writing log files

*Correct Answer(s):*
 3. Use Life Cycle hooks provided by Autoscaling to execute custom logic for moving the log data to a S3 bucket

**Explanation:**
Log files are frequently touched and written to, so it is best to use EBS volumes or local instance store for storing the data.  You can use AutoScaling lifecycle hooks to execute custom logic and move log files to an appropriate S3 location.  Storage gateway introduces a new component and not required.  EFS can be used for sharing data across EC2 instances and is supported only Linux instances.  In addition, EFS storage is more expensive compared to S3.  Modifying application involves additional time and cost

## Question 9:

 You are looking for a workflow tool to manage your infrastructure as code.The infrastructure provisioning is done with either CloudFormation or TerraformWhich AWS-managed tool would you use?

- 1. Pinpoint
- 2. Proton(Correct)
- 3. ECS
- 4. Batch

*Correct Answer(s):*
 2. Proton

**Explanation:**
AWS Proton is an Infrastructure as Code (IaC) deployment workflow tool.With Proton, you can provision environments and then configure services running in those environmentsEnvironments and services are based on environment templates and service templates that you choose in your AWS Proton versioned template libraryInfrastructure provisioning is done with either CloudFormation or Terraformhttps://docs.aws.amazon.com/proton/latest/userguide/ag-works.htmlECS is used for running containerized applicationsBatch is used for running non-interactive batch jobs in a fully managed environmentPinpoint is a multichannel marketing communication service that can deliver messages through email, SMS, voicemail, or push notificationRefer to SAA C03 - Services Summary lecture/article

## Question 10:

 You need to design a system to process log files at lowest cost possible.  Log files arrive infrequently.  Processing jobs can take up to 3 hours to complete and needs to run without interruption.  Which EC2 instance purchasing option would be suitable for this requirement?

- 1. Reserved
- 2. Savings Plan
- 3. On-Demand(Correct)
- 4. Spot

*Correct Answer(s):*
 3. On-Demand

**Explanation:**
Spot instances are upto 90% cheaper than On-Demand.  However, Spot instances can be terminated with a 2 minute notice.  Reserved Instances and Savings Plan are up to 75% cheaper when compared to On-Demand; however, reserved instances require 1 year or 3 year commitment.  Among these choices On-demand makes most sense as the log files arrive infrequently. Also review my pricing calculation tutorial. AWS Pricing Calculation Tutorial - Spot, Savings Plan, Reserved Instances, On-demand https://www.youtube.com/watch?v=sb266536q_k

## Question 11:

 A startup is looking for cost-effective options to add additional capacity to the app during peak demand. To maximize savings, the team wants to use a mix of on-demand and spot instances of various instance types. How would you implement this proposal with Auto Scaling?

- 1. Create one auto scaling group with two launch configurations. One for on-demand and another for spot instances
- 2. Create two auto scaling groups - one for on-demand and another for spot instances
- 3. Use Auto Scaling Launch Template and specify the on-demand and spot portion of the capacity that the auto scaling group needs to maintain(Correct)
- 4. Use different CloudWatch Alarm Triggers for on-demand and spot instances

*Correct Answer(s):*
 3. Use Auto Scaling Launch Template and specify the on-demand and spot portion of the capacity that the auto scaling group needs to maintain

**Explanation:**
Launch template offers flexible options to manage fleet capacity. You can specify a percentage distribution of on-demand and spot instances. To maximize the chances of fulfilling spot requests, you can specify a range of values for vCPU and memory configuration. Auto Scaling will identify a list of instance families that meet the criteria. Larger spot pools have a better chance of fulfilling the request.Please watch my YouTube video, "EC2 Spot Usage and How to Handle Interruption with Demos." This discussion is all about EC2 spot instances and various mechanisms to minimize the risk of interruption and how to handle interruptionhttps://www.youtube.com/watch?v=uEhtscDHxOM&t=0shttps://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-purchase-options.html

## Question 12:

 You application runs in two different regions and you would like aggregate instance utilization metrics across regions.  What is the mechanism that can be used for aggregating CloudWatch data across regions?

- 1. Use appropriate statistics in CloudWatch and pick data from the desired instances across regions
- 2. Use a script to pull data from different regions, and push it to CloudWatch Logs for analysis(Correct)
- 3. Enable Cross region access and then use CloudWatch to aggregate
- 4. Enable Detailed monitoring to allow aggregation across regions

*Correct Answer(s):*
 2. Use a script to pull data from different regions, and push it to CloudWatch Logs for analysis

**Explanation:**
You can perform aggregation only with a region.  To aggregate data across regions, you can consolidate the metrics to CloudWatch logs and then analyze with metrics filter.

## Question 13:

 You are using an Amazon Machine Image provided by Amazon in us-east-1.  You are happy with the performance and stability of the AMI for your application needs.  You are planning to deploy your application in us-west-1 and want to use the same AMI.  What are your options?

- 1. AMIs are very specific to a region and not available in other regions
- 2. You need to explicitly enable AMI to be made available for your account in another region
- 3. AMI IDs are very specific to a region.  To use the same AMI in another region, you need to find corresponding AMI ID for that region(Correct)
- 4. AMIs are globally available in all regions and can be referred to using the same AMI ID

*Correct Answer(s):*
 3. AMI IDs are very specific to a region.  To use the same AMI in another region, you need to find corresponding AMI ID for that region

**Explanation:**
Amazon AMIs are region specific.  If you want to use the same in AMI in a different region, you would need to find the corresponding AMI ID and use it.

## Question 14:

 You are planning to use SQS FIFO queue for restaurant order management system.  Each table in the restaurant has a unique Table ID and it is used as the message Group ID for orders placed at that table.  What is the sequence in which chefs will process the orders? (Choose Two)

- 1. Orders from different tables are processed in parallel(Correct)
- 2. Orders from a table are processed in sequence(Correct)
- 3. Orders from a table are processed in parallel
- 4. Orders are processed in sequence irrespective of the table

*Correct Answer(s):*
 1. Orders from different tables are processed in parallel2. Orders from a table are processed in sequence

**Explanation:**
SQS FIFO Queue allows you to create multiple FIFO Queues using Group ID.  If all messages have the same Group ID, messages are received by consumers strictly in the order it was sent to the queue.  When different Group IDs are used, it allows FIFO ordering by Group ID.  So, messages with the same Group ID are received by consumers in sequence; however, a different consumer can receive a message from another Group IDs.  Group ID allows you to create multiple FIFO queues

## Question 15:

 The customer needs to migrate 50 TB of data from on-premises file shares to S3Any new changes in on-premises (incremental data) need to be in sync with S3 until cutover to the cloudWhat data transfer service would you use for this? (Choose Two)

- 1. Snowball Edge Storage Optimized(Correct)
- 2. Data Sync(Correct)
- 3. S3 cp and sync commands that are available in the AWS command line tool
- 4. AWS Transfer Family
- 5. S3 Batch Operations

*Correct Answer(s):*
 1. Snowball Edge Storage Optimized2. Data Sync

**Explanation:**
This question asks about migration of existing data to cloud and transferring new data until cut over to the cloud. Among these choices, Data Sync and Snowball would meet the requirementsWhen transferring large amounts of data, we need to consider network bandwidth available between On-premises and AWS Cloud. If the question specifies network speed, instead of calculating during the exam, I simply remember this information: 100 Mbps network link can transfer 1 TB/day and then extrapolate for data provided in the question. So, transferring 50 TB can take 50 days using a 100 Mbps link. There is no mention of network speed in this question, and we need to pick two candidates for the migration and incremental data transfer.Among these services, we can use Snowball Edge Storage Optimized to ship up to 80 TB (Terabyte) of data per device. You can request multiple devices for transferring a larger amount of data. The end-to-end time to transfer is approximately one-week, including shipping and handling. Since we have 50 TB of data to transfer, a single appliance is sufficient to do the initial migrationThe question also asks about incremental data transfer. Data Sync is an AWS tool optimized for moving large amounts of data. You can use this to transfer from on-premises to AWS Storage services (S3, EFS, FSx for Windows). Data Sync supports both one-time migration and scheduled incremental transfer. Data Sync automatically tracks changes to perform incremental transfers efficientlyS3 cp and sync commands are very efficient too! In fact, I use S3 sync commands to back up my video files to AWS. However, for large-scale migration, running a CLI command is not optimal and would require a lot of scriptingS3 Batch Operations is primarily meant for large-scale operations on S3 objects. For example, to transfer objects from one bucket to another, data transformation using Lambda, and so forthAWS Transfer Family is a managed file transfer service, and you can transfer files using SFTP, FTP, FTPS, and AS2 Protocols into and out of AWS Storage Services like S3 and EFS. However, this would also have bandwidth constraints for the initial migration of 50 TB. While this tool can be used for incremental transfer of new data, you would have to write scripts to identify what files have changed

## Question 16:

 Application requires 10 EC2 instances running at all times even when an Availability Zone goes down.  The region where the solution is deployed has three Availability Zones.  How would you distribute instances across the three availability zones to optimize cost?

- 1. 4-4-4
- 2. 10-10-0
- 3. 5-5-5(Correct)
- 4. 4-4-6

*Correct Answer(s):*
 3. 5-5-5

**Explanation:**
When an AZ goes down, we still need ten servers to be up and running.Only 5-5-5 provides this ability while lowering the total instance count. Here we have 15 servers runningIn the 10-10-0 configuration, only two AZs are used, each with ten servers running. This will also meet the requirements; however, we have 20 servers running. So, the costs are higherThe 4-4-6 configuration would not meet the requirement as there will be only eight servers running when the third AZ goes downThe 4-4-4 configuration does not meet the requirements as there will be only eight servers running after an AZ failure

## Question 17:

 One of the high-profile security vulnerabilities was the Apache Log4j vulnerability, which allows remote code execution and the ability to download and run arbitrary code on your servers. Let’s assume an issue like this vulnerability is reported and you want to assess the impact to your environment consisting of 1000s of servers and containers. What tools would you use to identify vulnerable systems and apply the fix? (Choose Two)

- 1. Inspector(Correct)
- 2. Macie
- 3. Systems Manager(Correct)
- 4. GuardDuty
- 5. Control Tower

*Correct Answer(s):*
 1. Inspector3. Systems Manager

**Explanation:**
Inspector can scan hosts and container images and report Security exposures and vulnerabilities. This tool assigns a risk score to prioritize your remediation. Using the Systems Manager Patch Manager, you can automatically patch the vulnerable systems at scale. For patching container image, you may need additional CI/CD pipeline and tools to build a new image. GuardDuty is an intrusion detection system that alerts about malicious activities in your environment. Control Tower provides a blueprint that follows AWS security and compliance best practices and sets up a multi-account environment for you, called a Landing Zone. Amazon Macie scans your S3 buckets and flags them if it contains sensitive data. Macie can also alert you when policies or settings in S3 buckets are changed in a way that reduces the security

## Question 18:

 You have configured an Aurora database with five read replicas.  What is the recommended mechanism for clients to connect to read replicas?

- 1. Add logic in client to figure out which read replica is available and connect to one
- 2. Configure clients with all five read replica endpoints
- 3. Connect to primary instance in read-only mode and it will automatically route to an available read-replica
- 4. Use Aurora database reader endpoint.(Correct)

*Correct Answer(s):*
 4. Use Aurora database reader endpoint.

**Explanation:**
Each Aurora DB cluster has a reader endpoint. If there is more than one Aurora Replica, the reader endpoint directs each connection request to one of the Aurora Replicas.

## Question 19:

 You want to provide a buffer that shields consumers from a sudden spike in messages from producers.  Messages in the buffer needs to be available to all the consumers.  What service is suitable for this?

- 1. Kinesis Streams(Correct)
- 2. SQS FIFO
- 3. SNS
- 4. SQS Standard

*Correct Answer(s):*
 1. Kinesis Streams

**Explanation:**
With SQS each message is consumed by a single consumer.  SNS can fan-out messages to all subscribers; however, it is not meant as a buffering mechanism.  SNS is used for pushing messages.  Kinesis streams is used for buffering messages and multiple consumers can read the messages anytime

## Question 20:

 Your company's customers frequently need to upload files to your S3 bucket.Which of these options would meet the requirements?

- 1. AWS Transfer Family(Correct)
- 2. Snowball
- 3. Storage Gateway
- 4. Data Sync

*Correct Answer(s):*
 1. AWS Transfer Family

**Explanation:**
AWS Transfer Family is a managed file transfer service. Your customers can transfer files using SFTP, FTP, FTPS, and AS2 Protocols into and out of AWS Storage Services like S3 and EFS.Few other options are available. S3 Transfer Acceleration uses edge location and is suitable for routine transfer of files greater than 1 GB. CloudFront is another option that uses edge location and is suitable for routine transfer of files less than 1 GBData Sync requires agent installation and additional configuration at the client sideStorage Gateway on-premises servers access to virtually unlimited cloud storageSnowball is used for physically shipping large amounts of data (up to 80 TB per appliance)

## Question 21:

 A DynamoDB table is provisioned with 20 Read Units and 20 Write Units.  If items are 4KB in size, what is the net throughput that can be achieved?

- 1. 20 strongly consistent reads per second and 5 writes per second(Correct)
- 2. 20 Reads per second and 20 Writes per second
- 3. 10 strongly consistent reads per second and 5 writes per second
- 4. 40 eventually consistent reads per second and 20 writes per second

*Correct Answer(s):*
 1. 20 strongly consistent reads per second and 5 writes per second

**Explanation:**
A read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4 KB in size.  Item size is rounded to the next 4KB boundary.  For example: if item size is 4.5KB, DynamoDB would round it to 8KB for Read Capacity Unit calculation.  A write capacity unit represents one write per second, for an item up to 1 KB in size.  Item size is rounded to the next 1KB boundary.   For example: if item size is 4.5KB, DynamoDB would round it to 5KB for Write Capacity Unit calculation

## Question 22:

 When launching new instances, you are noticing Auto Scaling is prematurely terminating the instances. To troubleshoot the root cause, you launched a standalone instance with all the prerequisite software and concluded that it takes at least 7 minutes for the instance to get ready. What Auto Scaling parameter would you adjust to give extra time for the server to launch?

- 1. Cooldown period
- 2. ELB Deregistration delay
- 3. Warmup parameter
- 4. Health Check Grace Period(Correct)

*Correct Answer(s):*
 4. Health Check Grace Period

**Explanation:**
Health Check Grace Period is the amount of time that Auto Scaling waits before checking the health status of the EC2 instance. EC2 must pass EC2 status checks and ELB health checks (if they are part of ELB) before Auto scaling considers the instance healthy. If EC2 fails the health check, it will be considered unhealthy, and auto-scaling will initiate steps to replace the instance. You can increase this grace period for new instances when an application or server requires a longer time to initialize and come online. The default value is 300 secondsCooldown period (applies only for simple scaling). When a simple scaling policy adds or terminates instances, it waits for the cooldown period before another simple scaling activity is initiatedThe Auto Scaling warmup parameter applies to newly launched instances and ensures instances have sufficient time to initialize before they start reporting CloudWatch dataELB Deregistration Delay. When a target is removed from ELB, it goes through a deregistration phase. Deregistration can happen during an Auto Scaling scale-down event. ELB stops sending new requests to targets that are deregistering. However, there could be requests currently in flight on the server. The deregistration delay helps in-flight requests to completeRefer to Review of Elastic Load Balancing (ELB) and Auto Scaling Parameters article/lecture in this course

## Question 23:

 An application requires 100 GB of persistent volume storage. The application is expected to perform 600 IOPS.Which of these options meet the requirements cost-effectively?

- 1. General Purpose Volume with 200 GB of storage(Correct)
- 2. Provisioned IOPS Volume configured for 100 GB and 600 IOPS
- 3. General Purpose Volume with 100 GB of storage
- 4. Instance Store SSD with at least 100 GB of storage

*Correct Answer(s):*
 1. General Purpose Volume with 200 GB of storage

**Explanation:**
General Purpose Volume with 200 GB of storage. General purpose volume offers a baseline performance of 3 IOPS per GB. With 200 GB of storage, the baseline performance is 600 IOPS, which meets the requirement at a lower cost.Provisioned IOPS with 100 GB and 600 IOPS also meets the requirement. However, provisioning IOPS is expensive.For example, using AWS Pricing Calculator, 200 GB of General Purpose Volume costs approximately USD 20 per month. Whereas 100 GB Provisioned IOPS volume with 600 IOPS provisioned capacity cost is around USD 51 per month.General purpose volume with 100 GB of storage would offer only 300 IOPS baseline performance.Instance store SSD is not the right choice as the question asks for a persistent storage

## Question 24:

 Your company uses S3 for storing a variety of documents and files. Your users ask for a feature similar to a trash can or recycle bin. This feature should allow the users to restore any deleted files or objects within 30 days. The deleted files older than 30 days must be removed automatically. How would you accomplish this? (Choose Two)

- 1. Enable Versioning on the bucket(Correct)
- 2. Move the object to a temporary bucket and use it for restoring
- 3. Enable Lifecycle Policies on the bucket(Correct)
- 4. Enable Cross Region Replication and restore objects from replicated site

*Correct Answer(s):*
 1. Enable Versioning on the bucket3. Enable Lifecycle Policies on the bucket

**Explanation:**
You can use versioning to keep the older version of the objects and life cycle policies can be defined to remove the older version after 30 days.  Cross region can help in protecting against accidental deletion and disaster recovery by keeping a copy of data in a different region.  But it is more expensive as a full copy of your bucket is maintained in another region

## Question 25:

 You are using Elastic Load Balancer for your internal application.  Auto assigned ELB DNS names are long and cryptic.  What option do you have to make the service discovery easier?

- 1. Use SNS to broadcast DNS Names
- 2. Change ELB assigned DNS Name to a more meaningful name
- 3. Use Route 53 Public Hosted Zone to give a friendly name for your ELB
- 4. Use Route 53 Private Hosted Zone to give a friendly name for your ELB(Correct)

*Correct Answer(s):*
 4. Use Route 53 Private Hosted Zone to give a friendly name for your ELB

**Explanation:**
ELB does not allow you to change assigned DNS names.  You can use Route 53 to make service discovery easier (billing.example.com, orders.example.com, and so forth). With Route 53, you can assign custom names for your services.  Private Hosted Zone is visible only inside VPCs that you enable.  Public Hosted Zone is suitable for internet accessible services.  In this scenario, services are used internally, so Private Hosted Zone is suitable.  While SNS can be used for broadcasting service names, it does not help in providing a single well known access point for your ELB

## Question 26:

 You want a data store that provides low latency access to messages from smart devices that track user health. Multiple applications can consume the same message. The ordering of messages needs to be preserved. Data analysis needs to be performed in memory. What service can you use for this?

- 1. Kinesis Firehose
- 2. SQS Standard
- 3. Kinesis Data Streams(Correct)
- 4. SQS FIFO

*Correct Answer(s):*
 3. Kinesis Data Streams

**Explanation:**
Kinesis Data Streams is suitable for real-time processing of streaming data. It preserves the ordering of records, and multiple applications can read from the same stream. With Kinesis Data Analytics, you can run SQL queries to analyze streaming data in data streamsKinesis Firehose is used to receive messages, transform and load them to a destination like S3 data lakes, warehouses, and analytics servicesSQS messages are received by a single consumer and do not meet the requirements

## Question 27:

 Your DynamoDB application stores and retrieves Items that are 8KB in size.The application reads 10 items per second in eventually consistent modeThe application also writes 10 items per second.How much capacity would you need to provision?

- 1. 10 Read Capacity Units and 80 Write capacity units(Correct)
- 2. 20 Read Capacity Units and 80 Write capacity units
- 3. 80 Read Capacity Units and 80 Write capacity units
- 4. 40 Read Capacity Units and 10 Write capacity units

*Correct Answer(s):*
 1. 10 Read Capacity Units and 80 Write capacity units

**Explanation:**
A read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4 KB in size.  Item size is rounded to the next 4KB boundary.  For example: if item size is 4.5KB, DynamoDB would round it to 8KB for Read Capacity Unit calculation.  A write capacity unit represents one write per second, for an item up to 1 KB in size.  Item size is rounded to the next 1KB boundary.   For example: if item size is 4.5KB, DynamoDB would round it to 5KB for Write Capacity Unit calculation.  Calculation:Reads are counted in 4KB units.1 RCU = 1 strongly consistent or 2 eventually consistent readsEventually consistent reads offers twice the read capacitySo, to read a 8KB item we need 2 RCUs (4KB *2) in strongly consistent mode or 1 RCU in eventually consistent modeSince the question asks about 10 item reads per second in eventually consistent mode, we need 10 RCUsThe writes on the other hand are counted in 1 KB size.To write one item of 8KB size, DynamoDB would require 8 WCUs.So, to write 10 items per second, we need to provision 80 WCUs.Reference: https://aws.amazon.com/dynamodb/pricing/provisioned/

## Question 28:

 You are hired to help with migrating a customer's solution to the AWS Cloud.  Customer wants to perform a phased migration strategy and they would like to first run couple of webservers on AWS that points to existing on-premises database. Application requests should routed across webservers in AWS as well as webservers located on-premises.  Which load balancing product can be used for this requirement?

- 1. Classic Load Balancer
- 2. Network Load Balancer
- 3. Application Load Balancer
- 4. Either Application or Network Load Balancer(Correct)

*Correct Answer(s):*
 4. Either Application or Network Load Balancer

**Explanation:**
Both Application and Network Load Balancers allow you to add targets by IP address.  You can use this capability to register instances located on-premises and VPC to the same load balancer.  Do note that instances can be added only using private IP address and on-premises data center should have a VPN connection to AWS VPC or a Direct Connect link to your AWS infrastructure

## Question 29:

 A popular SaaS application is hosted using an Application Load Balancer (ALB). A big corporate customer of this application is requesting that the application endpoints have a static IP address so that they can configure the firewall to allow traffic to the endpoint. The SaaS application technical team is heavily using ALB's routing features, and it is a non-trivial task to move to a different load balancer type. Which one of these options is most operationally efficient to meet the requirement?

- 1. Use Route 53 Simple Routing to hide the Application Load Balancer and ask the customer to use the DNS name associated with that route
- 2. Perform a DNS lookup to find the Application Load Balancer IP address and ask the customer to use the IP address
- 3. Use Global Accelerator to hide the Application Load Balancer and ask the customer to use the Global Accelerator endpoint(Correct)
- 4. Use CloudFront to hide the Application Load Balancer and ask the customer to use the CloudFront endpoint
- 5. Configure a set of web server EC2 instances with Elastic IPs for this customer

*Correct Answer(s):*
 3. Use Global Accelerator to hide the Application Load Balancer and ask the customer to use the Global Accelerator endpoint

**Explanation:**
Configure a Global Accelerator in front of an application load balancer.Global Accelerator endpoint has two static IP addresses. Customer can configure their firewall and application to communicate with the Global Accelerator IP address. The requests are automatically forwarded to Application Load Balancer by Global accelerator. The global accelerator has several benefits like using the AWS edge network to route the request to the nearest endpoint, static IP address, traffic dial to easily shape traffic flow, responding instantaneously to changes in health and traffic conditions, etc.Application Load Balancer scales based on traffic and dynamically adjusts the number of load balancer nodes when needed. Calling an ALB endpoint using an IP address is not recommended as the IP address may not be valid after a load balancer scaling actionUsing EC2 webserver instances with Elastic IP can introduce scalability, availability and operational challenges as you need to start provisioning servers by customers.CloudFront endpoints can resolve to multiple IP addresses, and the IP list will keep changingRoute 53 simple routing will resolve to the Application Load balancer endpoint and does not improve the solution

## Question 30:

 What options do you have for serving private content using CloudFront?  Content is generated both by your own origin servers as well as from S3.

- 1. Signed URLs or Signed Cookies or both can be used(Correct)
- 2. Signed Cookies
- 3. Private content is not supported by CloudFront
- 4. Signed URLs

*Correct Answer(s):*
 1. Signed URLs or Signed Cookies or both can be used

**Explanation:**
With CloudFront, you can securely serve private content by using signed URLs, signed cookies (trusted signers), and use Origin Access Identity (OAIs) to restrict access to your Amazon S3 bucket

## Question 31:

 What does amazon do with the data you store in S3 under Shared Responsibility Model? (Choose Two)

- 1. Amazon may access customer data when required to do so by law(Correct)
- 2. Amazon does not access customer data
- 3. Amazon will not access customer data even when required to do so by law
- 4. Amazon tracks data stored and usage inorder to bill for services rendered(Correct)

*Correct Answer(s):*
 1. Amazon may access customer data when required to do so by law4. Amazon tracks data stored and usage inorder to bill for services rendered

**Explanation:**
To estimate the service costs, AWS tracks data transfer and usage. AWS will not otherwise access your data except when required to do so by law.

## Question 32:

 Your Lambda function subscribes to an SNS topic, and the Lambda function is invoked asynchronously when a message arrives for that topic. When there is an error while processing a message, you want to ensure that the message is available for your team to troubleshoot. What configuration can you use for this?

- 1. Configure Dead Letter Queue for Lambda function(Correct)
- 2. Configure SNS to fanout events to an SQS Queue and Lambda function.  Use events in Queue for troubleshooting
- 3. Catch Errors in Lambda function and redirect errors to SQS
- 4. Configure Dead Letter Queue for SNS Topic

*Correct Answer(s):*
 1. Configure Dead Letter Queue for Lambda function

**Explanation:**
Using Dead Letter configuration, you can direct Lambda to send unprocessed events to SQS queue or SNS topic.  This can be used for troubleshooting events that were unsuccessful. While you can catch errors in a Lambda function and push the events to SQS queue, Lambda does it automatically for you using Dead Letter config.  SNS Topic itself does not have dead letter configuration.  SQS has a dead letter option to move messages that were not processed after specified number of retries

## Question 33:

 You have a docker container that is listening on Port 80.  It is part of an ECS Task and managed using ECS.  An Elastic Load Balancer routes the requests to the container.  You want flexibility to launch multiple instances of this Task in a single EC2 Instance.  What Elastic Load Balancer can you use for this?

- 1. Classic Load Balancer
- 2. You cannot launch multiple tasks in the same EC2 instance
- 3. Application Load Balancer with Static Port Mapping
- 4. Application Load Balancer with Dynamic Port Mapping(Correct)

*Correct Answer(s):*
 4. Application Load Balancer with Dynamic Port Mapping

**Explanation:**
Dynamic Port mapping allows automatic mapping of unused EC2 instance port to container. When container is registered with ALB, it automatically tracks the instance and port combination.  This will allow you to run multiple tasks belonging to same task definition in a single EC2 instance.  In addition, it frees you from manually mapping the ports to container services

## Question 34:

 Your auto scaling group has this configuration: minimum: 1, desired: 3 and maximum: 5.  Assuming there are no other scaling policies or scheduled actions defined, how many instances would the auto scaling group launch and maintain?

- 1. 5
- 2. 1
- 3. Depends on the load on the system
- 4. 3(Correct)

*Correct Answer(s):*
 4. 3

**Explanation:**
Auto scaling group maintains the desired capacity

## Question 35:

 You are tasked with developing a monitoring solution that simulates a customer and verifies customer experience of your app. The monitoring script needs to simulate customer actions (as if they are interacting with a browser) and discover issues before customers do.Which AWS service would you use for this?

- 1. CloudWatch Synthetics(Correct)
- 2. AWS Batch running on a schedule
- 3. Lambda scripts integrated with EventBridge scheduled events
- 4. Route 53 Health Checks
- 5. ELB Health Checks

*Correct Answer(s):*
 1. CloudWatch Synthetics

**Explanation:**
You can use Amazon CloudWatch Synthetics to create canaries, configurable scripts that run on a schedule, to monitor your endpoints and APIs. Canaries follow the same routes and perform the same actions as a customer, which makes it possible for you to continually verify your customer experience even when you don't have any customer traffic on your applications. By using canaries, you can discover issues before your customers do. Canaries are scripts written in Node.js or Python. They create Lambda functions in your account that use Node.js or Python as a framework. Canaries work over both HTTP and HTTPS protocols. Canaries offer programmatic access to a headless Google Chrome Browser via Puppeteer or Selenium Webdriver.Lambda scripts and EventBridge scheduled events require a lot of work for user-interface testing.AWS Batch is designed to run non-interactive jobs.Route 53 health checks are designed to monitor the health of application and API endpoints. These tests assess if the endpoint is reachable, measure response time and so forth. These are not comprehensive user-interaction simulation test.ELB health checks are designed to monitor the health of individual targets (EC2 instances, Containers and so forth). ELB health checks are light weight that checks if the target is reachable and responds to simple health check query.

## Question 36:

 You have an RDS managed online transaction processing (OLTP) system.  You are noticing I/O throughput issues with the current system.  Which one of these is a viable option to reduce I/O demand on primary database?

- 1. Offload SELECT queries that needs most current data to READ replica
- 2. Offload SELECT queries that can tolerate stale data to READ Replica(Correct)
- 3. Use Asynchronous Replication for Standby to minimize I/O
- 4. Use Synchronous Replication for READ Replica and use that instance for READ queries

*Correct Answer(s):*
 2. Offload SELECT queries that can tolerate stale data to READ Replica

**Explanation:**
Offloading read only traffic to a read-replica is an effective technique to minimize load on the primary database instance. The read-replica is eventually consistent and can lag the primary by a few seconds to minutes depending on specific database product used. Standby Instance is always configured for synchronous replication and READ Replica is always configured for asynchronous replication.

## Question 37:

 You have enabled cross region replication for your S3 bucket.   When you delete an object in the source bucket, what is the behavior observed in replicated bucket?

- 1. Delete Marker is not replicated(Correct)
- 2. Object is deleted
- 3. Delete Marker is replicated
- 4. Object is not deleted

*Correct Answer(s):*
 1. Delete Marker is not replicated

**Explanation:**
In general, it is safe to assume deletes are not replicated.  When you delete an object in S3 source bucket, object is marked as previous version and a delete marker becomes the current version in S3 source bucket.  With latest S3 version replication configuration, delete marker is not replicated.  However, previous version of S3 replication did replicate delete markers.  If you delete a specific version of an object in source bucket, then that version is left untouched in the destination (to prevent accidental deletes or malicious deletes).  For more details: https://docs.aws.amazon.com/AmazonS3/latest/dev/replication-what-is-isnot-replicated.html

## Question 38:

 Amazon S3 Standard is designed to provide 99.999999999% durability.  What does durability refer to?

- 1. Probability of losing an object is 0.000000001% during a particular year(Correct)
- 2. Probability of losing a bucket is 0.000000001% during a particular year
- 3. Probability of S3 not accessible during a particular year
- 4. Probability of Availability Zone going down during a particular year

*Correct Answer(s):*
 1. Probability of losing an object is 0.000000001% during a particular year

**Explanation:**
Durability is used to indicate the risk of data loss.  Highly durable solutions like S3 are designed for 11 9's durability with multiple copies maintained across availability zones.  In addition, S3 automatically repairs corrupted data blocks

## Question 39:

 You need to a design a DynamoDB table that can eventually grow to billions of items.  As the items expire, it needs to be removed from the table.  Which one of these options can you use to efficiently remove the items while preserving provisioned capacity for user traffic?

- 1. Create Global Secondary Sparse Index that contains only items to be deleted.  Design your script to use this sparse index and remove the items
- 2. Use batch delete
- 3. Use Time-To-Live support in DynamoDB(Correct)
- 4. DynamoDB has unlimited scalability.  Time based retention is not recommended

*Correct Answer(s):*
 3. Use Time-To-Live support in DynamoDB

**Explanation:**
You can use Time To Live capability to perform automatic retention management.  To perform time based item expiration in DynamoDB, you can have to first enable the TTL setting on the table and specify an attribute to be used as the TTL value. The value stored in this attribute indicates the expiry time, specified in epoch time format. The I/O operations needed for TTL are carried out by the system and does not count toward your provisioned throughput or usage.

## Question 40:

 Your application has a Lambda function that needs access to both internet services and private resources in your VPC.  What steps are needed to accomplish this? (Select two)

- 1. Lambda running in your Account can access internet and resources in your VPC
- 2. Deploy Lambda function in a public subnet of your VPC
- 3. Configure Lambda function to run inside a private subnet with path to NAT(Correct)
- 4. Add NAT device to your VPC(Correct)

*Correct Answer(s):*
 3. Configure Lambda function to run inside a private subnet with path to NAT4. Add NAT device to your VPC

**Explanation:**
To access your VPC private resources, you need to configure VPC settings for your Lambda function.  Lambda function attaches an elastic network interface in your VPC and is assigned only a private IP address.  You would need a NAT device added to your VPC and a route established from the private subnet to NAT device.

## Question 41:

 Customer has on-premises Linux and windows applications that use NFS, SMB file shares. Customer is planning a lift and shift migration to cloud.What storage service would you use that minimizes changes to the application? (Choose Two)

- 1. FSx for Windows(Correct)
- 2. EFS(Correct)
- 3. S3
- 4. FSx for Lustre
- 5. EBS

*Correct Answer(s):*
 1. FSx for Windows2. EFS

**Explanation:**
Linux and Windows applications are using on-premises file shares and we need to identify equivalent service for lift and shift migration.Amazon EFS (Elastic File System) is a fully managed service providing NFS shared file system storage for Linux workloads.Amazon FSx for Windows is a fully managed service providing SMB shared file system storage for native access by Windows systems. And since SMB file shares can also be accessed from Linux and MacOS, any application or user can access the storage regardless of operating system

## Question 42:

 To meet compliance requirements, you must route your customers to the application hosted in the same country. For some countries where you do not have the infrastructure, you can route based on the continent. What Route 53 configuration can you use that also minimizes Route 53 cost?

- 1. Latency routing
- 2. Simple routing
- 3. Weighted routing
- 4. Geoproximity routing
- 5. Geolocation routing(Correct)

*Correct Answer(s):*
 5. Geolocation routing

**Explanation:**
With Geolocation Routing, you can route traffic based on the requester's location. You can configure route 53 records based on Country and Continent. In the case of the USA, you can even configure it by State.Simple Routing is used when you have an app hosted in a single locationGeoproximity Routing – Similar to Geolocation, if you have resources in multiple regions, you can route traffic to the nearest location and, optionally, shift traffic from resources in one location to another. This allows for more complex traffic shaping; however, Geoproximity requires the use of Traffic Flow, and it involves additional monthly costs (USD 50/month)Latency Routing – If you have resources in multiple regions, you can route traffic to the region that provides the best latency. However, latency routing does not follow geographical boundaries, and when there are two nearby regions, latency based Routing will route requests to a region that offers the best performance (and it may be in a different country)Weighed Routing – Route traffic to multiple resources in proportions that you specify

## Question 43:

 RDS automated backup is configured to run at 1 AM every day. Later in the day, your application team noticed a data corruption issue caused by an application bug. You need to revert the database to a state as it was at 5 AM. How can you accomplish this?

- 1. Data can be restored using last backup taken at 1AM. Changes from 1AM to 5AM is lost
- 2. You can do a point-in-time recovery and set desired restorable time to 5AM and RDS would automatically restore the data to a new instance(Correct)
- 3. You cannot do point-in-time recovery with automated backups.  You need manual snapshots for recovery
- 4. Data can be restored using last backup taken at 1AM. Changes from 1AM to 5AM needs to be manually restored

*Correct Answer(s):*
 2. You can do a point-in-time recovery and set desired restorable time to 5AM and RDS would automatically restore the data to a new instance

**Explanation:**
When RDS automatic backup is configured, you can initiate a point-in-time restore and specify any second during your retention period, up to the Latest Restorable Time.  Data from backup is restored to a new instance

## Question 44:

 The database credentials for an application are stored as a secure string parameter in the Systems Manager Parameter Store.The application uses IAM role with Get Parameter permission to access the database credentials. However, during testing, the application could not connect to the database. The developer verified and confirmed that the credential stored in parameter store are valid.What could be causing the connectivity problem?

- 1. Ensure IAM role has permission to access the KMS Keys used for secure string encryption(Correct)
- 2. Ensure IAM Role has Put Parameter permission
- 3. The application must decrypt the password before using the credentials
- 4. Use String parameter instead of SecureString

*Correct Answer(s):*
 1. Ensure IAM role has permission to access the KMS Keys used for secure string encryption

**Explanation:**
SecureString parameter uses KMS keys for encryption. Ensure the Application IAM Role has permission to use the keys and access the parameter. Regular String is not recommended for sensitive data as the value is stored in plain text. Another option for storing credentials is the Secrets Manager

## Question 45:

 An application has a web layer for interacting with users and an app layer for processing requests and storing them in a database. The containers in the web layer need access to S3 and SQS. The app layer needs to read messages in SQS, process the message, and store the results in a DynamoDB table. How would you configure security permissions?

- 1. Use two task roles, one for Web and another for App containers. Grant S3 and SQS access in the Web task role and assign SQS and DynamoDB access to the App Task role(Correct)
- 2. Use a single-task role for the application. Grant S3, SQS, and DynamoDB access to the task role
- 3. Use a container instance role for the application. Grant S3, SQS, and DynamoDB access to the role
- 4. Use a task execution role for the application. Grant S3, SQS, and DynamoDB access to the role

*Correct Answer(s):*
 1. Use two task roles, one for Web and another for App containers. Grant S3 and SQS access in the Web task role and assign SQS and DynamoDB access to the App Task role

**Explanation:**
Use two task roles, one for Web and another for App containers. Grant S3 and SQS access in the Web task role and assign SQS and DynamoDB access to the App Task role. This approach will ensure we only grant the required privileges to the tasks. Using a single-task role will grant excessive permissions to web and app tasks. The task execution role and container instance role are used for granting permission to launch tasks, download images, and write to CloudWatch logs

## Question 46:

 Your company has an on-premises data center.  For disaster recovery and long term storage of data, it currently uses a Tape backup solution where Tapes are physically transported to a third party offsite location.  How can AWS Cloud help in this situation? (Choose Two)

- 1. You have to use AWS Tools to easily backup to Cloud
- 2. You can avoid Manual Tape management Process using Storage Gateway Virtual Tape Backup Solution(Correct)
- 3. You can use Secure Snowball Appliance to seamlessly and continuously backup from your data center to cloud
- 4. You can benefit from 99.999999999% of durability at very low cost(Correct)

*Correct Answer(s):*
 2. You can avoid Manual Tape management Process using Storage Gateway Virtual Tape Backup Solution4. You can benefit from 99.999999999% of durability at very low cost

**Explanation:**
AWS provides low cost storage solutions that you can use to manage your backup files (even if your company is not migrating applications to cloud).  With Storage Gateway Virtual Tape Backup, you can use your existing backup software and third party tools to easily take virtual tape backup in the cloud.  you no longer have to deal with physical tapes and costly hardware.  Data is highly durable in the AWS cloud and available when needed and you pay only for what you use.

## Question 47:

 An online retailer is looking for an automated solution to alert about fraudulent transactions, fake and spam accounts. Which solution would you recommend?

- 1. Amazon SageMaker
- 2. Amazon Fraud Detector(Correct)
- 3. Amazon Kendra
- 4. Amazon Rekognition

*Correct Answer(s):*
 2. Amazon Fraud Detector

**Explanation:**
Amazon Fraud Detector can detect online frauds with machine learning. For example, this service can flag suspicious online payments, detect new account fraud and incorporate additional verification steps, account takeover detection, and so forthAmazon Rekognition is used for analyzing images and videoAmazon Kendra is an intelligent search service for your enterprise data and applications. It is powered by Machine Learning and supports natural language interaction and questionsWith Amazon SageMaker, you can Build, train and deploy Machine Learning models for any use case with fully managed infrastructure, tools, and workflowRefer to SAA C03 - Services Summary article/lecture in this course

## Question 48:

 In a multi-AZ  RDS Deployment, automatic failover will not happen under this condition:

- 1. Primary Instance Storage Volume Failure
- 2. Primary Instance Deadlock and Query Timeouts(Correct)
- 3. Primary Availability Zone Failure
- 4. Primary Instance Failure

*Correct Answer(s):*
 2. Primary Instance Deadlock and Query Timeouts

**Explanation:**
RDS does automatic failover under common failure scenarios:  Loss of Primary Availability Zone, Loss of network connectivity to primary, Unhealthy primary instance, Storage failure on primary

## Question 49:

 You would like to optimize cost by keeping excess capacity to a minimum.  Among these services, which one requires you to manage the required capacity?

- 1. SNS
- 2. DynamoDB(Correct)
- 3. API Gateway
- 4. Route 53

*Correct Answer(s):*
 2. DynamoDB

**Explanation:**
DynamoDB requires you to specify READ and WRITE capacity to provision appropriate resources.  By optimizing DynamoDB capacity, you can lower the overall solution cost.  You can also dynamically adjust DynamoDB capacity using autoscaling.  SNS, Route 53, API Gateway automatically scales based on workload and you don't need to manage capacity

## Question 50:

 You want to provide a buffer that shields consumers from a sudden spike in messages from producers. Multiple consumers can work on different messages concurrently. Message ordering does not have to be strict, and the occasional duplicate processing of messages is acceptable. What service is suitable for this?

- 1. SQS Standard(Correct)
- 2. Kinesis Streams
- 3. SQS FIFO
- 4. SNS

*Correct Answer(s):*
 1. SQS Standard

**Explanation:**
With SQS each message is consumed by a single consumer.  SQS Standard Queue allows concurrent processing of messages by different consumers.  SQS FIFO allows concurrent processing of messages belonging to different Group ID. SQS FIFO offers lower throughput and preserves ordering.  SNS can fan-out messages to all subscribers; however, it is not meant as a buffering mechanism.  SNS is used for pushing messages.  Kinesis streams is used for buffering messages and multiple consumers can read the messages anytime

## Question 51:

 How does Auto scaling handle spot interruptions?

- 1. Configure CloudWatch Alarms to monitor for spot interruptions and use it to trigger a Scaling Policy in Auto Scaling
- 2. Auto Scaling does not have special handling. You would need to use EventBridge to monitor for spot interruptions and deregisters instance from the elastic load balancer
- 3. Auto Scaling automatically handles spot interruptions, deregisters the instance from the load balancer, and initiates steps to launch a replacement instance(Correct)
- 4. Auto Scaling uses a health check to detect instances terminated due to spot interruptions and then replaces them with a new instance

*Correct Answer(s):*
 3. Auto Scaling automatically handles spot interruptions, deregisters the instance from the load balancer, and initiates steps to launch a replacement instance

**Explanation:**
Auto Scaling automatically handles spot interruptions, deregisters the instance from the load balancer, and initiates steps to launch a replacement instance. In addition, EC2 service publishes a capacity-rebalance early warning event when a spot pool is likely to get interrupted. In this case, Auto Scaling can take proactive action to launch a new replacement instance from another spot pool with less likelihood of interruptionPlease watch my YouTube video "EC2 Spot Usage and How to Handle Interruption with Demos." This discussion is all about EC2 spot instances and various mechanisms to minimize the risk of interruption and how to handle interruptionhttps://www.youtube.com/watch?v=uEhtscDHxOM&t=0s

## Question 52:

 A travel offers application uses DynamoDB for backend store.  You are noticing that most of the provisioned write capacity is used up for storing comments and reviews about products.  When customers attempt to purchase, their requests are throttled resulting in errors.  Which one of these options is NOT a valid solution to address this issue?

- 1. Use eventual consistency to double WRITE throughput(Correct)
- 2. Keep frequently updated attributes in a separate table and provision adequate capacity for that table
- 3. Use ElastiCache to offload read/write traffic for comments and reviews.  Periodically sync this data to backend tables
- 4. Keep attributes related to purchasing the product in a separate table and provision adequate capacity for the table

*Correct Answer(s):*
 1. Use eventual consistency to double WRITE throughput

**Explanation:**
Caching frequently viewed data or frequently changing data in Elasticache is a great way to lower traffic hitting your backend systems.  You can also move more frequently changing data to a separate table so that it consumes less provisioned capacity to read/update smaller items.  Capacity provisioning is done at table level; by separating critical purchase attributes to a separate table, you can ensure there is capacity available to handle that traffic.  DynamoDB Autoscaling is a great way to automatically adjust provisioned capacity based on demand on individual tables.  Eventual consistent is applicable only for READs and you can get double the throughput when compared to strongly consistent reads

## Question 53:

 A customer is interested in reducing the on-premises storage footprint. 50 TB data in on-premises file shares need to be transferred to the AWS cloud. Once the migration is completed, the On-premises application will start using cloud storage.The network link speed available for migration is 100 Mbps.The solution needs to be cost-effective and timely. What solution would you propose? (Choose Two)

- 1. AWS Storage Gateway(Correct)
- 2. Data Sync
- 3. AWS Transfer Family
- 4. S3 Batch Operations
- 5. Snowball Edge Storage Optimized(Correct)

*Correct Answer(s):*
 1. AWS Storage Gateway5. Snowball Edge Storage Optimized

**Explanation:**
This question asks about the migration of existing data to the cloud, presenting this cloud data to on-premises applications, and reducing the storage footprint on-premises. Among these choices, Storage Gateway and Snowball would meet the requirements.When transferring large amounts of data, we need to consider the network bandwidth between On-premises and AWS Cloud. If the question specifies network speed, instead of calculating during the exam, I simply remember this information: 100 Mbps network link can transfer 1 TB per day and then extrapolate for data provided in the question. So, transferring 50 TB can take 50 days using a 100 Mbps link.Among these services, we can use Snowball Edge Storage Optimized to ship up to 80 TB (Terabyte) of data per device. You can request multiple devices for transferring a larger amount of data. The end-to-end time to transfer is approximately one-week, including shipping and handling. Since we have 50 TB of data to transfer, a single appliance is sufficient to do the initial migration. In this case, physically shipping data using Snowball is more optimal and takes less time when compared to network transfer.We also need to reduce the storage footprint on-premises and use the cloud as primary storage for on-premises applications. The Storage Gateway product perfectly meets this requirement and gives on-premises servers access to virtually unlimited cloud storage. Storage Gateway can present S3 as a file-share, a volume, or a tape device to your on-premises servers. Any data stored using the Storage Gateway is automatically backed up to S3. Any data already stored in S3 is available for access through Storage Gateway. Data Sync is an AWS tool optimized for moving large amounts of data. However, there is a network bandwidth constraint for initial transfer. Also, this product would not replace existing on-premises file shares. So, we cannot use this for reducing storage footprint.S3 Batch Operations is primarily meant for large-scale operations on S3 objects. For example, to transfer objects from one bucket to another, data transformation using Lambda, and so forthAWS Transfer Family is a managed file transfer service, and you can transfer files using SFTP, FTP, FTPS, and AS2 Protocols into and out of AWS Storage Services like S3 and EFS. However, this would also have bandwidth constraints for the initial migration of 50 TB. And this tool cannot reduce storage foot print on-premises

## Question 54:

 You are making a batch call to DynamoDB and in response, two items of size 1.5KB and 5.5 KB were returned.  How many read capacity units would be used for these items if you requested most up-to-date data?

- 1. 2
- 2. 6
- 3. 3(Correct)
- 4. 4

*Correct Answer(s):*
 3. 3

**Explanation:**
First item requires 1 read (upto 4KB in size). Second item requires 2 reads to read 5.5KB item (rounded to next 4 KB)

## Question 55:

 Which of the following RDS service related statements is not correct:

- 1. Database Snapshots are user initiated backups
- 2. When daily backup is enabled, database transaction logs are also backed up automatically at a more frequent interval
- 3. Automated Backups are available for restoration after RDS DB instance is deleted.(Correct)
- 4. You can initiate point in time recovery of a database to anytime up to the Latest Restorable Time for a DB instance.  Latest Restorable Time could be within 5-10 minutes of current time

*Correct Answer(s):*
 3. Automated Backups are available for restoration after RDS DB instance is deleted.

**Explanation:**
Automated backups are deleted when the DB Instance is deleted. Only manually created DB Snapshots are retained after the DB Instance is deleted.  Transaction logs are captured automatically when backup is enabled.  Last restorable time can be within 5 minutes of current time as RDS automatically applies the transaction logs to last daily backup.

## Question 56:

 Your RDS instance was upgraded to most current major and minor database version.  Legal requirement calls for a 10 year retention of your database backups and some of the backup were created on database versions that are no longer supported by RDS.  What will happen when you restore an unsupported database version?

- 1. Older version can be restored from snapshot and you will be give a grace period of 30 days. After that window, it will be upgraded to most current version
- 2. Older version with unsupported database major version cannot be restored
- 3. Older version when restored from snapshot will be automatically upgraded to currently supported database engine version(Correct)
- 4. Older version with unsupported database minor version cannot be restored

*Correct Answer(s):*
 3. Older version when restored from snapshot will be automatically upgraded to currently supported database engine version

**Explanation:**
After restoring unsupported version of a database, RDS service will automatically upgrade it to the latest version

## Question 57:

 You want to optimize the infrastructure by using just-in-time provisioning of resources based on demand.  What can help in speeding up deployment of resources? (Choose Two)

- 1. Pre-baked AMIs(Correct)
- 2. CloudFormation
- 3. ECS Tasks and Containers(Correct)
- 4. Bootstrapping regular AMI with user data

*Correct Answer(s):*
 1. Pre-baked AMIs3. ECS Tasks and Containers

**Explanation:**
CloudFormation helps in automated resource provisioning. However, to speed up resource provisioning, you need to use pre-baked AMIs with all necessary software components pre-installed (referred as Golden images).  Docker Container is another option to quickly launch containers from pre-built images without worrying about software dependencies.   User Data gives you flexibility to customize AMI; however, it will still take time to download and install required software

## Question 58:

 Your security team follows the principle of immutable instances. With this approach, the servers are never patched; instead, the existing servers are replaced with new servers with correct software patches. To speed up the deployment, the security team periodically releases new AMI with all the security patches for known vulnerabilities. The infrastructure is managed using Auto Scaling. How would you replace existing vulnerable instances?

- 1. Update existing Launch template to use new AMI and use Auto Scaling Refresh instances feature
- 2. Use Systems Manager - Patch Manager to replace existing instances and launch new instances
- 3. Use AWS Config to detect and terminate existing vulnerable instances and let Auto scaling replace the terminated instances
- 4. Create a new version of the launch template to use the new AMI, update Auto Scaling Group to use this new version of the template, and then refresh instances(Correct)

*Correct Answer(s):*
 4. Create a new version of the launch template to use the new AMI, update Auto Scaling Group to use this new version of the template, and then refresh instances

**Explanation:**
The launch template is immutable, and you need to create a new version with the correct AMI and then configure Auto Scaling Group to use this new version of the launch template. With instance refresh, you can perform a rolling replacement of instances. It takes a set of instances out of service, terminates them, and launches a set of instances with the new desired configuration. Then, it waits until the instances pass your health checks and complete warmup before it moves on to replacing other instances. The Patch manager is used for patching existing instances and cannot replace them. Even though it is theoretically possible to develop a configuration rule using AWS Config, it is too much work that can be easily accomplished using launch templates and Auto Scaling Group.https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-instance-refresh.htmlhttps://docs.aws.amazon.com/config/latest/developerguide/ec2-managedinstance-applications-required.html

## Question 59:

 A microservice deployment uses an Elastic Load Balancer to facilitate service-to-service communication. The caller sends the request to a load balancer endpoint, and the load balancer routes the request to healthy containers running in an ECS cluster. However, the drawback of this approach is that every micro service requires a load balancer, which increases the deployment cost. Which options would lower the cost and ensure the requests are forwarded only to healthy containers? [Choose two]

- 1. Configure microservice code to poll ECS Service to list the running tasks. Implement caller code to invoke one of the running tasks using a round-robin scheme
- 2. Configure API Gateway and use path-based routing to route to existing load balancer endpoints
- 3. Use Application Load Balancer and create one target group for each microservice. Use Path-based routing to route calls to specific microservice(Correct)
- 4. Use Cloud Map and configure ECS to publish the tasks with Cloud Map. Configure services to directly communicate with each other by using Cloud Map entries
- 5. Use App Mesh and route calls to the services using Envoy proxy sidecar(Correct)

*Correct Answer(s):*
 3. Use Application Load Balancer and create one target group for each microservice. Use Path-based routing to route calls to specific microservice5. Use App Mesh and route calls to the services using Envoy proxy sidecar

**Explanation:**
We can minimize the number of load balancers using Application Load Balancer path-based routing capability. Here, we create one target group for each microservice and assign a unique path. Depending on the path used by the caller, the request is routed to the appropriate microservice. Another option is using App Mesh. With App Mesh, an envoy sidecar is deployed along with each container. App Mesh publishes services and their tasks to Envoy. Envoy performs a health check of tasks and routes the request to a healthy target. With App Mesh, we don't need an elastic load balancer. Cloud Map maintains a list of targets by service. So, a caller can direct call a container. However, the caller is responsible for checking the health and handling retries. Since the task list in Cloud Map is maintained as DNS entries, these entries can be stale and point to a task that is no longer running.Modifying code to identify running tasks and invoking them is too much work. Load balancer and App Mesh already provide this functionality.Configuring API Gateway to route to existing load balancers would not address the cost issue.

## Question 60:

 When a NAT Gateway is deployed in a VPC,  it (Choose Two)

- 1. Resides in a public subnet(Correct)
- 2. Resides in a private subnet
- 3. Scales across all availability zones
- 4. Scales inside one availability zone(Correct)

*Correct Answer(s):*
 1. Resides in a public subnet4. Scales inside one availability zone

**Explanation:**
NAT Gateway allows your private instances to connect to the internet for outbound requests. Unsolicited inbound requests are blocked.  NAT gateway resides in your public subnet and automatically scales with redundancy inside an availability zone.  As a general practice, AWS recommends NAT Gateway to be created in more than one availability zone for handling availability zone failures

## Question 61:

 The corporate policy requires credential rotation every 90 days. While the users were promptly changing their passwords on time, an audit of access key age showed that keys were not rotated for several months. How can you enforce this policy and take corrective action?

- 1. Use Detective to automatically disable keys that are older than the specified max access key age
- 2. Use Trusted Advisor to automatically disable keys that are older than the specified max access key age
- 3. Use Inspector to automatically disable keys that are older than the specified max access key age
- 4. Use AWS Config to automatically disable keys that are older than the specified max access key age(Correct)

*Correct Answer(s):*
 4. Use AWS Config to automatically disable keys that are older than the specified max access key age

**Explanation:**
AWS Config has a managed rule to check if active access keys are rotated within the number of days specified in the maxAccessKeyAge parameter. If a key is not rotated, the rule marks the key as non-compliant, and you can set up automatic remediation. For example, disable the keys or notify owners and so forthTrusted Advisor can alert about access keys that are older than 90 days. The max-age parameter in Trusted Advisor is not configurable. You can automate the remediation by monitoring EventBridge and triggering an action in response to the event. However, Config provides a more ready-to-use solution with a customizable max-age parameter. Config also maintains a change history and compliance timeline.Inspector is used for host-level vulnerability assessmentAmazon Detective is an interactive tool to investigate security findings and identify the root cause of potential security issues or suspicious activities. Detective can analyze trillions of events from multiple data sources such as Amazon Virtual Private Cloud (Amazon VPC) Flow Logs, AWS CloudTrail logs, Amazon Elastic Kubernetes Service (Amazon EKS) audit logs, and Amazon GuardDuty findings, and automatically creates a unified, interactive view of your resources, users, and the interactions between them over time.https://docs.aws.amazon.com/config/latest/developerguide/access-keys-rotated.htmlhttps://docs.aws.amazon.com/awssupport/latest/user/security-checks.html#iam-access-key-rotation

## Question 62:

 Your application publishes variety of critical messages that third party subscribers can subscribe to and use.  However, not all subscribers are available all the time and you would like to ensure that they have opportunity to process them when they are back online.  What mechanism can you use to support this?

- 1. Using SNS Topic, fan out messages to per subscriber SQS Queue.  Subscriber has to poll the queue to receive messages.(Correct)
- 2. Use SNS Topic for broadcasting messages to subscribers.  If a subscriber endpoint is unavailable, SNS auto retries upto a configurable window of 7 days.
- 3. Store in a database and allow subcribers to query the database
- 4. Publish messages to one SQS Queue that all subscribers can use to access the messages. Configure Dead Letter Queue (DLQ) to retain unprocessed message.

*Correct Answer(s):*
 1. Using SNS Topic, fan out messages to per subscriber SQS Queue.  Subscriber has to poll the queue to receive messages.

**Explanation:**
SNS retries only for specific protocols and endpoints for configured duration and it certainly is not designed to hold messages for extended duration when consumers are  not available. A single SQS message cannot be used to deliver messages to all consumers. You can use SNS to fanout messages to individual consumer specific SQS Queue.  SQS Messages can be retained for upto 14 days if subscriber is unavailable.

## Question 63:

 For disaster recovery, a customer needs to replicate the content of an existing S3 bucket to another bucket in a different regionWhich option would meet the requirements?

- 1. S3 Cross Region Replication
- 2. S3 Batch Operations for initial transfer and S3 Cross Region Replication for ongoing transfer(Correct)
- 3. Secure FTP
- 4. Storage Gateway

*Correct Answer(s):*
 2. S3 Batch Operations for initial transfer and S3 Cross Region Replication for ongoing transfer

**Explanation:**
We need to transfer the contents of an existing bucket to another bucket. When you enable S3 Replication, it does not transfer already existing objects. Only new changes are replicated. So, we need to do a one-time copy of existing objects. S3 Batch Operations is a serverless solution that can inventory and transfer existing objects. For ongoing incremental transfer of changes to existing objects and newly created objects, we can use S3 ReplicationSecure FTP is for existing FTP clients to transfer files to S3Storage Gateway is used more commonly in a hybrid setup that gives on-premises servers access to virtually unlimited cloud storage

## Question 64:

 A large number of consumers of your app use mobile phones. You notice increased latency as the request has to hop multiple networks before reaching your endpoint. You are exploring an edge computing solution to run your app servers inside the communication service providers’ network. Which service would meet these needs?

- 1. CloudFront
- 2. Elastic Transcoder
- 3. Wavelength(Correct)
- 4. Global Accelerator

*Correct Answer(s):*
 3. Wavelength

**Explanation:**
AWS Wavelength is a mobile edge computing infrastructure where EC2 and Storage services are embedded within Communication Service Providers 5G networks (called Wavelength Zones). Application traffic from 5G devices reach application servers running in Wavelength zones without leaving the telecommunication network. This avoids the latency that would result from application traffic traversing multiple hops across the internet to reach its destination, which allows customers to take full advantage of the latency and bandwidth benefits offered by modern 5G networksWhile CloudFront also uses edge locations to deliver content with low latency and high transfer speeds, it is a general-purpose solution. Whereas Wavelength is an edge computing solution targeted at mobile networksThe global accelerator has several benefits, like using the AWS edge network to route the request to the nearest endpoint. Wavelength Zones are AWS infrastructure deployments that embed AWS compute and storage services within communications service providers (CSP) 5G networks, so application traffic from 5G devices reaches application servers running in Wavelength Zones without leaving the telecommunications network.Amazon Elastic Transcoder is a media transcoding service in the cloud to convert media files from their source format into versions that will playback on devices like smartphones, tablets, and PCsPlease refer to SAA C03 - Services Summary article/lecture in this course

## Question 65:

 Your company uses WAF, Shield Advanced, Security Groups, and Network Firewall to protect your application and the infrastructure. However, there are differences in how various teams are using these productsYou are tasked with developing a solution to manage and apply all the firewall rules centrally. What service can be used for this task?

- 1. Use AWS Config to monitor the resources and configured rules. Configure remediation steps to automatically correct the rules and protect resources
- 2. Use Firewall Manager to manage rules and apply them across accounts(Correct)
- 3. Use Systems Manager to monitor, and correct deviations
- 4. Use the scheduled event to check the rules against a baseline and automatically correct the drift

*Correct Answer(s):*
 2. Use Firewall Manager to manage rules and apply them across accounts

**Explanation:**
Using Firewall Manager, we centrally manage all rules and apply them across accounts. Firewall Manager can automatically add protection to existing and new resources, detect and correct misconfigured rules

## Question 66:

 You are using API Gateway as a proxy for controlling access to backend services.  You are expecting a large jump in usage of your services after a planned marketing promotion.  How can you ensure API Gateway would scale to meet your needs?

- 1. Select appropriate Memory Size configuration for your service. API Gateway uses this to proprotionately allocate required CPU and Memory capacity
- 2. Enable Autoscaling option for API Gateway
- 3. Configure appropriate instance type
- 4. API Gateway is a serverless infrastructure that is automatically managed by AWS(Correct)

*Correct Answer(s):*
 4. API Gateway is a serverless infrastructure that is automatically managed by AWS

**Explanation:**
Amazon API Gateway is a serverlerss offering and will automatically scale to handle the amount of traffic your API receives.  Do note that API Gateway does throttle requests when it exceeds 10000 requests per second. You can contact AWS Support to increase the service limit

## Question 67:

 You are asked to provide a solution that periodically scans the company's AWS environment and benchmarks against AWS operational best practices for managing resources and infrastructure.In addition, you need a consistent process to review the applications and workload and compare them with AWS's architectural best practices and guidance.You are looking for specific guidance to improve your infrastructure and application architecture.What tools would you use? (Choose Two)

- 1. AWS Config
- 2. AWS Well-Architected Tool(Correct)
- 3. AWS Trusted Advisor(Correct)
- 4. AWS Artifact

*Correct Answer(s):*
 2. AWS Well-Architected Tool3. AWS Trusted Advisor

**Explanation:**
AWS Trusted Advisor – Compares your AWS environment against AWS best practices and prioritizes the finding for you. For example, if the number of servers is approaching your account quota limit, you cannot launch any more servers, preventing autoscaling from responding to traffic.AWS Well-Architected Tool is a self-service review of your application architecture and workloads. This tool provides feedback on best practices and architectural guidance based on the well-architected framework. To use this tool, you have to answer a series of foundational questions, and it identifies a list of issues found in your workloads and step-by-step guidance to make improvementsAWS Config – Continuously records configuration changes to your resources and automates remediation of misconfigured resourcesAWS Artifact is a self-service portal to access AWS compliance reportsFor example, you can access Service Organization Control (SOC) reports, Payment Card Industry (PCI) reports, and certifications from accreditation bodies across geographies and compliance verticals that validate the implementation and operating effectiveness of AWS security controlsAll agreements that you sign with AWS are also managed using AWS Artifacthttps://repost.aws/questions/QU_fgOWav5SCqjHSE4uxPYgQ/aws-trusted-advisor-service-vs-aws-well-architected-framework-tool

