# AWS Solutions Architect Associate with Practice Test: 


## Question 1:

 Which of the following resources cannot be tagged?

- 1. Instance
- 2. EBS Volume
- 3. VPC
- 4. Elastic IP(Correct)

*Correct Answer(s):*
 4. Elastic IP

**Explanation:**
An Elastic IP cannot be tagged. For a full list of resources that can and cannot be tagged, see the link below. Tags can be used to organize your AWS resources. This is helpful when you have similar resources that you need to categorize. For example, you may have a group of EC2 instances that belong to the development team, and other instances that belong to the production team. You could tag those instances to keep them organized, and to assign roles appropriately. Tags can only be assigned to an object that already exist.   http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html#tag-restrictions

## Question 2:

 You are writing data to S3 using the API. You have just completed a POST operation. Which codes returned indicate that the operation was successful?

- 1. No code is generated. To validate the operation you should check the logs.
- 2. 300, 301, or 304
- 3. 200, 201, or 204(Correct)
- 4. 200, 201, 202

*Correct Answer(s):*
 3. 200, 201, or 204

**Explanation:**
Data can be written to S3 using an API POST operation. The status code returned to the client upon successful upload is 200, 201, or 204 by default.  For more details see https://restfulapi.net/http-status-201-created/   and  https://restfulapi.net/http-status-202-accepted/  and   https://restfulapi.net/http-status-204-no-content/

## Question 3:

 You are going to terminate an EC2 instance and plan to also delete the EBS volume, but you want to store a copy of the volume in case you ever need to access  the data on it again. Which option should you use?

- 1. Take a snapshot, which will store a copy of the volume in EBS.
- 2. Take a snapshot, which will store a copy of the volume in S3.(Correct)
- 3. Detach the volume and store it in S3.
- 4. Detach the volume and store it in EBS.

*Correct Answer(s):*
 2. Take a snapshot, which will store a copy of the volume in S3.

**Explanation:**
You can take snapshots of an EBS volume. The snapshot is a point-in-time picture of the volume that is stored in S3. Like all data stored on S3, it will exist redundantly in multiple Availability Zones. Snapshots can be used to create multiple new EBS volumes. This is useful if you need to move a volume to a different AZ. You can create a new volume based on the snapshot, and it will be an exact copy of the original.

## Question 4:

 You have created an EC2 instance with a public IP address. An Internet gateway is deployed for the VPC. Which statement regarding this configuration is correct?

- 1. The instance must have a publcly routable ENI to reach the Internet
- 2. The Internet Gateway can perform a one-to-one NAT(Correct)
- 3. You must enable source/destination check on the Internet Gateway
- 4. The security group must have inbound and outbound rules for all traffic that you wish to allow.

*Correct Answer(s):*
 2. The Internet Gateway can perform a one-to-one NAT

**Explanation:**
Think of an Internet Gateway as a Virtual Private Cloud (VPC) component that connects your VPC to the Internet, sort of like a border router. The Internet gateway is the target for all traffic out of your VPC that is bound for the Internet. It will perform a one-to-one Network Address Translation (NAT) to replace the private IP of an instance with the public IP. Your instances will only be aware of the private addressing scheme within the VPC. An public IP or Elastic IP must be configured on the instance. An Elastic Network Interface (ENI) is not required. To perform many-to-one NAT you should use a NAT Instance or a NAT Gateway.  https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html

## Question 5:

 You are unable to connect to or restart an RDS DB instance. The state of the database is STORAGE_FULL. What should your first troubleshooting step be?

- 1. Connect to the DB instance to determine what might be using storage space unnecessarily(Correct)
- 2. Restart the DB instance
- 3. Increase the allocated storage to the instance
- 4. Shrink the transaction log file

*Correct Answer(s):*
 1. Connect to the DB instance to determine what might be using storage space unnecessarily

**Explanation:**
The first step is to connect to the DB instance if possible, and to try to determine what might be using storage space unnecessarily. You should also determine the DB instance status to ensure that you are troubleshooting the correct issue. Confirm that the instance has a status of storage-full. If you cannot connect to the instance you can increase the Allocated Storage property of your DB instance. This process varies based on the database engine being used. Once you have regained access you can review and clean up temp objects, optimizing tables, and shrink files to resolve the underlying issue.    https://aws.amazon.com/premiumsupport/knowledge-center/rds-out-of-storage/

## Question 6:

 To satisfy compliance requirements you need to run EC2 instances that on hardware that is dedicated to your organization. You do not have any server bound licenses, and do not care which host your instances run on, as long as you are not sharing host hardware with instances from other companies. Which product should you use?

- 1. Dedicated Host
- 2. VPC
- 3. Dedicated Instance(Correct)
- 4. Hardware Security Module

*Correct Answer(s):*
 3. Dedicated Instance

**Explanation:**
Dedicated Instances allow a customer to run EC2 instances that on dedicated hardware. Dedicated Instances will never run on hardware that is shared between multiple customers. Dedicated hosts can also be used to run EC2 instances on dedicated physical servers. This gives you additional control over how instances are placed on a physical server. This works well if you have server-bound software licenses.  https://aws.amazon.com/ec2/purchasing-options/dedicated-instances/

## Question 7:

 You need to create a fast a flexible database in the cloud that does not require complex queries or other features of a relational database. You should be able to easily scale the performance of the solution by changing the read and write capacity units. Which service should you use?

- 1. DyanmoDB(Correct)
- 2. RDS
- 3. S3
- 4. Redshift

*Correct Answer(s):*
 1. DyanmoDB

**Explanation:**
DynamoDB is a fast and flexible NoSQL database service. This is a non-relational database. This is useful for applications that need consistent single-digit millisecond latency at any scale. Use cases include mobile, web, gaming, and IoT applications and more. You can scale the performance capacity by modifying the Read Capacity Units (RCU) and Write Capacity Units (WCU) that you subscribe to.   https://aws.amazon.com/dynamodb/

## Question 8:

 Your organization has an database application running on EC2 that has a Recovery Time Objective (RTO) of less than 2 hours, and the Recovery Point Objective (RPO) must be 30 minutes or less. The application is deployed in multiple availability zones. What DR strategy could be used to achieve this RTO and RPO in the event of this kind of failure?

- 1. Back up the DB every 30 minutes to S3 and store transaction logs in S3 every 10 minutes(Correct)
- 2. Back up the DB every 30 minutes to EC2 Instance Store and store transaction logs in an EC2 Instance Store every 10 minutes
- 3. Back up the DB every 30 minutes to EC2 Instance Store and store transaction logs in S3 every 10 minutes
- 4. Back up the DB every 30 minutes to Glacier and store transaction logs in S3 every 10 minutes

*Correct Answer(s):*
 1. Back up the DB every 30 minutes to S3 and store transaction logs in S3 every 10 minutes

**Explanation:**
You could accomplish the RTO and RPO by backing up the DB every 30 minutes to S3 and store transaction logs in S3 every 10 minutes. Glacier should not be used because it does not support the RTO requirement of 2 hours. Think of Amazon Glacier as a archiving service in the cloud. It provides a secure, durable, and extremely low-cost cloud storage service. It can take up anywhere from a matter of minutes, or as long as to four hours to access anything in Glacier, so it is largely for offline storage. The time it takes depends of the service level you subscribe to. This is suitable for long-term archiving and backups. EC2 Instance Store should not be used to back up data. An EC2 instance store is temporary storage on disks that are physically attached to the host computer. There are many use cases for this storage type, such as temporary content or data that is replicated across many instances. The data is discarded when the associated EC2 instance stops or is terminated. This storage is not meant for valuable, long-term data. You can back this data up periodically to S3 or EBS.

## Question 9:

 You have an RDS instance that is not running in a VPC. You want to configure security policies using a DB security group. Which statements regarding this configuration are correct? (Choose two.)

- 1. All network access is enabled for DB instances by default.
- 2. A DB security group can be used to control access to an RDS instance that is not in a VPC.(Correct)
- 3. You can create rules for inbound and outbound traffic.
- 4. You do not need to configure a destination port number.(Correct)

*Correct Answer(s):*
 2. A DB security group can be used to control access to an RDS instance that is not in a VPC.4. You do not need to configure a destination port number.

**Explanation:**
A DB security group can be used to control access to an RDS instance that is not in a VPC. This is unusual, and only occurs in DBs running on the EC2-Classic platform. All network access is turned off for DB instances by default. You can create rules to allow certain types of traffic in. You can create rules for inbound traffic in a DB security group. The source can be a range of IP addresses or an EC2 Security Group. DB security groups do not require the configuration of a destination port number.   https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithSecurityGroups.html

## Question 10:

 What type of storage device is an EBS volume?

- 1. Block Storage(Correct)
- 2. Object Storage
- 3. File-level storage
- 4. iSCSI Volume

*Correct Answer(s):*
 1. Block Storage

**Explanation:**
Block storage devices manage data in sequences of bytes or bits. These are referred to as blocks. Traditional hard disks are the best know example of a block storage device. EC2 supports two types of block devices: Instance Store and EBS. An EC2 instance store is temporary storage on disks that are physically attached to the host computer. There are many use cases for this storage type, such as temporary content or data that is replicated across many instances. The data is discarded when the associated EC2 instance stops or is terminated. This storage is not meant for valuable, long-term data. You can back this data up periodically to S3 or EBS. SSD instance stores can be used when you need high performance and low latency, but do not need data to persist when the instance is terminated. Elastic Block Storage provides virtual “Disks” for your EC2 instances. Think of EBS as raw, unformatted disks. They are formatted with a file system, such as NTFS or ESXt, by the instance. Multiple EBS devices can be supported on the same EC2 instance, just like multiple disks on a VM.  https://aws.amazon.com/ebs/faqs/

## Question 11:

 You are planning on creating an EC2 instance that will need access to data on Dynamo DB. Which options would accomplish this goal? (Choose two.)

- 1. Create an IAM role with the correct permissions and assign it to the EC2 instance.(Correct)
- 2. Assign an IAM user to the EC2 instance.
- 3. Store access keys in the EC2 instance.(Correct)
- 4. Configure a security group that includes IAM permissions to the Dynamo DB.

*Correct Answer(s):*
 1. Create an IAM role with the correct permissions and assign it to the EC2 instance.3. Store access keys in the EC2 instance.

**Explanation:**
Applications running on EC2 instances can access Dynamo DB by storing access keys within the EC2 instance, however the preferred approach is to use an IAM role and assign it to the instance. This enables programs running on the EC2 instance to get temporary credentials, and access Dynamo DB without storing access keys. IAM roles can be assigned to an EC2 instance when it is created, or after.  https://aws.amazon.com/blogs/security/easily-replace-or-attach-an-iam-role-to-an-existing-ec2-instance-by-using-the-ec2-console/

