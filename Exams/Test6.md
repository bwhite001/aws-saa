# Practice Exams | AWS Certified Solutions Architect Associate: 


## Question 1:

 A Machine Learning research group uses a proprietary computer vision application hosted on an Amazon EC2 instance. Every time the instance needs to be stopped and started again, the application takes about 3 minutes to start as some auxiliary software programs need to be executed so that the application can function. The research group would like to minimize the application boostrap time whenever the system needs to be stopped and then started at a later point in time.

As a solutions architect, which of the following solutions would you recommend for this use-case?

- 1. Create an Amazon Machine Image (AMI) and launch your Amazon EC2 instances from that
- 2. Use Amazon EC2 Meta-Data
- 3. Use Amazon EC2 Instance Hibernate(Correct)
- 4. Use Amazon EC2 User-Data

*Correct Answer(s):*
 3. Use Amazon EC2 Instance Hibernate

**Explanation:**
Correct option:

Use Amazon EC2 Instance Hibernate

When you hibernate an instance, AWS signals the operating system to perform hibernation (suspend-to-disk). Hibernation saves the contents from the instance memory (RAM) to your Amazon EBS root volume. AWS then persists the instance's Amazon EBS root volume and any attached Amazon EBS data volumes.

When you start your instance:

The Amazon EBS root volume is restored to its previous state

The RAM contents are reloaded

The processes that were previously running on the instance are resumed

Previously attached data volumes are reattached and the instance retains its instance ID

Overview of Amazon EC2 hibernation:

via - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Hibernate.html

By using Amazon EC2 hibernate, we have the capability to resume it at any point of time, with the application already launched, thus helping us cut the 3 minutes start time.

Incorrect options:

Use Amazon EC2 User-Data - Amazon EC2 instance user data is the data that you specified in the form of a configuration script while launching your instance. Here, the problem is that the application takes 3 minutes to launch, no matter what. EC2 user data won't help us because it's just here to help us execute a list of commands, not speed them up.

Use Amazon EC2 Meta-Data - Amazon EC2 instance metadata is data about your instance that you can use to configure or manage the running instance. Instance metadata is divided into categories, for example, host name, events, and security groups. The EC2 meta-data is a distractor and can only help us determine some metadata attributes on our EC2 instances.

Create an Amazon Machine Image (AMI) and launch your Amazon EC2 instances from that - An Amazon Machine Image (AMI) provides the information required to launch an instance. You must specify an AMI when you launch an instance. You can launch multiple instances from a single AMI when you need multiple instances with the same configuration. You can use different AMIs to launch instances when you need instances with different configurations.

Creating an AMI may help with all the system dependencies, but it won't help us with speeding up the application start time.

References:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Hibernate.html

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html

## Question 2:

 Your company has deployed an application that will perform a lot of overwrites and deletes on data and require the latest information to be available anytime data is read via queries on database tables.

As a Solutions Architect, which database technology will you recommend?

- 1. Amazon Simple Storage Service (Amazon S3)
- 2. Amazon Neptune
- 3. Amazon Relational Database Service (Amazon RDS)(Correct)
- 4. Amazon ElastiCache

*Correct Answer(s):*
 3. Amazon Relational Database Service (Amazon RDS)

**Explanation:**
Correct option:

Amazon Relational Database Service (Amazon RDS)

Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching, and backups. RDS allows you to create, read, update, and delete records without any item lock or ambiguity. All RDS transactions must be ACID compliant or be Atomic, Consistent, Isolated, and Durable to ensure data integrity.

Atomicity requires that either transaction as a whole is successfully executed or if a part of the transaction fails, then the entire transaction be invalidated. Consistency mandates the data written to the database as part of the transaction must adhere to all defined rules, and restrictions including constraints, cascades, and triggers. Isolation is critical to achieving concurrency control and makes sure each transaction is independent unto itself. Durability requires that all of the changes made to the database be permanent once a transaction is completed.
Hence, the best fit is Amazon RDS.

Incorrect options:

Amazon ElastiCache - Amazon ElastiCache allows you to seamlessly set up, run, and scale popular open-source compatible in-memory data stores in the cloud. Build data-intensive apps or boost the performance of your existing databases by retrieving data from high throughput and low latency in-memory data stores. Amazon ElastiCache is a popular choice for real-time use cases like Caching, Session Stores, Gaming, Geospatial Services, Real-Time Analytics, and Queuing. ElastiCache could work but it's a better fit as a caching technology to enhance reads.

Amazon Simple Storage Service (Amazon S3) - This option is incorrect as Amazon S3 is not a database technology that supports queries on database tables out of the box. It is an object storage service that offers industry-leading scalability, data availability, security, and performance. Your applications can easily achieve thousands of transactions per second in request performance when uploading and retrieving storage from Amazon S3.

After a successful write of a new object or an overwrite of an existing object, any subsequent read request immediately receives the latest version of the object. Amazon S3 also provides strong consistency for list operations, so after a write, you can immediately perform a listing of the objects in a bucket with any changes reflected. Strong read-after-write consistency helps when you need to immediately read an object after a write. For example, strong read-after-write consistency when you often read and list immediately after writing objects.

Amazon Neptune - Amazon Neptune is a fast, reliable, fully-managed graph database service that makes it easy to build and run applications that work with highly connected datasets. The core of Amazon Neptune is a purpose-built, high-performance graph database engine optimized for storing billions of relationships and querying the graph with milliseconds latency.

Amazon Neptune is highly available, with read replicas, point-in-time recovery, continuous backup to Amazon S3, and replication across Availability Zones. Neptune is secure with support for HTTPS encrypted client connections and encryption at rest. Amazon Neptune is fully managed, so you no longer need to worry about database management tasks such as hardware provisioning, software patching, setup, configuration, or backups. Amazon Neptune is a graph database so it's not a good fit.

References:

https://aws.amazon.com/relational-database/

https://aws.amazon.com/rds/

https://aws.amazon.com/neptune/

https://docs.aws.amazon.com/AmazonS3/latest/dev/Introduction.html#ConsistencyModel

## Question 3:

 An e-commerce company operates multiple AWS accounts and has interconnected these accounts in a hub-and-spoke style using the AWS Transit Gateway. Amazon Virtual Private Cloud (Amazon VPCs) have been provisioned across these AWS accounts to facilitate network isolation.

Which of the following solutions would reduce both the administrative overhead and the costs while providing shared access to services required by workloads in each of the VPCs?

- 1. Build a shared services Amazon Virtual Private Cloud (Amazon VPC)(Correct)
- 2. Use Fully meshed VPC Peering connection
- 3. Use VPCs connected with AWS Direct Connect
- 4. Use Transit VPC to reduce cost and share the resources across Amazon Virtual Private Cloud (Amazon VPCs)

*Correct Answer(s):*
 1. Build a shared services Amazon Virtual Private Cloud (Amazon VPC)

**Explanation:**
Correct option:

Build a shared services Amazon Virtual Private Cloud (Amazon VPC)

Consider an organization that has built a hub-and-spoke network with AWS Transit Gateway. VPCs have been provisioned into multiple AWS accounts, perhaps to facilitate network isolation or to enable delegated network administration. When deploying distributed architectures such as this, a popular approach is to build a "shared services VPC, which provides access to services required by workloads in each of the VPCs. This might include directory services or VPC endpoints. Sharing resources from a central location instead of building them in each VPC may reduce administrative overhead and cost.

Centralized VPC Endpoints (multiple VPCs):

via - https://aws.amazon.com/blogs/architecture/reduce-cost-and-increase-security-with-amazon-vpc-endpoints/

A VPC endpoint allows you to privately connect your VPC to supported AWS services without requiring an Internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Endpoints are virtual devices that are horizontally scaled, redundant, and highly available VPC components. They allow communication between instances in your VPC and services without imposing availability risks or bandwidth constraints on your network traffic.

VPC endpoints enable you to reduce data transfer charges resulting from network communication between private VPC resources (such as Amazon Elastic Cloud Compute—or EC2—instances) and AWS Services (such as Amazon Quantum Ledger Database, or QLDB). Without VPC endpoints configured, communications that originate from within a VPC destined for public AWS services must egress AWS to the public Internet in order to access AWS services. This network path incurs outbound data transfer charges. Data transfer charges for traffic egressing from Amazon EC2 to the Internet vary based on volume. With VPC endpoints configured, communication between your VPC and the associated AWS service does not leave the Amazon network. If your workload requires you to transfer significant volumes of data between your VPC and AWS, you can reduce costs by leveraging VPC endpoints.

Incorrect options:

Use Transit VPC to reduce cost and share the resources across Amazon Virtual Private Cloud (Amazon VPCs) - Transit VPC uses customer-managed Amazon Elastic Compute Cloud (Amazon EC2) VPN instances in a dedicated transit VPC with an Internet gateway. This design requires the customer to deploy, configure, and manage EC2-based VPN appliances, which will result in additional EC2, and potentially third-party product and licensing charges. Note that this design will generate additional data transfer charges for traffic traversing the transit VPC: data is charged when it is sent from a spoke VPC to the transit VPC, and again from the transit VPC to the on-premises network or a different AWS Region. Transit VPC is not the right choice here.

More on Transit VPC:

via - https://d0.awsstatic.com/aws-answers/AWS_Single_Region_Multi_VPC_Connectivity.pdf

Use Fully meshed VPC Peering connection - This approach creates multiple peering connections to facilitate the sharing of information between resources in different VPCs. This design connects multiple VPCs in a fully meshed configuration, with peering connections between each pair of VPCs. With this configuration, each VPC has access to the resources in all other VPCs. Each peering connection requires modifications to all the other VPCs’ route tables and, as the number of VPCs grows, this can be difficult to maintain. And keep in mind that AWS recommends a maximum of 125 peering connections per VPC. It's complex to manage and isn't a right fit for the current scenario.

More on Fully meshed VPC Peers:

via - https://d0.awsstatic.com/aws-answers/AWS_Single_Region_Multi_VPC_Connectivity.pdf

Use VPCs connected with AWS Direct Connect - This approach is a good alternative for customers who need to connect a high number of VPCs to a central VPC or on-premises resources, or who already have an AWS Direct Connect connection in place. This design also offers customers the ability to incorporate transitive routing into their network design. For example, if VPC A and VPC B are both connected to an on-premises network using AWS Direct Connect connections, then the two VPCs can be connected to each other via AWS Direct Connect. AWS Direct Connect requires physical cables and takes about a month for setting up, this is not an ideal solution for the given scenario.

References:

https://aws.amazon.com/blogs/architecture/reduce-cost-and-increase-security-with-amazon-vpc-endpoints/

https://d0.awsstatic.com/aws-answers/AWS_Single_Region_Multi_VPC_Connectivity.pdf

## Question 4:

 A media company is migrating its flagship application from its on-premises data center to AWS for improving the application's read-scaling capability as well as its availability. The existing architecture leverages a Microsoft SQL Server database that sees a heavy read load. The engineering team does a full copy of the production database at the start of the business day to populate a dev database. During this period, application users face high latency leading to a bad user experience.

The company is looking at alternate database options and migrating database engines if required. What would you suggest?

- 1. Leverage Amazon Aurora MySQL with Multi-AZ Aurora Replicas and restore the dev database via mysqldump
- 2. Leverage Amazon RDS for MySQL with a Multi-AZ deployment and use the standby instance as the dev database
- 3. Leverage Amazon Aurora MySQL with Multi-AZ Aurora Replicas and create the dev database by restoring from the automated backups of Amazon Aurora(Correct)
- 4. Leverage Amazon RDS for SQL server with a Multi-AZ deployment and read replicas. Use the read replica as the dev database

*Correct Answer(s):*
 3. Leverage Amazon Aurora MySQL with Multi-AZ Aurora Replicas and create the dev database by restoring from the automated backups of Amazon Aurora

**Explanation:**
Correct option:

Leverage Amazon Aurora MySQL with Multi-AZ Aurora Replicas and create the dev database by restoring from the automated backups of Amazon Aurora

Amazon Aurora (Aurora) is a fully managed relational database engine that's compatible with MySQL and PostgreSQL. An Amazon Aurora DB cluster consists of one or more DB instances and a cluster volume that manages the data for those DB instances. An Aurora cluster volume is a virtual database storage volume that spans multiple Availability Zones (AZs), with each Availability Zone (AZ) having a copy of the Amazon Aurora DB cluster data. Aurora supports Multi-AZ Aurora Replicas that improve the application's read-scaling and availability.

Amazon Aurora Overview:

via - https://aws.amazon.com/rds/aurora/

Aurora backs up your cluster volume automatically and retains restore data for the length of the backup retention period. Aurora backups are continuous and incremental so you can quickly restore to any point within the backup retention period. No performance impact or interruption of database service occurs as backup data is being written.


via - https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Managing.Backups.html

Automated backups occur daily during the preferred backup window. If the backup requires more time than allotted to the backup window, the backup continues after the window ends, until it finishes. The backup window can't overlap with the weekly maintenance window for the DB cluster. Aurora backups are continuous and incremental, but the backup window is used to create a daily system backup that is preserved within the backup retention period. The latest restorable time for a DB cluster is the most recent point at which you can restore your DB cluster, typically within 5 minutes of the current time.

For the given use case, you can create the dev database by restoring from the automated backups of Amazon Aurora.

Incorrect options:

Leverage Amazon Aurora MySQL with Multi-AZ Aurora Replicas and restore the dev database via mysqldump - Restoring the dev database via mysqldump would still result in a significant load on the primary DB, so this option fails to address the given requirement.

Leverage Amazon RDS for MySQL with a Multi-AZ deployment and use the standby instance as the dev database - The standby is there just for handling failover in a Multi-AZ deployment. You cannot access the standby instance and use it as a dev database. Hence this option is incorrect.

Leverage Amazon RDS for SQL server with a Multi-AZ deployment and read replicas. Use the read replica as the dev database - Amazon RDS supports Multi-AZ deployments for Microsoft SQL Server by using either SQL Server Database Mirroring (DBM) or Always On Availability Groups (AGs). Amazon RDS monitors and maintains the health of your Multi-AZ deployment.

Multi-AZ deployments provide increased availability, data durability, and fault tolerance for DB instances. In the event of planned database maintenance or unplanned service disruption, Amazon RDS automatically fails over to the up-to-date secondary DB instance. For SQL Server, I/O activity is suspended briefly during backup for Multi-AZ deployments.

A read replica is only meant to serve read traffic. The primary purpose of the read replica is to replicate the data in the primary DB instance. A read replica cannot be used as a dev database because it does not allow any database write operations.

References:

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Managing.Backups.html

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/SQLServer.ReadReplicas.html

## Question 5:

 The engineering team at a logistics company has noticed that the Auto Scaling group (ASG) is not terminating an unhealthy Amazon EC2 instance.

As a Solutions Architect, which of the following options would you suggest to troubleshoot the issue? (Select three)

- 1. The instance maybe in Impaired status(Correct)
- 2. The instance has failed the Elastic Load Balancing (ELB) health check status(Correct)
- 3. A user might have updated the configuration of the Auto Scaling group (ASG) and increased the minimum number of instances forcing ASG to keep all instances alive
- 4. The health check grace period for the instance has not expired(Correct)
- 5. The Amazon EC2 instance could be a spot instance type, which cannot be terminated by the Auto Scaling group (ASG)
- 6. A custom health check might have failed. The Auto Scaling group (ASG) does not terminate instances that are set unhealthy by custom checks

*Correct Answer(s):*
 1. The instance maybe in Impaired status2. The instance has failed the Elastic Load Balancing (ELB) health check status4. The health check grace period for the instance has not expired

**Explanation:**
Correct options:

The health check grace period for the instance has not expired

Amazon EC2 Auto Scaling doesn't terminate an instance that came into service based on Amazon EC2 status checks and Elastic Load Balancing (ELB) health checks until the health check grace period expires.

More on Health check grace period:

via - https://docs.aws.amazon.com/autoscaling/ec2/userguide/healthcheck.html#health-check-grace-period

The instance maybe in Impaired status

Amazon EC2 Auto Scaling does not immediately terminate instances with an Impaired status. Instead, Amazon EC2 Auto Scaling waits a few minutes for the instance to recover. Amazon EC2 Auto Scaling might also delay or not terminate instances that fail to report data for status checks. This usually happens when there is insufficient data for the status check metrics in Amazon CloudWatch.

The instance has failed the Elastic Load Balancing (ELB) health check status

By default, Amazon EC2 Auto Scaling doesn't use the results of ELB health checks to determine an instance's health status when the group's health check configuration is set to EC2. As a result, Amazon EC2 Auto Scaling doesn't terminate instances that fail ELB health checks. If an instance's status is OutofService on the ELB console, but the instance's status is Healthy on the Amazon EC2 Auto Scaling console, confirm that the health check type is set to ELB.

Incorrect options:

The Amazon EC2 instance could be a spot instance type, which cannot be terminated by the Auto Scaling group (ASG) - This is an incorrect statement. Amazon EC2 Auto Scaling terminates Spot instances when capacity is no longer available or the Spot price exceeds your maximum price.

A user might have updated the configuration of the Auto Scaling group (ASG) and increased the minimum number of instances forcing ASG to keep all instances alive - This statement is incorrect. If the configuration is updated and ASG needs more number of instances, ASG will launch new, healthy instances and does not keep unhealthy ones alive.

A custom health check might have failed. The Auto Scaling group (ASG) does not terminate instances that are set unhealthy by custom checks - This statement is incorrect. You can define custom health checks in Amazon EC2 Auto Scaling. When a custom health check determines that an instance is unhealthy, the check manually triggers SetInstanceHealth and then sets the instance's state to Unhealthy. Amazon EC2 Auto Scaling then terminates the unhealthy instance.

References:

https://aws.amazon.com/premiumsupport/knowledge-center/auto-scaling-terminate-instance/

https://aws.amazon.com/premiumsupport/knowledge-center/auto-scaling-instance-how-terminated/

## Question 6:

 A big data consulting firm needs to set up a data lake on Amazon S3 for a Health-Care client. The data lake is split in raw and refined zones. For compliance reasons, the source data needs to be kept for a minimum of 5 years. The source data arrives in the raw zone and is then processed via an AWS Glue based extract, transform, and load (ETL) job into the refined zone. The business analysts run ad-hoc queries only on the data in the refined zone using Amazon Athena. The team is concerned about the cost of data storage in both the raw and refined zones as the data is increasing at a rate of 1 terabyte daily in each zone.

As a solutions architect, which of the following would you recommend as the MOST cost-optimal solution? (Select two)

- 1. Use AWS Glue ETL job to write the transformed data in the refined zone using CSV format
- 2. Setup a lifecycle policy to transition the refined zone data into Amazon S3 Glacier Deep Archive after 1 day of object creation
- 3. Use AWS Glue ETL job to write the transformed data in the refined zone using a compressed file format(Correct)
- 4. Create an AWS Lambda function based job to delete the raw zone data after 1 day
- 5. Setup a lifecycle policy to transition the raw zone data into Amazon S3 Glacier Deep Archive after 1 day of object creation(Correct)

*Correct Answer(s):*
 3. Use AWS Glue ETL job to write the transformed data in the refined zone using a compressed file format5. Setup a lifecycle policy to transition the raw zone data into Amazon S3 Glacier Deep Archive after 1 day of object creation

**Explanation:**
Correct options:

Setup a lifecycle policy to transition the raw zone data into Amazon S3 Glacier Deep Archive after 1 day of object creation

You can manage your objects so that they are stored cost-effectively throughout their lifecycle by configuring their Amazon S3 Lifecycle. An S3 Lifecycle configuration is a set of rules that define actions that Amazon S3 applies to a group of objects. For example, you might choose to transition objects to the Amazon S3 Standard-IA storage class 30 days after you created them, or archive objects to the Amazon S3 Glacier storage class one year after creating them.

For the given use-case, the raw zone consists of the source data, so it cannot be deleted due to compliance reasons. Therefore, you should use a lifecycle policy to transition the raw zone data into Amazon S3 Glacier Deep Archive after 1 day of object creation.

Please read more about Amazon S3 Object Lifecycle Management:

via - https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html

Use AWS Glue ETL job to write the transformed data in the refined zone using a compressed file format

AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics.
You cannot transition the refined zone data into Amazon S3 Glacier Deep Archive because it is used by the business analysts for ad-hoc querying. Therefore, the best optimization is to have the refined zone data stored in a compressed format via the Glue job. The compressed data would reduce the storage cost incurred on the data in the refined zone.

Please see this example for a AWS Glue ETL Pipeline:

via - https://aws.amazon.com/glue/

Incorrect options:

Create an AWS Lambda function based job to delete the raw zone data after 1 day - As mentioned in the use-case, the source data needs to be kept for a minimum of 5 years for compliance reasons. Therefore the data in the raw zone cannot be deleted after 1 day.

Setup a lifecycle policy to transition the refined zone data into Amazon S3 Glacier Deep Archive after 1 day of object creation - You cannot transition the refined zone data into Amazon S3 Glacier Deep Archive because it is used by the business analysts for ad-hoc querying. Hence this option is incorrect.

Use AWS Glue ETL job to write the transformed data in the refined zone using CSV format - It is cost-optimal to write the data in the refined zone using a compressed format instead of CSV format. The compressed data would reduce the storage cost incurred on the data in the refined zone. So, this option is incorrect.

References:

https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html

https://aws.amazon.com/glue/

## Question 7:

 A financial services company wants to store confidential data in Amazon S3 and it needs to meet the following data security and compliance norms:


Encryption key usage must be logged for auditing purposes
Encryption Keys must be rotated every year
The data must be encrypted at rest


Which is the MOST operationally efficient solution?

- 1. Server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) with automatic key rotation(Correct)
- 2. Server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) with manual key rotation
- 3. Server-side encryption (SSE-S3) with automatic key rotation
- 4. Server-side encryption with customer-provided keys (SSE-C) with automatic key rotation

*Correct Answer(s):*
 1. Server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) with automatic key rotation

**Explanation:**
Correct option:

Server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) with automatic key rotation

Server-side encryption is the encryption of data at its destination by the application or service that receives it. Amazon S3 encrypts your data at the object level as it writes it to disks in its data centers and decrypts it for you when you access it.

Amazon S3 now applies server-side encryption with Amazon S3 managed keys (SSE-S3) as the base level of encryption for every bucket in Amazon S3. Starting January 5, 2023, all new object uploads to Amazon S3 are automatically encrypted at no additional cost and with no impact on performance.

Amazon S3 server-side encryption

via - https://docs.aws.amazon.com/AmazonS3/latest/userguide/serv-side-encryption.html

AWS KMS is a service that combines secure, highly available hardware and software to provide a key management system scaled for the cloud. Amazon S3 uses server-side encryption with AWS KMS (SSE-KMS) to encrypt your S3 object data. Also, when SSE-KMS is requested for the object, the S3 checksum as part of the object's metadata, is stored in encrypted form.

If you use KMS keys, you can use AWS KMS through the AWS Management Console or the AWS KMS API to do the following:


Centrally create, view, edit, monitor, enable or disable, rotate, and schedule deletion of KMS keys.
Define the policies that control how and by whom KMS keys can be used.
Audit their usage to prove that they are being used correctly. Auditing is supported by the AWS KMS API, but not by the AWS KMSAWS Management Console.


When you enable automatic key rotation for a KMS key, AWS KMS generates new cryptographic material for the KMS key every year.

AWS KMS keys:

via - https://docs.aws.amazon.com/kms/latest/developerguide/rotate-keys.html

For the given use case, you can set up server-side encryption with AWS KMS Keys (SSE-KMS) with automatic key rotation.

Incorrect options:

Server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) with manual key rotation - Although it is possible to manually rotate the AWS KMS key, it is not the best fit solution as it is not operationally efficient.

Server-side encryption (SSE-S3) with automatic key rotation - When you use Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3), each object is encrypted with a unique key. As an additional safeguard, it encrypts the key itself with a root key that it regularly rotates. However, with SSE-S3, you cannot log the usage of the encryption key for auditing purposes. So this option is incorrect.

Server-side encryption with customer-provided keys (SSE-C) with automatic key rotation - It is possible to automatically rotate the customer-provided keys but you will need to develop the underlying solution to automate the key rotation. Therefore, this option is not operationally efficient.

References:

https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#master_keys

https://docs.aws.amazon.com/kms/latest/developerguide/rotate-keys.html

https://docs.aws.amazon.com/AmazonS3/latest/userguide/serv-side-encryption.html

## Question 8:

 An IT company has built a solution wherein an Amazon Redshift cluster writes data to an Amazon S3 bucket belonging to a different AWS account. However, it is found that the files created in the Amazon S3 bucket using the UNLOAD command from the Amazon Redshift cluster are not even accessible to the Amazon S3 bucket owner.

What could be the reason for this denial of permission for the bucket owner?

- 1. When two different AWS accounts are accessing an Amazon S3 bucket, both the accounts must share the bucket policies. An erroneous policy can lead to such permission failures
- 2. The owner of an Amazon S3 bucket has implicit access to all objects in his bucket. Permissions are set on objects after they are completely copied to the target location. Since the owner is unable to access the uploaded files, the write operation may be still in progress
- 3. By default, an Amazon S3 object is owned by the AWS account that uploaded it. So the Amazon S3 bucket owner will not implicitly have access to the objects written by the Amazon Redshift cluster(Correct)
- 4. When objects are uploaded to Amazon S3 bucket from a different AWS account, the S3 bucket owner will get implicit permissions to access these objects. This issue seems to be due to an upload error that can be fixed by providing manual access from AWS console

*Correct Answer(s):*
 3. By default, an Amazon S3 object is owned by the AWS account that uploaded it. So the Amazon S3 bucket owner will not implicitly have access to the objects written by the Amazon Redshift cluster

**Explanation:**
Correct option:

By default, an Amazon S3 object is owned by the AWS account that uploaded it. So the Amazon S3 bucket owner will not implicitly have access to the objects written by the Amazon Redshift cluster - By default, an Amazon S3 object is owned by the AWS account that uploaded it. This is true even when the bucket is owned by another account. Because the Amazon Redshift data files from the UNLOAD command were put into your bucket by another account, you (the bucket owner) don't have default permission to access those files.

To get access to the data files, an AWS Identity and Access Management (IAM) role with cross-account permissions must run the UNLOAD command again. Follow these steps to set up the Amazon Redshift cluster with cross-account permissions to the bucket:


From the account of the Amazon S3 bucket, create an IAM role (Bucket Role) with permissions to the bucket.
From the account of the Amazon Redshift cluster, create another IAM role (Cluster Role) with permissions to assume the Bucket Role.
Update the Bucket Role to grant bucket access and create a trust relationship with the Cluster Role.
From the Amazon Redshift cluster, run the UNLOAD command using the Cluster Role and Bucket Role.


This solution doesn't apply to Amazon Redshift clusters or Amazon S3 buckets that use server-side encryption with AWS Key Management Service (AWS KMS).

Incorrect options:

When objects are uploaded to Amazon S3 bucket from a different AWS account, the S3 bucket owner will get implicit permissions to access these objects. This issue seems to be due to an upload error that can be fixed by providing manual access from AWS console - By default, an Amazon S3 object is owned by the AWS account that uploaded it. So, the bucket owner will not have any default permissions on the objects. Therefore, this option is incorrect.

The owner of an Amazon S3 bucket has implicit access to all objects in his bucket. Permissions are set on objects after they are completely copied to the target location. Since the owner is unable to access the uploaded files, the write operation may be still in progress - This is an incorrect statement, given only as a distractor.

When two different AWS accounts are accessing an Amazon S3 bucket, both the accounts must share the bucket policies. An erroneous policy can lead to such permission failures - This is an incorrect statement, given only as a distractor.

Reference:

https://aws.amazon.com/premiumsupport/knowledge-center/s3-access-denied-redshift-unload/

## Question 9:

 An application is currently hosted on four Amazon EC2 instances (behind Application Load Balancer) deployed in a single Availability Zone (AZ). To maintain an acceptable level of end-user experience, the application needs at least 4 instances to be always available.

As a solutions architect, which of the following would you recommend so that the application achieves high availability with MINIMUM cost?

- 1. Deploy the instances in two Availability Zones (AZs). Launch two instances in each Availability Zone (AZ)
- 2. Deploy the instances in three Availability Zones (AZs). Launch two instances in each Availability Zone (AZ)(Correct)
- 3. Deploy the instances in one Availability Zones. Launch two instances in the Availability Zone (AZ)
- 4. Deploy the instances in two Availability Zones (AZs). Launch four instances in each Availability Zone (AZ)

*Correct Answer(s):*
 2. Deploy the instances in three Availability Zones (AZs). Launch two instances in each Availability Zone (AZ)

**Explanation:**
Correct option:

Deploy the instances in three Availability Zones (AZs). Launch two instances in each Availability Zone (AZ)

The correct option is to deploy the instances in three Availability Zones (AZs) and launch two instances in each Availability Zone (AZ). Even if one of the AZs goes out of service, still we shall have 4 instances available and the application can maintain an acceptable level of end-user experience. Therefore, we can achieve high availability with just 6 instances in this case.

Incorrect options:

Deploy the instances in two Availability Zones (AZs). Launch two instances in each Availability Zone (AZ) - When we launch two instances in two AZs, we run the risk of falling below the minimum acceptable threshold of 4 instances if one of the AZs fails. So this option is ruled out.

Deploy the instances in two Availability Zones (AZs). Launch four instances in each Availability Zone (AZ) - When we launch four instances in two AZs, we have to bear costs for 8 instances which is NOT cost-optimal. So this option is ruled out.

Deploy the instances in one Availability Zones. Launch two instances in the Availability Zone (AZ) - We can't have just two instances in a single AZ as that is below the minimum acceptable threshold of 4 instances.

## Question 10:

 What does this IAM policy do?

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Mystery Policy",
      "Action": [
        "ec2:RunInstances"
      ],
      "Effect": "Allow",
      "Resource": "*",
      "Condition": {
        "IpAddress": {
          "aws:SourceIp": "34.50.31.0/24"
        }
      }
    }
  ]
}

- 1. It allows starting an Amazon EC2 instance only when the IP where the call originates is within the 34.50.31.0/24 CIDR block(Correct)
- 2. It allows starting an Amazon EC2 instance only when they have a Public IP within the 34.50.31.0/24 CIDR block
- 3. It allows starting an Amazon EC2 instance only when they have a Private IP within the 34.50.31.0/24 CIDR block
- 4. It allows starting an Amazon EC2 instance only when they have an Elastic IP within the 34.50.31.0/24 CIDR block

*Correct Answer(s):*
 1. It allows starting an Amazon EC2 instance only when the IP where the call originates is within the 34.50.31.0/24 CIDR block

**Explanation:**
Correct option:

It allows starting an Amazon EC2 instance only when the IP where the call originates is within the 34.50.31.0/24 CIDR block

You manage access in AWS by creating policies and attaching them to IAM identities (users, groups of users, or roles) or AWS resources. A policy is an object in AWS that, when associated with an identity or resource, defines their permissions. AWS evaluates these policies when an IAM principal (user or role) makes a request. Permissions in the policies determine whether the request is allowed or denied. Most policies are stored in AWS as JSON documents. AWS supports six types of policies: identity-based policies, resource-based policies, permissions boundaries, Organizations service control policy (SCPs), access control lists (ACLs), and session policies.

Consider the following snippet from the given policy document:

      "Condition": {
        "IpAddress": {
          "aws:SourceIp": "34.50.31.0/24"
        }
      }


The aws:SourceIP in this condition always represents the IP of the caller of the API. That is very helpful if you want to restrict access to certain AWS API for example from the public IP of your on-premises infrastructure.

Please see this overview of Elastic vs Public vs Private IP addresses:

elastic IP address (EIP) - An elastic IP address (EIP) is a static IPv4 address designed for dynamic cloud computing. An Elastic IP address is associated with your AWS account. With an Elastic IP address, you can mask the failure of an instance or software by rapidly remapping the address to another instance in your account.

Private IP address - A private IPv4 address is an IP address that's not reachable over the Internet. You can use private IPv4 addresses for communication between instances in the same VPC.

Public IP address - A public IP address is an IPv4 address that's reachable from the Internet. You can use public addresses for communication between your instances and the Internet.

Please note 34.50.31.0/24 is a public IP range, not a private IP range. Private IP ranges are:
192.168.0.0 - 192.168.255.255 (65,536 IP addresses)
172.16.0.0 - 172.31.255.255 (1,048,576 IP addresses)
10.0.0.0 - 10.255.255.255 (16,777,216 IP addresses)

Incorrect options:

It allows starting an Amazon EC2 instance only when they have a Public IP within the 34.50.31.0/24 CIDR block

It allows starting an Amazon EC2 instance only when they have an Elastic IP within the 34.50.31.0/24 CIDR block

It allows starting an Amazon EC2 instance only when they have a Private IP within the 34.50.31.0/24 CIDR block

Each of these three options suggests that the IP addresses of the Amazon EC2 instances must belong to the 34.50.31.0/24 CIDR block for the EC2 instances to start. Actually, the policy states that the AMazon EC2 instance should start only when the IP where the call originates is within the 34.50.31.0/24 CIDR block. Hence these options are incorrect.

References:

https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html

https://aws.amazon.com/premiumsupport/knowledge-center/iam-restrict-calls-ip-addresses/

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-instance-addressing.html

## Question 11:

 You have been hired as a Solutions Architect to advise a company on the various authentication/authorization mechanisms that AWS offers to authorize an API call within the Amazon API Gateway. The company would prefer a solution that offers built-in user management.

Which of the following solutions would you suggest as the best fit for the given use-case?

- 1. Use Amazon Cognito User Pools(Correct)
- 2. Use AWS Lambda authorizer for Amazon API Gateway
- 3. Use Amazon Cognito Identity Pools
- 4. Use AWS_IAM authorization

*Correct Answer(s):*
 1. Use Amazon Cognito User Pools

**Explanation:**
Correct option:

Use Amazon Cognito User Pools

A user pool is a user directory in Amazon Cognito. You can leverage Amazon Cognito User Pools to either provide built-in user management or integrate with external identity providers, such as Facebook, Twitter, Google+, and Amazon. Whether your users sign-in directly or through a third party, all members of the user pool have a directory profile that you can access through a Software Development Kit (SDK).

User pools provide:
1. Sign-up and sign-in services.
2. A built-in, customizable web UI to sign in users.
3. Social sign-in with Facebook, Google, Login with Amazon, and Sign in with Apple, as well as sign-in with SAML identity providers from your user pool.
4. User directory management and user profiles.
5. Security features such as multi-factor authentication (MFA), checks for compromised credentials, account takeover protection, and phone and email verification.
6. Customized workflows and user migration through AWS Lambda triggers.

After creating an Amazon Cognito user pool, in API Gateway, you must then create a COGNITO_USER_POOLS authorizer that uses the user pool.

Amazon Cognito User Pools:

via - https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/identity-and-access-management.html

Incorrect options:

Use AWS_IAM authorization - For consumers who currently are located within your AWS environment or have the means to retrieve AWS Identity and Access Management (IAM) temporary credentials to access your environment, you can use AWS_IAM authorization and add least-privileged permissions to the respective IAM role to securely invoke your API. API Gateway API Keys is not a security mechanism and should not be used for authorization unless it’s a public API. It should be used primarily to track a consumer’s usage across your API.

Use AWS Lambda authorizer for Amazon API Gateway - If you have an existing Identity Provider (IdP), you can use an AWS Lambda authorizer for Amazon API Gateway to invoke a Lambda function to authenticate/validate a given user against your Identity Provider. You can use a Lambda authorizer for custom validation logic based on identity metadata.

A Lambda authorizer can send additional information derived from a bearer token or request context values to your backend service. For example, the authorizer can return a map containing user IDs, user names, and scope. By using Lambda authorizers, your backend does not need to map authorization tokens to user-centric data, allowing you to limit the exposure of such information to just the authorization function.

When using Lambda authorizers, AWS strictly advises against passing credentials or any sort of sensitive data via query string parameters or headers, so this is not as secure as using Amazon Cognito User Pools.

In addition, both these options do not offer built-in user management.

Use Amazon Cognito Identity Pools - The two main components of Amazon Cognito are user pools and identity pools. Identity pools provide AWS credentials to grant your users access to other AWS services. To enable users in your user pool to access AWS resources, you can configure an identity pool to exchange user pool tokens for AWS credentials. So, identity pools aren't an authentication mechanism in themselves and hence aren't a choice for this use case.

References:

https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/identity-and-access-management.html

https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-enable-cognito-user-pool.html

https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html

## Question 12:

 A financial services company wants a single log processing model for all the log files (consisting of system logs, application logs, database logs, etc) that can be processed in a serverless fashion and then durably stored for downstream analytics. The company wants to use an AWS managed service that automatically scales to match the throughput of the log data and requires no ongoing administration.

As a solutions architect, which of the following AWS services would you recommend solving this problem?

- 1. Amazon EMR
- 2. Amazon Kinesis Data Firehose(Correct)
- 3. AWS Lambda
- 4. Amazon Kinesis Data Streams

*Correct Answer(s):*
 2. Amazon Kinesis Data Firehose

**Explanation:**
Correct option:

Amazon Kinesis Data Firehose

Amazon Kinesis Data Firehose is the easiest way to reliably load streaming data into data lakes, data stores, and analytics tools. It can capture, transform, and load streaming data into Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, and Splunk, enabling near real-time analytics with existing business intelligence tools and dashboards you’re already using today. It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. Therefore, this is the correct option.

Please see this overview of how Kinesis Firehose works:

via - https://aws.amazon.com/kinesis/data-firehose/

Incorrect options:

Amazon Kinesis Data Streams - Amazon Kinesis Data Streams (KDS) is a massively scalable and durable real-time data streaming service. The throughput of an Amazon Kinesis data stream is designed to scale without limits via increasing the number of shards within a data stream. With Amazon Kinesis Data Streams, you can scale up to a sufficient number of shards (note, however, that you'll need to provision enough shards ahead of time). As it requires manual administration of shards, it's not the correct choice for the given use-case.

Amazon EMR - Amazon EMR is the industry-leading cloud big data platform for processing vast amounts of data using open source tools such as Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi, and Presto. With EMR you can run Petabyte-scale analysis at less than half of the cost of traditional on-premises solutions and over 3x faster than standard Apache Spark. Amazon EMR uses Hadoop, an open-source framework, to distribute your data and processing across a resizable cluster of Amazon EC2 instances.

Using an Amazon EMR cluster would imply managing the underlying infrastructure so it’s ruled out.

AWS Lambda - AWS Lambda lets you run code without provisioning or managing servers. It cannot be used for production-grade serverless log analytics.

Reference:

https://aws.amazon.com/kinesis/data-firehose/

## Question 13:

 The engineering manager for a content management application wants to set up Amazon RDS read replicas to provide enhanced performance and read scalability. The manager wants to understand the data transfer charges while setting up Amazon RDS read replicas.

Which of the following would you identify as correct regarding the data transfer charges for Amazon RDS read replicas?

- 1. There are data transfer charges for replicating data across AWS Regions(Correct)
- 2. There are data transfer charges for replicating data within the same Availability Zone (AZ)
- 3. There are data transfer charges for replicating data within the same AWS Region
- 4. There are no data transfer charges for replicating data across AWS Regions

*Correct Answer(s):*
 1. There are data transfer charges for replicating data across AWS Regions

**Explanation:**
Correct option:

There are data transfer charges for replicating data across AWS Regions

Amazon RDS Read Replicas provide enhanced performance and durability for Amazon RDS database (DB) instances. They make it easy to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads.

A read replica is billed as a standard DB Instance and at the same rates. You are not charged for the data transfer incurred in replicating data between your source DB instance and read replica within the same AWS Region.


via - https://aws.amazon.com/rds/faqs/

Incorrect options:

There are data transfer charges for replicating data within the same Availability Zone (AZ)

There are data transfer charges for replicating data within the same AWS Region

There are no data transfer charges for replicating data across AWS Regions

These three options contradict the explanation provided above, so these options are incorrect.

Reference:

https://aws.amazon.com/rds/faqs/

## Question 14:

 A company has historically operated only in the us-east-1 region and stores encrypted data in Amazon S3 using SSE-KMS. As part of enhancing its security posture as well as improving the backup and recovery architecture, the company wants to store the encrypted data in Amazon S3 that is replicated into the us-west-1 AWS region. The security policies mandate that the data must be encrypted and decrypted using the same key in both AWS regions.

Which of the following represents the best solution to address these requirements?

- 1. Create an Amazon CloudWatch scheduled rule to invoke an AWS Lambda function to copy the daily data from the source bucket in us-east-1 region to the destination bucket in us-west-1 region. Provide AWS KMS key access to the AWS Lambda function for encryption and decryption operations on the data in the source and destination Amazon S3 buckets
- 2. Enable replication for the current bucket in us-east-1 region into another bucket in us-west-1 region. Share the existing AWS KMS key from us-east-1 region to us-west-1 region
- 3. Change the AWS KMS single region key used for the current Amazon S3 bucket into an AWS KMS multi-region key. Enable Amazon S3 batch replication for the existing data in the current bucket in us-east-1 region into another bucket in us-west-1 region
- 4. Create a new Amazon S3 bucket in the us-east-1 region with replication enabled from this new bucket into another bucket in us-west-1 region. Enable SSE-KMS encryption on the new bucket in us-east-1 region by using an AWS KMS multi-region key. Copy the existing data from the current Amazon S3 bucket in us-east-1 region into this new Amazon S3 bucket in us-east-1 region(Correct)

*Correct Answer(s):*
 4. Create a new Amazon S3 bucket in the us-east-1 region with replication enabled from this new bucket into another bucket in us-west-1 region. Enable SSE-KMS encryption on the new bucket in us-east-1 region by using an AWS KMS multi-region key. Copy the existing data from the current Amazon S3 bucket in us-east-1 region into this new Amazon S3 bucket in us-east-1 region

**Explanation:**
Correct option:

Create a new Amazon S3 bucket in the us-east-1 region with replication enabled from this new bucket into another bucket in us-west-1 region. Enable SSE-KMS encryption on the new bucket in us-east-1 region by using an AWS KMS multi-region key. Copy the existing data from the current Amazon S3 bucket in us-east-1 region into this new Amazon S3 bucket in us-east-1 region

AWS KMS supports multi-region keys, which are AWS KMS keys in different AWS regions that can be used interchangeably – as though you had the same key in multiple regions. Each set of related multi-region keys has the same key material and key ID, so you can encrypt data in one AWS region and decrypt it in a different AWS region without re-encrypting or making a cross-region call to AWS KMS.

You can use multi-region AWS KMS keys in Amazon S3. However, Amazon S3 currently treats multi-region keys as though they were single-region keys, and does not use the multi-region features of the key.

Multi-region AWS KMS keys:

via - https://docs.aws.amazon.com/kms/latest/developerguide/multi-region-keys-overview.html

For the given use case, you must create a new bucket in the us-east-1 region with replication enabled from this new bucket into another bucket in us-west-1 region. This would ensure that the data is available in another region for backup and recovery purposes. You should also enable SSE-KMS encryption on the new bucket in us-east-1 region by using an AWS KMS multi-region key so that the data can be encrypted and decrypted using the same key in both AWS regions. Since the existing data in the current bucket was encrypted using the AWS KMS key restricted to the us-east-1 region, so data must be copied to the new bucket in us-east-1 region for replication as well as multi-region KMS key based encryption to kick-in.

To require server-side encryption of all objects in a particular Amazon S3 bucket, you can use a policy. For example, the following bucket policy denies the upload object (s3:PutObject) permission to everyone if the request does not include the x-amz-server-side-encryption header requesting server-side encryption with SSE-KMS.

{
   "Version":"2012-10-17",
   "Id":"PutObjectPolicy",
   "Statement":[{
         "Sid":"DenyUnEncryptedObjectUploads",
         "Effect":"Deny",
         "Principal":"*",
         "Action":"s3:PutObject",
         "Resource":"arn:aws:s3:::DOC-EXAMPLE-BUCKET1/*",
         "Condition":{
            "StringNotEquals":{
               "s3:x-amz-server-side-encryption":"aws:kms"
            }
         }
      }
   ]
}


The following example IAM policies show statements for using AWS KMS server-side encryption with replication.

In this example, the encryption context is the object ARN. If you use SSE-KMS with an Amazon S3 Bucket Key enabled, you must use the bucket ARN as the encryption context.

{
    "Version": "2012-10-17",
    "Statement": [{
            "Action": ["kms:Decrypt"],
            "Effect": "Allow",
            "Resource": "List of AWS KMS key ARNs used to encrypt source objects.",
            "Condition": {
                "StringLike": {
                    "kms:ViaService": "s3.source-bucket-region.amazonaws.com",
                    "kms:EncryptionContext:aws:s3:arn": "arn:aws:s3:::source-bucket-name/key-prefix1/*"
                }
            }
        },

        {
            "Action": ["kms:Encrypt"],
            "Effect": "Allow",
            "Resource": "AWS KMS key ARNs (for the AWS Region of the destination bucket 1). Used to encrypt object replicas created in destination bucket 1.",
            "Condition": {
                "StringLike": {
                    "kms:ViaService": "s3.destination-bucket-1-region.amazonaws.com",
                    "kms:EncryptionContext:aws:s3:arn": "arn:aws:s3:::destination-bucket-name-1/key-prefix1/*"
                }
            }
        },
        {
            "Action": ["kms:Encrypt"],
            "Effect": "Allow",
            "Resource": "AWS KMS key ARNs (for the AWS Region of destination bucket 2). Used to encrypt object replicas created in destination bucket 2.",
            "Condition": {
                "StringLike": {
                    "kms:ViaService": "s3.destination-bucket-2-region.amazonaws.com",
                    "kms:EncryptionContext:aws:s3:arn": "arn:aws:s3:::destination-bucket-2-name/key-prefix1*"
                }
            }
        }
    ]
}


Incorrect options:

Change the AWS KMS single region key used for the current Amazon S3 bucket into an AWS KMS multi-region key. Enable Amazon S3 batch replication for the existing data in the current bucket in us-east-1 region into another bucket in us-west-1 region - Amazon S3 batch replication can certainly be used to replicate the existing data in the current bucket in us-east-1 region into another bucket in us-west-1 region.

However, you cannot convert an existing single-Region key to a multi-Region key. This design ensures that all data protected with existing single-Region keys maintain the same data residency and data sovereignty properties. So this option is incorrect.

Enable replication for the current bucket in us-east-1 region into another bucket in us-west-1 region. Share the existing AWS KMS key from us-east-1 region to us-west-1 region - You cannot share an AWS KMS key to another region, so this option is incorrect.

Create an Amazon CloudWatch scheduled rule to invoke an AWS Lambda function to copy the daily data from the source bucket in us-east-1 region to the destination bucket in us-west-1 region. Provide AWS KMS key access to the AWS Lambda function for encryption and decryption operations on the data in the source and destination Amazon S3 buckets - This option is a distractor as the daily frequency of data replication would result in significant data loss in case of a disaster. In addition, this option involves significant development effort to create the functionality to reliably replicate the data from source to destination buckets. So this option is not the best fit for the given use case.

References:

https://docs.aws.amazon.com/kms/latest/developerguide/multi-region-keys-overview.html

https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication-config-for-kms-objects.html

## Question 15:

 An HTTP application is deployed on an Auto Scaling Group, is accessible from an Application Load Balancer (ALB) that provides HTTPS termination, and accesses a PostgreSQL database managed by Amazon RDS.

How should you configure the security groups? (Select three)

- 1. The security group of the Application Load Balancer should have an inbound rule from anywhere on port 80
- 2. The security group of Amazon RDS should have an inbound rule from the security group of the Amazon EC2 instances in the Auto Scaling group on port 80
- 3. The security group of Amazon RDS should have an inbound rule from the security group of the Amazon EC2 instances in the Auto Scaling group on port 5432(Correct)
- 4. The security group of the Amazon EC2 instances should have an inbound rule from the security group of the Application Load Balancer on port 80(Correct)
- 5. The security group of the Amazon EC2 instances should have an inbound rule from the security group of the Amazon RDS database on port 5432
- 6. The security group of the Application Load Balancer should have an inbound rule from anywhere on port 443(Correct)

*Correct Answer(s):*
 3. The security group of Amazon RDS should have an inbound rule from the security group of the Amazon EC2 instances in the Auto Scaling group on port 54324. The security group of the Amazon EC2 instances should have an inbound rule from the security group of the Application Load Balancer on port 806. The security group of the Application Load Balancer should have an inbound rule from anywhere on port 443

**Explanation:**
Correct options:

The security group of Amazon RDS should have an inbound rule from the security group of the Amazon EC2 instances in the Auto Scaling group on port 5432

The security group of the Amazon EC2 instances should have an inbound rule from the security group of the Application Load Balancer on port 80

The security group of the Application Load Balancer should have an inbound rule from anywhere on port 443

A security group acts as a virtual firewall that controls the traffic for one or more instances. When you launch an instance, you can specify one or more security groups; otherwise, we use the default security group. You can add rules to each security group that allows traffic to or from its associated instances. You can modify the rules for a security group at any time; the new rules are automatically applied to all instances that are associated with the security group. When we decide whether to allow traffic to reach an instance, we evaluate all the rules from all the security groups that are associated with the instance.

The following are the characteristics of security group rules:
1. By default, security groups allow all outbound traffic.
2. Security group rules are always permissive; you can't create rules that deny access.
3. Security groups are stateful

PostgreSQL port = 5432
HTTP port = 80
HTTPS port = 443

The traffic goes like this :
The client sends an HTTPS request to ALB on port 443. This is handled by the rule - "The security group of the Application Load Balancer should have an inbound rule from anywhere on port 443"

The Application Load Balancer then forwards the request to one of the Amazon EC2 instances. This is handled by the rule - "The security group of the Amazon EC2 instances should have an inbound rule from the security group of the Application Load Balancer on port 80"

The Amazon EC2 instance further accesses the PostgreSQL database managed by Amazon RDS on port 5432. This is handled by the rule - "The security group of Amazon RDS should have an inbound rule from the security group of the Amazon EC2 instances in the Auto Scaling group on port 5432"

Incorrect options:

The security group of the Application Load Balancer should have an inbound rule from anywhere on port 80 - The client sends an HTTPS request to ALB on port 443 and not on port 80, so this is incorrect.

The security group of the Amazon EC2 instances should have an inbound rule from the security group of the Amazon RDS database on port 5432 - The security group of the Amazon EC2 instances should have an inbound rule from the security group of the Application Load Balancer and not from the security group of the Amazon RDS database, so this option is incorrect.

The security group of Amazon RDS should have an inbound rule from the security group of the Amazon EC2 instances in the Auto Scaling group on port 80 - The Amazon EC2 instance further accesses the PostgreSQL database managed by Amazon RDS on port 5432 and not on port 80, so this option is incorrect.

Reference:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html

## Question 16:

 A silicon valley based startup has a two-tier architecture using Amazon EC2 instances for its flagship application. The web servers (listening on port 443), which have been assigned security group A, are in public subnets across two Availability Zones (AZs) and the MSSQL based database instances (listening on port 1433), which have been assigned security group B, are in two private subnets across two Availability Zones (AZs). The DevOps team wants to review the security configurations of the application architecture.

As a solutions architect, which of the following options would you select as the MOST secure configuration? (Select two)

- 1. For security group A: Add an inbound rule that allows traffic from all sources on port 443. Add an outbound rule with the destination as security group B on port 1433(Correct)
- 2. For security group B: Add an inbound rule that allows traffic only from security group A on port 1433(Correct)
- 3. For security group B: Add an inbound rule that allows traffic only from security group A on port 443
- 4. For security group B: Add an inbound rule that allows traffic only from all sources on port 1433
- 5. For security group A: Add an inbound rule that allows traffic from all sources on port 443. Add an outbound rule with the destination as security group B on port 443

*Correct Answer(s):*
 1. For security group A: Add an inbound rule that allows traffic from all sources on port 443. Add an outbound rule with the destination as security group B on port 14332. For security group B: Add an inbound rule that allows traffic only from security group A on port 1433

**Explanation:**
Correct options:

For security group A: Add an inbound rule that allows traffic from all sources on port 443. Add an outbound rule with the destination as security group B on port 1433

For security group B: Add an inbound rule that allows traffic only from security group A on port 1433

A security group acts as a virtual firewall that controls the traffic for one or more instances. When you launch an instance, you can specify one or more security groups; otherwise, we use the default security group. You can add rules to each security group that allows traffic to or from its associated instances. You can modify the rules for a security group at any time; the new rules are automatically applied to all instances that are associated with the security group. When we decide whether to allow traffic to reach an instance, we evaluate all the rules from all the security groups that are associated with the instance.

The following are the characteristics of security group rules:

By default, security groups allow all outbound traffic.

Security group rules are always permissive; you can't create rules that deny access.

Security groups are stateful

The MOST secure configuration for the given use case is:

For security group A: Add an inbound rule that allows traffic from all sources on port 443. Add an outbound rule with the destination as security group B on port 1433

The above rules make sure that web servers are listening for traffic on all sources on the HTTPS protocol on port 443. The web servers only allow outbound traffic to MSSQL servers in Security Group B on port 1433.

For security group B: Add an inbound rule that allows traffic only from security group A on port 1433.
The above rule makes sure that the MSSQL servers only accept traffic from web servers in security group A on port 1433.

Therefore, both of these options are correct.

Incorrect options:

For security group A: Add an inbound rule that allows traffic from all sources on port 443. Add an outbound rule with the destination as security group B on port 443 - As the MSSQL based database instances are listening on port 1433, therefore for security group A, the outbound rule should be added on port 443 with the destination as security group B.

For security group B: Add an inbound rule that allows traffic only from all sources on port 1433 - The inbound rule should allow traffic only from security group A on port 1433. Allowing traffic from all sources will compromise security.

For security group B: Add an inbound rule that allows traffic only from security group A on port 443 -  The inbound rule should allow traffic only from security group A on port 1433 because the MSSQL based database instances are listening on port 1433.

Reference:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html

## Question 17:

 A company has recently launched a new mobile gaming application that the users are adopting rapidly. The company uses Amazon RDS MySQL as the database. The engineering team wants an urgent solution to this issue where the rapidly increasing workload might exceed the available database storage.

As a solutions architect, which of the following solutions would you recommend so that it requires minimum development and systems administration effort to address this requirement?

- 1. Migrate Amazon RDS MySQL database to Amazon DynamoDB which automatically allocates storage space when required
- 2. Migrate RDS MySQL database to Amazon Aurora which offers storage auto-scaling
- 3. Create read replica for Amazon RDS MySQL
- 4. Enable storage auto-scaling for Amazon RDS MySQL(Correct)

*Correct Answer(s):*
 4. Enable storage auto-scaling for Amazon RDS MySQL

**Explanation:**
Correct option:

Enable storage auto-scaling for Amazon RDS MySQL

If your workload is unpredictable, you can enable storage autoscaling for an Amazon RDS DB instance. With storage autoscaling enabled, when Amazon RDS detects that you are running out of free database space it automatically scales up your storage. Amazon RDS starts a storage modification for an autoscaling-enabled DB instance when these factors apply:

Free available space is less than 10 percent of the allocated storage.

The low-storage condition lasts at least five minutes.

At least six hours have passed since the last storage modification.

The maximum storage threshold is the limit that you set for autoscaling the DB instance. You can't set the maximum storage threshold for autoscaling-enabled instances to a value greater than the maximum allocated storage.

Incorrect options:

Migrate RDS MySQL database to Amazon Aurora which offers storage auto-scaling - Although Aurora offers automatic storage scaling, this option is ruled out since it involves significant systems administration effort to migrate from Amazon RDS MySQL to Aurora. It is much easier to just enable storage auto-scaling for Amazon RDS MySQL.

Migrate Amazon RDS MySQL database to Amazon DynamoDB which automatically allocates storage space when required - This option is ruled out since Amazon DynamoDB is a NoSQL database which implies significant development effort to change the application logic to connect and query data from the underlying database. It is much easier to just enable storage auto-scaling for Amazon RDS MySQL.

Create read replica for Amazon RDS MySQL - Read replicas make it easy to take advantage of supported engines' built-in replication functionality to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads. You can create multiple read replicas for a given source DB Instance and distribute your application’s read traffic amongst them. This option acts as a distractor as read replicas cannot help to automatically scale storage for the primary database.

Reference:

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIOPS.StorageTypes.html

## Question 18:

 A retail company wants to rollout and test a blue-green deployment for its global application in the next 48 hours. Most of the customers use mobile phones which are prone to Domain Name System (DNS) caching. The company has only two days left for the annual Thanksgiving sale to commence.

As a Solutions Architect, which of the following options would you recommend to test the deployment on as many users as possible in the given time frame?

- 1. Use AWS CodeDeploy deployment options to choose the right deployment
- 2. Use Elastic Load Balancing (ELB) to distribute traffic across deployments
- 3. Use AWS Global Accelerator to distribute a portion of traffic to a particular deployment(Correct)
- 4. Use Amazon Route 53 weighted routing to spread traffic across different deployments

*Correct Answer(s):*
 3. Use AWS Global Accelerator to distribute a portion of traffic to a particular deployment

**Explanation:**
Correct option:

Blue/green deployment is a technique for releasing applications by shifting traffic between two identical environments running different versions of the application: "Blue" is the currently running version and "green" the new version. This type of deployment allows you to test features in the green environment without impacting the currently running version of your application. When you’re satisfied that the green version is working properly, you can gradually reroute the traffic from the old blue environment to the new green environment. Blue/green deployments can mitigate common risks associated with deploying software, such as downtime and rollback capability.

Use AWS Global Accelerator to distribute a portion of traffic to a particular deployment

AWS Global Accelerator is a network layer service that directs traffic to optimal endpoints over the AWS global network, this improves the availability and performance of your internet applications. It provides two static anycast IP addresses that act as a fixed entry point to your application endpoints in a single or multiple AWS Regions, such as your Application Load Balancers, Network Load Balancers, Elastic IP addresses or Amazon EC2 instances, in a single or in multiple AWS regions.

AWS Global Accelerator uses endpoint weights to determine the proportion of traffic that is directed to endpoints in an endpoint group, and traffic dials to control the percentage of traffic that is directed to an endpoint group (an AWS region where your application is deployed).

While relying on the DNS service is a great option for blue/green deployments, it may not fit use-cases that require a fast and controlled transition of the traffic. Some client devices and internet resolvers cache DNS answers for long periods; this DNS feature improves the efficiency of the DNS service as it reduces the DNS traffic across the Internet, and serves as a resiliency technique by preventing authoritative name-server overloads. The downside of this in blue/green deployments is that you don’t know how long it will take before all of your users receive updated IP addresses when you update a record, change your routing preference or when there is an application failure.

With AWS Global Accelerator, you can shift traffic gradually or all at once between the blue and the green environment and vice-versa without being subject to DNS caching on client devices and internet resolvers, traffic dials and endpoint weights changes are effective within seconds.

Incorrect options:

Use Amazon Route 53 weighted routing to spread traffic across different deployments - Weighted routing lets you associate multiple resources with a single domain name (example.com) or subdomain name (acme.example.com) and choose how much traffic is routed to each resource. This can be useful for a variety of purposes, including load balancing and testing new versions of the software. As discussed earlier, DNS caching is a negative behavior for this use case and hence Amazon Route 53 is not a good option.

Use Elastic Load Balancing (ELB) to distribute traffic across deployments - Elastic Load Balancing (ELB) can distribute traffic across healthy instances. You can also use the Application Load Balancers weighted target groups feature for blue/green deployments as it does not rely on the DNS service. In addition you don’t need to create new ALBs for the green environment. As the use-case refers to a global application, so this option cannot be used for a multi-Region solution which is needed for the given requirement.

Use AWS CodeDeploy deployment options to choose the right deployment - In AWS CodeDeploy, a deployment is the process, and the components involved in the process, of installing content on one or more instances. This content can consist of code, web and configuration files, executables, packages, scripts, and so on. AWS CodeDeploy deploys content that is stored in a source repository, according to the configuration rules you specify. Blue/Green deployment is one of the deployment types that CodeDeploy supports. CodeDeploy is not meant to distribute traffic across instances, so this option is incorrect.

References:

https://aws.amazon.com/blogs/networking-and-content-delivery/using-aws-global-accelerator-to-achieve-blue-green-deployments

https://docs.aws.amazon.com/codedeploy/latest/userguide/deployments.html

https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-weighted

## Question 19:

 An IT company wants to optimize the costs incurred on its fleet of 100 Amazon EC2 instances for the next year. Based on historical analyses, the engineering team observed that 70 of these instances handle the compute services of its flagship application and need to be always available. The other 30 instances are used to handle batch jobs that can afford a delay in processing.

As a solutions architect, which of the following would you recommend as the MOST cost-optimal solution?

- 1. Purchase 70 reserved instances (RIs) and 30 spot instances(Correct)
- 2. Purchase 70 reserved instances and 30 on-demand instances
- 3. Purchase 70 on-demand instances and 30 reserved instances
- 4. Purchase 70 on-demand instances and 30 spot instances

*Correct Answer(s):*
 1. Purchase 70 reserved instances (RIs) and 30 spot instances

**Explanation:**
Correct option:

Purchase 70 reserved instances (RIs) and 30 spot instances

As 70 instances need to be always available, these can be purchased as reserved instances for a one-year duration.
The other 30 instances responsible for the batch job can be purchased as spot instances. Even if some of the spot instances are interrupted, other spot instances can continue with the job.

Please see this detailed overview of various types of Amazon EC2 instances from a pricing perspective:

via - https://aws.amazon.com/ec2/pricing/

Incorrect options:

Purchase 70 on-demand instances and 30 spot instances

Purchase 70 on-demand instances and 30 reserved instances

Purchasing 70 on-demand instances would be costlier than 70 reserved instances, so these two options are ruled out.

Purchase 70 reserved instances and 30 on-demand instances - Purchasing 30 instances as on-demand instances to handle the batch jobs would not be cost-optimal as these instances don't need to be always available. Spot instances are better at handling such batch jobs. So this option is not correct.

Reference:

https://aws.amazon.com/ec2/pricing/

## Question 20:

 An analytics company wants to improve the performance of its big data processing workflows running on Amazon Elastic File System (Amazon EFS). Which of the following performance modes should be used for Amazon EFS to address this requirement?

- 1. General Purpose
- 2. Provisioned Throughput
- 3. Max I/O(Correct)
- 4. Bursting Throughput

*Correct Answer(s):*
 3. Max I/O

**Explanation:**
Correct option:

Max I/O

How Amazon EFS Works:

via - https://aws.amazon.com/efs/

Max I/O performance mode is used to scale to higher levels of aggregate throughput and operations per second. This scaling is done with a tradeoff of slightly higher latencies for file metadata operations. Highly parallelized applications and workloads, such as big data analysis, media processing, and genomic analysis, can benefit from this mode.


via - https://docs.aws.amazon.com/efs/latest/ug/performance.html

Incorrect options:

Provisioned Throughput

Bursting Throughput

These two options have been added as distractors as these refer to the throughput mode of Amazon EFS and not the performance mode. There are two throughput modes to choose from for your file system, Bursting Throughput and Provisioned Throughput. With Bursting Throughput mode, throughput on Amazon EFS scales as the size of your file system in the standard storage class grows. With Provisioned Throughput mode, you can instantly provision the throughput of your file system (in MiB/s) independent of the amount of data stored.

General Purpose - General Purpose performance mode is ideal for latency-sensitive use cases, like web serving environments, content management systems, home directories, and general file serving. If you don't choose a performance mode when you create your file system, Amazon EFS selects the General Purpose mode for you by default.

References:

https://docs.aws.amazon.com/efs/latest/ug/performance.html

https://aws.amazon.com/efs/

## Question 21:

 A social media application is hosted on an Amazon EC2 fleet running behind an Application Load Balancer. The application traffic is fronted by an Amazon CloudFront distribution. The engineering team wants to decouple the user authentication process for the application, so that the application servers can just focus on the business logic.

As a Solutions Architect, which of the following solutions would you recommend to the development team so that it requires minimal development effort?

- 1. Use Amazon Cognito Authentication via Cognito Identity Pools for your Application Load Balancer
- 2. Use Amazon Cognito Authentication via Cognito User Pools for your Application Load Balancer(Correct)
- 3. Use Amazon Cognito Authentication via Cognito User Pools for your Amazon CloudFront distribution
- 4. Use Amazon Cognito Authentication via Cognito Identity Pools for your Amazon CloudFront distribution

*Correct Answer(s):*
 2. Use Amazon Cognito Authentication via Cognito User Pools for your Application Load Balancer

**Explanation:**
Correct option:

Use Amazon Cognito Authentication via Cognito User Pools for your Application Load Balancer

Application Load Balancer can be used to securely authenticate users for accessing your applications. This enables you to offload the work of authenticating users to your load balancer so that your applications can focus on their business logic. You can use Cognito User Pools to authenticate users through well-known social IdPs, such as Amazon, Facebook, or Google, through the user pools supported by Amazon Cognito or through corporate identities, using SAML, LDAP, or Microsoft AD, through the user pools supported by Amazon Cognito. You configure user authentication by creating an authenticate action for one or more listener rules.


via - https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-authenticate-users.html

Exam Alert:

Please review the following note to understand the differences between Amazon Cognito User Pools and Amazon Cognito Identity Pools:

via - https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html

Incorrect options:

Use Amazon Cognito Authentication via Cognito Identity Pools for your Application Load Balancer - There is no such thing as using Amazon Cognito Authentication via Cognito Identity Pools for managing user authentication for the application. Application-specific user authentication can be provided via Cognito User Pools. Amazon Cognito identity pools provide temporary AWS credentials for users who are guests (unauthenticated) and for users who have been authenticated and received a token.

Use Amazon Cognito Authentication via Cognito User Pools for your Amazon CloudFront distribution - You cannot directly integrate Cognito User Pools with CloudFront distribution as you have to create a separate AWS Lambda@Edge function to accomplish the authentication via Cognito User Pools. This involves additional development effort, so this option is not the best fit for the given use-case.

Use Amazon Cognito Authentication via Cognito Identity Pools for your Amazon CloudFront distribution - You cannot use Cognito Identity Pools for managing user authentication, so this option is not correct.

References:

https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-authenticate-users.html

https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html

https://aws.amazon.com/blogs/networking-and-content-delivery/authorizationedge-using-cookies-protect-your-amazon-cloudfront-content-from-being-downloaded-by-unauthenticated-users/

## Question 22:

 An IT company has an Access Control Management (ACM) application that uses Amazon RDS for MySQL but is running into performance issues despite using Read Replicas. The company has hired you as a solutions architect to address these performance-related challenges without moving away from the underlying relational database schema. The company has branch offices across the world, and it needs the solution to work on a global scale.

Which of the following will you recommend as the MOST cost-effective and high-performance solution?

- 1. Use Amazon DynamoDB Global Tables to provide fast, local, read and write performance in each region
- 2. Spin up Amazon EC2 instances in each AWS region, install MySQL databases and migrate the existing data into these new databases
- 3. Spin up a Amazon Redshift cluster in each AWS region. Migrate the existing data into Redshift clusters
- 4. Use Amazon Aurora Global Database to enable fast local reads with low latency in each region(Correct)

*Correct Answer(s):*
 4. Use Amazon Aurora Global Database to enable fast local reads with low latency in each region

**Explanation:**
Correct option:

Use Amazon Aurora Global Database to enable fast local reads with low latency in each region

Amazon Aurora is a MySQL and PostgreSQL-compatible relational database built for the cloud, that combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases. Amazon Aurora features a distributed, fault-tolerant, self-healing storage system that auto-scales up to 64TB per database instance. Aurora is not an in-memory database.

Amazon Aurora Global Database is designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS regions. It replicates your data with no impact on database performance, enables fast local reads with low latency in each region, and provides disaster recovery from region-wide outages. Amazon Aurora Global Database is the correct choice for the given use-case.

Amazon Aurora Global Database Features:

via - https://aws.amazon.com/rds/aurora/global-database/

Incorrect options:

Use Amazon DynamoDB Global Tables to provide fast, local, read and write performance in each region - Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale. It's a fully managed, multi-region, multi-master, durable database with built-in security, backup and restore, and in-memory caching for internet-scale applications.

Global Tables builds upon DynamoDB’s global footprint to provide you with a fully managed, multi-region, and multi-master database that provides fast, local, read, and write performance for massively scaled, global applications. Global Tables replicates your Amazon DynamoDB tables automatically across your choice of AWS regions. Given that the use-case wants you to continue with the underlying schema of the relational database, DynamoDB is not the right choice as it's a NoSQL database.

Amazon DynamoDB Global Tables Overview:

via - https://aws.amazon.com/dynamodb/global-tables/

Spin up a Amazon Redshift cluster in each AWS region. Migrate the existing data into Redshift clusters - Amazon Redshift is a fully-managed petabyte-scale cloud-based data warehouse product designed for large scale data set storage and analysis. Amazon Redshift is not suited to be used as a transactional relational database, so this option is not correct.

Spin up Amazon EC2 instances in each AWS region, install MySQL databases and migrate the existing data into these new databases - Setting up Amazon EC2 instances in multiple regions with manually managed MySQL databases represents a maintenance nightmare and is not the correct choice for this use-case.

References:

https://aws.amazon.com/rds/aurora/global-database/

https://aws.amazon.com/dynamodb/global-tables/

## Question 23:

 You would like to use AWS Snowball to move on-premises backups into a long term archival tier on AWS. Which solution provides the MOST cost savings?

- 1. Create a AWS Snowball job and target an Amazon S3 Glacier Deep Archive Vault
- 2. Create an AWS Snowball job and target an Amazon S3 bucket. Create a lifecycle policy to transition this data to Amazon S3 Glacier Deep Archive on the same day(Correct)
- 3. Create an AWS Snowball job and target a Amazon S3 Glacier Vault
- 4. Create an AWS Snowball job and target an Amazon S3 bucket. Create a lifecycle policy to transition this data to Amazon S3 Glacier on the same day

*Correct Answer(s):*
 2. Create an AWS Snowball job and target an Amazon S3 bucket. Create a lifecycle policy to transition this data to Amazon S3 Glacier Deep Archive on the same day

**Explanation:**
Correct option:

Create an AWS Snowball job and target an Amazon S3 bucket. Create a lifecycle policy to transition this data to Amazon S3 Glacier Deep Archive on the same day

AWS Snowball, a part of the AWS Snow Family, is a data migration and edge computing device that comes in two options. Snowball Edge Storage Optimized devices provide both block storage and Amazon S3-compatible object storage, and 40 vCPUs. They are well suited for local storage and large scale data transfer. AWS Snowball Edge Compute Optimized devices provide 52 vCPUs, block and object storage, and an optional GPU for use cases like advanced machine learning and full-motion video analysis in disconnected environments.

AWS Snowball Edge Storage Optimized is the optimal choice if you need to securely and quickly transfer dozens of terabytes to petabytes of data to AWS. It provides up to 80 terabytes of usable HDD storage, 40 vCPUs, 1 terabyte of SATA SSD storage, and up to 40 gigabytes network connectivity to address large scale data transfer and pre-processing use cases.

The original AWS Snowball devices were transitioned out of service and AWS Snowball Edge Storage Optimized are now the primary devices used for data transfer. You may see the AWS Snowball device on the exam, just remember that the original AWS Snowball device had 80 terabytes of storage space.

For this scenario, you will want to minimize the time spent in Amazon S3 Standard for all files to avoid unintended Amazon S3 Standard storage charges. To do this, AWS recommends using a zero-day lifecycle policy. From a cost perspective, when using a zero-day lifecycle policy, you are only charged Amazon S3 Glacier Deep Archive rates. When billed, the lifecycle policy is accounted for first, and if the destination is Amazon S3 Glacier Deep Archive, you are charged Amazon S3 Glacier Deep Archive rates for the transferred files.

You can't move data directly from AWS Snowball into Amazon S3 Glacier, you need to go through Amazon S3 first, and then use a lifecycle policy. So this option is correct.

Incorrect options:

Create an AWS Snowball job and target a Amazon S3 Glacier Vault

Create a AWS Snowball job and target an Amazon S3 Glacier Deep Archive Vault

Amazon S3 Glacier and S3 Glacier Deep Archive are a secure, durable, and extremely low-cost Amazon S3 cloud storage classes for data archiving and long-term backup. They are designed to deliver 99.999999999% durability and provide comprehensive security and compliance capabilities that can help meet even the most stringent regulatory requirements.
Finally, Amazon S3 Glacier Deep Archive provides more cost savings than Amazon S3 Glacier.

Both these options are incorrect as you can't move data directly from AWS Snowball into a Amazon S3 Glacier Vault or a Glacier Deep Archive Vault. You need to go through Amazon S3 first and then use a lifecycle policy.

Create an AWS Snowball job and target an Amazon S3 bucket. Create a lifecycle policy to transition this data to Amazon S3 Glacier on the same day - As Amazon S3 Glacier Deep Archive provides more cost savings than Amazon S3 Glacier, you should use Amazon S3 Glacier Deep Archive for long term archival for this use-case.

References:

https://aws.amazon.com/snowball/features/

https://aws.amazon.com/glacier/

## Question 24:

 Amazon EC2 Auto Scaling needs to terminate an instance from Availability Zone (AZ) us-east-1a as it has the most number of instances amongst the Availability Zone (AZs) being used currently. There are 4 instances in the Availability Zone (AZ) us-east-1a like so: Instance A has the oldest launch template, Instance B has the oldest launch configuration, Instance C has the newest launch configuration and Instance D is closest to the next billing hour.

Which of the following instances would be terminated per the default termination policy?

- 1. Instance C
- 2. Instance A
- 3. Instance B(Correct)
- 4. Instance D

*Correct Answer(s):*
 3. Instance B

**Explanation:**
Correct option:

Instance B

Per the default termination policy, the first priority is given to any allocation strategy for On-Demand vs Spot instances. As no such information has been provided for the given use-case, so this criterion can be ignored. The next priority is to consider any instance with the oldest launch template unless there is an instance that uses a launch configuration. So this rules out Instance A. Next, you need to consider any instance which has the oldest launch configuration. This implies Instance B will be selected for termination and Instance C will also be ruled out as it has the newest launch configuration. Instance D, which is closest to the next billing hour, is not selected as this criterion is last in the order of priority.

Please see this note for a deep-dive on the default termination policy:


via - https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html

Incorrect options:

Instance A

Instance C

Instance D

These three options contradict the explanation provided above, so these options are incorrect.

Reference:

https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html

## Question 25:

 A company has many Amazon Virtual Private Cloud (Amazon VPC) in various accounts, that need to be connected in a star network with one another and connected with on-premises networks through AWS Direct Connect.

What do you recommend?

- 1. AWS Transit Gateway(Correct)
- 2. VPC Peering Connection
- 3. AWS PrivateLink
- 4. Virtual private gateway (VGW)

*Correct Answer(s):*
 1. AWS Transit Gateway

**Explanation:**
Correct option:

AWS Transit Gateway

AWS Transit Gateway is a service that enables customers to connect their Amazon Virtual Private Clouds (VPCs) and their on-premises networks to a single gateway. With AWS Transit Gateway, you only have to create and manage a single connection from the central gateway into each Amazon VPC, on-premises data center, or remote office across your network. Transit Gateway acts as a hub that controls how traffic is routed among all the connected networks which act like spokes.
So, this is a perfect use-case for the Transit Gateway.

Without AWS Transit Gateway

via - https://aws.amazon.com/transit-gateway/

With AWS Transit Gateway

via - https://aws.amazon.com/transit-gateway/

Incorrect options:

VPC Peering Connection - A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your VPCs, or with a VPC in another AWS account. The VPCs can be in different regions (also known as an inter-region VPC peering connection).

VPC Peering helps connect two VPCs and is not transitive. It would require to create many peering connections between all the VPCs to have them connect. This alone wouldn't work, because we would need to also connect the on-premises data center through Direct Connect and Direct Connect Gateway, but that's not mentioned in this answer.

Virtual private gateway (VGW) - A virtual private gateway (VGW), also known as a VPN Gateway, is the endpoint on the VPC side of your VPN connection. You can create a virtual private gateway before creating the VPC itself.
VPN Gateway is a distractor here because we haven't mentioned a VPN.

AWS PrivateLink - AWS PrivateLink simplifies the security of data shared with cloud-based applications by eliminating the exposure of data to the public Internet. AWS PrivateLink provides private connectivity between VPCs, AWS services, and on-premises applications, securely on the Amazon network.
Private Link is utilized to create a private connection between an application that is fronted by an NLB in an account, and an Elastic Network Interface (ENI) in another account, without the need of VPC peering, and allowing the connections between the two to remain within the AWS network.

References:

https://aws.amazon.com/transit-gateway/

https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html

https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_CreateVpnGateway.html

## Question 26:

 You have a team of developers in your company, and you would like to ensure they can quickly experiment with AWS Managed Policies by attaching them to their accounts, but you would like to prevent them from doing an escalation of privileges, by granting themselves the AdministratorAccess managed policy. How should you proceed?

- 1. Attach an IAM policy to your developers, that prevents them from attaching the AdministratorAccess policy
- 2. Create a Service Control Policy (SCP) on your AWS account that restricts developers from attaching themselves the AdministratorAccess policy
- 3. For each developer, define an IAM permission boundary that will restrict the managed policies they can attach to themselves(Correct)
- 4. Put the developers into an IAM group, and then define an IAM permission boundary on the group that will restrict the managed policies they can attach to themselves

*Correct Answer(s):*
 3. For each developer, define an IAM permission boundary that will restrict the managed policies they can attach to themselves

**Explanation:**
Correct option:

For each developer, define an IAM permission boundary that will restrict the managed policies they can attach to themselves

AWS supports permissions boundaries for IAM entities (users or roles). A permissions boundary is an advanced feature for using a managed policy to set the maximum permissions that an identity-based policy can grant to an IAM entity. An entity's permissions boundary allows it to perform only the actions that are allowed by both its identity-based policies and its permissions boundaries.
Here we have to use an IAM permission boundary. They can only be applied to roles or users, not IAM groups.

Permissions boundaries for IAM entities:

via - https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html

Incorrect options:

Create a Service Control Policy (SCP) on your AWS account that restricts developers from attaching themselves the AdministratorAccess policy - Service control policy (SCP) is one type of policy that you can use to manage your organization. SCPs offer central control over the maximum available permissions for all accounts in your organization, allowing you to ensure your accounts stay within your organization’s access control guidelines. SCPs are available only in an organization that has all features enabled. SCPs aren't available if your organization has enabled only the consolidated billing features. Attaching an SCP to an AWS Organizations entity (root, OU, or account) defines a guardrail for what actions the principals can perform.
If you consider this option, since AWS Organizations is not mentioned in this question, so we can't apply an SCP.

Attach an IAM policy to your developers, that prevents them from attaching the AdministratorAccess policy - This option is incorrect as the developers can remove this policy from themselves and escalate their privileges.

Put the developers into an IAM group, and then define an IAM permission boundary on the group that will restrict the managed policies they can attach to themselves - IAM permission boundary can only be applied to roles or users, not IAM groups. Hence this option is incorrect.

References:

https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html

https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scp.html

https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html

## Question 27:

 A social photo-sharing web application is hosted on Amazon Elastic Compute Cloud (Amazon EC2) instances behind an Elastic Load Balancer. The app gives the users the ability to upload their photos and also shows a leaderboard on the homepage of the app. The uploaded photos are stored in Amazon Simple Storage Service (Amazon S3) and the leaderboard data is maintained in Amazon DynamoDB. The Amazon EC2 instances need to access both Amazon S3 and Amazon DynamoDB for these features.

As a solutions architect, which of the following solutions would you recommend as the MOST secure option?

- 1. Attach the appropriate IAM role to the Amazon EC2 instance profile so that the instance can access Amazon S3 and Amazon DynamoDB(Correct)
- 2. Encrypt the AWS credentials via a custom encryption library and save it in a secret directory on the Amazon EC2 instances. The application code can then safely decrypt the AWS credentials to make the API calls to Amazon S3 and Amazon DynamoDB
- 3. Save the AWS credentials (access key Id and secret access token) in a configuration file within the application code on the Amazon EC2 instances. Amazon EC2 instances can use these credentials to access Amazon S3 and Amazon DynamoDB
- 4. Configure AWS CLI on the Amazon EC2 instances using a valid IAM user's credentials. The application code can then invoke shell scripts to access Amazon S3 and Amazon DynamoDB via AWS CLI

*Correct Answer(s):*
 1. Attach the appropriate IAM role to the Amazon EC2 instance profile so that the instance can access Amazon S3 and Amazon DynamoDB

**Explanation:**
Correct option:

Attach the appropriate IAM role to the Amazon EC2 instance profile so that the instance can access Amazon S3 and Amazon DynamoDB

Applications that run on an Amazon EC2 instance must include AWS credentials in their AWS API requests. You could have your developers store AWS credentials directly within the Amazon EC2 instance and allow applications in that instance to use those credentials. But developers would then have to manage the credentials and ensure that they securely pass the credentials to each instance and update each Amazon EC2 instance when it's time to rotate the credentials.

Instead, you should use an IAM role to manage temporary credentials for applications that run on an Amazon EC2 instance. When you use a role, you don't have to distribute long-term credentials (such as a username and password or access keys) to an Amazon EC2 instance. The role supplies temporary permissions that applications can use when they make calls to other AWS resources. When you launch an Amazon EC2 instance, you specify an IAM role to associate with the instance. Applications that run on the instance can then use the role-supplied temporary credentials to sign API requests. Therefore, this option is correct.


via - https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html

Incorrect options:

Save the AWS credentials (access key Id and secret access token) in a configuration file within the application code on the Amazon EC2 instances. Amazon EC2 instances can use these credentials to access Amazon S3 and Amazon DynamoDB

Configure AWS CLI on the Amazon EC2 instances using a valid IAM user's credentials. The application code can then invoke shell scripts to access Amazon S3 and Amazon DynamoDB via AWS CLI

Encrypt the AWS credentials via a custom encryption library and save it in a secret directory on the Amazon EC2 instances. The application code can then safely decrypt the AWS credentials to make the API calls to Amazon S3 and Amazon DynamoDB

Keeping the AWS credentials (encrypted or plain text) on the Amazon EC2 instance is a bad security practice, therefore these three options using the AWS credentials are incorrect.

Reference:

https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html

## Question 28:

 A retail company wants to share sensitive accounting data that is stored in an Amazon RDS database instance with an external auditor. The auditor has its own AWS account and needs its own copy of the database.

Which of the following would you recommend to securely share the database with the auditor?

- 1. Export the database contents to text files, store the files in Amazon S3, and create a new IAM user for the auditor with access to that bucket
- 2. Create a snapshot of the database in Amazon S3 and assign an IAM role to the auditor to grant access to the object in that bucket
- 3. Create an encrypted snapshot of the database, share the snapshot, and allow access to the AWS Key Management Service (AWS KMS) encryption key(Correct)
- 4. Set up a read replica of the database and configure IAM standard database authentication to grant the auditor access

*Correct Answer(s):*
 3. Create an encrypted snapshot of the database, share the snapshot, and allow access to the AWS Key Management Service (AWS KMS) encryption key

**Explanation:**
Correct option:

Create an encrypted snapshot of the database, share the snapshot, and allow access to the AWS Key Management Service (AWS KMS) encryption key

You can share the AWS Key Management Service (AWS KMS) key that was used to encrypt the snapshot with any accounts that you want to be able to access the snapshot. You can share AWS KMS Key with another AWS account by adding the other account to the AWS KMS key policy.

Making an encrypted snapshot of the database will give the auditor a copy of the database, as required for the given use case.

Incorrect options:

Create a snapshot of the database in Amazon S3 and assign an IAM role to the auditor to grant access to the object in that bucket - Amazon RDS stores the DB snapshots in the Amazon S3 bucket belonging to the same AWS region where the Amazon RDS instance is located. Amazon RDS stores these on your behalf and you do not have direct access to these snapshots in Amazon S3, so it's not possible to grant access to the snapshot objects in Amazon S3.

Export the database contents to text files, store the files in Amazon S3, and create a new IAM user for the auditor with access to that bucket - This solution is feasible though not optimal. It requires a lot of unnecessary work and is difficult to audit when such bulk data is exported into text files.

Set up a read replica of the database and configure IAM standard database authentication to grant the auditor access - Read Replicas make it easy to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads. Creating Read Replicas for audit purposes is overkill. Also, the question mentions that the auditor needs to have their own copy of the database, which is not possible with replicas.

Reference:

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ShareSnapshot.html

## Question 29:

 An IT company is working on client engagement to build a real-time data analytics tool for the Internet of Things (IoT) data. The IoT data is funneled into Amazon Kinesis Data Streams which further acts as the source of a delivery stream for Amazon Kinesis Firehose. The engineering team has now configured a Kinesis Agent to send IoT data from another set of devices to the same Amazon Kinesis Firehose delivery stream. They noticed that data is not reaching Kinesis Firehose as expected.
As a solutions architect, which of the following options would you attribute as the MOST plausible root cause behind this issue?

- 1. The data sent by Kinesis Agent is lost because of a configuration error
- 2. Kinesis Agent can only write to Amazon Kinesis Data Streams, not to Amazon Kinesis Firehose
- 3. Kinesis Agent cannot write to Amazon Kinesis Firehose for which the delivery stream source is already set as Amazon Kinesis Data Streams(Correct)
- 4. Amazon Kinesis Firehose delivery stream has reached its limit and needs to be scaled manually

*Correct Answer(s):*
 3. Kinesis Agent cannot write to Amazon Kinesis Firehose for which the delivery stream source is already set as Amazon Kinesis Data Streams

**Explanation:**
Correct option:

Kinesis Agent cannot write to Amazon Kinesis Firehose for which the delivery stream source is already set as Amazon Kinesis Data Streams

Amazon Kinesis Data Firehose is the easiest way to reliably load streaming data into data lakes, data stores, and analytics tools. It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. It can also batch, compress, transform, and encrypt the data before loading it, minimizing the amount of storage used at the destination and increasing security.
When an Amazon Kinesis Data Stream is configured as the source of a Kinesis Firehose delivery stream, Firehose’s PutRecord and PutRecordBatch operations are disabled and Kinesis Agent cannot write to Kinesis Firehose Delivery Stream directly. Data needs to be added to the Amazon Kinesis Data Stream through the Kinesis Data Streams PutRecord and PutRecords operations instead. Therefore, this option is correct.

Incorrect options:

Kinesis Agent can only write to Amazon Kinesis Data Streams, not to Amazon Kinesis Firehose - Kinesis Agent is a stand-alone Java software application that offers an easy way to collect and send data to Amazon Kinesis Data Streams or Amazon Kinesis Firehose. So this option is incorrect.

Amazon Kinesis Firehose delivery stream has reached its limit and needs to be scaled manually - Amazon Kinesis Firehose is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. Therefore this option is not correct.

How Amazon Kinesis Firehose works:

via - https://aws.amazon.com/kinesis/data-firehose/

The data sent by Kinesis Agent is lost because of a configuration error - This is a made-up option and has been added as a distractor.

References:

https://aws.amazon.com/kinesis/data-firehose/

https://docs.aws.amazon.com/streams/latest/dev/writing-with-agents.html

https://docs.aws.amazon.com/firehose/latest/dev/writing-with-agents.html

## Question 30:

 Consider the following policy associated with an IAM group containing several users:

{
    "Version":"2012-10-17",
    "Id":"EC2TerminationPolicy",
    "Statement":[
        {
            "Effect":"Deny",
            "Action":"ec2:*",
            "Resource":"*",
            "Condition":{
                "StringNotEquals":{
                    "ec2:Region":"us-west-1"
                }
            }
        },
        {
            "Effect":"Allow",
            "Action":"ec2:TerminateInstances",
            "Resource":"*",
            "Condition":{
                "IpAddress":{
                    "aws:SourceIp":"10.200.200.0/24"
                }
            }
        }
    ]
}


Which of the following options is correct?

- 1. Users belonging to the IAM user group can terminate an Amazon EC2 instance in the us-west-1 region when the EC2 instance's IP address is 10.200.200.200
- 2. Users belonging to the IAM user group can terminate an Amazon EC2 instance in the us-west-1 region when the user's source IP is 10.200.200.200(Correct)
- 3. Users belonging to the IAM user group cannot terminate an Amazon EC2 instance in the us-west-1 region when the user's source IP is 10.200.200.200
- 4. Users belonging to the IAM user group can terminate an Amazon EC2 instance belonging to any region except the us-west-1 region when the user's source IP is 10.200.200.200

*Correct Answer(s):*
 2. Users belonging to the IAM user group can terminate an Amazon EC2 instance in the us-west-1 region when the user's source IP is 10.200.200.200

**Explanation:**
Correct option:

Users belonging to the IAM user group can terminate an Amazon EC2 instance in the us-west-1 region when the user's source IP is 10.200.200.200

The given policy denies all EC2 specification actions on all resources when the region of the underlying resource is not us-west-1. The policy allows the terminate EC2 action on all resources when the source IP address is in the CIDR range 10.200.200.0/24, therefore it would allow the user with the source IP 10.200.200.200 to terminate the Amazon EC2 instance.

Incorrect options:

Users belonging to the IAM user group cannot terminate an Amazon EC2 instance in the us-west-1 region when the user's source IP is 10.200.200.200

Users belonging to the IAM user group can terminate an Amazon EC2 instance in the us-west-1 region when the EC2 instance's IP address is 10.200.200.200

Users belonging to the IAM user group can terminate an Amazon EC2 instance belonging to any region except the us-west-1 region when the user's source IP is 10.200.200.200

These three options contradict the explanation provided above, so these options are incorrect.

Reference:

https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html

## Question 31:

 Your company has a monthly big data workload, running for about 2 hours, which can be efficiently distributed across multiple servers of various sizes, with a variable number of CPUs. The solution for the workload should be able to withstand server failures.

Which is the MOST cost-optimal solution for this workload?

- 1. Run the workload on Reserved Instances (RI)
- 2. Run the workload on Dedicated Hosts
- 3. Run the workload on Spot Instances
- 4. Run the workload on a Spot Fleet(Correct)

*Correct Answer(s):*
 4. Run the workload on a Spot Fleet

**Explanation:**
Correct option:

Run the workload on a Spot Fleet

The Spot Fleet selects the Spot Instance pools that meet your needs and launches Spot Instances to meet the target capacity for the fleet. By default, Spot Fleets are set to maintain target capacity by launching replacement instances after Spot Instances in the fleet are terminated.

A Spot Instance is an unused Amazon EC2 instance that is available for less than the On-Demand price. Spot Instances provide great cost efficiency, but we need to select an instance type in advance. In this case, we want to use the most cost-optimal option and leave the selection of the cheapest spot instance to a Spot Fleet request, which can be optimized with the lowestPrice strategy. So this is the correct option.

Key Spot Instance Concepts:

via - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html

Incorrect options:

Run the workload on Spot Instances - A Spot Instance is an unused Amazon EC2 instance that is available for less than the On-Demand price. Because Spot Instances enable you to request unused Amazon EC2 instances at steep discounts, you can lower your Amazon EC2 costs significantly. The hourly price for a Spot Instance is called a Spot price. Only spot fleets can maintain target capacity by launching replacement instances after Spot Instances in the fleet are terminated, so spot instances, by themselves, are not the right fit for this use-case.

Run the workload on Reserved Instances (RI) -  Reserved Instances are less cost-optimized than Spot Instances, and most efficient when used continuously. Here the workload is once a month, so this is not efficient.

Run the workload on Dedicated Hosts - Amazon EC2 Dedicated Hosts allow you to use your eligible software licenses from vendors such as Microsoft and Oracle on Amazon EC2 so that you get the flexibility and cost-effectiveness of using your licenses, but with the resiliency, simplicity, and elasticity of AWS. An Amazon EC2 Dedicated Host is a physical server fully dedicated for your use, so you can help address corporate compliance requirement. They're not particularly cost-efficient. So this option is not correct.

References:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-fleet.html#spot-fleet-allocation-strategy

## Question 32:

 A developer has configured inbound traffic for the relevant ports in both the Security Group of the Amazon EC2 instance as well as the network access control list (network ACL) of the subnet for the Amazon EC2 instance. The developer is, however, unable to connect to the service running on the Amazon EC2 instance.

As a solutions architect, how will you fix this issue?

- 1. Network access control list (network ACL) are stateful, so allowing inbound traffic to the necessary ports enables the connection. Security Groups are stateless, so you must allow both inbound and outbound traffic
- 2. Security Groups are stateful, so allowing inbound traffic to the necessary ports enables the connection. Network access control list (network ACL) are stateless, so you must allow both inbound and outbound traffic(Correct)
- 3. Rules associated with network access control list (network ACL) should never be modified from command line. An attempt to modify rules from command line blocks the rule and results in an erratic behavior
- 4. IAM Role defined in the Security Group is different from the IAM Role that is given access in the network access control list (network ACL)

*Correct Answer(s):*
 2. Security Groups are stateful, so allowing inbound traffic to the necessary ports enables the connection. Network access control list (network ACL) are stateless, so you must allow both inbound and outbound traffic

**Explanation:**
Correct option:

Security Groups are stateful, so allowing inbound traffic to the necessary ports enables the connection. Network access control list (network ACL) are stateless, so you must allow both inbound and outbound traffic

Security groups are stateful, so allowing inbound traffic to the necessary ports enables the connection. Network ACLs are stateless, so you must allow both inbound and outbound traffic.

To enable the connection to a service running on an instance, the associated network ACL must allow both inbound traffic on the port that the service is listening on as well as allow outbound traffic from ephemeral ports. When a client connects to a server, a random port from the ephemeral port range (1024-65535) becomes the client's source port.

The designated ephemeral port then becomes the destination port for return traffic from the service, so outbound traffic from the ephemeral port must be allowed in the network ACL.

By default, network ACLs allow all inbound and outbound traffic. If your network ACL is more restrictive, then you need to explicitly allow traffic from the ephemeral port range.

If you accept traffic from the internet, then you also must establish a route through an internet gateway. If you accept traffic over VPN or AWS Direct Connect, then you must establish a route through a virtual private gateway.

Incorrect options:

Network access control list (network ACL) are stateful, so allowing inbound traffic to the necessary ports enables the connection. Security Groups are stateless, so you must allow both inbound and outbound traffic - This is incorrect as already discussed.

IAM Role defined in the Security Group is different from the IAM Role that is given access in the network access control list (network ACL) - This is a made-up option and just added as a distractor.

Rules associated with network access control list (network ACL) should never be modified from command line. An attempt to modify rules from command line blocks the rule and results in an erratic behavior - This option is a distractor. AWS does not support modifying rules of Network ACLs from the command line tool.

Reference:

https://aws.amazon.com/premiumsupport/knowledge-center/resolve-connection-sg-acl-inbound/

## Question 33:

 An IT company is working on a client project to build a Supply Chain Management application. The web-tier of the application runs on an Amazon EC2 instance and the database tier is on Amazon RDS MySQL. For beta testing, all the resources are currently deployed in a single Availability Zone (AZ). The development team wants to improve application availability before the go-live.

Given that all end users of the web application would be located in the US, which of the following would be the MOST resource-efficient solution?

- 1. Deploy the web-tier Amazon EC2 instances in two regions, behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in Multi-AZ configuration
- 2. Deploy the web-tier Amazon EC2 instances in two Availability Zones (AZs), behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in Multi-AZ configuration(Correct)
- 3. Deploy the web-tier Amazon EC2 instances in two regions, behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in read replica configuration
- 4. Deploy the web-tier Amazon EC2 instances in two Availability Zones (AZs), behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in read replica configuration

*Correct Answer(s):*
 2. Deploy the web-tier Amazon EC2 instances in two Availability Zones (AZs), behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in Multi-AZ configuration

**Explanation:**
Correct option:

Deploy the web-tier Amazon EC2 instances in two Availability Zones (AZs), behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in Multi-AZ configuration

Elastic Load Balancing automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, and Lambda functions. It can handle the varying load of your application traffic in a single Availability Zone or across multiple Availability Zones. Therefore, deploying the web-tier Amazon EC2 instances in two Availability Zones (AZs), behind an Elastic Load Balancer would improve the availability of the application.

Amazon RDS Multi-AZ deployments provide enhanced availability and durability for RDS database (DB) instances, making them a natural fit for production database workloads. When you provision a Multi-AZ DB Instance, Amazon RDS automatically creates a primary DB Instance and synchronously replicates the data to a standby instance in a different Availability Zone (AZ). Each Availability Zone (AZ) runs on its own physically distinct, independent infrastructure, and is engineered to be highly reliable.
Deploying the Amazon RDS MySQL database in Multi-AZ configuration would improve availability and hence this is the correct option.

Incorrect options:

Deploy the web-tier Amazon EC2 instances in two Availability Zones (AZs), behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in read replica configuration

Deploy the web-tier Amazon EC2 instances in two regions, behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in read replica configuration

Amazon RDS Read Replicas provide enhanced performance and durability for RDS database (DB) instances. They make it easy to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads. Read replicas are meant to address scalability issues. You cannot use read replicas for improving availability, so both these options are incorrect.

Exam Alert:

Please review this comparison vis-a-vis Multi-AZ vs Read Replica for Amazon RDS:

via - https://aws.amazon.com/rds/features/multi-az/

Deploy the web-tier Amazon EC2 instances in two regions, behind an Elastic Load Balancer. Deploy the Amazon RDS MySQL database in Multi-AZ configuration - As Elastic Load Balancing does not work across regions, so this option is incorrect.

Reference:

https://aws.amazon.com/rds/features/multi-az/

## Question 34:

 You have multiple AWS accounts within a single AWS Region managed by AWS Organizations and you would like to ensure all Amazon EC2 instances in all these accounts can communicate privately. Which of the following solutions provides the capability at the CHEAPEST cost?

- 1. Create an AWS Transit Gateway and link all the virtual private cloud (VPCs) in all the accounts together
- 2. Create a VPC peering connection between all virtual private cloud (VPCs)
- 3. Create a Private Link between all the Amazon EC2 instances
- 4. Create a virtual private cloud (VPC) in an account and share one or more of its subnets with the other accounts using Resource Access Manager(Correct)

*Correct Answer(s):*
 4. Create a virtual private cloud (VPC) in an account and share one or more of its subnets with the other accounts using Resource Access Manager

**Explanation:**
Correct option:

Create a virtual private cloud (VPC) in an account and share one or more of its subnets with the other accounts using Resource Access Manager

AWS Resource Access Manager (RAM) is a service that enables you to easily and securely share AWS resources with any AWS account or within your AWS Organization. You can share AWS Transit Gateways, Subnets, AWS License Manager configurations, and Amazon Route 53 Resolver rules resources with RAM. RAM eliminates the need to create duplicate resources in multiple accounts, reducing the operational overhead of managing those resources in every single account you own. You can create resources centrally in a multi-account environment, and use RAM to share those resources across accounts in three simple steps: create a Resource Share, specify resources, and specify accounts. RAM is available to you at no additional charge.

The correct solution is to share the subnet(s) within a VPC using RAM. This will allow all Amazon EC2 instances to be deployed in the same VPC (although from different accounts) and easily communicate with one another.

How AWS Resource Access Manager (AWS RAM) Works:

via - https://aws.amazon.com/ram/

Incorrect options:

Create a Private Link between all the Amazon EC2 instances - AWS PrivateLink simplifies the security of data shared with cloud-based applications by eliminating the exposure of data to the public Internet. AWS PrivateLink provides private connectivity between VPCs, AWS services, and on-premises applications, securely on the Amazon network.
Private Link is a distractor in this question. Private Link is leveraged to create a private connection between an application that is fronted by an NLB in an account, and an Elastic Network Interface (ENI) in another account, without the need of VPC peering and allowing the connections between the two to remain within the AWS network.

Create a VPC peering connection between all virtual private cloud (VPCs) - A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your VPCs, or with a VPC in another AWS account. The VPCs can be in different regions (also known as an inter-region VPC peering connection).
VPC peering connections will work, but won't efficiently scale if you add more accounts (you'll have to create many connections).