## Question 12:

 What is the maximum amount of data that can be stored in an S3 bucket?

- 1. 1 Petabyte
- 2. 5 TB
- 3. 500 TB
- 4. Unlimited(Correct)

*Correct Answer(s):*
 4. Unlimited

**Explanation:**
To store data in S3 you will first create a container called a Bucket. There is no imposed storage limit on a bucket. Each object can include up to 5 TB of data. https://aws.amazon.com/s3/faqs/

## Question 13:

 What is the purpose of Cloud Formation?

- 1. Automatically map resources and correlate objects within an AWS account
- 2. Add instances to an Autoscaling group dynamically
- 3. Assign policies to groups of users to control access to AWS resources
- 4. Create templates that can be used to deploy AWS resources(Correct)

*Correct Answer(s):*
 4. Create templates that can be used to deploy AWS resources

**Explanation:**
Cloud formation is an extremely powerful automation tool. This is an automated way to create and manage AWS resources. For example, if you need to build an Amazon RDS DB instance with provisioned IOPs you can simply choose that template, and Cloud Formation will set everything up in AWS. The template defines the required AWS resources ad any associated dependencies required to run your application. The Cloud Formation Designer tool makes it easy to create your own templates and edit them.

## Question 14:

 You have a group of redundant Web Servers spread across multiple regions and Availability Zones that must be highly available. What options can be used to accomplish this goal? (Choose two.)

- 1. ELB(Correct)
- 2. Elastic Transcoder
- 3. NAT
- 4. CloudFront
- 5. Route 53(Correct)

*Correct Answer(s):*
 1. ELB5. Route 53

**Explanation:**
When you see the term 'high availability' on the exam you should immediately associate it with Elastic Load Balancing (ELB). AWS provides high availability using the ELB with autoscaling and multiple availability zones. An ELB can be used to distribute incoming traffic across multiple EC2 instances automatically within a region. Route 53 can provide availability in the event of a region-wide failure. Route 53 includes health checks that can be used to monitor web applications, web servers, and other resources. Route 53 will submit automated health check requests over the Internet to your application. When a health check fails, Route53 routes traffic away from the failed resource.   https://aws.amazon.com/blogs/aws/amazon-route-53-elb-integration-dns-failover/

## Question 15:

 Which of the following are valid account types when using consolidated billing with AWS organizations? (Choose two.)

- 1. Master(Correct)
- 2. Subordinate
- 3. Member(Correct)
- 4. Child

*Correct Answer(s):*
 1. Master3. Member

**Explanation:**
Consolidated Billing can be used with multiple Amazon Web Services (AWS) accounts within your organization. One will be designated the master account. You will be able to view all AWS charges across all accounts and perform reports on each. This is a free feature. All charges are billed to the master account. Other accounts are called member or linked accounts. The linked accounts are independent in every other way, unless you use AWS organizations to create roles.  https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_create.html

## Question 16:

 You need to create an image that you can use to deploy a new EC2 instances with a specific configuration and common applications pre-installed. Which AWS product or resource should you use?

- 1. Template
- 2. User Data
- 3. AMI(Correct)
- 4. Snapshot

*Correct Answer(s):*
 3. AMI

**Explanation:**
AMIs are pre-built machine images that you can use to deploy a new EC2 instance. An instance is a virtual server in the cloud. There are many instance types that are provided by AWS. You can also create and register your own custom AMI. The Amazon Linux AMI is available with the free tier, and is supported and maintained by AWS. It comes bundled with packages that allow you to integrate with AWS services including AWS CLI, Amazon EC2 API, AMI tools, the Boto Library for Python, and Elastic Load Balancing tools.   https://aws.amazon.com/amazon-linux-ami/faqs/

## Question 17:

 Which method should be used to migrate a VMware Virtual Machine to AWS with minimal downtime?

- 1. Create an S3 backup of the VM and restore from that
- 2. Use import/export to perform a native migration of the VM
- 3. Use the AWS Connector for vCenter to import the VM(Correct)
- 4. Use cross-platform vMotion to migrate the VM

*Correct Answer(s):*
 3. Use the AWS Connector for vCenter to import the VM

**Explanation:**
You can use the AWS Connector for vCenter to migrate VMs from a vSphere environment into AWS. You can migrate the VM into AWS and launch an EC2 instance based on it.  https://aws.amazon.com/ec2/vcenter-portal/

## Question 18:

 Which SQL Edition on RDS has a maximum size of 10 GB?

- 1. Enterprise Edition
- 2. Standard Edition
- 3. Web Edition
- 4. SQL Express(Correct)

*Correct Answer(s):*
 4. SQL Express

**Explanation:**
SQL Express Edition is an entry-level database product used for very small applications. The maximum size of a SQL Express database supported is 10 GB.   https://www.gfi.com/support/products/gfi-archiver/What-are-the-size-limitations-for-SQL-Express-Databases

## Question 19:

 Which statements regarding RDS billing are accurate? (Choose two.)

- 1. You are billed for replication between Multi-AZ instances.
- 2. If you scale provisioned storage mid-month your bill will be pro-rated.(Correct)
- 3. You are billed based on I/O requests per month.(Correct)
- 4. Idle instances are not billed.

*Correct Answer(s):*
 2. If you scale provisioned storage mid-month your bill will be pro-rated.3. You are billed based on I/O requests per month.

**Explanation:**
You are billed based on the amount of storage capacity you have provisioned to your DB Instance. If you change the amount of provisioned storage capacity mid-month your bill will be pro-rated. You are also billed based on I/O requests per month, DB Instance hours, Provisioned IOPS per month, Backup Storage, and data transfer. You are not charged for replication traffic between multi-AZ instances.

## Question 20:

 Is Oracle supported on a T2.Micro RDS instance?

- 1. Oracle is supported on T2.Micro(Correct)
- 2. You can, but it is not a supported configuration
- 3. Only for testing
- 4. Oracle cannot run on a Micro instance

*Correct Answer(s):*
 1. Oracle is supported on T2.Micro

**Explanation:**
Oracle is supported on a T2.Micro instance. For a full list of supported instance types, see this link:  https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Oracle.html#Oracle.Concepts.InstanceClasses

## Question 21:

 What is the minimum number of security groups that must be assigned to an EC2 instance?

- 1. 3
- 2. 0
- 3. 1(Correct)
- 4. 2

*Correct Answer(s):*
 3. 1

**Explanation:**
Each EC2 instance must be assigned to at least one security group. You can assign multiple security groups to the same instance if you want to enforce multiple policies against the instance. The default security policy is assigned if one is not explicitly chosen.

## Question 22:

 Which statement regarding Network ACLs is correct?

- 1. Network ACLs are stateless, and a custom ACL permits all inbound and outbound traffic by default.
- 2. Network ACLs are stateless, and a custom ACL blocks all inbound and outbound traffic by default.(Correct)
- 3. Network ACLs are stateful, and a custom ACL blocks all inbound and outbound traffic by default.
- 4. Network ACLs are stateful, and a custom ACL permits all inbound and outbound traffic by default.

*Correct Answer(s):*
 2. Network ACLs are stateless, and a custom ACL blocks all inbound and outbound traffic by default.

**Explanation:**
VPCs include a default Network ACL that allows all inbound and outbound traffic. You can create your own custom Network ACLs and associate them with a subnet. Custom Network ACLs will deny all inbound and outbound traffic by default. If you do not create a custom Network ACL the default Network ACL is enforced. Each subnet can only be associated with a single Network ACL.  https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html

## Question 23:

 Which AWS service provides temporary storage on disks that are physically attached to the host computer?

- 1. Instance Store(Correct)
- 2. Reduced Redundancy Storage
- 3. EBS
- 4. io1

*Correct Answer(s):*
 1. Instance Store

**Explanation:**
An EC2 instance store is temporary storage on disks that are physically attached to the host computer. This is sometimes referred to as ephemeral storage. There are many use cases for this storage type, such as temporary content or data that is replicated across many instances. The data is discarded when the associated EC2 instance stops or is terminated. If an instance is rebooted the data in the instance store persists. This storage is not meant for valuable, long-term data. You can back this data up periodically to S3 or EBS. SSD instance stores can be used when you need high performance and low latency, but do not need data to persist when the instance is terminated. The EC2 instance store is dedicated to a specific instance. The instance runs on a host computer with other instances, so the actual underlying storage system is most likely shared by multiple instances. The instance store cannot be detached from an instance and attached to another.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html

## Question 24:

 How frequently do provisioned IOPs volumes send metrics to CloudWatch?

- 1. 2 per minute
- 2. 5 per minute
- 3. 1 per minute(Correct)
- 4. 10 per minute

*Correct Answer(s):*
 3. 1 per minute

**Explanation:**
Provisioned IOPS SSD (io1) volumes send one-minute metrics to CloudWatch. Amazon CloudWatch is a monitoring service for AWS cloud resources and applications. You can view metrics for CPU utilization, data transfer, and disk usage activity from Amazon EC2 instances. You can also collect and monitor log files and set alarms. You can even define automated actions if certain events occur. Amazon CloudWatch supports monitoring of many AWE resources, including EC2, DynamoDB tables, and RDS DB instances.

## Question 25:

 You want to create a complete AWS deployment and you must be able to reproduce the complete configuration for Test and Dev environments. You must also be able to maintain version control or configuration changes. Which AWS service allows you to treat your architecture as code?

- 1. CloudTrail
- 2. CloudWatch
- 3. CloudFront
- 4. CloudFormation(Correct)

*Correct Answer(s):*
 4. CloudFormation

**Explanation:**
CloudFormation is an extremely powerful automation tool. CloudFormation can be used to create templates that automate the deployment of AWS resources. This allows you to treat your infrastructure like code. For example, assume you need to build an AutoScaling group with an Elastic Load Balancer, along with an Amazon RDS DB instance and all the required VPC configuration. You can simply create a template, or multiple smaller templates, that define the required AWS resources. When you execute the template(s) all the resources will be created. You could also create copies of the templates for version control, or to create a test or dev environment. The CloudFormation Designer tool makes it easy to create your own templates and edit them.   https://aws.amazon.com/cloudformation/

## Question 26:

 Which statements regarding Multi-AZ RDS failover are correct? (Choose two.)

- 1. Failovers complete nearly instantaneously.
- 2. You can initiate a failover to avoid downtime when rebooting your instance.(Correct)
- 3. During failover the CNAME record is not modified.
- 4. Failovers normally complete within 1 to 2 minutes.(Correct)

*Correct Answer(s):*
 2. You can initiate a failover to avoid downtime when rebooting your instance.4. Failovers normally complete within 1 to 2 minutes.