Create an AWS Transit Gateway and link all the virtual private cloud (VPCs) in all the accounts together - AWS Transit Gateway is a service that enables customers to connect their Amazon Virtual Private Clouds (VPCs) and their on-premises networks to a single gateway.
A Transit Gateway will work but will be an expensive solution. Here we want to minimize cost.

References:

https://aws.amazon.com/ram/

https://aws.amazon.com/privatelink/

https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html

https://aws.amazon.com/transit-gateway/

## Question 35:

 A big-data consulting firm is working on a client engagement where the extract, transform, and load (ETL) workloads are currently handled via a Hadoop cluster deployed in the on-premises data center. The client wants to migrate their ETL workloads to AWS Cloud. The AWS Cloud solution needs to be highly available with about 50 Amazon Elastic Compute Cloud (Amazon EC2) instances per Availability Zone (AZ).

As a solutions architect, which of the following Amazon EC2 placement groups would you recommend for handling the distributed ETL workload?

- 1. Partition placement group(Correct)
- 2. Spread placement group
- 3. Cluster placement group
- 4. Both Spread placement group and Partition placement group

*Correct Answer(s):*
 1. Partition placement group

**Explanation:**
Correct option:

Partition placement group

You can use placement groups to influence the placement of a group of interdependent instances to meet the needs of your workload. Depending on the type of workload, you can create a placement group using one of the following placement strategies:

Partition placement group – spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka. Therefore, this is the correct option for the given use-case.


via - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

Incorrect options:

Cluster placement group

Cluster Placement Group – packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of HPC applications. This is not suited for distributed and replicated workloads such as Hadoop.


via - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

Spread placement group

Spread Placement Group – strictly places a small group of instances across distinct underlying hardware to reduce correlated failures. This is not suited for distributed and replicated workloads such as Hadoop.


via - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

Both Spread placement group and Partition placement group - As mentioned earlier, the spread placement group is not suited for distributed and replicated workloads such as Hadoop. So this option is also incorrect.

Reference:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

## Question 36:

 A media company has created an AWS Direct Connect connection for migrating its flagship application to the AWS Cloud. The on-premises application writes hundreds of video files into a mounted NFS file system daily. Post-migration, the company will host the application on an Amazon EC2 instance with a mounted Amazon Elastic File System (Amazon EFS) file system. Before the migration cutover, the company must build a process that will replicate the newly created on-premises video files to the Amazon EFS file system.

Which of the following represents the MOST operationally efficient way to meet this requirement?

- 1. Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an AWS VPC peering endpoint for Amazon EFS by using a private VIF. Set up an AWS DataSync scheduled task to send the video files to the Amazon EFS file system every 24 hours
- 2. Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an Amazon S3 bucket by using a VPC gateway endpoint for Amazon S3. Set up an AWS Lambda function to process event notifications from Amazon S3 and copy the video files from Amazon S3 to the Amazon EFS file system
- 3. Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an AWS PrivateLink interface VPC endpoint for Amazon EFS by using a private VIF. Set up an AWS DataSync scheduled task to send the video files to the Amazon EFS file system every 24 hours(Correct)
- 4. Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an Amazon S3 bucket by using public VIF. Set up an AWS Lambda function to process event notifications from Amazon S3 and copy the video files from Amazon S3 to the Amazon EFS file system

*Correct Answer(s):*
 3. Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an AWS PrivateLink interface VPC endpoint for Amazon EFS by using a private VIF. Set up an AWS DataSync scheduled task to send the video files to the Amazon EFS file system every 24 hours

**Explanation:**
Correct option:

Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an AWS PrivateLink interface VPC endpoint for Amazon EFS by using a private VIF. Set up an AWS DataSync scheduled task to send the video files to the Amazon EFS file system every 24 hours

AWS DataSync is an online data transfer service that simplifies, automates, and accelerates copying large amounts of data between on-premises storage systems and AWS Storage services, as well as between AWS Storage services.

You can use AWS DataSync to migrate data located on-premises, at the edge, or in other clouds to Amazon S3, Amazon EFS, Amazon FSx for Windows File Server, Amazon FSx for Lustre, Amazon FSx for OpenZFS, and Amazon FSx for NetApp ONTAP.

AWS DataSync:

via - https://aws.amazon.com/datasync/

To establish a private connection between your virtual private cloud (VPC) and the Amazon EFS API, you can create an interface VPC endpoint. You can also access the interface VPC endpoint from on-premises environments or other VPCs using AWS VPN, AWS Direct Connect, or VPC peering.

AWS Direct Connect provides three types of virtual interfaces: public, private, and transit.

AWS Direct Connect VIFs:

via - https://aws.amazon.com/premiumsupport/knowledge-center/public-private-interface-dx/

For the given use case, you can send data over the Direct Connect connection to an AWS PrivateLink interface VPC endpoint for Amazon EFS by using a private VIF.

Using task scheduling in AWS DataSync, you can periodically execute a transfer task from your source storage system to the destination. You can use the DataSync scheduled task to send the video files to the Amazon EFS file system every 24 hours.

Incorrect options:

Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an AWS VPC peering endpoint for Amazon EFS by using a private VIF. Set up an AWS DataSync scheduled task to send the video files to the Amazon EFS file system every 24 hours - A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them privately. You cannot use VPC peering to transfer data over the Direct Connect connection from the on-premises systems to AWS. So this option is incorrect.

Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an Amazon S3 bucket by using public VIF. Set up an AWS Lambda function to process event notifications from Amazon S3 and copy the video files from Amazon S3 to the Amazon EFS file system - You can use a public virtual interface to connect to AWS resources that are reachable by a public IP address such as an Amazon Simple Storage Service (Amazon S3) bucket or AWS public endpoints. Although it is theoretically possible to set up this solution, however, it is not the most operationally efficient solution, since it involves sending data via AWS DataSync to Amazon S3 and then in turn using an AWS Lambda function to finally send data to Amazon EFS.

Configure an AWS DataSync agent on the on-premises server that has access to the NFS file system. Transfer data over the AWS Direct Connect connection to an Amazon S3 bucket by using a VPC gateway endpoint for Amazon S3. Set up an AWS Lambda function to process event notifications from Amazon S3 and copy the video files from Amazon S3 to the Amazon EFS file system - You can access Amazon S3 from your VPC using gateway VPC endpoints. You cannot use the Amazon S3 gateway endpoint to transfer data over the AWS Direct Connect connection from the on-premises systems to Amazon S3. So this option is incorrect.

References:

https://aws.amazon.com/datasync/

https://aws.amazon.com/blogs/storage/transferring-files-from-on-premises-to-aws-and-back-without-leaving-your-vpc-using-aws-datasync/

https://docs.aws.amazon.com/efs/latest/ug/efs-vpc-endpoints.html

https://aws.amazon.com/datasync/faqs/

https://aws.amazon.com/premiumsupport/knowledge-center/public-private-interface-dx/

https://docs.aws.amazon.com/datasync/latest/userguide/task-scheduling.html

## Question 37:

 A junior DevOps engineer wants to change the default configuration for Amazon EBS volume termination. By default, the root volume of an Amazon EC2 instance for an EBS-backed AMI is deleted when the instance terminates.

Which option below helps change this default behavior to ensure that the volume persists even after the instance terminates?

- 1. Set the DeleteOnTermination attribute to false(Correct)
- 2. Set the TerminateOnDelete attribute to false
- 3. Set the TerminateOnDelete attribute to true
- 4. Set the DeleteOnTermination attribute to true

*Correct Answer(s):*
 1. Set the DeleteOnTermination attribute to false

**Explanation:**
Correct option:

Set the DeleteOnTermination attribute to false

An Amazon EC2 instance can be launched from either an instance store-backed AMI or an Amazon EBS-backed AMI. Instances that use Amazon EBS for the root device automatically have an Amazon EBS volume attached. By default, the root volume for an AMI backed by Amazon EBS is deleted when the instance terminates.
The default behavior can be changed to ensure that the volume persists after the instance terminates. To change the default behavior, set the DeleteOnTermination attribute to false using a block device mapping.

Incorrect options:

Set the TerminateOnDelete attribute to true

Set the TerminateOnDelete attribute to false

Both these options are incorrect as there is no such attribute as TerminateOnDelete. These options have been added as distractors.

Set the DeleteOnTermination attribute to true - If you set the DeleteOnTermination attribute to true, then the root volume for an AMI backed by Amazon EBS would be deleted when the instance terminates. Therefore, this option is incorrect.

Reference:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/RootDeviceStorage.html

## Question 38:

 A financial services company has developed its flagship application on AWS Cloud with data security requirements such that the encryption key must be stored in a custom application running on-premises. The company wants to offload the data storage as well as the encryption process to Amazon S3 but continue to use the existing encryption key.

Which of the following Amazon S3 encryption options allows the company to leverage Amazon S3 for storing data with given constraints?

- 1. Client-Side Encryption with data encryption is done on the client-side before sending it to Amazon S3
- 2. Server-Side Encryption with Amazon S3 managed keys (SSE-S3)
- 3. Server-Side Encryption with Customer-Provided Keys (SSE-C)(Correct)
- 4. Server-Side Encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS)

*Correct Answer(s):*
 3. Server-Side Encryption with Customer-Provided Keys (SSE-C)

**Explanation:**
Correct option:

Server-Side Encryption with Customer-Provided Keys (SSE-C)

You have the following options for protecting data at rest in Amazon S3:

Server-Side Encryption – Request Amazon S3 to encrypt your object before saving it on disks in its data centers and then decrypt it when you download the objects.

Client-Side Encryption – Encrypt data client-side and upload the encrypted data to Amazon S3. In this case, you manage the encryption process, the encryption keys, and related tools.

For the given use-case, the company wants to manage the encryption keys via its custom application and let Amazon S3 manage the encryption, therefore you must use Server-Side Encryption with Customer-Provided Keys (SSE-C).

Please review these three options for Server Side Encryption on Amazon S3:

via - https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html

Incorrect options:

Server-Side Encryption with Amazon S3 managed keys (SSE-S3) - When you use Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3), each object is encrypted with a unique key. As an additional safeguard, it encrypts the key itself with a master key that it regularly rotates. So this option is incorrect.

Server-Side Encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) - Unless you specify otherwise, buckets use SSE-S3 by default to encrypt objects. However, you can choose to configure buckets to use server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) instead. Amazon S3 uses server-side encryption with AWS KMS (SSE-KMS) to encrypt your S3 object data. Also, when SSE-KMS is requested for the object, the S3 checksum as part of the object's metadata, is stored in encrypted form.

Client-Side Encryption with data encryption is done on the client-side before sending it to Amazon S3 - You can encrypt the data client-side and upload the encrypted data to Amazon S3. In this case, you manage the encryption process, the encryption keys, and related tools.

Reference:

https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html

## Question 39:

 Your company has an on-premises Distributed File System Replication (DFSR) service to keep files synchronized on multiple Windows servers, and would like to migrate to AWS cloud.

What do you recommend as a replacement for the DFSR?

- 1. Amazon Simple Storage Service (Amazon S3)
- 2. Amazon Elastic File System (Amazon EFS)
- 3. Amazon FSx for Lustre
- 4. Amazon FSx for Windows File Server(Correct)

*Correct Answer(s):*
 4. Amazon FSx for Windows File Server

**Explanation:**
Correct option:

Amazon FSx for Windows File Server

Amazon FSx for Windows File Server provides fully managed, highly reliable file storage that is accessible over the industry-standard Service Message Block (SMB) protocol.  It is built on Windows Server, delivering a wide range of administrative features such as user quotas, end-user file restore, and Microsoft Active Directory (AD) integration.
The Distributed File System Replication (DFSR) service is a new multi-master replication engine that is used to keep folders synchronized on multiple servers. Amazon FSx supports the use of Microsoft’s Distributed File System (DFS) to organize shares into a single folder structure up to hundreds of PB in size.

Amazon FSx for Windows is a perfect distributed file system, with replication capability, and can be mounted on Windows.

How Amazon FSx for Windows Works:

via - https://aws.amazon.com/fsx/windows/

Incorrect options:

Amazon FSx for Lustre - Amazon FSx for Lustre makes it easy and cost-effective to launch and run the world’s most popular high-performance file system. It is used for workloads such as machine learning, high-performance computing (HPC), video processing, and financial modeling. The open-source Lustre file system is designed for applications that require fast storage – where you want your storage to keep up with your compute. Amazon FSx enables you to use Lustre file systems for any workload where storage speed matters. FSx for Lustre integrates with Amazon S3, making it easy to process data sets with the Lustre file system. Amazon FSx for Lustre is for Linux only, so this option is incorrect.

Amazon Elastic File System (Amazon EFS) - Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources. It is built to scale on-demand to petabytes without disrupting applications, growing and shrinking automatically as you add and remove files, eliminating the need to provision and manage capacity to accommodate growth. Amazon EFS is a network file system but for Linux only, so this option is incorrect.

Amazon Simple Storage Service (Amazon S3) - Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. Amazon S3 cannot be mounted as a file system on Windows, so this option is incorrect.

References:

https://docs.microsoft.com/en-us/previous-versions/windows/desktop/dfsr/dfsr-overview

https://aws.amazon.com/fsx/windows/

https://aws.amazon.com/fsx/lustre/