**Explanation:**
RDS Multi-AZ is used to provide enhanced availability and durability for Database (DB) Instances. A Multi-AZ DB Instance includes a primary DB Instance, and all changes are synchronously replicated to a standby instance in a different Availability Zone (AZ). This ensures that the primary and standby instances run on different hardware, and will be highly available. If a failure occurs RDS will perform an automatic failover to the standby. No manual intervention is required. When a failure occurs AWS will simply change the CNAME record to point at the standby, which becomes the new primary. Failovers normally complete within 1 to 2 minutes. You can also initiate a failover to avoid downtime when rebooting your instance.    https://aws.amazon.com/rds/faqs/

## Question 27:

 You want Lambda functions that are being used to transcode video to complete more quickly. Which configuration change can you make to accomplish this?

- 1. Change the number of vCPUs configured for the Lambda function
- 2. Change the default configuration and allow parallel instances of the Lambda function
- 3. Change the amount of memory configured for the Lambda function(Correct)
- 4. Change the Lambda auto-scaling configuration

*Correct Answer(s):*
 3. Change the amount of memory configured for the Lambda function

**Explanation:**
You should change the amount of memory configured for the Lambda function​. You cannot configure the number of Virtual CPUs. As you change the memory allocation, the CPU resources available automatically scale as well. Lamba functions can run in parallel by default.    https://aws.amazon.com/lambda/faqs/

## Question 28:

 What AWS service can allow you to continuously collect, store, and process streaming data?

- 1. EC2
- 2. Kinesis(Correct)
- 3. DynamoDB
- 4. Redshift

*Correct Answer(s):*
 2. Kinesis

**Explanation:**
Kinesis is a platform that makes it easy to load and analyze streaming data. Web applications, mobile devices, and other applications can generate massive amounts of streaming data. Kinesis can help you continuously collect, store, and process this data.    https://aws.amazon.com/kinesis/data-streams/faqs/

## Question 29:

 Which techniques could be used to encrypt data prior to uploading it to S3 over the Internet? (Choose two.)

- 1. Use the Amazon S3 encryption client with a client-side master key that you provide(Correct)
- 2. AWS KMS Managed Keys (SSE-KMS)
- 3. Use the Amazon S3 encryption client with an AWS provided Customer Master Key (CMK)(Correct)
- 4. Server Side Encryption with Customer Provided keys (SSE-C)

*Correct Answer(s):*
 1. Use the Amazon S3 encryption client with a client-side master key that you provide3. Use the Amazon S3 encryption client with an AWS provided Customer Master Key (CMK)

**Explanation:**
Data at rest can be automatically encrypted by Amazon S3, or you can use client-side encryption prior to uploading your data. The Amazon S3 Encryption Client provides an encryption library that can be used for client-side encryption. You can use a client-side master key or an AWS Key Management Service (KMS) customer key.   https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingClientSideEncryption.html

## Question 30:

 What is the purpose of AWS Consolidated Billing?

- 1. To create a single bill for multiple AWS accounts.(Correct)
- 2. To allow you to accurately identify the source of monthly charges.
- 3. To create a single bill for multiple AWS services under a single account.
- 4. To create a single bill for multiple AWS VPCs.

*Correct Answer(s):*
 1. To create a single bill for multiple AWS accounts.

**Explanation:**
Consolidated Billing can be used with multiple Amazon Web Services (AWS) accounts within your organization. One will be designated the payer account. You will be able to view all AWS charges across all accounts and perform reports on each. This is a free feature. All charges are billed to the payer account. Other accounts are called linked accounts. The linked accounts are independent in every other way. For example, the payer account owner cannot access data belonging to the linked account owners. Each account has its own IAM credentials independent of the other accounts.  https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html

## Question 31:

 What is the purpose of database sharding?

- 1. Combining small databases together
- 2. Breaking a large database into several smaller databases(Correct)
- 3. Clustering multiple unrelated databases together
- 4. Creating and rebuilding database indexes

*Correct Answer(s):*
 2. Breaking a large database into several smaller databases

**Explanation:**
Sharding is used to break large databases into smaller databases. Database Sharding is a “shared-nothing” partitioning scheme for large databases. Sharding enables new levels of database performance and scalability. A good analogy is broken glass. Sharding is like breaking your database down into smaller chunks and spreading them out across a number of distributed servers.

## Question 32:

 What resources are Network ACLs associated with?

- 1. Subnet(Correct)
- 2. VPC
- 3. RDS Instances
- 4. EC2 Instances

*Correct Answer(s):*
 1. Subnet

**Explanation:**
A Network access control list (ACL) is a firewall that can be used to secure a VPC. You can configure Network ACLs in addition to security groups to enhance security. For example, you could have different Security Group configurations associated with instances in a subnet. But there may be certain traffic that you know you need to block across every instance on a subnet, and you could use a Network ACL to accomplish that goal. VPCs include a default Network ACL that allows all inbound and outbound traffic. You can create your own custom Network ACLs and associate them with a subnet. Custom Network ACLs will deny all inbound and outbound traffic by default. If you do not create a custom Network ACL the default Network ACL is enforced. Each subnet can only be associated with a single Network ACL. The rules are interrogated based on the rule number, and the first matching rule is enforced.

## Question 33:

 You have detached an Elastic Network Interface (ENI) from an instance. You plan to now attach it to an instance that is currently stopped. What is it called when you attach an ENI to a stopped instance?

- 1. Cold Attach
- 2. Suspended Attach
- 3. Hot Attach
- 4. Warm Attach(Correct)

*Correct Answer(s):*
 4. Warm Attach

**Explanation:**
You can attach an ENI to an instance when it is stopped. This is called a warm attach. You can also attach an ENI to a running instance (hot attach), or when the instance is being launched (cold attach). Elastic network interfaces (ENI) can be attached to an instance in a VPC. The ENI will have one or more IPv4 or IPv6 addresses and a MAC address. ENIs can be created an attached to an instance. They can also be detached from an instance and subsequently attached to another instance.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html

## Question 34:

 You have a large amount of data that you want to copy from a source DB into an RDS SQL instance. You plan to use the SQL Server bulk copy feature to accomplish this task. Which statements regarding the SQL Server Bulk Copy feature are correct? (Choose two.)

- 1. Bulk Copy is an efficient way to migrate data.(Correct)
- 2. It can write data to an ASCII file.(Correct)
- 3. Bulk copy uses a bak file to store data.
- 4. The target database schema will be created automatically.

*Correct Answer(s):*
 1. Bulk Copy is an efficient way to migrate data.2. It can write data to an ASCII file.

**Explanation:**
The SQL Server bulk copy feature can be used to efficiently copy data from a source DB into an RDS SQL instance. Bulk copy writes to a data file that exists on the source machine. It can be written as an ASCII file. Bulk copy is then used to push the data to a destination DB instance. Before you use bulk copy, you must first import your database schema to the destination DB instance.  https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/SQLServer.Procedural.Importing.Snapshots.html

## Question 35:

 Which of the following solutions can help to run jobs that have many parallel or sequential steps across multiple applications? Assume that the job may also require human interaction steps.

- 1. SNS
- 2. SQS
- 3. SWF(Correct)
- 4. Elastic Transcoder

*Correct Answer(s):*
 3. SWF

**Explanation:**
Simple Workflow Service (SWF) is a great way to coordinate many tasks that occur across multiple applications. It provides full control over tasks, including tracking their progress and maintaining their state. It can automatically recover and retry a task if it fails. This allows developers to focus on application functionality instead of managing the infrastructure plumbing.  https://aws.amazon.com/swf/

## Question 36:

 You are planning on running Orace on RDS, but need to ensure that you can properly monitor it. Which statements regarding this scenario are correct? (Choose two.)

- 1. Statspack is not available on RDS
- 2. Oracle tuning and diagnostic packs are supported on all editions
- 3. Oracle tuning and diagnostic packs are available on RDS(Correct)
- 4. Oracle tuning and diagnostic packs require Oracle Enterprise Edition(Correct)

*Correct Answer(s):*
 3. Oracle tuning and diagnostic packs are available on RDS4. Oracle tuning and diagnostic packs require Oracle Enterprise Edition

**Explanation:**
Oracle tuning and diagnostic packs are available on RDS, as they are with conventionally-hosted databases. You must be running Oracle Enterprise Edition and have the appropriate licensing.

## Question 37:

 You have a group of four EC2 instances that serve a similar function.You want the workload to be evenly distributed across these instances. You also want to ensure that they are highly-available. Instances exist in multiple regions. Which options could be used accomplish your goals? (Choose two.)

- 1. Use ELB to distribute with workload across instances in multiple availability zones.(Correct)
- 2. Use ELB to distribute with workload across instances in multiple regions.
- 3. Use Route 53 DNS failover to enable failover across availability zones.
- 4. Use Route 53 DNS failover to enable failover across regions.(Correct)

*Correct Answer(s):*
 1. Use ELB to distribute with workload across instances in multiple availability zones.4. Use Route 53 DNS failover to enable failover across regions.

**Explanation:**
Route53 should only route traffic to Web Servers that are healthy and functioning properly. You can associate health checks with your resource DNS record sets. When a health check fails, Route53 routes traffic away from the associated resource. This is referred to as DNS failover. Route 53 DNS failover includes integration with Elastic Load Balancer (ELB). If your application is unavailable in a region, Route 53 will not route to that region.

## Question 38:

 Which statement regarding Lambda is correct?

- 1. Lambda uses Elastic Beanstalk to deploy resources that can run your code.
- 2. Lambda allows you to run code on EC2 instances.
- 3. Lambda never charges you for idle resources.(Correct)
- 4. You have root level access to instances that run your Lambda functions.

*Correct Answer(s):*
 3. Lambda never charges you for idle resources.

**Explanation:**
AWS Lambda lets you run code without a virtual machine, and you only pay for the compute time you consume. So if you don’t need a server on all day every day you don’t have to set one up. And here is no charge when your code is not running. This can save a significant amount of money. You simply upload your code and Lambda takes it from there, including scaling and high availability.   https://aws.amazon.com/documentation/lambda/

## Question 39:

 You have a large amount of processing that needs to be performed using EC2 instances. You want to temporarily increase the number of instances to get the work finished, and will terminate these instances as soon as the task is complete. What type of instance would be most cost effective for this use case?

- 1. Reserved instances
- 2. Dedicated Hosts
- 3. On demand instances
- 4. Spot Instances(Correct)

*Correct Answer(s):*
 4. Spot Instances

**Explanation:**
EC2 Spot instances are a cost-efficient option when you need computing resources. Spot Instances allow you to bid on spare Amazon EC2 computing capacity at a discount. This can allow you to significantly reduce the cost of running your applications, and temporarily scale up your computing capacity and throughput. Spot instances only run if your bid price exceeds the Spot price. They offer all the same performance and reliability characteristics of any other EC2 instance, but can reduce your operating costs by up to 50-90%. They are useful for applications such as stateless web services, image rendering, big data analytics and massively parallel computations because of their temporary nature, and the high scalability.

## Question 40:

 What type of database solution does RDS provide?

- 1. Relational database engines(Correct)
- 2. NoSQL
- 3. High-performance streaming data
- 4. Petabyte-scale data warehouse

*Correct Answer(s):*
 1. Relational database engines

**Explanation:**
Amazon Relational Database Service (Amazon RDS) is a relational database service in the cloud. It makes it easy to create a database that is easy to manage and highly scalable. This can help free administrators up from time consuming database management tasks. RDS provides six database engines to choose from, including Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle, and Microsoft SQL Server.

## Question 41:

 Which of the following statements regarding resource tagging is correct?

- 1. It is possible to terminate, stop, or delete a resource based solely on its tags
- 2. It is not possible to terminate, stop, or delete a resource based on its tags and resource identifier
- 3. It is not possible to terminate, stop, or delete a resource based solely on its tags(Correct)

*Correct Answer(s):*
 3. It is not possible to terminate, stop, or delete a resource based solely on its tags

**Explanation:**
It is not possible to terminate, stop, or delete a resource based solely on its tags. The resource identifier must also be specified. The link below includes a great example of how to use a resource identifier and tag to delete snapshots.

## Question 42:

 Which of the following are block storage devices supported by AWS? (Choose two.)

- 1. Instance Store(Correct)
- 2. Redshift
- 3. EBS(Correct)
- 4. S3

*Correct Answer(s):*
 1. Instance Store3. EBS

**Explanation:**
Block storage devices manage data in sequences of bytes or bits. These are referred to as blocks. Traditional hard disks are the best known example of a block storage device. EC2 supports two types of block devices: Instance Store and EBS. An EC2 instance store is temporary storage on disks that are physically attached to the host computer. There are many use cases for this storage type, such as temporary content or data that is replicated across many instances. The data is discarded when the associated EC2 instance stops or is terminated. Elastic Block Storage provides virtual “Disks” for your EC2 instances. Think of EBS as raw, unformatted block storage volumes. They are formatted with a file system, such as NTFS or EXt, by the operating system of the instance.  https://aws.amazon.com/ebs/

## Question 43:

 In a Multi-AZ RDS deployment, what role does the secondary instance provide?

- 1. Reads can be performed against the secondary
- 2. No reads or writes can be performed against the secondary instance(Correct)
- 3. Maintenance such as changing an instance size cannot be performed on the secondary instance
- 4. Reads and Writes can be performed against the secondary

*Correct Answer(s):*
 2. No reads or writes can be performed against the secondary instance

**Explanation:**
No reads or writes can be performed against the secondary instance​. A Read Replica can be used to offload read operations to another instance. Maintenance can be performed on the secondary instance, including backups and changing the instance type. This allows you to avoid the downtime typically associated with this type of maintenance.   https://aws.amazon.com/rds/details/multi-az/

## Question 44:

 Which statements regarding EC2 Instance and System Status Checks are correct? (Choose two.)

- 1. System Status Checks are related to the health of the actual physical host that your instances run on.(Correct)
- 2. Instance Status Checks show issues that must be resolved by the customer and not AWS.(Correct)
- 3. Instance Status Checks show issues will be resolved by AWS staff.
- 4. Stopping and restarting an instance will not resolve an issue shown in the System Status Checks.

*Correct Answer(s):*
 1. System Status Checks are related to the health of the actual physical host that your instances run on.2. Instance Status Checks show issues that must be resolved by the customer and not AWS.

**Explanation:**
EC2 Status checks are broken down into two categories: System Status Checks and Instance Status Checks. System Status Checks are related to the health of the actual physical host that your instances run on. This means that the problem is something that AWS must work to resolve. Possible causes of a System Status Check failure include loss of network connectivity, power loss, or hardware or software issues on the host. You can simply wait for AWS to resolve these issues, or you can take action by stopping and restarting the instance. This will bring the instance back up on another host. This is not an option with instance store, so in this case you can terminate and replace the instance.  Instance Status Checks are related to the health of an EC2 instance itself. This means that the problem must be resolved by whoever manages the instance, and is not going to be addressed by AWS.  Possible issues include incorrect network or startup configuration, memory is exhausted, file system corruption, or an incompatible kernel. To resolve these issues you can try re-booting the instance. If that does not work you must repair the issue in the Guest Operating System.    https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-system-instance-status-check.html

## Question 45:

 What is the purpose of AWS public data sets?

- 1. To make the operation of RedShift more efficient.
- 2. To allow easy, free access to massive public data sets.(Correct)
- 3. To allow you to publish your own datasets publicly.

*Correct Answer(s):*
 2. To allow easy, free access to massive public data sets.

**Explanation:**
AWS hosts a variety of public data sets that are available free of charge. Examples include large datasets such as the mapping of the Human Genome, SpaceNet, Landsat, ant others. Anyone can access these datasets via the AWS centralized data repository. You can analyze the data using EC2 instances or Amazon EMR (Hosted Hadoop) clusters.   https://aws.amazon.com/public-datasets/

## Question 46:

 Which of the following methods can be used to manage IAM? (Choose all that apply.)

- 1. API(Correct)
- 2. Existing SDK Libraries(Correct)
- 3. CLI(Correct)
- 4. AWS Management Console(Correct)

*Correct Answer(s):*
 1. API2. Existing SDK Libraries3. CLI4. AWS Management Console

**Explanation:**
IAM can be managed using any of these methods. Identity and Access Management (IAM) is used to control users groups, and roles within AWS. This is ideal for organizations that have multiple users and systems in the AWS cloud. Within IAM you can set password retention policies, and configure mutli-factor authentication. You can even create fine grained access control rules, such as the time of day a user can access a resource, or acceptable source IPs. You can also enable mobile applications to securely access AWS resources. IAM can be integrated with existing Active Directory installations.

## Question 47:

 You have a group of EC2 instances that belong to the development team, and other instances that belong to the production team. What could you use to categorize and organize these resources?

- 1. SWF
- 2. ARN
- 3. Tags(Correct)
- 4. SQS

*Correct Answer(s):*
 3. Tags

**Explanation:**
Tags can be used to organize your AWS resources. This is helpful when you have similar resources that you need to categorize. For example, you may have a group of EC2 instances that belong to the development team, and other instances that belong to the production team. You could tag those instances to keep them organized, and to assign roles appropriately. Tags can only be assigned to an object that already exists.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html

## Question 48:

 What service does Elastic Beanstalk provide?

- 1. SSD based storage for Elastic Container Service
- 2. Load balancing across EC2 instances running in different availability zones
- 3. Auto-scaling or resources for standalone EC2 instances
- 4. Automatic deployment of AWS resources to execute code provided by the customer(Correct)

*Correct Answer(s):*
 4. Automatic deployment of AWS resources to execute code provided by the customer

**Explanation:**
AWS Elastic Beanstalk can be used to deploy web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS. It is designed for developers to upload their code, which is then inspected by Amazon. Amazon then provisions the required resources for you, including capacity provisioning, load balancing, auto-scaling, and application health monitoring. You can access the underlying resources at any time and maintain full administrative control.

## Question 49:

 How does ELB help with application availability? (Choose two.)

- 1. By automatically rebooting instances if a host fails
- 2. By distributing traffic across instances in multiple AZs(Correct)
- 3. By performing periodic health checks on instances(Correct)
- 4. By using Route 53 failover routing to spread traffic across instances

*Correct Answer(s):*
 2. By distributing traffic across instances in multiple AZs3. By performing periodic health checks on instances

**Explanation:**
Elastic Load Balancing (ELB) can be used to distribute incoming traffic across multiple EC2 instances automatically. These instances can be in different availability zones. The ELB Classic Load Balancer is ideal for simple load balancing of traffic across multiple EC2 instances. The Application Load Balancer is ideal for more complex load balancing needs. The load balancer also protects against operating system level failures by performing periodic health checks. ELB will not route traffic to an instance that has failed a health check. If the health issue is resolved ELB will resume sending traffic to it. The load balancer uses a listener to check for incoming connection requests. Clients will connect to it over a specified protocol and port number. On the back end it distributes the connections across multiple instances.    https://docs.aws.amazon.com/elasticloadbalancing/2012-06-01/APIReference/API_HealthCheck.html

## Question 50:

 You have 20 TB of on-premise data that you want to store on Amazon Glacier. You have a slow Internet connection and uploading the data will take a long time. How can you quickly get this data into Glacier?

- 1. Use Snowball to place the data directly into Glacier.
- 2. Use Snowball to get the data into S3. Use a lifecycle policy to migrate the data to Glacier.(Correct)
- 3. Use import/export to place the data directly into Glacier.
- 4. Use a multipart upload to accelerate file transfer.

*Correct Answer(s):*
 2. Use Snowball to get the data into S3. Use a lifecycle policy to migrate the data to Glacier.

**Explanation:**
Direct import into Amazon Glacier is no longer supported. For larger import jobs you can perform an Amazon S3 import, and use a lifecycle policy to archive the objects to Glacier. https://docs.aws.amazon.com/AWSImportExport/latest/DG/AWSImportExport-dg.pdf

## Question 51:

 You have placed highly sensitive data in an S3 bucket and need to protect it. What mechanisms can you use to restrict access? (Choose three.)

- 1. Configure IAM policies(Correct)
- 2. Configure CloudWatch protection on the bucket
- 3. Configure the bucket policy(Correct)
- 4. Configure an S3 ACL(Correct)
- 5. Configure restrictive IAM federations

*Correct Answer(s):*
 1. Configure IAM policies3. Configure the bucket policy4. Configure an S3 ACL

**Explanation:**
You can protect an S3 bucket using Identity and Access Management (IAM) policies, bucket policies, Access Control Lists (ACLs) and query string authentication. For more, see: https://aws.amazon.com/blogs/security/iam-policies-and-bucket-policies-and-acls-oh-my-controlling-access-to-s3-resources/

## Question 52:

 How can you efficiently assign permissions to a large number of IAM users in the most secure manner possible?

- 1. Reduce privileges on individual IAM users
- 2. Create a lenient policy, apply it to all users, and tighten it as needed
- 3. Create IAM groups(Correct)
- 4. Use policy conditions to define which users get certain roles

*Correct Answer(s):*
 3. Create IAM groups