## Question 40:

 A cybersecurity company uses a fleet of Amazon EC2 instances to run a proprietary application. The infrastructure maintenance group at the company wants to be notified via an email whenever the CPU utilization for any of the Amazon EC2 instances breaches a certain threshold.

Which of the following services would you use for building a solution with the LEAST amount of development effort? (Select two)

- 1. AWS Lambda
- 2. AWS Step Functions
- 3. Amazon CloudWatch(Correct)
- 4. Amazon Simple Notification Service (Amazon SNS)(Correct)
- 5. Amazon Simple Queue Service (Amazon SQS)

*Correct Answer(s):*
 3. Amazon CloudWatch4. Amazon Simple Notification Service (Amazon SNS)

**Explanation:**
Correct options:

Amazon Simple Notification Service (Amazon SNS)

Amazon Simple Notification Service (Amazon SNS) is a highly available, durable, secure, fully managed pub/sub messaging service that enables you to decouple microservices, distributed systems, and serverless applications. Amazon SNS provides topics for high-throughput, push-based, many-to-many messaging.

Amazon CloudWatch

Amazon CloudWatch is a monitoring and observability service built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers. Amazon CloudWatch provides you with data and actionable insights to monitor your applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health. Amazon CloudWatch allows you to monitor AWS cloud resources and the applications you run on AWS.

You can use Amazon CloudWatch Alarms to send an email via Amazon SNS whenever any of the Amazon EC2 instances breaches a certain threshold. Hence both these options are correct.

Incorrect options:

AWS Lambda - With AWS Lambda, you can run code without provisioning or managing servers. You pay only for the compute time that you consume—there’s no charge when your code isn’t running. You can run code for virtually any type of application or backend service—all with zero administration. You cannot use AWS Lambda to monitor CPU utilization of Amazon EC2 instances or send notification emails, hence this option is incorrect.

Amazon Simple Queue Service (Amazon SQS) - Amazon SQS Standard offers a reliable, highly scalable hosted queue for storing messages as they travel between computers. Amazon SQS lets you easily move data between distributed application components and helps you build applications in which messages are processed independently (with message-level ack/fail semantics), such as automated workflows. You cannot use Amazon SQS to monitor CPU utilization of Amazon EC2 instances or send notification emails, hence this option is incorrect.

AWS Step Functions - AWS Step Functions lets you coordinate multiple AWS services into serverless workflows so you can build and update apps quickly. Using Step Functions, you can design and run workflows that stitch together services, such as AWS Lambda, AWS Fargate, and Amazon SageMaker, into feature-rich applications. You cannot use Step Functions to monitor CPU utilization of Amazon EC2 instances or send notification emails, hence this option is incorrect.

References:

https://aws.amazon.com/cloudwatch/faqs/

https://aws.amazon.com/sns/

## Question 41:

 A weather forecast agency collects key weather metrics across multiple cities in the US and sends this data in the form of key-value pairs to AWS Cloud at a one-minute frequency.

As a solutions architect, which of the following AWS services would you use to build a solution for processing and then reliably storing this data with high availability? (Select two)

- 1. Amazon Redshift
- 2. AWS Lambda(Correct)
- 3. Amazon RDS
- 4. Amazon DynamoDB(Correct)
- 5. Amazon ElastiCache

*Correct Answer(s):*
 2. AWS Lambda4. Amazon DynamoDB

**Explanation:**
Correct options:

AWS Lambda

With AWS Lambda, you can run code without provisioning or managing servers. You pay only for the compute time that you consume—there’s no charge when your code isn’t running. You can run code for virtually any type of application or backend service—all with zero administration.

Amazon DynamoDB

Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale. It's a fully managed, multi-region, multi-master, durable database with built-in security, backup and restore, and in-memory caching for internet-scale applications. Amazon DynamoDB is a NoSQL database and it's best suited to store data in key-value pairs.

AWS Lambda can be combined with DynamoDB to process and capture the key-value data from the IoT sources described in the use-case. So both these options are correct.

Incorrect options:

Amazon Redshift - Amazon Redshift is a fully-managed petabyte-scale cloud-based data warehouse product designed for large scale data set storage and analysis. You cannot use Redshift to capture data in key-value pairs from the IoT sources, so this option is not correct.

Amazon ElastiCache - Amazon ElastiCache allows you to seamlessly set up, run, and scale popular open-Source compatible in-memory data stores in the cloud. Build data-intensive apps or boost the performance of your existing databases by retrieving data from high throughput and low latency in-memory data stores. Amazon ElastiCache is a popular choice for real-time use cases like Caching, Session Stores, Gaming, Geospatial Services, Real-Time Analytics, and Queuing. Elasticache is used as a caching layer in front of relational databases. It is not a good fit to store data in key-value pairs from the IoT sources, so this option is not correct.

Amazon RDS - Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching, and backups. Relational databases are not a good fit to store data in key-value pairs, so this option is not correct.

References:

https://aws.amazon.com/dynamodb/

https://aws.amazon.com/lambda/faqs/

## Question 42:

 Upon a security review of your AWS account, an AWS consultant has found that a few Amazon RDS databases are unencrypted. As a Solutions Architect, what steps must be taken to encrypt the Amazon RDS databases?

- 1. Enable Multi-AZ for the database, and make sure the standby instance is encrypted. Stop the main database to that the standby database kicks in, then disable Multi-AZ
- 2. Enable encryption on the Amazon RDS database using the AWS Console
- 3. Create a Read Replica of the database, and encrypt the read replica. Promote the read replica as a standalone database, and terminate the previous database
- 4. Take a snapshot of the database, copy it as an encrypted snapshot, and restore a database from the encrypted snapshot. Terminate the previous database(Correct)

*Correct Answer(s):*
 4. Take a snapshot of the database, copy it as an encrypted snapshot, and restore a database from the encrypted snapshot. Terminate the previous database

**Explanation:**
Correct option:

Take a snapshot of the database, copy it as an encrypted snapshot, and restore a database from the encrypted snapshot. Terminate the previous database

Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching and backups.

You can encrypt your Amazon RDS DB instances and snapshots at rest by enabling the encryption option for your Amazon RDS DB instances. Data that is encrypted at rest includes the underlying storage for DB instances, its automated backups, read replicas, and snapshots.

You can only enable encryption for an Amazon RDS DB instance when you create it, not after the DB instance is created. However, because you can encrypt a copy of an unencrypted DB snapshot, you can effectively add encryption to an unencrypted DB instance. That is, you can create a snapshot of your DB instance, and then create an encrypted copy of that snapshot. So this is the correct option.

Incorrect options:

Create a Read Replica of the database, and encrypt the read replica. Promote the read replica as a standalone database, and terminate the previous database - If the master is not encrypted, the read replicas cannot be encrypted. So this option is incorrect.

Enable Multi-AZ for the database, and make sure the standby instance is encrypted. Stop the main database to that the standby database kicks in, then disable Multi-AZ - Multi-AZ is to help with High Availability, not encryption. So this option is incorrect.

Enable encryption on the Amazon RDS database using the AWS Console - There is no direct option to encrypt an Amazon RDS database using the AWS Console.

Steps to encrypt an un-encrypted RDS database:
1. Create a snapshot of the un-encrypted database
2. Copy the snapshot and enable encryption for the snapshot
3. Restore the database from the encrypted snapshot
4. Migrate applications to the new database, and delete the old database

Reference:

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html

## Question 43:

 A Hollywood studio is planning a series of promotional events leading up to the launch of the trailer of its next sci-fi thriller. The executives at the studio want to create a static website with lots of animations in line with the theme of the movie. The studio has hired you as a solutions architect to build a scalable serverless solution.

Which of the following represents the MOST cost-optimal and high-performance solution?

- 1. Host the website on AWS Lambda. Create an Amazon CloudFront distribution with Lambda as the origin
- 2. Build the website as a static website hosted on Amazon S3. Create an Amazon CloudFront distribution with Amazon S3 as the origin. Use Amazon Route 53 to create an alias record that points to your Amazon CloudFront distribution(Correct)
- 3. Host the website on an Amazon EC2 instance. Create a Amazon CloudFront distribution with the Amazon EC2 instance as the custom origin
- 4. Host the website on an instance in the studio's on-premises data center. Create an Amazon CloudFront distribution with this instance as the custom origin

*Correct Answer(s):*
 2. Build the website as a static website hosted on Amazon S3. Create an Amazon CloudFront distribution with Amazon S3 as the origin. Use Amazon Route 53 to create an alias record that points to your Amazon CloudFront distribution

**Explanation:**
Correct option:

Build the website as a static website hosted on Amazon S3. Create an Amazon CloudFront distribution with Amazon S3 as the origin. Use Amazon Route 53 to create an alias record that points to your Amazon CloudFront distribution

You can use Amazon S3 to host a static website. On a static website, individual web pages include static content. They might also contain client-side scripts. To host a static website on Amazon S3, you configure an Amazon S3 bucket for website hosting and then upload your website content to the bucket.

Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.

You can use Amazon CloudFront to improve the performance of your website. CloudFront makes your website files (such as HTML, images, and video) available from data centers around the world (called edge locations). When a visitor requests a file from your website, CloudFront automatically redirects the request to a copy of the file at the nearest edge location. This results in faster download times than if the visitor had requested the content from a data center that is located farther away. Therefore, this option is correct.

Hosting a static website on Amazon S3:

via - https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html

Incorrect options:

Host the website on AWS Lambda. Create an Amazon CloudFront distribution with Lambda as the origin

With AWS Lambda, you can run code without provisioning or managing servers. You can't host a website on Lambda. Also, you can't have CloudFront in front of Lambda. So this option is incorrect.

Host the website on an Amazon EC2 instance. Create a Amazon CloudFront distribution with the Amazon EC2 instance as the custom origin

Host the website on an instance in the studio's on-premises data center. Create an Amazon CloudFront distribution with this instance as the custom origin

Hosting the website on an Amazon EC2 instance or a data-center specific instance is ruled out as the studio wants a serverless solution. So both these options are incorrect.

References:

https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html

https://docs.aws.amazon.com/AmazonS3/latest/dev/website-hosting-custom-domain-walkthrough.html

https://docs.aws.amazon.com/AmazonS3/latest/dev/website-hosting-cloudfront-walkthrough.html

## Question 44:

 What does this IAM policy do?

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Mystery Policy",
      "Action": [
        "ec2:RunInstances"
      ],
      "Effect": "Allow",
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "aws:RequestedRegion": "eu-west-1"
        }
      }
    }
  ]
}

- 1. It allows running Amazon EC2 instances in any region when the API call is originating from the eu-west-1 region
- 2. It allows running Amazon EC2 instances only in the eu-west-1 region, and the API call can be made from anywhere in the world(Correct)
- 3. It allows running Amazon EC2 instances in the eu-west-1 region, when the API call is made from the eu-west-1 region
- 4. It allows running Amazon EC2 instances anywhere but in the eu-west-1 region

*Correct Answer(s):*
 2. It allows running Amazon EC2 instances only in the eu-west-1 region, and the API call can be made from anywhere in the world

**Explanation:**
Correct option:

It allows running Amazon EC2 instances only in the eu-west-1 region, and the API call can be made from anywhere in the world

You manage access in AWS by creating policies and attaching them to IAM identities (users, groups of users, or roles) or AWS resources. A policy is an object in AWS that, when associated with an identity or resource, defines their permissions. AWS evaluates these policies when an IAM principal (user or role) makes a request. Permissions in the policies determine whether the request is allowed or denied. Most policies are stored in AWS as JSON documents. AWS supports six types of policies: identity-based policies, resource-based policies, permissions boundaries, Organizations service control policy (SCPs), access control lists (ACLs), and session policies.

You can use the aws:RequestedRegion key to compare the AWS Region that was called in the request with the Region that you specify in the policy. You can use this global condition key to control which Regions can be requested.

aws:RequestedRegion represents the target of the API call. So in this example, we can only launch an Amazon EC2 instance in eu-west-1, and we can do this API call from anywhere.

Incorrect options:

It allows running Amazon EC2 instances anywhere but in the eu-west-1 region

It allows running Amazon EC2 instances in any region when the API call is originating from the eu-west-1 region

It allows running Amazon EC2 instances in the eu-west-1 region, when the API call is made from the eu-west-1 region

These three options contradict the earlier details provided in the explanation. To summarize, aws:RequestedRegion represents the target of the API call. So, we can only launch an Amazon EC2 instance in eu-west-1 region and we can do this API call from anywhere. Hence these options are incorrect.

References:

https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html

https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html

## Question 45:

 A health-care solutions company wants to run their applications on single-tenant hardware to meet regulatory guidelines.

Which of the following is the MOST cost-effective way of isolating their Amazon Elastic Compute Cloud (Amazon EC2)instances to a single tenant?

- 1. Dedicated Instances(Correct)
- 2. On-Demand Instances
- 3. Dedicated Hosts
- 4. Spot Instances

*Correct Answer(s):*
 1. Dedicated Instances

**Explanation:**
Correct option:

Dedicated Instances

Dedicated Instances are Amazon EC2 instances that run in a virtual private cloud (VPC) on hardware that's dedicated to a single customer. Dedicated Instances that belong to different AWS accounts are physically isolated at a hardware level, even if those accounts are linked to a single-payer account. However, Dedicated Instances may share hardware with other instances from the same AWS account that are not Dedicated Instances.

A Dedicated Host is also a physical server that's dedicated for your use. With a Dedicated Host, you have visibility and control over how instances are placed on the server.

Differences between Dedicated Hosts and Dedicated Instances:

via - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-hosts-overview.html#dedicated-hosts-dedicated-instances

Incorrect options:

Spot Instances -  A Spot Instance is an unused Amazon EC2 instance that is available for less than the On-Demand price.  Your Spot Instance runs whenever capacity is available and the maximum price per hour for your request exceeds the Spot price. Any instance present with unused capacity will be allocated. Even though this is cost-effective, it does not fulfill the single-tenant hardware requirement of the client and hence is not the correct option.

Dedicated Hosts - An Amazon EC2 Dedicated Host is a physical server with EC2 instance capacity fully dedicated to your use. Dedicated Hosts allow you to use your existing software licenses on EC2 instances. With a Dedicated Host, you have visibility and control over how instances are placed on the server. This option is costlier than the Dedicated Instance and hence is not the right choice for the current requirement.

On-Demand Instances - With On-Demand Instances, you pay for compute capacity by the second with no long-term commitments. You have full control over its lifecycle—you decide when to launch, stop, hibernate, start, reboot, or terminate it. Hardware isolation is not possible and on-demand has one of the costliest instance charges and hence is not the correct answer for current requirements.

High Level Overview of Amazon EC2 Instance Purchase Options:

via - https://aws.amazon.com/ec2/pricing/

References:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-instance.html

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html

## Question 46:

 You would like to mount a network file system on Linux instances, where files will be stored and accessed frequently at first, and then infrequently. What solution is the MOST cost-effective?

- 1. Amazon S3 Intelligent Tiering
- 2. Amazon FSx for Lustre
- 3. Amazon EFS Infrequent Access(Correct)
- 4. Amazon S3 Glacier Deep Archive

*Correct Answer(s):*
 3. Amazon EFS Infrequent Access

**Explanation:**
Correct option:

Amazon EFS Infrequent Access

Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources. Amazon EFS is a regional service storing data within and across multiple Availability Zones (AZs) for high availability and durability.

Amazon EFS Infrequent Access (EFS IA) is a storage class that provides price/performance that is cost-optimized for files, not accessed every day, with storage prices up to 92% lower compared to Amazon EFS Standard. Therefore, this is the correct option.

How Amazon EFS works:

via - https://aws.amazon.com/efs/

Incorrect options:

Amazon S3 Intelligent Tiering - Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. The Amazon S3 Intelligent-Tiering storage class is designed to optimize costs by automatically moving data to the most cost-effective access tier, without performance impact or operational overhead. It works by storing objects in two access tiers: one tier that is optimized for frequent access and another lower-cost tier that is optimized for infrequent access.

You can't mount a network file system on Amazon S3 Intelligent Tiering as it's an object storage service, so this option is incorrect.

Amazon S3 Glacier Deep Archive - Amazon S3 Glacier and S3 Glacier Deep Archive are a secure, durable, and extremely low-cost Amazon S3 cloud storage classes for data archiving and long-term backup. They are designed to deliver 99.999999999% durability, and provide comprehensive security and compliance capabilities that can help meet even the most stringent regulatory requirements.

You can't mount a network file system on Amazon S3 Glacier or S3 Glacier Deep Archive. These are data archiving solutions and hence this option is incorrect.

Amazon FSx for Lustre - Amazon FSx for Lustre makes it easy and cost-effective to launch and run the world’s most popular high-performance file system. It is used for workloads such as machine learning, high-performance computing (HPC), video processing, and financial modeling. Amazon FSx enables you to use Lustre file systems for any workload where storage speed matters.

Amazon FSx for Lustre is a file system better suited for distributed computing for HPC (high-performance computing) and is very expensive

References:

https://aws.amazon.com/efs/

https://aws.amazon.com/efs/features/infrequent-access/

## Question 47:

 A developer needs to implement an AWS Lambda function in AWS account A that accesses an Amazon Simple Storage Service (Amazon S3) bucket in AWS account B.

As a Solutions Architect, which of the following will you recommend to meet this requirement?

- 1. The Amazon S3 bucket owner should make the bucket public so that it can be accessed by the AWS Lambda function in the other AWS account
- 2. Create an IAM role for the AWS Lambda function that grants access to the Amazon S3 bucket. Set the IAM role as the Lambda function's execution role and that would give the AWS Lambda function cross-account access to the Amazon S3 bucket
- 3. AWS Lambda cannot access resources across AWS accounts. Use Identity federation to work around this limitation of Lambda
- 4. Create an IAM role for the AWS Lambda function that grants access to the Amazon S3 bucket. Set the IAM role as the AWS Lambda function's execution role. Make sure that the bucket policy also grants access to the AWS Lambda function's execution role(Correct)

*Correct Answer(s):*
 4. Create an IAM role for the AWS Lambda function that grants access to the Amazon S3 bucket. Set the IAM role as the AWS Lambda function's execution role. Make sure that the bucket policy also grants access to the AWS Lambda function's execution role

**Explanation:**
Correct option:

Create an IAM role for the AWS Lambda function that grants access to the Amazon S3 bucket. Set the IAM role as the AWS Lambda function's execution role. Make sure that the bucket policy also grants access to the AWS Lambda function's execution role

If the IAM role that you create for the Lambda function is in the same AWS account as the bucket, then you don't need to grant Amazon S3 permissions on both the IAM role and the bucket policy. Instead, you can grant the permissions on the IAM role and then verify that the bucket policy doesn't explicitly deny access to the Lambda function role. If the IAM role and the bucket are in different accounts, then you need to grant Amazon S3 permissions on both the IAM role and the bucket policy. Therefore, this is the right way of giving access to AWS Lambda for the given use-case.

Complete list of steps to be followed:

via - https://aws.amazon.com/premiumsupport/knowledge-center/lambda-execution-role-s3-bucket/

Incorrect options:

AWS Lambda cannot access resources across AWS accounts. Use Identity federation to work around this limitation of Lambda - This is an incorrect statement, used only as a distractor.

Create an IAM role for the AWS Lambda function that grants access to the Amazon S3 bucket. Set the IAM role as the Lambda function's execution role and that would give the AWS Lambda function cross-account access to the Amazon S3 bucket - When the execution role of AWS Lambda and Amazon S3 bucket to be accessed are from different accounts, then you need to grant Amazon S3 bucket access permissions to the IAM role and also ensure that the bucket policy grants access to the AWS Lambda function's execution role.

The Amazon S3 bucket owner should make the bucket public so that it can be accessed by the AWS Lambda function in the other AWS account - Making the Amazon S3 bucket public for the given use-case will be considered as a security bad practice. It's usually done for very few use-cases such as hosting a website on Amazon S3. Therefore this option is incorrect.

Reference:

https://aws.amazon.com/premiumsupport/knowledge-center/lambda-execution-role-s3-bucket/

## Question 48:

 A manufacturing company receives unreliable service from its data center provider because the company is located in an area prone to natural disasters. The company is not ready to fully migrate to the AWS Cloud, but it wants a failover environment on AWS in case the on-premises data center fails. The company runs web servers that connect to external vendors. The data available on AWS and on-premises must be uniform.

Which of the following solutions would have the LEAST amount of downtime?

- 1. Set up a Amazon Route 53 failover record. Run an AWS Lambda function to execute an AWS CloudFormation template to launch two Amazon EC2 instances. Set up AWS Storage Gateway with stored volumes to back up data to Amazon S3. Set up an AWS Direct Connect connection between a VPC and the data center
- 2. Set up a Amazon Route 53 failover record. Execute an AWS CloudFormation template from a script to provision Amazon EC2 instances behind an Application Load Balancer. Set up AWS Storage Gateway with stored volumes to back up data to Amazon S3
- 3. Set up a Amazon Route 53 failover record. Set up an AWS Direct Connect connection between a VPC and the data center. Run application servers on Amazon EC2 in an Auto Scaling group. Run an AWS Lambda function to execute an AWS CloudFormation template to create an Application Load Balancer
- 4. Set up a Amazon Route 53 failover record. Run application servers on Amazon EC2 instances behind an Application Load Balancer in an Auto Scaling group. Set up AWS Storage Gateway with stored volumes to back up data to Amazon S3(Correct)

*Correct Answer(s):*
 4. Set up a Amazon Route 53 failover record. Run application servers on Amazon EC2 instances behind an Application Load Balancer in an Auto Scaling group. Set up AWS Storage Gateway with stored volumes to back up data to Amazon S3

**Explanation:**
Correct option:

Set up a Amazon Route 53 failover record. Run application servers on Amazon EC2 instances behind an Application Load Balancer in an Auto Scaling group. Set up AWS Storage Gateway with stored volumes to back up data to Amazon S3

If you have multiple resources that perform the same function, you can configure DNS failover so that Route 53 will route your traffic from an unhealthy resource to a healthy resource.

Elastic Load Balancing is used to automatically distribute your incoming application traffic across all the Amazon EC2 instances that you are running. You can use Elastic Load Balancing to manage incoming requests by optimally routing traffic so that no one instance is overwhelmed. Your load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group.

AWS Storage Gateway is a hybrid cloud storage service that gives you on-premises access to virtually unlimited cloud storage. It provides low-latency performance by caching frequently accessed data on-premises while storing data securely and durably in Amazon cloud storage services. Storage Gateway optimizes data transfer to AWS by sending only changed data and compressing data. Storage Gateway also integrates natively with Amazon S3 cloud storage which makes your data available for in-cloud processing.

Incorrect options:

Set up a Amazon Route 53 failover record. Execute an AWS CloudFormation template from a script to provision Amazon EC2 instances behind an Application Load Balancer. Set up AWS Storage Gateway with stored volumes to back up data to Amazon S3