**Explanation:**
IAM Groups can be used to simplify user management. Groups should relate to job functions, such as administrators, developers, helpdesk, etc. You will then assign permissions to each group, and pick which users are members of each group. This makes it easy to change permissions for everyone in a group quickly and easily.   https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html

## Question 53:

 Which statements regarding EBS Snapshots are correct? (Choose two.)

- 1. If you have multiple snapshots that are in the pending (in-progress) state, it can affect the performance of the instance.(Correct)
- 2. A maximum of 5 pending snapshots can exist per a single gp2, io1, or Magnetic volume.(Correct)
- 3. Multiple snapshots cannot be in progress at the same time.
- 4. Snapshots are stored on EC2, and cannot impact the performance of the instance.

*Correct Answer(s):*
 1. If you have multiple snapshots that are in the pending (in-progress) state, it can affect the performance of the instance.2. A maximum of 5 pending snapshots can exist per a single gp2, io1, or Magnetic volume.

**Explanation:**
You can take snapshots of an EBS volume. The snapshot is a point-in-time picture of the volume that is stored in S3. Like all data stored on S3, it will exist redundantly in multiple Availability Zones. Snapshots can be used to create multiple new EBS volumes. This is useful if you need to move a volume to a different AZ. You can create a new volume based on the snapshot, and it will be an exact copy of the original. If you have multiple snapshots that are in the pending (in-progress) state, it can affect the performance of the instance. A maximum of 5 pending snapshots can exist per a single gp2, io1, or Magnetic volume. Only 1 pending snapshot at a time is allowed for a single st1 or sc1 volume.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-snapshot.html

## Question 54:

 Which AWS Service records API calls to your account?

- 1. AWS Inspector
- 2. CloudFormation
- 3. CloudWatch
- 4. CloudTrail(Correct)
- 5. IAM

*Correct Answer(s):*
 4. CloudTrail

**Explanation:**
AWS CloudTrail can be used to monitor API calls for your account. You can analyze log files to view past activity. Logs for API calls include the identity of the API caller, the time, and the source IP address. It also shows the request parameters, and the response returned by the AWS service. CloudTrail records API calls to the AWS Management Console, AWS SDKs, command line tools, and higher level tools including AWS CloudFormation.  https://aws.amazon.com/cloudtrail/

## Question 55:

 When you create a new user in IAM what permissions do they have be default?

- 1. Console only
- 2. Read-only
- 3. Administrator
- 4. None(Correct)

*Correct Answer(s):*
 4. None

**Explanation:**
New users in IAM do not have any permissions by default. You can grant permissions by assigning IAM policies to the users.   https://docs.aws.amazon.com/IAM/latest/UserGuide/access_controlling.html

## Question 56:

 Which of the following statements are incorrect?

- 1. RDS stands for Relational Database Service
- 2. EBS stands for Elastic Block Storage(Correct)
- 3. EC2 stands for Elastic Compute Cloud
- 4. S3 stands for Simple Storage Service

*Correct Answer(s):*
 2. EBS stands for Elastic Block Storage

**Explanation:**
Elastic Block Store provides virtual “Disks” for your EC2 instances. Think of EBS as raw, unformatted disks. They are formatted with a file system, such as NTFS or ESXt, by the instance. Multiple EBS devices can be supported on the same EC2 instance, just like multiple disks on a VM.   https://aws.amazon.com/ebs/

## Question 57:

 Can IAM be used to control access to the operating system of an EC2 instance?

- 1. Yes, but only if MFA is in use
- 2. No(Correct)
- 3. Yes, but only if a federation is configured
- 4. Yes

*Correct Answer(s):*
 2. No

**Explanation:**
Access to EC2 instances is controlled using SSH keys, Operating System passwords, and security groups. IAM does not provide any controls that can be used to allow or deny access to the operating system of a specific instance.

## Question 58:

 You have configured Multi-AZ RDS to protect your database instance from an Availability Zone level failure. Which statement regarding this configuration is correct?

- 1. The standby instance can be used to perform reads and writes to reduce the workload on the primary instance.
- 2. The standby instance can be used to perform only reads to reduce the workload on the primary instance.
- 3. Maintenance must be performed on the primary instance only, and the changes are replicated to the secondary.
- 4. The standby instance cannot perform reads or writes, and is only there for failover purposes.(Correct)

*Correct Answer(s):*
 4. The standby instance cannot perform reads or writes, and is only there for failover purposes.

**Explanation:**
Multi-AZ RDS is used to provide enhanced availability and durability for Database (DB) Instances. A Multi-AZ DB Instance includes a primary DB Instance, and all changes are synchronously replicated to a standby instance in a different Availability Zone (AZ). This ensures that the primary and standby instances run on different hardware, and will be highly available. If a failure occurs RDS will perform an automatic failover to the standby. The standby instance cannot perform any read or write database operations.  https://aws.amazon.com/rds/details/multi-az/

## Question 59:

 You have an application running behind an Elastic Load Balancer (ELB). You want to ensure that a user will continuously use the same instance rather than simply being directed to the instance with the smallest load. Which ELB option should you use?

- 1. A preferential affinity load balancer
- 2. A Classic Load Balancer with Sticky Sessions enabled(Correct)
- 3. Configure IAM-aware Load Balancing

*Correct Answer(s):*
 2. A Classic Load Balancer with Sticky Sessions enabled

**Explanation:**
The classic load balancer operates at layer 4 of the OSI model. It listens for traffic on a specific layer 4 port, and then distributes the traffic to multiple instances on the back end. For example – assume an ELB receives a request from a client on TCP port 80 (HTTP). The ELB will have a pool of backend servers that it will use to fulfill the client requests. By default, a Classic Load Balancer routes each request independently to the registered instance with the smallest load. The sticky session feature can be used to bind user sessions to a specific instance. This is important if you want to ensure that a user will continuously use the same instance. You can configure ELB to either use application cookies, or create its own cookie. The cookie is then used to track which backend server the user traffic should be forwarded to.   https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-sticky-sessions.html

## Question 60:

 Are in-place atomic updates supported on Dynamo DB?

- 1. No
- 2. Yes(Correct)

*Correct Answer(s):*
 2. Yes

**Explanation:**
Amazon DynamoDB supports fast in-place atomic updates. These are used to update values, such as a website counter. The atomic counter increments or decrements a numeric attribute in a row using a single API call. You can also perform atomic add or remove operations to sets, lists, or maps.   https://aws.amazon.com/dynamodb/faqs/

## Question 61:

 AWS uses a shared-responsibility model for security. Some aspects are your responsibility, while others are handled by Amazon. Which aspects are Amazon responsible for? (Choose two.)

- 1. Physical facility access(Correct)
- 2. Encryption of storage devices and management of keys
- 3. Retiring old hardware and ensuring that it does not contain sensitive data(Correct)
- 4. Maintenance and hardening of the guest Operating System.

*Correct Answer(s):*
 1. Physical facility access3. Retiring old hardware and ensuring that it does not contain sensitive data

**Explanation:**
AWS uses a shared security responsibility model. This means that certain aspects of security are Amazon's responsibility, while others are up to the customer. There are many examples of these responsibilities that are too numerous to list here, but some good examples follow below. AWS provides "security of the cloud". This relates to physical security of AWS datacenters, secure retirement of old hardware, border firewall, and other similar concerns. The customer provides "security in the cloud". The customer must ensure that the guest operating system running on instances is properly updated and is hardened. Security groups must be created to control which types of traffic are permitted. The customer manages IAM credentials and MFA to protect the AWS console.   https://aws.amazon.com/compliance/shared-responsibility-model/

## Question 62:

 Which solution provides a cloud based email service?

- 1. SQS
- 2. ST1
- 3. SES(Correct)
- 4. SWF

*Correct Answer(s):*
 3. SES

**Explanation:**
Simple Email Service (SES) is a cloud based email service. SES is a pay as you go service with no minimum commitments. It is commonly used for marketing and transactional emails (such as order confirmations and shipping notices).   https://aws.amazon.com/ses/

## Question 63:

 Which of the below are viable DDoS mitigation techniques? (Choose Three.)

- 1. Configure alerts in CloudWatch(Correct)
- 2. Use dedicated instances to run your instance on a specific host, separate from your other instances
- 3. Configure an Elastic Load Balancer with auto scaling groups(Correct)
- 4. Modify the Operating System Firewall Rules to block the attack
- 5. Distribute content to multiple locations using CloudFront(Correct)

*Correct Answer(s):*
 1. Configure alerts in CloudWatch3. Configure an Elastic Load Balancer with auto scaling groups5. Distribute content to multiple locations using CloudFront

**Explanation:**
CloudFront filters requests to ensure that only valid HTTP(S) requests will be forwarded to backend hosts. CloudFront can also block attacks originating from a particular geographic location. CloudFront is a Content Delivery network, or CDN. CloudFront leverages edge locations that are spread across the globe to deliver websites, video content, and other web assets from the nearest edge location. This improves the overall performance of these services. Elastic Load Balancing (ELB) automatic distributes application across multiple EC2 instances in multiple Availability Zones. This makes It more difficult to overload a single EC2 instance. ELB only supports valid TCP requests, which prevents common DDoS (UDP and SYN floods) from reaching EC2 instances. Amazon CloudWatch is a monitoring service for AWS cloud resources and applications. You can view metrics for CPU utilization, data transfer, and disk usage activity from Amazon EC2 instances. You can also collect and monitor log files and set alarms. You can even define automated actions if certain events occur. Amazon CloudWatch supports monitoring of many AWE resources, including EC2, DynamoDB tables, and RDS DB instances. Dedicated Instances are not a viable mitigation technique. Dedicated Instances allow a customer to run EC2 instances that on dedicated hardware. Dedicated Instances will never run on hardware that is shared between multiple customers. However a single customer may have many instances running on the same physical host.  https://aws.amazon.com/answers/networking/aws-ddos-attack-mitigation/

## Question 64:

 An on-demand EC2 instance is no longer required, but you do not want to stop or terminate it just in case somebody changes their mind. You leave the instance running but it is idle. Will charges be incurred for this instance?

- 1. You will still be billed for this instance unless you stop or terminate it.(Correct)
- 2. You will be billed until the end of the current month if you terminate the instance.
- 3. You will be billed for this instance even if it stopped. To avoid billing you should terminate the instance.
- 4. You are not billed for idle VMs.

*Correct Answer(s):*
 1. You will still be billed for this instance unless you stop or terminate it.

**Explanation:**
On-Demand instances let you pay for compute capacity by the hour or second. There is no long-term commitment like you have with a reserved instance. You will be billed any time your instances are in a "running" state. If you stop or terminate the instance you will no longer be billed.

## Question 65:

 Which AWS service provides monitoring and alerting services for AWS cloud resources and applications?

- 1. IAM
- 2. CloudWatch(Correct)
- 3. CloudTrail
- 4. Trusted Advisor
- 5. CloudFormation
- 6. AWS Inspector

*Correct Answer(s):*
 2. CloudWatch

**Explanation:**
Amazon CloudWatch is a monitoring service for AWS cloud resources and applications. You can view metrics for CPU utilization, data transfer, and disk usage activity from Amazon EC2 instances. You can also collect and monitor log files and set alarms. You can even define automated actions if certain events occur. Amazon CloudWatch supports monitoring of many AWS resources, including EC2, DynamoDB tables, and RDS DB instances. EC2 instances are enabled for basic monitoring by default. This provides data in 5-minute periods at no charge. For an additional charge you can enable detailed monitoring on an instance. This provides data in 1-minute periods.  https://aws.amazon.com/cloudwatch/

## Question 66:

 You want to create a point-in-time picture of an EBS volume that is stored in S3. It must be stored redundantly in multiple Availability Zones. Which service should you use?

- 1. S3 LifeCycle Management
- 2. EBS Snapshot(Correct)
- 3. Multi-AZ RDS
- 4. S3 Version Control

*Correct Answer(s):*
 2. EBS Snapshot

**Explanation:**
You can take snapshots of an EBS volume. The snapshot is a point-in-time picture of the volume that is stored in S3. Like all data stored on S3, it will exist redundantly in multiple Availability Zones. Snapshots can be used to create multiple new EBS volumes. This is useful if you need to move a volume to a different AZ. You can create a new volume based on the snapshot, and it will be an exact copy of the original. Snapshots are incremental in nature, meaning that only blocks that have changed since the last snapshot are saved in the new snapshot. However you can still delete older snapshots at any time and it does not affect your ability to restore based on newer snapshots.  When you take an EBS snapshot the required blocks need to be copied to S3. This can take a significant amount of time, especially if many blocks have changed since the last snapshot. An in-progress snapshot is based on the state of the instance at the exact moment you took the snapshot. It is not affected by ongoing reads and writes to the volume. This might exclude cached data, which could create a data consistency issue when you try to restore. Ideally you should quiesce changes to the volume prior to taking the snapshot. You can also un-mount the volume to ensure an application-consistent snapshot.    https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html

## Question 67:

 When is data on ephemeral storage (EC2 instance store) automatically deleted? (Choose two.)

- 1. When the instance is terminated.(Correct)
- 2. When the instance is stopped.(Correct)
- 3. When the instance is backed up.
- 4. When the instance is rebooted.
- 5. When the instance store is attached to another instance.

*Correct Answer(s):*
 1. When the instance is terminated.2. When the instance is stopped.

**Explanation:**
EC2 instance store is also referred to as ephemeral storage. It is important to know this for the exam. An EC2 instance store is temporary storage on disks that are physically attached to the host computer. There are many use cases for this storage type, such as temporary content or data that is replicated across many instances. The data is discarded when the associated EC2 instance stops or is terminated. If an instance is rebooted the data in the instance store persists. This storage is not meant for valuable, long-term data. You can back this data up periodically to S3 or EBS. SSD instance stores can be used when you need high performance and low latency, but do not need data to persist when the instance is terminated. The instance store cannot be detached from an instance and attached to another.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html

## Question 68:

 What is the maximum response time for a production system down case on the Business Plan?

- 1. 30 minutes
- 2. 10 minutes
- 3. 1 day
- 4. 1 hour(Correct)

*Correct Answer(s):*
 4. 1 hour

**Explanation:**
The maximum response time is one hour.    https://aws.amazon.com/premiumsupport/features/

## Question 69:

 You have created an S3 bucket, and plan to store valuable data such as photos and video content in it. How is this data actually stored?

- 1. Copies are stored in a single facility in a single region.
- 2. Copies are stored in multiple regions.
- 3. Copies are stored in one region and replicated to the CDN as a backup.
- 4. Copies are stored in multiple facilities in the same region.(Correct)

*Correct Answer(s):*
 4. Copies are stored in multiple facilities in the same region.

**Explanation:**
When you create a bucket you can choose the region. The objects in your bucket never leave that region. Within the region your objects are stored on multiple facilities. To store data in S3 you will first create a container called a Bucket.  https://aws.amazon.com/s3/faqs/

## Question 70:

 Which statement regarding the scope of virtual networks in AWS is correct?

- 1. A subnet created in a VPC is local to an Availability Zone.(Correct)
- 2. Elastic IP addresses are global objects that can be used across regions.
- 3. A VPC is local to an availability zone.
- 4. Route 53 DNS records are specific to a region.

*Correct Answer(s):*
 1. A subnet created in a VPC is local to an Availability Zone.

**Explanation:**
A VPC spans all the Availability Zones in the region that it is created in. After creating a VPC you can add subnets that are local to an Availability Zone. When you create a subnet, you specify the CIDR block for the subnet (also known as a subnet mask). Each subnet must reside entirely within one Availability Zone and cannot span zones. Route53 DNS Records are global objects, and are available across regions. Elastic IP addresses are regional objects, and can only be used in the region in which they were created.   https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html

## Question 71:

 You have web content stored in an S3 bucket in the US-East-1 region. Users all over the world will be accessing this content, and you would like to place copies of the frequently accessed data in edge locations to reduce latency for distant users. Which AWS product can help?

- 1. Elastic Beanstalk
- 2. CloudFront(Correct)
- 3. CloudFormation
- 4. Transfer Acceleration

*Correct Answer(s):*
 2. CloudFront

**Explanation:**
CloudFront is a Content Delivery network, or CDN. CloudFront leverages edge locations that are spread across the globe to deliver websites, video content, and other web assets from the nearest edge location. This improves the overall performance of these services.  CloudFront supports other AWS features such as S3, EC2, Amazon Elastic Load Balancing, and Route 53.    https://aws.amazon.com/cloudfront/

## Question 72:

 Which statements regarding NAT are correct? (Choose two.)

- 1. You do not have root level access to a NAT instance
- 2. A NAT Instance is created based on a special AMI(Correct)
- 3. A NAT gateway is a managed service, a NAT instance is not(Correct)
- 4. You have root level access to a NAT Gateway

*Correct Answer(s):*
 2. A NAT Instance is created based on a special AMI3. A NAT gateway is a managed service, a NAT instance is not

**Explanation:**
Network Address Translation (NAT) is a widely used network standard that translates one IP address to another. AWS instances are often created with private IP addresses that are not routable on the Internet. When an instance with a private IP address needs to send traffic to the Internet, the traffic is routed to the NAT instance. The NAT instance removes the original source IP address and replaces it with the public Elastic IP (EIP) address of the NAT instance. One IP address is used to represent many instances. The NAT instance keeps track of which conversation belongs to each instance by using different port numbers. Amazon provides AMIs that are configured to run as NAT instances. The NAT instance can work NAT instances are not highly available. You must use a script to manage failover between instances. NAT Gateways are a good alternative if high availability is required.

## Question 73:

 How can you set up zone apex support for Route 53, and point to an ELB? For example, a zone apex could be "trainertests.com". It is the root domain for a site.

- 1. By using an alias record in Route 53(Correct)
- 2. By using an MX record in Route 53
- 3. By using an A record in Route 53
- 4. By using an NS record in Route 53

*Correct Answer(s):*
 1. By using an alias record in Route 53

**Explanation:**
Route 53 offers Alias records. This is a DNS record type that is specific to AWS. Alias records can map to ELB, CloudFront distributions, Elastic Beanstalk, or Amazon S3 buckets. Alias records are similar to CNAME records because you are mapping one DNS name to a different target. You can map a zone apex using alias records. For example, you could create an alias record to map trainertests.com to an ELB DNS name. The IP address associated with an ELB can change during scale up or scale down. Because this address is hidden behind the alias record this process is transparent to end users, and does not result in the need for a DNS record  change.

## Question 74:

 Can you control user access to tasks and resources without configuring IAM?

- 1. no(Correct)
- 2. yes

*Correct Answer(s):*
 1. no

**Explanation:**
Identity and Access Management (IAM) is used to control users groups, and roles within AWS. This is ideal for organizations that have multiple users and systems in the AWS cloud. Within IAM you can set password retention policies, and configure mutli-factor authentication. You can even create fine grained access control rules, such as the time of day a user can access a resource, or acceptable source IPs. You can also enable mobile applications to securely access AWS resources. IAM can be integrated with existing Active Directory installations.

## Question 75:

 You have an application that runs on EC2, and you want to provide availability by maintaining EC2 instances in different availability zones. EC2 instances should automatically be created and terminated as the workload increases or decreases.

- 1. Elastic Beanstalk
- 2. Auto Scaling Group(Correct)
- 3. ELB(Correct)
- 4. SQS

*Correct Answer(s):*
 2. Auto Scaling Group3. ELB

**Explanation:**
Auto Scaling ensures that you have the proper amount of EC2 instances to handle the workload generated by your application. You can associate an auto scaling group with an Elastic Load Balancer to distribute workload across instances in multiple Availability Zones.  https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-load-balancer.html

## Question 76:

 You must ensure that you have the proper amount of EC2 instances to handle the workload generated by your application. You want to specify the minimum and maximum number of instances that can exist, and create criteria that determines when new instances should be created.

- 1. Lambda Function
- 2. Elastic Load Balancer
- 3. Auto Scaling Group(Correct)
- 4. DynamoDB Table

*Correct Answer(s):*
 3. Auto Scaling Group

**Explanation:**
AutoScaling ensures that you have the proper amount of EC2 instances to handle the workload generated by your application. The AutoScaling Group specifies the minimum and maximum number of instances that can exist in the AutoScaling group. You can also specify desired number of instances. AutoScaling will automatically launch or terminate instances based on the needs of your application. The AutoScaling group uses a launch configuration as a template for its EC2 instances. The launch configuration specifies the AMI that should be used to create the instances. It also allows you to specify the instance type, key pair, security groups, and block device mapping for your instances.  https://aws.amazon.com/autoscaling/faqs/

## Question 77:

 You have attached multiple IAM policies to the same entity. A request to complete an operation is allowed by Policy1, but is denied by Policy2. What is the result of this scenario?

- 1. Multiple policies cannot be assigned to a single entity.
- 2. The deny statement overrides any allow statements.(Correct)
- 3. The allow statement overrides any deny statements.
- 4. The first matching statement analyzed will be applied.

*Correct Answer(s):*
 2. The deny statement overrides any allow statements.

**Explanation:**
The deny statement overrides any allow statements. Policy2 explicitly denies the operation. Policy1 returns an allow, but the explicit deny from Policy2 overrides the allow from Policy1. For a great example of how this works see the link below.   https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html#AccessPolicyLanguage_Interplay