Set up a Amazon Route 53 failover record. Run an AWS Lambda function to execute an AWS CloudFormation template to launch two Amazon EC2 instances. Set up AWS Storage Gateway with stored volumes to back up data to Amazon S3. Set up an AWS Direct Connect connection between a VPC and the data center

Set up a Amazon Route 53 failover record. Set up an AWS Direct Connect connection between a VPC and the data center. Run application servers on Amazon EC2 in an Auto Scaling group. Run an AWS Lambda function to execute an AWS CloudFormation template to create an Application Load Balancer

AWS CloudFormation is a convenient provisioning mechanism for a broad range of AWS and third-party resources. It supports the infrastructure needs of many different types of applications such as existing enterprise applications, legacy applications, applications built using a variety of AWS resources, and container-based solutions.

These three options involve AWS CloudFormation as part of the solution. Now, AWS CloudFormation takes time to provision the resources and hence is not the right solution when LEAST amount of downtime is mandated for the given use case. Therefore, these options are not the right fit for the given requirement.

References:

https://aws.amazon.com/route53/

https://aws.amazon.com/storagegateway/

## Question 49:

 The engineering team at an e-commerce company is working on cost optimizations for Amazon Elastic Compute Cloud (Amazon EC2) instances. The team wants to manage the workload using a mix of on-demand and spot instances across multiple instance types. They would like to create an Auto Scaling group with a mix of these instances.

Which of the following options would allow the engineering team to provision the instances for this use-case?

- 1. You can only use a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost(Correct)
- 2. You can use a launch configuration or a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost
- 3. You can neither use a launch configuration nor a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost
- 4. You can only use a launch configuration to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost

*Correct Answer(s):*
 1. You can only use a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost

**Explanation:**
Correct option:

You can only use a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost

A launch template is similar to a launch configuration, in that it specifies instance configuration information such as the ID of the Amazon Machine Image (AMI), the instance type, a key pair, security groups, and the other parameters that you use to launch EC2 instances. Also, defining a launch template instead of a launch configuration allows you to have multiple versions of a template.

With launch templates, you can provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost. Hence this is the correct option.

Incorrect options:

You can only use a launch configuration to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost

You can use a launch configuration or a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost

A launch configuration is an instance configuration template that an Auto Scaling group uses to launch EC2 instances. When you create a launch configuration, you specify information for the instances such as the ID of the Amazon Machine Image (AMI), the instance type, a key pair, one or more security groups, and a block device mapping.

You cannot use a launch configuration to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances. Therefore both these options are incorrect.

You can neither use a launch configuration nor a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances to achieve the desired scale, performance, and cost - You can use a launch template to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances. So this option is incorrect.

References:

https://docs.aws.amazon.com/autoscaling/ec2/userguide/LaunchTemplates.html

https://docs.aws.amazon.com/autoscaling/ec2/userguide/LaunchConfiguration.html

## Question 50:

 An e-commerce application uses an Amazon Aurora Multi-AZ deployment for its database. While analyzing the performance metrics, the engineering team has found that the database reads are causing high input/output (I/O) and adding latency to the write requests against the database.

As an AWS Certified Solutions Architect Associate, what would you recommend to separate the read requests from the write requests?

- 1. Provision another Amazon Aurora database and link it to the primary database as a read replica
- 2. Set up a read replica and modify the application to use the appropriate endpoint(Correct)
- 3. Configure the application to read from the Multi-AZ standby instance
- 4. Activate read-through caching on the Amazon Aurora database

*Correct Answer(s):*
 2. Set up a read replica and modify the application to use the appropriate endpoint

**Explanation:**
Correct option:

Set up a read replica and modify the application to use the appropriate endpoint

An Amazon Aurora DB cluster consists of one or more DB instances and a cluster volume that manages the data for those DB instances. An Aurora cluster volume is a virtual database storage volume that spans multiple Availability Zones (AZs), with each Availability Zone (AZ) having a copy of the DB cluster data. Two types of DB instances make up an Aurora DB cluster:

Primary DB instance – Supports read and write operations, and performs all of the data modifications to the cluster volume. Each Aurora DB cluster has one primary DB instance.

Aurora Replica – Connects to the same storage volume as the primary DB instance and supports only read operations. Each Aurora DB cluster can have up to 15 Aurora Replicas in addition to the primary DB instance. Aurora automatically fails over to an Aurora Replica in case the primary DB instance becomes unavailable. You can specify the failover priority for Aurora Replicas. Aurora Replicas can also offload read workloads from the primary DB instance.


via - https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.html

Aurora Replicas have two main purposes. You can issue queries to them to scale the read operations for your application. You typically do so by connecting to the reader endpoint of the cluster. That way, Aurora can spread the load for read-only connections across as many Aurora Replicas as you have in the cluster. Aurora Replicas also help to increase availability. If the writer instance in a cluster becomes unavailable, Aurora automatically promotes one of the reader instances to take its place as the new writer.

While setting up a Multi-AZ deployment for Aurora, you create an Aurora replica or reader node in a different Availability Zone (AZ).

Multi-AZ for Aurora:


You use the reader endpoint for read-only connections for your Aurora cluster. This endpoint uses a load-balancing mechanism to help your cluster handle a query-intensive workload. The reader endpoint is the endpoint that you supply to applications that do reporting or other read-only operations on the cluster. The reader endpoint load-balances connections to available Aurora Replicas in an Aurora DB cluster.


via - https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Endpoints.html

Incorrect options:

Provision another Amazon Aurora database and link it to the primary database as a read replica - You cannot provision another Aurora database and then link it as a read-replica for the primary database. This option is ruled out.

Configure the application to read from the Multi-AZ standby instance - This option has been added as a distractor as Aurora does not have any entity called standby instance. You create a standby instance while setting up a Multi-AZ deployment for Amazon RDS and NOT for Aurora.

Multi-AZ for Amazon RDS:


Activate read-through caching on the Amazon Aurora database - Amazon Aurora does not have built-in support for read-through caching, so this option just serves as a distractor. To implement caching, you will need to integrate something like Amazon ElastiCache and that would need code changes for the application.

References:

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.html

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Concepts.AuroraHighAvailability.html

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.Endpoints.html

## Question 51:

 Which of the following IAM policies provides read-only access to the Amazon S3 bucket mybucket and its content?