## Question 78:

 What is the impact on I/O operations while you take a database snapshot?

- 1. I/O operations may be briefly suspended for a few minutes(Correct)
- 2. I/O is halted while the instance reboots
- 3. There is no impact
- 4. I/O operations will be handled by a replica if the DB exists in multiple availability zones

*Correct Answer(s):*
 1. I/O operations may be briefly suspended for a few minutes

**Explanation:**
Storage I/O might be briefly impacted when a DB snapshot is taken. This typically lasts less than a few seconds. I/O suspension does not occur for DB deployments that span multiple availability zones, because the backup is taken from the standby.

## Question 79:

 You are creating a new security group. What will the default settings be? (Choose two.)

- 1. Allow all inbound traffic
- 2. Allow instances in the same group to communicate
- 3. Block all outbound traffic
- 4. Block communications within the security group unless explicitly allowed(Correct)
- 5. Allow all outbound traffic(Correct)

*Correct Answer(s):*
 4. Block communications within the security group unless explicitly allowed5. Allow all outbound traffic

**Explanation:**
When you create a security group all inbound traffic is blocked because it has no inbound rules. The security group includes an implicit "deny all", meaning that any traffic not explicitly allowed is blocked. The security group includes a default outbound rule that allows all traffic. This rule can be removed, and you can specify certain types of traffic that should be allowed out. Instances that are associated with the same security group can't talk to each other unless you add rules explicitly allowing it. The default security group does allow traffic between instances associated with it.

## Question 80:

 What is the purpose of tagging an EC2 resource?

- 1. You can mark certain traffic with VLAN tags
- 2. You can mark certain traffic with QoS tags
- 3. You can group instances together for high availability purposes
- 4. You can assign your own metadata to resources(Correct)

*Correct Answer(s):*
 4. You can assign your own metadata to resources

**Explanation:**
Tags can be used to organize your AWS resources. This is helpful when you have similar resources that you need to categorize. For example, you may have a group of EC2 instances that belong to the development team, and other instances that belong to the production team. You could tag those instances to keep them organized, and to assign roles appropriately. Tags can only be assigned to an object that already exists.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html

## Question 81:

 Which statements regarding EC2 Instance Store are correct? (Choose two.)

- 1. Instance Store can be detached from one instance and attached to another.
- 2. Instance Store is ideal when you need high performance and low latency, but do not need data to persist.(Correct)
- 3. Data is discarded when the associated EC2 instance is rebooted.
- 4. Data is discarded when the associated EC2 instance stops or is terminated.(Correct)

*Correct Answer(s):*
 2. Instance Store is ideal when you need high performance and low latency, but do not need data to persist.4. Data is discarded when the associated EC2 instance stops or is terminated.

**Explanation:**
An EC2 instance store is temporary storage on disks that are physically attached to the host computer. This is sometimes referred to as ephemeral storage. There are many use cases for this storage type, such as temporary content or data that is replicated across many instances. The data is discarded when the associated EC2 instance stops or is terminated. If an instance is rebooted the data in the instance store persists. This storage is not meant for valuable, long-term data. You can back this data up periodically to S3 or EBS. SSD instance stores can be used when you need high performance and low latency, but do not need data to persist when the instance is terminated. The EC2 instance store is dedicated to a specific instance. The instance runs on a host computer with other instances, so the actual underlying storage system is most likely shared by multiple instances. The instance store cannot be detached from an instance and attached to another.  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html

## Question 82:

 You are using S3 to create a static website. You have created an S3 bucket are now uploading an index document that references a number of other files in the S3 bucket. How can you ensure that the required files are publicly accessible? (Choose two.)

- 1. Bucket policies can be used to configure public access to the objects in the bucket.(Correct)
- 2. IAM can be used to make only the required objects public.
- 3. Enable your bucket for static website hosting(Correct)
- 4. You should grant public access to your bucket using an S3 ACL.

*Correct Answer(s):*
 1. Bucket policies can be used to configure public access to the objects in the bucket.3. Enable your bucket for static website hosting

**Explanation:**
You should start by enabling the bucket for website hosting. You must also make the objects that you want to serve publicly readable using a bucket policy. See step 7 of the following link for bucket policy details. https://docs.aws.amazon.com/AmazonS3/latest/user-guide/static-website-hosting.html

## Question 83:

 Which statements regarding RDS backups are correct? (Choose two.)

- 1. RDS backups are based on a storage volume snapshot that is stored on S3.(Correct)
- 2. The backup can be taken at any time of day and has no performance impact.
- 3. RDS backups will stop as soon as the backup window ends, regardless of whether or not they are complete.
- 4. A maximum of 100 manual snapshots of an RDS instance can be taken.(Correct)

*Correct Answer(s):*
 1. RDS backups are based on a storage volume snapshot that is stored on S3.4. A maximum of 100 manual snapshots of an RDS instance can be taken.

**Explanation:**
Amazon RDS creates and saves a daily backup of your DB instance. This is done by taking a storage volume snapshot, and storing it on S3. The backup is taken during the backup window for the instance. You can specify the retention policy, and will be able to recover the database to any point in time during the backup retention period. You can also run a manual backup on demand at any time by creating a DB snapshot. A maximum of 100 manual snapshots can be taken.   https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Limits.html

## Question 84:

 You must be able to access a group of objects with minimal latency. You do not expect these objects to be accessed very often. Which S3 tier provides low-latency access to data at a reduced cost per GB?

- 1. S3 General Purpose
- 2. S3-IA(Correct)
- 3. S3-Standard
- 4. S3 Provisioned IOPs
- 5. Glacier

*Correct Answer(s):*
 2. S3-IA

**Explanation:**
S3-Standard and S3-Infrequent Access offer identical performance. Glacier would be the least expensive solution, but does not meet the requirement of minimal latency. S3-IA offers the same performance as S3 Standard at a reduced cost, but there is a retrieval fee for data.  https://aws.amazon.com/s3/storage-classes/

## Question 85:

 You have an app that allows users to upload, view, and download pictures into Amazon S3. You expect to have an enormous amount of users that are going to self-register. Your solution must be able to scale to more than 100,000 users. What option should be used to register each user and grant access?

- 1. Create an IAM role with the correct permissions. Grant the mobile app temporary credentials using Security Token Service.
- 2. Use Security Token Service to create permanent credentials, and then store the credentials in the mobile application.
- 3. Use Cognito to auto-create unique identifiers for users. Store each user's information in DynamoDB. Grant the mobile app temporary credentials using Security Token Service.(Correct)
- 4. Create an IAM user and auto-assign a role. Use Security Token Service to grant the mobile app temporary credentials.

*Correct Answer(s):*
 3. Use Cognito to auto-create unique identifiers for users. Store each user's information in DynamoDB. Grant the mobile app temporary credentials using Security Token Service.

**Explanation:**
You should use Cognito to auto-create unique identifiers for users. Cognito is used to add sign-up and sign-in options to mobile and web apps. Users can be authenticated using identity providers such as Facebook, Twitter, or Amazon. It also supports SAML identity solutions. Data can be locally stored on user devices, enabling offline usage. Cognito can scale to hundreds of millions of users. IAM Roles and Users will not scale to the level required for this use case.

## Question 86:

 You have created a custom Network ACL and associated it with a subnet in your VPC. It is configured to permit outbound HTTP traffic. No other rues have been configured. Which statement regarding this configuration is correct?

- 1. The default Network ACL will be applied to this subnet as well.
- 2. The Network ACL is stateful.
- 3. For instances to access HTTP through this Network ACL you must create a rule for inbound HTTP.(Correct)
- 4. Network ACLs can only be applied to instances, not subnets.

*Correct Answer(s):*
 3. For instances to access HTTP through this Network ACL you must create a rule for inbound HTTP.

**Explanation:**
Network ACLs are not a stateful firewall. This means that Network ACLs do not track connection states and allow return traffic. You must have the desired traffic open in both directions. You can configure Network ACLs and security groups to enhance security. For example, you could have different Security Group configurations associated with instances in a subnet. But there may be certain traffic that you know you need to block across every instance on a subnet, and you could use a Network ACL to accomplish that goal. VPCs include a default Network ACL that allows all inbound and outbound traffic. You can create your own custom Network ACLs and associate them with a subnet. Custom Network ACLs will deny all inbound and outbound traffic by default. If you do not create a custom Network ACL the default Network ACL is enforced. Each subnet can only be associated with a single Network ACL. The rules are interrogated based on the rule number, and the first matching rule is enforced.   https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html

## Question 87:

 What is the purpose of AWS Direct Connect?

- 1. Provides a private physical connection between your datacenter and your VPC.(Correct)
- 2. Provides a secure VPN tunnel over the Internet to your VPC.
- 3. Allows you to establish a connection between VPCs in different AWS accounts.
- 4. Allows you to create a peer relationship between VPCs.

*Correct Answer(s):*
 1. Provides a private physical connection between your datacenter and your VPC.

**Explanation:**
Direct Connect can be used to create a dedicated network connection between your organization and an AWS Direct Connect location. This is useful if you need a high-throughput, consistent network experience. All data transferred over this connection is charged a reduced Direct Connect data transfer rate. 1 Gbps and 10 Gbps connections are available, and multiple connections can be supported for increased bandwidth. Multiple VLANs can be carried over the connection using an 802.1q trunk port. For example, assume you have private resources on AWS. You can access them over a defined VLAN that is dedicated to private traffic. Other VLANs could be used to access resources with public IP addresses.

## Question 88:

 Is shell access permitted to an RDS instance?

- 1. Yes, because RDS is an unmanaged service.
- 2. No, because RDS is an unmanaged service.
- 3. No, because RDS is a managed service.(Correct)
- 4. Yes, because RDS is a managed service.

*Correct Answer(s):*
 3. No, because RDS is a managed service.

**Explanation:**
Shell access to RDS instances is prohibited. Backups, software patching, automatic failure detection, and recovery are all handled by AWS. Automated backups and on-demand snapshots are supported.

## Question 89:

 Which of the following devices are supported for MFA with IAM? (Choose two.)

- 1. Virtual MFA for your smartphone(Correct)
- 2. RSA Hardware Devices
- 3. Hardware Key Fobs(Correct)
- 4. Email MFA

*Correct Answer(s):*
 1. Virtual MFA for your smartphone3. Hardware Key Fobs

**Explanation:**
Multi-Factor Authentication (MFA) is a widely accepted security best practice that ensure the security of an environment. The best known example of MFA is an ATM card. A user must have something they know (PIN) and something they physically possess (ATM Card) to withdraw funds. Stealing the PIN alone is worthless. Similarly, when a user signs into AWS website they must provide their user name and password. This is one factor – something they know. The second factor (something they have) could be a variety of mechanisms. Supported device types include Virtual MFA devices, Hardware Key Fobs, Hardware Display Cards, and SMS MFA devices. MFA can be configured for individual IAM users and can be also be used to control access to AWS service APIs. MFA is included at no charge.     https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html

## Question 90:

 Your organization plans to store data that is subject to PCI compliance regulations on AWS. You currently undergo rigorous auditing processes, including penetration testing. You need to ability to continue these practices after migrating to AWS. Which statement regarding this scenario is correct?

- 1. Penetration testing is not supported on EC2
- 2. Penetration testing is supported across all instance types.
- 3. AWS does not support PCI compliant applications.
- 4. AWS must approve customer-performed penetration testing(Correct)

*Correct Answer(s):*
 4. AWS must approve customer-performed penetration testing

**Explanation:**
AWS must grant permission for all penetration tests. You can request permission from the AWS portal. You cannot begin the penetration test until AWS has approved the request. AWS has been PCI DSS Certified since 2010. AWS does not permit penetration testing of small or micro RDS instance types.  https://aws.amazon.com/security/penetration-testing/

## Question 91:

 Which of the following are characteristics of an Elastic IP address? (Choose two.)

- 1. An Elastic IP is a private IP address.
- 2. An Elastic IP can be detached from one EC2 instance and attached to another.(Correct)
- 3. An Elastic IP is a public IP address.(Correct)
- 4. You are only billed for Elastic IP addresses when they are attached to an instance.

*Correct Answer(s):*
 2. An Elastic IP can be detached from one EC2 instance and attached to another.3. An Elastic IP is a public IP address.

**Explanation:**
An Elastic IP address is a static IPv4 address that is associated with your AWS account. An Elastic IP can be attached to and detached from an EC2 instance, allowing you to mask failures. An Elastic IP address is a publicly routable IPv4 address.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html

## Question 92:

 You are taking an EBS snapshot of an instance that has changed significantly since the last backup. The snapshot is in the pending state. Which statements regarding this scenario are correct? (Choose two.)

- 1. The volume can still be used normally.(Correct)
- 2. Changes that occur while the snapshot is in progress will be captured in the snapshot.
- 3. The snapshot operation is copying changed blocks from EBS to S3.(Correct)
- 4. You cannot take another snapshot while the first is still in the pending state.

*Correct Answer(s):*
 1. The volume can still be used normally.3. The snapshot operation is copying changed blocks from EBS to S3.

**Explanation:**
You can take snapshots of an EBS volume. The snapshot is a point-in-time picture of the volume that is stored in S3. Like all data stored on S3, it will exist redundantly in multiple Availability Zones. Snapshots can be used to create multiple new EBS volumes. This is useful if you need to move a volume to a different AZ. You can create a new volume based on the snapshot, and it will be an exact copy of the original. Snapshots are incremental in nature, meaning that only blocks that have changed since the last snapshot are saved in the new snapshot. However you can still delete older snapshots at any time and it does not affect your ability to restore based on newer snapshots. When you take an EBS snapshot the required blocks need to be copied to S3. This can take a significant amount of time, especially if many blocks have changed since the last snapshot. An in-progress snapshot is based on the state of the instance at the exact moment you took the snapshot. It is not affected by ongoing reads and writes to the volume. This might exclude cached data, which could create a data consistency issue when you try to restore. Ideally you should quiesce changes to the volume prior to taking the snapshot. You can also un-mount the volume to ensure an application-consistent snapshot. If you have multiple snapshots that are in the pending (in-progress) state, it can affect the performance of the instance. A maximum of 5 pending snapshots can exist per a single gp2, io1, or Magnetic volume. Only 1 pending snapshot at a time is allowed for a single st1 or sc1 volume. Snapshots of encrypted volumes are automatically encrypted. If you create a volume from an encrypted snapshot it will also be automatically encrypted.

## Question 93:

 You have created an auto scaling group that currently has four instances up and running. You want future instances to be based on a different AMI. What configuration task should you complete?

- 1. Modify the existing Launch Configuration.
- 2. Create an auto scaling sub-group based on the new AMI.
- 3. Create a new Launch Configuration.(Correct)
- 4. Re-configure the auto scaling group.

*Correct Answer(s):*
 3. Create a new Launch Configuration.

**Explanation:**
The Auto Scaling group uses a launch configuration as a template for its EC2 instances. The launch configuration specifies the AMI that should be used to create the instances. It also allows you to specify the instance type, key pair, security groups, and block device mapping for your instances. You will specify the launch configuration when you create an Auto Scaling group. Once a launch configuration is created you cannot modify it. If you want to make a change to the launch configuration you must create a new launch configuration, and then update your Auto Scaling group. New instances launched in the Auto Scaling group will be based on the new launch configuration parameters. Existing instances will continue to run as they were configured.   https://docs.aws.amazon.com/autoscaling/ec2/userguide/change-launch-config.html

## Question 94:

 How frequently can ELB publish log files?

- 1. Every 5 minutes(Correct)
- 2. Once per hour
- 3. Every 30 seconds
- 4. Once per minute

*Correct Answer(s):*
 1. Every 5 minutes

**Explanation:**
Elastic Load Balancing supports logging of information related to connection details, including the time the request was received, the client's IP address, latencies, request paths, and server responses. Access logging is disabled by default. If you enable this feature you must choose an S3 bucket to store the data that is generated. There is no cost for this feature, but it may consume a large amount of space on S3 that you will be billed for. A publishing interval between 5 and 60 minutes is supported.  https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-access-logs.html

## Question 95:

 What type of MFA support does AWS offer?

- 1. Any RADIUS based MFA solution is supported
- 2. MFA is not supported
- 3. AWS multi-factor token devices or private MFA solutions are supported.
- 4. Only AWS multi-factor token devices are supported.(Correct)

*Correct Answer(s):*
 4. Only AWS multi-factor token devices are supported.

**Explanation:**
Multi-Factor Authentication (MFA) is a widely accepted security best practice that ensure the security of an environment. The best known example of MFA is an ATM card. A user must have something they know (PIN) and something they physically possess (ATM Card) to withdraw funds. Stealing the PIN alone is worthless. Similarly, when a user signs into AWS website they must provide their user name and password. This is one factor – something they know. The second factor (something they have) could be a variety of mechanisms. Supported device types include Virtual MFA devices, Hardware Key Fobs, Hardware Display Cards, and SMS MFA devices. MFA can be configured for individual IAM users and can be also be used to control access to AWS service APIs. MFA is included at no charge.

## Question 96:

 Which of the following resources are global and available across multiple regions for Disaster Recovery? (Choose two.)

- 1. Route 53 DNS Records(Correct)
- 2. Security Groups
- 3. Amazon Machine Images
- 4. Elastic IP Addresses
- 5. IAM Roles(Correct)

*Correct Answer(s):*
 1. Route 53 DNS Records5. IAM Roles

**Explanation:**
Route 53 DNS Records and IAM Roles are global objects, and are available across regions. Elastic IP addresses, Security Groups, and Amazon Machine Images are all regional objects, and can only be used in the region in which they were created.    http://jayendrapatil.com/aws-global-vs-regional-vs-az-resources/

## Question 97:

 You recently took a snapshot of an EBS volume, and it is taking some time to complete because many changes have occurred since the last snapshot. Which of the following statements are correct?

- 1. Snapshots are not incremental in nature.
- 2. An in-progress snapshot is based on the state of the instance at the exact moment you took the snapshot.(Correct)
- 3. The size of the snapshot is affected by ongoing reads and writes while the snapshot is created.
- 4. Changes made while a snapshot is in-progress will also be captured in the snapshot.

*Correct Answer(s):*
 2. An in-progress snapshot is based on the state of the instance at the exact moment you took the snapshot.

**Explanation:**
When you take an EBS snapshot the required blocks need to be copied to S3. This can take a significant amount of time, especially if many blocks have changed since the last snapshot. An in-progress snapshot is based on the state of the instance at the exact moment you took the snapshot. It is not affected by ongoing reads and writes to the volume. This might exclude cached data, which could create a data consistency issue when you try to restore. Ideally you should quiesce changes to the volume prior to taking the snapshot. You can also un-mount the volume to ensure an application-consistent snapshot.   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-snapshot.html

## Question 98:

 What AWS resource provides specifies the AMI that should be used to create instances in an Auto Scaling Group?

- 1. Cloud Formation Template
- 2. CloudWatch
- 3. User Data Script
- 4. Launch Configuration(Correct)

*Correct Answer(s):*
 4. Launch Configuration

**Explanation:**
The Auto Scaling group uses a launch configuration as a template for its EC2 instances. The launch configuration specifies the AMI that should be used to create the instances. It also allows you to specify the instance type, key pair, security groups, and block device mapping for your instances. You will specify the launch configuration when you create an Auto Scaling group. Once a launch configuration is created you cannot modify it. If you want to make a change to the launch configuration you must create a new launch configuration, and then update your Auto Scaling group. New instances launched in the Auto Scaling group will be based on the new launch configuration parameters. Existing instances will continue to run as they were configured.    https://docs.aws.amazon.com/autoscaling/ec2/userguide/LaunchConfiguration.html

## Question 99:

 What is the purpose of the AWS Directory service?

- 1. Create a file-share with user defined folders and directories and granular permissions.
- 2. Tag AWS resources with descriptive information to help provide automation.
- 3. Connect your AWS services to your on-premises active directory domain or fully migrate active Directory services to the AWS Cloud.(Correct)
- 4. Create a directory of users and groups within your AWS account, and allow the creation of policies that can be used to control permissions.

*Correct Answer(s):*
 3. Connect your AWS services to your on-premises active directory domain or fully migrate active Directory services to the AWS Cloud.

**Explanation:**
AWS Directory Service can be used to connect your AWS services to your on-premises active directory domain. You can also fully migrate active Directory services to the AWS Cloud. It supports standard Active Directory administration tools and features, including Group Policy, trusts, and single sign-on. This allows you to join EC2 virtual Servers and RDS SQL servers to a domain. It also integrates nicely with Amazon Workspaces, which provides virtual desktops in the cloud.   https://aws.amazon.com/directoryservice/

## Question 100:

 Can a new IAM role be granted to a running EC2 instance?

- 1. Roles can be changed with a user data script
- 2. Roles can be assigned to an instance at any time(Correct)
- 3. Roles can only be assigned to users
- 4. Roles can only be assigned during instance creation

*Correct Answer(s):*
 2. Roles can be assigned to an instance at any time

**Explanation:**
Rolces can be assigned to an instance at any time, and can be changed as needed on a running instance. For full details, see: https://tinyurl.com/zw5pkpz