- 1. {
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket"
         ],
         "Resource":"arn:aws:s3:::mybucket/*"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket"
      }
   ]
}
- 2. {
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket",
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket/*"
      }
   ]
}
- 3. {
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket"
         ],
         "Resource":"arn:aws:s3:::mybucket"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket/*"
      }
   ]
}
(Correct)
- 4. {
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket",
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket"
      }
   ]
}

*Correct Answer(s):*
 3. {
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket"
         ],
         "Resource":"arn:aws:s3:::mybucket"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket/*"
      }
   ]
}


**Explanation:**
Correct option:

{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket"
         ],
         "Resource":"arn:aws:s3:::mybucket"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket/*"
      }
   ]
}


You manage access in AWS by creating policies and attaching them to IAM identities (users, groups of users, or roles) or AWS resources. A policy is an object in AWS that, when associated with an identity or resource, defines their permissions. AWS evaluates these policies when an IAM principal (user or role) makes a request. Permissions in the policies determine whether the request is allowed or denied. Most policies are stored in AWS as JSON documents. AWS supports six types of policies: identity-based policies, resource-based policies, permissions boundaries, service control policy (SCP)of AWS Organizations, access control list (ACL), and session policies.

s3:ListBucket is applied to buckets, so the ARN is in the form  "Resource":"arn:aws:s3:::mybucket", without a trailing /
s3:GetObject is applied to objects within the bucket, so the ARN is in the form "Resource":"arn:aws:s3:::mybucket/*", with a trailing /* to indicate all objects within the bucket mybucket

Therefore, this is the correct option.

Incorrect options:

{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket",
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket"
      }
   ]
}


This option is incorrect as it provides read-only access only to the bucket, not its contents.

{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket",
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket/*"
      }
   ]
}


This option is incorrect as it provides read-only access only to the objects within the bucket and it does not provide listBucket permissions to the bucket itself.

{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket"
         ],
         "Resource":"arn:aws:s3:::mybucket/*"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::mybucket"
      }
   ]
}


This option is incorrect as it provides listing access only to the bucket contents.

References:

https://aws.amazon.com/blogs/security/writing-iam-policies-how-to-grant-access-to-an-amazon-s3-bucket/

https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html

## Question 52:

 A startup has just developed a video backup service hosted on a fleet of Amazon EC2 instances. The Amazon EC2 instances are behind an Application Load Balancer and the instances are using Amazon Elastic Block Store (Amazon EBS) Volumes for storage. The service provides authenticated users the ability to upload videos that are then saved on the EBS volume attached to a given instance. On the first day of the beta launch, users start complaining that they can see only some of the videos in their uploaded videos backup. Every time the users log into the website, they claim to see a different subset of their uploaded videos.

Which of the following is the MOST optimal solution to make sure that users can view all the uploaded videos? (Select two)

- 1. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon S3 Glacier Deep Archive and then modify the application to use Amazon S3 Glacier Deep Archive for storing the videos
- 2. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon S3 and then modify the application to use Amazon S3 standard for storing the videos(Correct)
- 3. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon RDS and then modify the application to use Amazon RDS for storing the videos
- 4. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon DynamoDB and then modify the application to use Amazon DynamoDB for storing the videos
- 5. Mount Amazon Elastic File System (Amazon EFS) on all Amazon EC2 instances. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon EFS. Modify the application to use Amazon EFS for storing the videos(Correct)

*Correct Answer(s):*
 2. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon S3 and then modify the application to use Amazon S3 standard for storing the videos5. Mount Amazon Elastic File System (Amazon EFS) on all Amazon EC2 instances. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon EFS. Modify the application to use Amazon EFS for storing the videos

**Explanation:**
Correct options:

Write a one time job to copy the videos from all Amazon EBS volumes to Amazon S3 and then modify the application to use Amazon S3 standard for storing the videos

Mount Amazon Elastic File System (Amazon EFS) on all Amazon EC2 instances. Write a one time job to copy the videos from all Amazon EBS volumes to Amazon EFS. Modify the application to use Amazon EFS for storing the videos

Amazon Elastic Block Store (EBS) is an easy to use, high-performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction-intensive workloads at any scale.

Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources. It is built to scale on-demand to petabytes without disrupting applications, growing and shrinking automatically as you add and remove files, eliminating the need to provision and manage capacity to accommodate growth.

Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance.

As Amazon EBS volumes are attached locally to the Amazon EC2 instances, therefore the uploaded videos are tied to specific Amazon EC2 instances. Every time the user logs in, they are directed to a different instance and therefore their videos get dispersed across multiple EBS volumes. The correct solution is to use either Amazon S3 or Amazon EFS to store the user videos.

Incorrect options:

Write a one time job to copy the videos from all Amazon EBS volumes to Amazon S3 Glacier Deep Archive and then modify the application to use Amazon S3 Glacier Deep Archive for storing the videos - Amazon S3 Glacier Deep Archive is meant to be used for long term data archival. It cannot be used to serve static content such as videos or images via a web application. So this option is incorrect.

Write a one time job to copy the videos from all Amazon EBS volumes to Amazon RDS and then modify the application to use Amazon RDS for storing the videos - Amazon RDS is a relational database and not the right candidate for storing videos.

Write a one time job to copy the videos from all Amazon EBS volumes to Amazon DynamoDB and then modify the application to use Amazon DynamoDB for storing the videos - Amazon DynamoDB is a NoSQL database and not the right candidate for storing videos.

Reference:

https://aws.amazon.com/ebs/

## Question 53:

 An IT company provides Amazon Simple Storage Service (Amazon S3) bucket access to specific users within the same account for completing project specific work. With changing business requirements, cross-account S3 access requests are also growing every month. The company is looking for a solution that can offer user level as well as account-level access permissions for the data stored in Amazon S3 buckets.

As a Solutions Architect, which of the following would you suggest as the MOST optimized way of controlling access for this use-case?

- 1. Use Security Groups
- 2. Use Identity and Access Management (IAM) policies
- 3. Use Amazon S3 Bucket Policies(Correct)
- 4. Use Access Control Lists (ACLs)

*Correct Answer(s):*
 3. Use Amazon S3 Bucket Policies

**Explanation:**
Correct option:

Use Amazon S3 Bucket Policies

Bucket policies in Amazon S3 can be used to add or deny permissions across some or all of the objects within a single bucket. Policies can be attached to users, groups, or Amazon S3 buckets, enabling centralized management of permissions. With bucket policies, you can grant users within your AWS Account or other AWS Accounts access to your Amazon S3 resources.

You can further restrict access to specific resources based on certain conditions. For example, you can restrict access based on request time (Date Condition), whether the request was sent using SSL (Boolean Conditions), a requester’s IP address (IP Address Condition), or based on the requester's client application (String Conditions). To identify these conditions, you use policy keys.

Types of access control in Amazon S3:

via - https://d1.awsstatic.com/whitepapers/aws-security-whitepaper.pdf

Incorrect options:

Use Identity and Access Management (IAM) policies - AWS IAM enables organizations with many employees to create and manage multiple users under a single AWS account. IAM policies are attached to the users, enabling centralized control of permissions for users under your AWS Account to access buckets or objects. With IAM policies, you can only grant users within your own AWS account permission to access your Amazon S3 resources. So, this is not the right choice for the current requirement.

Use Access Control Lists (ACLs) - Within Amazon S3, you can use ACLs to give read or write access on buckets or objects to groups of users. With ACLs, you can only grant other AWS accounts (not specific users) access to your Amazon S3 resources. So, this is not the right choice for the current requirement.

Use Security Groups - A security group acts as a virtual firewall for Amazon EC2 instances to control incoming and outgoing traffic. Amazon S3 does not support Security Groups, this option just acts as a distractor.

Reference:

https://d1.awsstatic.com/whitepapers/aws-security-whitepaper.pdf

## Question 54:

 A silicon valley based startup has a content management application with the web-tier running on Amazon EC2 instances and the database tier running on Amazon Aurora. Currently, the entire infrastructure is located in us-east-1 region. The startup has 90% of its customers in the US and Europe. The engineering team is getting reports of deteriorated application performance from customers in Europe with high application load time.

As a solutions architect, which of the following would you recommend addressing these performance issues? (Select two)

- 1. Create Amazon Aurora Multi-AZ standby instance in the eu-west-1 region
- 2. Setup another fleet of Amazon EC2 instances for the web tier in the eu-west-1 region. Enable failover routing policy in Amazon Route 53
- 3. Create Amazon Aurora read replicas in the eu-west-1 region(Correct)
- 4. Setup another fleet of Amazon EC2 instances for the web tier in the eu-west-1 region. Enable geolocation routing policy in Amazon Route 53
- 5. Setup another fleet of Amazon EC2 instances for the web tier in the eu-west-1 region. Enable latency routing policy in Amazon Route 53(Correct)

*Correct Answer(s):*
 3. Create Amazon Aurora read replicas in the eu-west-1 region5. Setup another fleet of Amazon EC2 instances for the web tier in the eu-west-1 region. Enable latency routing policy in Amazon Route 53

**Explanation:**
Correct options:

Setup another fleet of Amazon EC2 instances for the web tier in the eu-west-1 region. Enable latency routing policy in Amazon Route 53

Amazon Route 53 is a highly available and scalable cloud Domain Name System (DNS) web service. Use latency based routing when you have resources in multiple AWS Regions and you want to route traffic to the region that provides the lowest latency. To use latency-based routing, you create latency records for your resources in multiple AWS Regions. When Amazon Route 53 receives a DNS query for your domain or subdomain (example.com or acme.example.com), it determines which AWS Regions you've created latency records for, determines which region gives the user the lowest latency, and then selects a latency record for that region. Route 53 responds with the value from the selected record, such as the IP address for a web server.

As customers in Europe are facing performance issues with high application load time, you can use latency based routing to reduce the latency. Hence this is the correct option.

Amazon Route 53 Routing Policy Overview:

via - https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html

Create Amazon Aurora read replicas in the eu-west-1 region

Amazon Aurora is a MySQL and PostgreSQL-compatible relational database built for the cloud, that combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases. Amazon Aurora features a distributed, fault-tolerant, self-healing storage system that auto-scales up to 64TB per database instance.

Amazon Aurora read replicas can be used to scale out reads across regions. This will improve the application performance for users in Europe. Therefore, this is also a correct option for the given use-case.

Incorrect options:

Setup another fleet of Amazon EC2 instances for the web tier in the eu-west-1 region. Enable geolocation routing policy in Amazon Route 53 - Geolocation routing lets you choose the resources that serve your traffic based on the geographic location of your users, meaning the location that DNS queries originate from. For example, you might want all queries from Europe to be routed to an ELB load balancer in the Frankfurt region. You can also use geolocation routing to restrict the distribution of content to only the locations in which you have distribution rights. You cannot use geolocation routing to reduce latency, hence this option is incorrect.

Setup another fleet of Amazon EC2 instances for the web tier in the eu-west-1 region. Enable failover routing policy in Amazon Route 53 - Failover routing lets you route traffic to a resource when the resource is healthy or to a different resource when the first resource is unhealthy. The primary and secondary records can route traffic to anything from an Amazon S3 bucket that is configured as a website to a complex tree of records. You cannot use failover routing to reduce latency, hence this option is incorrect.

Create Amazon Aurora Multi-AZ standby instance in the eu-west-1 region - Amazon Aurora Multi-AZ enhances the availability and durability for the database, it does not help in read scaling, so it is not a correct option for the given use-case.

References:

https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html

https://aws.amazon.com/blogs/aws/new-cross-region-read-replicas-for-amazon-aurora/

## Question 55:

 To improve the performance and security of the application, the engineering team at a company has created an Amazon CloudFront distribution with an Application Load Balancer as the custom origin. The team has also set up an AWS Web Application Firewall (AWS WAF) with Amazon CloudFront distribution. The security team at the company has noticed a surge in malicious attacks from a specific IP address to steal sensitive data stored on the Amazon EC2 instances.

As a solutions architect, which of the following actions would you recommend to stop the attacks?

- 1. Create an IP match condition in the AWS WAF to block the malicious IP address(Correct)
- 2. Create a deny rule for the malicious IP in the network access control list (network ACL) associated with each of the instances
- 3. Create a ticket with AWS support to take action against the malicious IP
- 4. Create a deny rule for the malicious IP in the Security Groups associated with each of the instances

*Correct Answer(s):*
 1. Create an IP match condition in the AWS WAF to block the malicious IP address

**Explanation:**
Correct option:

Create an IP match condition in the AWS WAF to block the malicious IP address

AWS WAF is a web application firewall that helps protect your web applications or APIs against common web exploits that may affect availability, compromise security, or consume excessive resources. AWS WAF gives you control over how traffic reaches your applications by enabling you to create security rules that block common attack patterns, such as SQL injection or cross-site scripting, and rules that filter out specific traffic patterns you define.

How AWS WAF Works:

via - https://aws.amazon.com/waf/

If you want to allow or block web requests based on the IP addresses that the requests originate from, create one or more IP match conditions. An IP match condition lists up to 10,000 IP addresses or IP address ranges that your requests originate from. So, this option is correct.

Incorrect options:

Create a deny rule for the malicious IP in the network access control list (network ACL) associated with each of the instances - Network access control list (network ACL) are not associated with instances. So this option is also ruled out.

Create a deny rule for the malicious IP in the Security Groups associated with each of the instances - You cannot deny rules in Security Groups. So this option is ruled out.

Create a ticket with AWS support to take action against the malicious IP - Managing the security of your application is your responsibility, not that of AWS, so you cannot raise a ticket for this issue.

Reference:

https://docs.aws.amazon.com/waf/latest/developerguide/classic-web-acl-ip-conditions.html

## Question 56:

 An application runs big data workloads on Amazon Elastic Compute Cloud (Amazon EC2) instances. The application runs 24x7 all round the year and needs at least 20 instances to maintain a minimum acceptable performance threshold and the application needs 300 instances to handle spikes in the workload. Based on historical workloads processed by the application, it needs 80 instances 80% of the time.

As a solutions architect, which of the following would you recommend as the MOST cost-optimal solution so that it can meet the workload demand in a steady state?

- 1. Purchase 80 reserved instances (RIs). Provision additional on-demand and spot instances per the workload demand (Use Auto Scaling Group with launch template to provision the mix of on-demand and spot instances)(Correct)
- 2. Purchase 80 spot instances. Use Auto Scaling Group to provision the remaining instances as on-demand instances per the workload demand
- 3. Purchase 20 on-demand instances. Use Auto Scaling Group to provision the remaining instances as spot instances per the workload demand
- 4. Purchase 80 on-demand instances. Provision additional on-demand and spot instances per the workload demand (Use Auto Scaling Group with launch template to provision the mix of on-demand and spot instances)

*Correct Answer(s):*
 1. Purchase 80 reserved instances (RIs). Provision additional on-demand and spot instances per the workload demand (Use Auto Scaling Group with launch template to provision the mix of on-demand and spot instances)

**Explanation:**
Correct option:

Purchase 80 reserved instances (RIs). Provision additional on-demand and spot instances per the workload demand (Use Auto Scaling Group with launch template to provision the mix of on-demand and spot instances)

As the steady-state workload demand is 80 instances, we can save on costs by purchasing 80 reserved instances. Based on additional workload demand, we can specify a mix of on-demand and spot instances using Application Load Balancer with a launch template to provision the mix of on-demand and spot instances.

Please see this detailed overview of various types of Amazon EC2 instances from a pricing perspective:

via - https://aws.amazon.com/ec2/pricing/

Incorrect options:

Purchase 20 on-demand instances. Use Auto Scaling Group to provision the remaining instances as spot instances per the workload demand - Provisioning 20 on-demand instances implies that there would be a shortfall of 60 instances 80% of the time. Provisioning all of these 60 instances as spot instances is highly risky as there is no guarantee regarding the availability of the spot instances, which means we may not even meet the steady-state requirement for the workload, so this option is incorrect.

Purchase 80 on-demand instances. Provision additional on-demand and spot instances per the workload demand (Use Auto Scaling Group with launch template to provision the mix of on-demand and spot instances) - Provisioning 80 on-demand instances would end up costlier than the option where we provision 80 reserved instances. So this option is ruled out.

Purchase 80 spot instances. Use Auto Scaling Group to provision the remaining instances as on-demand instances per the workload demand - The option to purchase 80 spot instances is incorrect, as there is no guarantee regarding the availability of the spot instances, which means we may not even meet the steady-state workload.

Reference:

https://aws.amazon.com/ec2/pricing/

## Question 57:

 You would like to migrate an AWS account from an AWS Organization A to an AWS Organization B. What are the steps do to it?

- 1. Open an AWS Support ticket to ask them to migrate the account
- 2. Send an invite to the new organization. Remove the member account from the old organization. Accept the invite to the new organization from the member account
- 3. Send an invite to the new organization. Accept the invite to the new organization from the member account. Remove the member account from the old organization
- 4. Remove the member account from the old organization. Send an invite to the member account from the new Organization. Accept the invite to the new organization from the member account(Correct)

*Correct Answer(s):*
 4. Remove the member account from the old organization. Send an invite to the member account from the new Organization. Accept the invite to the new organization from the member account

**Explanation:**
Correct option:

Remove the member account from the old organization. Send an invite to the member account from the new Organization. Accept the invite to the new organization from the member account

AWS Organizations helps you centrally govern your environment as you grow and scale your workloads on AWS. Using AWS Organizations, you can automate account creation, create groups of accounts to reflect your business needs, and apply policies for these groups for governance. You can also simplify billing by setting up a single payment method for all of your AWS accounts. Through integrations with other AWS services, you can use Organizations to define central configurations and resource sharing across accounts in your organization.

To migrate accounts from one organization to another, you must have root or IAM access to both the member and master accounts. Here are the steps to follow:
1. Remove the member account from the old organization
2. Send an invite to the member account from the new Organization
3. Accept the invite to the new organization from the member account

Incorrect options:

Send an invite to the new organization. Accept the invite to the new organization from the member account. Remove the member account from the old organization

Send an invite to the new organization. Remove the member account from the old organization. Accept the invite to the new organization from the member account

These two options contradict the steps described earlier for account migration from one organization to another.

Open an AWS Support ticket to ask them to migrate the account - You don't need to contact AWS support for account migration.

References:

https://aws.amazon.com/organizations/

https://aws.amazon.com/premiumsupport/knowledge-center/organizations-move-accounts/

## Question 58:

 What is true about Amazon RDS Read Replicas encryption?

- 1. If the master database is unencrypted, the read replicas are encrypted
- 2. If the master database is unencrypted, the read replicas can be either encrypted or unencrypted
- 3. If the master database is encrypted, the read replicas can be either encrypted or unencrypted
- 4. If the master database is encrypted, the read replicas are encrypted(Correct)

*Correct Answer(s):*
 4. If the master database is encrypted, the read replicas are encrypted

**Explanation:**
Correct option:

If the master database is encrypted, the read replicas are encrypted

Amazon RDS Read Replicas provide enhanced performance and durability for RDS database (DB) instances. They make it easy to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads. For the MySQL, MariaDB, PostgreSQL, Oracle, and SQL Server database engines, Amazon RDS creates a second DB instance using a snapshot of the source DB instance. It then uses the engines' native asynchronous replication to update the read replica whenever there is a change to the source DB instance. read replicas can be within an Availability Zone, Cross-AZ, or Cross-Region.

On a database instance running with Amazon RDS encryption, data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas, and snapshots. Therefore, this option is correct.

Amazon RDS Read Replica Overview:

via - https://aws.amazon.com/rds/features/read-replicas/

Incorrect options:

If the master database is encrypted, the read replicas can be either encrypted or unencrypted - If the master database is encrypted, the read replicas are necessarily encrypted, so this option is incorrect.

If the master database is unencrypted, the read replicas can be either encrypted or unencrypted

If the master database is unencrypted, the read replicas are encrypted

If the master database is not encrypted, the read replicas cannot be encrypted, so both these options are incorrect.

References:

https://aws.amazon.com/rds/features/read-replicas/

## Question 59:

 A systems administrator has created a private hosted zone and associated it with a Virtual Private Cloud (VPC). However, the Domain Name System (DNS) queries for the private hosted zone remain unresolved.

As a Solutions Architect, can you identify the Amazon Virtual Private Cloud (Amazon VPC) options to be configured in order to get the private hosted zone to work?

- 1. Fix the Name server (NS) record and Start Of Authority (SOA) records that may have been created with wrong configurations
- 2. Enable DNS hostnames and DNS resolution for private hosted zones(Correct)
- 3. Remove any overlapping namespaces for the private and public hosted zones
- 4. Fix conflicts between your private hosted zone and any Resolver rule that routes traffic to your network for the same domain name, as it results in ambiguity over the route to be taken

*Correct Answer(s):*
 2. Enable DNS hostnames and DNS resolution for private hosted zones

**Explanation:**
Correct option:

Enable DNS hostnames and DNS resolution for private hosted zones

DNS hostnames and DNS resolution are required settings for private hosted zones. DNS queries for private hosted zones can be resolved by the Amazon-provided VPC DNS server only. As a result, these options must be enabled for your private hosted zone to work.

DNS hostnames: For non-default virtual private clouds that aren't created using the Amazon VPC wizard, this option is disabled by default. If you create a private hosted zone for a domain and create records in the zone without enabling DNS hostnames, private hosted zones aren't enabled. To use a private hosted zone, this option must be enabled.

DNS resolution: Private hosted zones accept DNS queries only from a VPC DNS server. The IP address of the VPC DNS server is the reserved IP address at the base of the VPC IPv4 network range plus two. Enabling DNS resolution allows you to use the VPC DNS server as a Resolver for performing DNS resolution. Keep this option disabled if you're using a custom DNS server in the DHCP Options set, and you're not using a private hosted zone.

Incorrect options:

Remove any overlapping namespaces for the private and public hosted zones - If you have private and public hosted zones that have overlapping namespaces, such as example.com and accounting.example.com, then the Resolver routes traffic based on the most specific match. It won't result in unresolved queries, hence this option is wrong.

Fix the Name server (NS) record and Start Of Authority (SOA) records that may have been created with wrong configurations - When you create a hosted zone, Amazon Route 53 automatically creates a name server (NS) record and a start of authority (SOA) record for the zone for public hosted zone. However, this issue is about the private hosted zone, hence this is an incorrect option.

Fix conflicts between your private hosted zone and any Resolver rule that routes traffic to your network for the same domain name, as it results in ambiguity over the route to be taken - If you have a private hosted zone (example.com) and a Resolver rule that routes traffic to your network for the same domain name, the Resolver rule takes precedence. It won't result in unresolved queries.

References:

https://aws.amazon.com/premiumsupport/knowledge-center/vpc-enable-private-hosted-zone/

https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zone-private-considerations.html

https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zone-public-considerations.html

## Question 60:

 You are establishing a monitoring solution for desktop systems, that will be sending telemetry data into AWS every 1 minute. Data for each system must be processed in order, independently, and you would like to scale the number of consumers to be possibly equal to the number of desktop systems that are being monitored.

What do you recommend?

- 1. Use an Amazon Simple Queue Service (Amazon SQS) FIFO (First-In-First-Out) queue, and send the telemetry data as is
- 2. Use an Amazon Simple Queue Service (Amazon SQS) standard queue, and send the telemetry data as is
- 3. Use an Amazon Kinesis Data Stream, and send the telemetry data with a Partition ID that uses the value of the Desktop ID
- 4. Use an Amazon Simple Queue Service (Amazon SQS) FIFO (First-In-First-Out) queue, and make sure the telemetry data is sent with a Group ID attribute representing the value of the Desktop ID(Correct)

*Correct Answer(s):*
 4. Use an Amazon Simple Queue Service (Amazon SQS) FIFO (First-In-First-Out) queue, and make sure the telemetry data is sent with a Group ID attribute representing the value of the Desktop ID

**Explanation:**
Correct option:

Use an Amazon Simple Queue Service (Amazon SQS) FIFO (First-In-First-Out) queue, and make sure the telemetry data is sent with a Group ID attribute representing the value of the Desktop ID

Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. SQS offers two types of message queues. Standard queues offer maximum throughput, best-effort ordering, and at-least-once delivery. SQS FIFO queues are designed to guarantee that messages are processed exactly once, in the exact order that they are sent.

We, therefore, need to use an SQS FIFO queue. If we don't specify a GroupID, then all the messages are in absolute order, but we can only have 1 consumer at most.
To allow for multiple consumers to read data for each Desktop application, and to scale the number of consumers, we should use the "Group ID" attribute. So this is the correct option.

Incorrect options:

Use an Amazon Simple Queue Service (Amazon SQS) FIFO (First-In-First-Out) queue, and send the telemetry data as is - This is incorrect because if we send the telemetry data as is then we will not be able to scale the number of consumers to be equal to the number of desktop systems. In this case, each message will have its consumer. So we should use the "Group ID" attribute so that multiple consumers can read data for each Desktop application.

Use an Amazon Simple Queue Service (Amazon SQS) standard queue, and send the telemetry data as is - An Amazon SQS standard queue has no ordering capability so that's ruled out.

Use an Amazon Kinesis Data Stream, and send the telemetry data with a Partition ID that uses the value of the Desktop ID - Amazon Kinesis Data Streams (KDS) is a massively scalable and durable real-time data streaming service. KDS can continuously capture gigabytes of data per second from hundreds of thousands of sources such as website clickstreams, database event streams, financial transactions, social media feeds, IT logs, and location-tracking events.
A Kinesis Data Stream would work and would give us the data for each desktop application within shards, but we can only have as many consumers as shards in Kinesis (which is in practice, much less than the number of producers).

References:

https://aws.amazon.com/blogs/compute/solving-complex-ordering-challenges-with-amazon-sqs-fifo-queues/

https://aws.amazon.com/sqs/faqs/

https://aws.amazon.com/kinesis/data-streams/faqs/

## Question 61:

 A company is looking at storing their less frequently accessed files on AWS that can be concurrently accessed by hundreds of Amazon EC2 instances. The company needs the most cost-effective file storage service that provides immediate access to data whenever needed.

Which of the following options represents the best solution for the given requirements?

- 1. Amazon Elastic File System (EFS) Standard–IA storage class(Correct)
- 2. Amazon Elastic File System (EFS) Standard storage class
- 3. Amazon Elastic Block Store (EBS)
- 4. Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class

*Correct Answer(s):*
 1. Amazon Elastic File System (EFS) Standard–IA storage class

**Explanation:**
Correct option:

Amazon Elastic File System (EFS) Standard–IA storage class - Amazon EFS is a file storage service for use with Amazon compute (EC2, containers, serverless) and on-premises servers. Amazon EFS provides a file system interface, file system access semantics (such as strong consistency and file locking), and concurrently accessible storage for up to thousands of Amazon EC2 instances.

The Amazon S3 Standard–IA storage class reduces storage costs for files that are not accessed every day. It does this without sacrificing the high availability, high durability, elasticity, and POSIX file system access that Amazon EFS provides. AWS recommends Standard-IA storage if you need your full dataset to be readily accessible and want to automatically save on storage costs for files that are less frequently accessed.

Incorrect options:

Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class - Amazon S3 is an object storage service. Amazon S3 makes data available through an Internet API that can be accessed anywhere. It is not a file storage service, as is needed in the use case.

Amazon Elastic File System (EFS) Standard storage class - Amazon EFS Standard storage classes are ideal for workloads that require the highest levels of durability and availability. The Amazon EFS Standard storage class is used for frequently accessed files. It is the storage class to which customer data is initially written for Standard storage classes. The company is also looking at cutting costs by optimally storing the infrequently accessed data. Hence, Amazon EFS standard storage class is not the right solution for the given use case.

Amazon Elastic Block Store (EBS) - Amazon EBS is a block-level storage service for use with Amazon EC2. Amazon EBS can deliver performance for workloads that require the lowest latency access to data from a single Amazon EC2 instance. Amazon EBS volume cannot be accessed by hundreds of Amazon EC2 instances concurrently. It is not a file storage service, as is needed in the use case.

Reference:

https://docs.aws.amazon.com/efs/latest/ug/storage-classes.html

## Question 62:

 An engineering team wants to examine the feasibility of the user data feature of Amazon EC2 for an upcoming project.

Which of the following are true about the Amazon EC2 user data configuration? (Select two)

- 1. By default, user data is executed every time an Amazon EC2 instance is re-started
- 2. By default, scripts entered as user data do not have root user privileges for executing
- 3. When an instance is running, you can update user data by using root user credentials
- 4. By default, user data runs only during the boot cycle when you first launch an instance(Correct)
- 5. By default, scripts entered as user data are executed with root user privileges(Correct)

*Correct Answer(s):*
 4. By default, user data runs only during the boot cycle when you first launch an instance5. By default, scripts entered as user data are executed with root user privileges

**Explanation:**
Correct options:

User Data is generally used to perform common automated configuration tasks and even run scripts after the instance starts. When you launch an instance in Amazon EC2, you can pass two types of user data - shell scripts and cloud-init directives. You can also pass this data into the launch wizard as plain text or as a file.

By default, scripts entered as user data are executed with root user privileges

Scripts entered as user data are executed as the root user, hence do not need the sudo command in the script. Any files you create will be owned by root; if you need non-root users to have file access, you should modify the permissions accordingly in the script.

By default, user data runs only during the boot cycle when you first launch an instance

By default, user data scripts and cloud-init directives run only during the boot cycle when you first launch an instance. You can update your configuration to ensure that your user data scripts and cloud-init directives run every time you restart your instance.

Incorrect options:

By default, user data is executed every time an Amazon EC2 instance is re-started - As discussed above, this is not a default configuration of the system. But, can be achieved by explicitly configuring the instance.

When an instance is running, you can update user data by using root user credentials - You can't change the user data if the instance is running (even by using root user credentials), but you can view it.

By default, scripts entered as user data do not have root user privileges for executing - Scripts entered as user data are executed as the root user, hence do not need the sudo command in the script.

Reference:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html

## Question 63:

 A financial services company has deployed its flagship application on Amazon EC2 instances. Since the application handles sensitive customer data, the security team at the company wants to ensure that any third-party Secure Sockets Layer certificate (SSL certificate) SSL/Transport Layer Security (TLS) certificates configured on Amazon EC2 instances via the AWS Certificate Manager (ACM) are renewed before their expiry date. The company has hired you as an AWS Certified Solutions Architect Associate to build a solution that notifies the security team 30 days before the certificate expiration. The solution should require the least amount of scripting and maintenance effort.

What will you recommend?

- 1. Leverage AWS Config managed rule to check if any third-party SSL/TLS certificates imported into ACM are marked for expiration within 30 days. Configure the rule to trigger an Amazon SNS notification to the security team if any certificate expires within 30 days(Correct)
- 2. Monitor the days to expiry Amazon CloudWatch metric for certificates created via ACM. Create a CloudWatch alarm to monitor such certificates based on the days to expiry metric and then trigger a custom action of notifying the security team
- 3. Monitor the days to expiry Amazon CloudWatch metric for certificates imported into ACM. Create a CloudWatch alarm to monitor such certificates based on the days to expiry metric and then trigger a custom action of notifying the security team
- 4. Leverage AWS Config managed rule to check if any SSL/TLS certificates created via ACM are marked for expiration within 30 days. Configure the rule to trigger an Amazon SNS notification to the security team if any certificate expires within 30 days

*Correct Answer(s):*
 1. Leverage AWS Config managed rule to check if any third-party SSL/TLS certificates imported into ACM are marked for expiration within 30 days. Configure the rule to trigger an Amazon SNS notification to the security team if any certificate expires within 30 days

**Explanation:**
Correct option:

Leverage AWS Config managed rule to check if any third-party SSL/TLS certificates imported into ACM are marked for expiration within 30 days. Configure the rule to trigger an Amazon SNS notification to the security team if any certificate expires within 30 days

AWS Certificate Manager is a service that lets you easily provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services and your internal connected resources. SSL/TLS certificates are used to secure network communications and establish the identity of websites over the Internet as well as resources on private networks.

AWS Config provides a detailed view of the configuration of AWS resources in your AWS account. This includes how the resources are related to one another and how they were configured in the past so that you can see how the configurations and relationships change over time.


via - https://docs.aws.amazon.com/config/latest/developerguide/how-does-config-work.html

AWS Config provides AWS-managed rules, which are predefined, customizable rules that AWS Config uses to evaluate whether your AWS resources comply with common best practices. You can leverage an AWS Config managed rule to check if any ACM certificates in your account are marked for expiration within the specified number of days. Certificates provided by ACM are automatically renewed. ACM does not automatically renew the certificates that you import. The rule is NON_COMPLIANT if your certificates are about to expire.


via - https://docs.aws.amazon.com/config/latest/developerguide/how-does-config-work.html

You can configure AWS Config to stream configuration changes and notifications to an Amazon SNS topic. For example, when a resource is updated, you can get a notification sent to your email, so that you can view the changes. You can also be notified when AWS Config evaluates your custom or managed rules against your resources.

Incorrect options:

Monitor the days to expiry Amazon CloudWatch metric for certificates imported into ACM. Create a CloudWatch alarm to monitor such certificates based on the days to expiry metric and then trigger a custom action of notifying the security team - AWS Certificate Manager (ACM) does not attempt to renew third-party certificates that are imported. Also, an administrator needs to reconfigure missing DNS records for certificates that use DNS validation if the record was removed for any reason after the certificate was issued. Metrics and events provide you visibility into such certificates that require intervention to continue the renewal process. Amazon CloudWatch metrics and Amazon EventBridge events are enabled for all certificates that are managed by ACM. Users can monitor days to expiry as a metric for ACM certificates through Amazon CloudWatch. An Amazon EventBridge expiry event is published for any certificate that is at least 45 days away from expiry by default. Users can build alarms to monitor certificates based on days to expiry and also trigger custom actions such as calling a Lambda function or paging an administrator.

It is certainly possible to use the days to expiry CloudWatch metric to build a CloudWatch alarm to monitor the imported ACM certificates. The alarm will, in turn, trigger a notification to the security team. But this option needs more configuration effort than directly using the AWS Config managed rule that is available off-the-shelf.

Leverage AWS Config managed rule to check if any SSL/TLS certificates created via ACM are marked for expiration within 30 days. Configure the rule to trigger an Amazon SNS notification to the security team if any certificate expires within 30 days

Monitor the days to expiry Amazon CloudWatch metric for certificates created via ACM. Create a CloudWatch alarm to monitor such certificates based on the days to expiry metric and then trigger a custom action of notifying the security team

Any SSL/TLS certificates created via ACM do not need any monitoring/intervention for expiration. ACM automatically renews such certificates. Hence both these options are incorrect.

References:

https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html

https://docs.aws.amazon.com/config/latest/developerguide/how-does-config-work.html

https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config.html

https://docs.aws.amazon.com/config/latest/developerguide/acm-certificate-expiration-check.html

https://aws.amazon.com/blogs/security/how-to-monitor-expirations-of-imported-certificates-in-aws-certificate-manager-acm/

## Question 64:

 A company is developing a global healthcare application that requires the least possible latency for database read/write operations from users in several geographies across the world. The company has hired you as an AWS Certified Solutions Architect Associate to build a solution using Amazon Aurora that offers an effective recovery point objective (RPO) of seconds and a recovery time objective (RTO) of a minute.

Which of the following options would you recommend?

- 1. Set up an Amazon Aurora provisioned Database cluster
- 2. Set up an Amazon Aurora serverless Database cluster
- 3. Set up an Amazon Aurora Global Database cluster(Correct)
- 4. Set up an Amazon Aurora multi-master Database cluster

*Correct Answer(s):*
 3. Set up an Amazon Aurora Global Database cluster

**Explanation:**
Correct option:

Set up an Amazon Aurora Global Database cluster

Amazon Aurora Global Database is designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS Regions. It replicates your data with no impact on database performance, enables fast local reads with low latency in each Region, and provides disaster recovery from Region-wide outages.

If your primary Region suffers a performance degradation or outage, you can promote one of the secondary Regions to take read/write responsibilities. An Aurora cluster can recover in less than 1 minute, even in the event of a complete Regional outage. This provides your application with an effective recovery point objective (RPO) of 1 second and a recovery time objective (RTO) of less than 1 minute, providing a strong foundation for a global business continuity plan.


via - https://aws.amazon.com/rds/aurora/global-database/

Incorrect options:

Set up an Amazon Aurora serverless Database cluster

Set up an Amazon Aurora provisioned Database cluster

Both these options work in a single AWS Region, so these options are incorrect.

Set up an Amazon Aurora multi-master Database cluster - AWS does not offer the multi-master feature in a Aurora database cluster, so this option acts as a distractor.

Reference:

https://aws.amazon.com/rds/aurora/global-database/

## Question 65:

 You would like to store a database password in a secure place, and enable automatic rotation of that password every 90 days. What do you recommend?

- 1. AWS Systems Manager Parameter Store
- 2. AWS CloudHSM
- 3. AWS Key Management Service (AWS KMS)
- 4. AWS Secrets Manager(Correct)

*Correct Answer(s):*
 4. AWS Secrets Manager

**Explanation:**
Correct option:

AWS Secrets Manager

AWS Secrets Manager helps you protect secrets needed to access your applications, services, and IT resources. The service enables you to easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle. Users and applications retrieve secrets with a call to Secrets Manager APIs, eliminating the need to hardcode sensitive information in plain text. Secrets Manager offers secret rotation with built-in integration for Amazon RDS, Amazon Redshift, and Amazon DocumentDB. The correct answer here is Secrets Manager

Incorrect options:

AWS Key Management Service (AWS KMS) - AWS Key Management Service (AWS KMS) is a service that combines secure, highly available hardware and software to provide a key management system scaled for the cloud. When you use server-side encryption with AWS KMS (SSE-KMS), you can specify a customer-managed CMK that you have already created. SSE-KMS provides you with an audit trail that shows when your CMK was used and by whom. KMS is an encryption service, it's not a secrets store. So this option is incorrect.

AWS CloudHSM - AWS CloudHSM is a cloud-based hardware security module (HSM) that enables you to easily generate and use your encryption keys on the AWS Cloud. With AWS CloudHSM, you can manage your encryption keys using FIPS 140-2 Level 3 validated HSMs. AWS CloudHSM is standards-compliant and enables you to export all of your keys to most other commercially-available HSMs, subject to your configurations. It is a fully-managed service that automates time-consuming administrative tasks for you, such as hardware provisioning, software patching, high-availability, and backups.

AWS CloudHSM is also an encryption service, not a secrets store. So this option is incorrect.

AWS Systems Manager Parameter Store - AWS Systems Manager Parameter Store (aka SSM Parameter Store) provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, Amazon EC2 instance IDs, Amazon Machine Image (AMI) IDs, and license codes as parameter values. You can store values as plain text or encrypted data. You can reference Systems Manager parameters in your scripts, commands, SSM documents, and configuration and automation workflows by using the unique name that you specified when you created the parameter.

AWS Systems Manager Parameter Store can serve as a secrets store, but you must rotate the secrets yourself, it doesn't have an automatic capability for this. So this option is incorrect.

References:

https://aws.amazon.com/secrets-manager/

https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingKMSEncryption.html

https://aws.amazon.com/cloudhsm/

https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html

https://aws.amazon.com/blogs/mt/the-right-way-to-store-secrets-using-parameter-store/

https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html
